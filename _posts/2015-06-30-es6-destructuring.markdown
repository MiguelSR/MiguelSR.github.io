---
layout: post
comments: true
title:  "EcmaScript 6: Desestructuración"
date:   2015-06-30 18:30:00
tags: js es6 destructuring desestructuracion
---

Uno de las cosas que me fastidian de hacer este blog en castellano es tener que traducir los nombres. Lo digo porque en este artículo vamos a hablar de la **desestructuración**, ¡término algo engorroso! Tampoco es que el inglés **destructuring** sea muy distinto, pero da menos cante. En fin, qué más da.

### Desestructuración de arrays

Empecemos con el ejemplo más simple de desestructuración. En él podemos ver como definir tres variables y asignarles los valores de un array en una sola línea.

{% highlight js %}
var myArray = [1, 2, 3];
var [first, second, third] = myArray;
console.log(first, second, third); // 1 2 3
{% endhighlight %}

Evidentemente esto es una manera más sencilla de escribir lo que hasta ahora sería:

{% highlight js %}
var myArray = [1, 2, 3];
var first = myArray[0],
    second = myArray[1],
    third = myArray[2];
console.log(first, second, third); // 1 2 3
{% endhighlight %}

Por tanto, podemos ver que la gracia de la desestructuración radica en asignar las propiedades de estructuras complejas (en este caso arrays) de una tacada usando una estructura que imita a la del objeto a copiar.

Pongamos un ejemplo con una estructura un poco más compleja:

{% highlight js %}
var myArray = [1, [2, 3], {'foo': 'bar'}];
var [first, second, third] = myArray;
console.log(first, second, third); // 1 Array[ 2, 3 ] Object { foo: "bar" }
{% endhighlight %}

Bien, el resultado esperado. ¿Y si intentamos replicar la estructura en **la parte izquierda**?

{% highlight js %}
var myArray = [1, [2, 3], {'foo': 'bar'}];
var [first, [second, third], myObject] = myArray;
console.log(first, second, third, myObject ); // 1 2 3 Object { foo: "bar" }
{% endhighlight %}

¡Muy interesante! ¿Qué pasará si omitimos alguno de los elementos?

{% highlight js %}
var myArray = [1, [2, 3], {'foo': 'bar'}];
var [first, [second, third]] = myArray; // Omito el objeto que hay al final del array
console.log(first, second, third ); // 1 2 3
var [,,myObject] = myArray; // Fijaos en que he omitido los dos primeros items
console.log(myObject); // Object { foo: "bar" }
{% endhighlight %}

Si os acordáis de los [parámetros rest]({% post_url 2015-06-22-es6-rest-parameters-and-defaults %}), tal vez penséis que podríamos usarlos aquí. ¿Podremos?
{% highlight js %}
var myArray = [1, [2, 3], {'foo': 'bar'}];
var [firstItem, ...restOfItems] = myArray;
console.log(firstItem); // 1
console.log(restOfItems); // Array [ Array[2], Object ]
{% endhighlight %}

¡Bieeeeeeen! Una característica que en principio parecía una chorradilla parece que podría llegar a sernos realmente útil :). Pasemos al siguiente punto.

###  Desestructuración de objetos

Viene a ser más o menos lo mismo, ya os podéis imaginar.

{% highlight js %}
var myObject = {foo: "foo"}
var {foo: myFoo} = myObject;
console.log(myFoo); // "foo"
console.log(foo); // ReferenceError: foo is not defined
{% endhighlight %}

Similar pero con una sintaxis un poco rarilla. Si os fijáis, en la parte de la izquierda, tenemos que repetir la clave a la que queremos acceder y especificar un nombre de variable en el valor. ¿Será esto siempre así? ¡No! Si la variable tiene el mismo nombre que el valor, es más sencillo.

{% highlight js %}
var myObject = {foo: "foo", bar: "bar"}
var {foo, bar} = myObject; // Equivalente a var {foo: foo, bar: bar}
console.log(foo, bar); // "foo" "bar"
{% endhighlight %}

Análogamente al caso de los arrays, también se pueden desestructurar objetos con estructuras más complejas. Para ello debemos replicar la estructura deseada en la parte de la izquierda de la asignación. Lo dejo como ejercicio para el lector. Ya se puede probar en Firefox con la consola. En Chrome, a día 30 de Junio del 2015, todavía no está implementada la desestructuración.

### Valores por defecto

Volvemos a echar la vista atrás al artículo de los valores por defecto. En la desestructuración también son aplicables. Veamos unos ejemplillos.

{% highlight js %}
var [emptyArray = true] = [];
console.log(emptyArray); // true

var {foo, bar, baz: baz = "baz"} = {foo: "foo", bar: "bar"}
console.log(foo, bar, baz); // "foo" "bar" "baz"
{% endhighlight %}

La cosa se complica bastante, así que habrá que usar la desestructuración con cautela :).

Pues bien, aquí me quedo. Podéis profundizar buscando info por ahí y practicando con la consola del Firefox.

En esta ocasión, para cambiar un poco la norma, no solo os voy a vincular [la entrada correspondiente del blog de Mozilla Hacks][fuente_original], si no también [este otro artículo][desestructuracion_es_terrible] en el que intentan convencernos para **no** usar la desestructuración. En mi opinión es una gilipollez.

¡Nos vemos!

[fuente_original]: https://hacks.mozilla.org/2015/05/es6-in-depth-destructuring/
[desestructuracion_es_terrible]: http://teeohhem.com/why-destructuring-is-a-terrible-idea-in-es6/
