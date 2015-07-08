---
layout: post
comments: true
title:  "EcmaScript 6: Generadores"
date:   2015-06-08 21:43:00
tags: js es6 generadores
---

¡Hola de nuevo, lectores! Hoy os traigo un nuevo artículo presentando una nueva funcionalidad de EcmaScript 6, como de costumbre. Esta vez, me refiero a los **generadores**.

En el anterior artículo comentaba medio en serio medio en broma dos cosas: que implementar iteradores no iba a servir para casi nada en la práctica (pero era una muy buena noticia que existiesen) y que Javascript empezaba a parecerse a un lenguaje *serio*.

**¿Por qué un lenguaje serio?** Porque ahora contamos con los susodichos iteradores y, además, con los emocionantes generadores, una funcionalidad que conocerán por ejemplo los lectores que vengan de Python.

**¿Y por qué no vamos a implementar iteradores?** Pues porque los generadores ya lo hacen por nosotros sin tener que mancharnos las manos. De hecho, esta funcionalidad, a los que no tengan más trasfondo que JS, puede que les parezca un poco *mágica*.

Pues bien, **¿qué es un generador?**. Vamos a poner un ejemplo, y así seguimos la tónica de este blog :).

{% highlight js %}
function* greatGenerator(name) {
    yield "Hola " + name + "!";
    yield "Esta línea saldrá en la segunda ejecución";
    yield "Esta otra, en la tercera";
    if (name === "Miguel") yield "Esta otra, saldrá en la cuarta solo si te llamas miguel"
}
var generatorInstance = greatGenerator("paco");
console.log(generatorInstance.next().value); // Hola paco!
console.log(generatorInstance.next().value); // Esta línea saldrá la segunda ejecución
console.log(generatorInstance.next().value); // Esta otra, en la tercera
console.log(generatorInstance.next().value); // undefined
{% endhighlight %}

Nótese la sintaxis: **function*** en lugar de *function* y **yield** en lugar del aburrido *return*. Además, obtenemos los resultados con la función **next()** y de ahí accedemos a **value**.

Podemos comprobar que la funcioncilla *greatGenerator* devuelve un resultado distinto en cada ejecución. **¿Por qué?** Pues porque *yield* es una especie de *return* que deja "una marca" en el punto de retorno de la ejecución anterior. Por tanto, en cada llamada a *next()*, la función se vuelve a retomar justo donde se quedó, continúa ejecutándose y vuelve a retornar el siguiente yield.

Esto, tal y como está planteado puede parecer una chorrada, pero no hace falta mucho pensar mucho para encontrar posibles usos. Véase el caso, por ejemplo, de recorrer una base de datos e ir devolviendo filas por bloques manteniendo un cursor apuntando siempre a la última fila devuelta.

Como decíamos, obtenemos el valor accediento al atributo value. Esto es porque *next()* devuelve un objeto del tipo *{value: "foo", done: false}*. Tal vez este objeto  te resulte familiar, ya que es precisamente **el que tuvimos que construir a mano en el último artículo**. Y es por esto por lo que decía que rara vez tendremos que usar iteradores a mano, ya que con los generadores, podemos hacer que cualquier objeto sea iterable. ¡Y con una sintaxis mucho más clara!

Como colofón os dejo con una función bastante tonta para recorrer un array grandullón en pedazos más pequeños.

{% highlight js %}
function* getArrayByChunks(hugeArray, chunkSize) {
    for (var i = 0; i < hugeArray.length; i = i + chunkSize) {
        yield hugeArray.slice(i, chunkSize + i); 
    }
}

var myIterator = getArrayByChunks([1,2,3,4,5,6,7,8,9,10], 3);
do {
    var result = myIterator.next();
    console.log(result.value);
} while (!result.done);
// [1, 2, 3]
// [4, 5, 6]
// [7, 8, 9]
// [10]

{% endhighlight %}

¡Bien!

Os animo a que probéis más cosillas (tanto Chrome como Firefox ya implementan estas funcionalidades de ES6) y que intentéis sacar partido a esta interesantísima herramienta del nuevo JavaScript. Como siempre, enlazo al [artículo que me ha servido de inspiración][fuente_original].

Algún lector me ha comentado que los artículos son demasiado breves. Puede que sea verdad, pero por ahora me gusta así. Intento tener esto más como un índice de funcionalidades que como una explicación detallada. En cualquier caso, referencias de Javascript no faltan en Internet.

El próximo artículo, como algunos ya sabrán, hablará de **Plantillas en cadenas de texto**. Una característica que, a decir verdad, no me emociona en demasía.

[fuente_original]: https://hacks.mozilla.org/2015/05/es6-in-depth-generators/
