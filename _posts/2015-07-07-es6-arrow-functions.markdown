---
layout: post
comments: true
title:  "EcmaScript 6: Funciones flecha"
date:   2015-07-07 21:00:00
tags: js es6 arrow functions funciones flecha this
---

Las funciones flechas son sin lugar a dudas una de las novedades más esperadas de EcmaScript 6. Estoy seguro de que a la inmensa mayoría de las personas que alguna vez haya programado en JavaScript le suena este patrón.

{% highlight js %}
function foo() {
    var self = this;
    setTimeout(function() {
        this.bar = 'baz';
    }, 500)
}
{% endhighlight %}

O este otro, sólo válido a partir de ES5.

{% highlight js %}
function foo() {
    setTimeout(function() {
        this.bar = 'baz';
    }.bind(this), 500)
}
{% endhighlight %}

O le sonarán las funciones **call** y **apply**, o **_.bindAll**, o **$.proxy**...

¿Qué tienen en común todos estos ejemplillos? Pues bien, son maneras de forzar la ejecución de una función con un valor de **this** dado. Este es uno de los puntos claves de JavaScript. A muchos programadores que aun no comprenden el lenguaje les suele parecer bastante raro. Y es que *this*, toma un valor u otro dependiendo de **como se ejecute** una función, no de como se declare.

¿A que viene esta lección gratuita de semejante obviedad? Primero, no está de más recordarla. Segundo, nuestras **arrow functions**, de repente, anulan este concepto. Refactoricemos el código anterior usando una función flecha gorda.

{% highlight js %}
var myObject = {}
function foo() {
    setTimeout( () => this.bar = 'baz', 1)
}
foo.call(myObject);
myObject.bar // "baz"
{% endhighlight %}

Se puede ver en este ejemplo que, como decía en el párrafo anterior, **el valor de this** ya no varía en tiempo de ejecución.

Lo que antes era una función anónima al uso ahora se ha transformado en un *lambda* que utiliza el operador *=>* para separar argumentos y cuerpo. Particularmente, esta función no recibe ningún argumento... ¿podríamos pasarle alguno? ¡Pues claro! Otro ejemplillo.

{% highlight js %}
var myArray = [];
function foo() {
    ["foo", "bar", "baz"].forEach( element => this.push(element));
}
foo.call(myArray);
console.log(myArray); // Array [ "foo", "bar", "baz" ]
{% endhighlight %}

Y por supuesto, también varios argumentos.
{% highlight js %}
var myObject = {};
function foo() {
    ["foo", "bar", "baz"].forEach( (element, index) => this[index] = element);
}
foo.call(myObject);
console.log(myObject); // Object { 0: "foo", 1: "bar", 2: "baz" }
{% endhighlight %}

¡Magnífico! Repasemos un poco la sintaxis y añadamos algunas cosillas.

* Podemos ver que los **parámetros se pueden poner con o sin paréntesis**. Esto es así sólo si hay *exactamente* un parámetro.
* Podríamos usar los **parámetros rest** que veíamos en artículos anteriores, ¡y también los **parámetros por defecto**!
* El cuerpo de la función puede ser inline, **pero también podemos meterlo en un bloque {}**.
* Además, aunque todavía no lo hayamos visto, si la función es inline, **hay un return implícito**. ¡Ejemplo!

{% highlight js %}
var odds = [1,2,3,4,5].filter(num => num % 2);
console.log(odds); // Array [ 1, 3, 5 ]
{% endhighlight %}

Tenemos una manera sencilla de ejecutar callbacks anónimos sin tener que hacer el trámite de guardar el valor de this, hacerle un bind a la función o lo que sea. Eso sí, la sintaxis es bastante parca, no tiene demasiado que ver con el **function** que usábamos hasta ahora. Me imagino que con el tiempo saldrán defensores y detractores, pero definitivamente creo que es un avance en el lenguaje. A mí particularmente me gusta.

A los lectores más inquietos se le habrán ocurrido varias preguntas. *¿Qué pasa con **this**? ¿Y con **arguments**? ¿Devuelven algo las funciones que no sean inline? ¿Como encaja esto con la desestructuración?*. A todos ellos les animo a abrir la consola del Firefox y ponerse a caacharrear un ratillo. Después, cuando se hayan cansado, cogen y se leen [el artículo de Mozilla Hacks][fuente_original].

¡A cuidarse!

[fuente_original]: https://hacks.mozilla.org/2015/05/es6-in-depth-destructuring/
