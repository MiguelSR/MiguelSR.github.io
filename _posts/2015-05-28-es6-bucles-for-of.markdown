---
layout: post
comments: true
title:  "EcmaScript 6: Bucles for-of"
date:   2015-05-28 21:45:00
categories: js es6 for-of
tags: js es6 for-of
---
Mi principal motivación para hacer este blog es escribir acerca de ES6. Concretamente, escribir acerca de ES6 siguiendo el hilo de los artículos que están publicando en [Mozilla Hacks][mozilla_hacks], al menos por ahora. No voy a entrar en detalle de qué es EcmaScript, pero para hacer una aproximación burda, digamos que es una actualización esperada durante años que llega justo cuando JavaScript es el lenguaje de moda. Para más info, nada más que buscar por ahí. Comentemos una interesante novedad de ES6.

**Bucles for-of**

En algunas entrevistas de trabajo me han preguntado, *¿cómo recorrerías un array en JavaScript?*. La pregunta tiene su rollo, ya que se puede responder de distintas maneras. Cada una tiene sus particularidades, que especifico más o menos en los comentarios del código.

{% highlight js %}
// Modo 1: Similar a como recorreríamos un objeto
// Puntos negativos: La especificación no garantiza que for..in respete el orden... ¡mejor no usarlo!
for (var arrayIndex in myAray) {
    console.log(myArray[arrayIndex]); // 1 2 3
    console.log(typeof arrayIndex); // "string" WTF?
}

// Modo 2: Estilo C
// Puntos negativos: Necesitamos variable de longitud y variable para iterar, sintaxis que huele a C.
for (var i=0; i<myArray.length; i++) {
    console.log(myArray[i]);
}

// Modo 3: Tirar de jQuery
// Puntos negativos: ¿Realmente necesitamos una librería externa para recorrer un triste array?
$.each(myArray, function(arrayIndex, value) {
    console.log(value);
});

// Modo 4: Tirar de Underscore
// Puntos negativos: Los del anterior, y cambiando el orden de los parámetros... ¡para volverse loco!
_.each(myArray, function(value, arrayIndex) {
    console.log(value);
});

// Modo 5: Usar forEach
// Puntos negativos: No podemos usar ni continue ni return ni break
myArray.forEach(function (value) {
    console.log(value);
});

{% endhighlight %}

Así a bote pronto se me han ocurrido estos cinco. Posiblemente haya más. Además, la descripción ha sido somera, con lo cual seguro que me dejo locuras variadas que nadie se esperaría. Por ejemplo *each* de jQuery tiene [una manera de hacer break/continue un poco díscola][jquery_each].

Para resolver este entuerto, a los sabios que diseñan JavaScript se le ha ocurrido una solución: *introducir una nueva manera de recorrer un array*

{% highlight js %}
// Así debemos recorrer los arrays a partír de ahora :)
for (var element of myArray) {
   console.log(element); 
   // ¡Sin necesidad de variables ni librerías externas!
   // ¡¡Orden correcto!!
   // ¡¡¡Con break, continue y return!!!
}
{% endhighlight %}

Lo cual puede ser un poco lioso para los que empiecen, ya que se parece *demasiado* a cómo se recorren los objetos:
{% highlight js %}
for (var element in myObject) {
   console.log(element); // Key
   console.log(myObject[element]); // Value
}
{% endhighlight %}

Así que a los despistados les tocará aprenderse un nemotécnico que relacione "of" con "Array" e "in" con "Object".

Por cierto, comentar que for..of también sirve para recorrer Strings, Maps y Sets. De los Maps y los Sets digo yo que ya hablaré en un futuro. Para los strings pongo un ejemplillo.
{% highlight js %}
for (var letter of "foobar") {
   console.log(letter);
   // f
   // o
   // o
   // b
   // a
   // r
}
{% endhighlight %}

Me encanta que ya haya una manera directa y concisa de recorrer arrays en JavaScript. Por otro lado, creo que va a ser una fuente de confusiones. No obstante, a día de hoy es tal el lío, que una manera más de hacerlo sólo hará un poco más divertida la situación.

Para el siguiente artículo hablaré de los iteradores.  Mientras tanto, no dejéis de visitar el blog de Mozilla; os dejo el [artículo de inspiración][inspiracion], el cual en cierto modo he fusilado y recortado.

[inspiracion]:   https://hacks.mozilla.org/2015/04/es6-in-depth-iterators-and-the-for-of-loop/
[mozilla_hacks]: https://hacks.mozilla.org/
[jquery_each]:   http://stackoverflow.com/a/17162375
