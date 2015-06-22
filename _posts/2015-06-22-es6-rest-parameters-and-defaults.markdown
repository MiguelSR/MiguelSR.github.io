---
layout: post
comments: true
title:  "EcmaScript 6: Parámetros rest y parámetros por defecto"
date:   2015-06-22 21:30:00
tags: js es6 parameters rest defaults
---

Como ya muchos sabréis, [la nueva especificación de EcmaScript ha sido aprobada][especificacion], así que estamos de enhorabuena, ya que los artículos publicados hasta ahora no habrán sido escritos en vano :P. A no ser que [la otra noticia relevante del mundillo front-end][web_assembly] convierta JS en algo del pasado. ¡El tiempo dirá!

Poco importa ahora, ¡sigamos desgranando las novedades de ES6! Hoy nos tocan los **parámetros rest**[^1] y **parámetros por defecto**.

En una función de Javascript se puede acceder a los argumentos de dos maneras distintas: con la declaración formal de los parámetros, o con el objeto **arguments**.

{% highlight js %}
function foo(bar, baz) {
  console.log(bar, baz); // miguelsr .js
  console.log(arguments); // ["miguelsr", "js", ".org"]
}
foo("miguelsr", ".js", ".org");
{% endhighlight %}

Como se puede ver, se pueden pasar un número aleatorio de parámetros a la función *foo* y recogerlos posteriormente con *arguments*. No obstante, esto no es muy bueno, veamos algunos ejemplos de por qué.

{% highlight js %}
function foo() {
  var argumentsCopy = arguments.slice();
}
foo(); // TypeError: arguments.slice is not a function.

(function() { console.log(arguments instanceof Array) })() // false

function bar(arguments) {
  console.log(arguments);
}
bar(1, 2, 3, 4, 5, 6); // 1 en lugar de Array [ 1, 2, 3, 4, 5, 6 ]

{% endhighlight %}

Pues ya véis:

* *arguments* parece un Array, pero no lo es, así que no implementa las funciones de *Array.prototype*. Una de esas encantadoras y desconcertantes rarezas de Javascript.
* *arguments* se puede sobrescribir, otra rareza de Javascript (una rareza terrible, todo sea dicho).
* Viendo la interfaz de una función, ¡no podemos saber si se espera que reciba cero, uno, quince o infinitos parámetros!

Por tanto, está guay que ES6 defina estos nuevos **parámetros rest**.

{% highlight js %}
function foo(bar, ...baz) {
  var bazCopy = baz.slice(); // No falla :)
  console.log(bar); // 1
  console.log(baz); // Array [ 2, 3, 4, 5 ]
  console.log(baz instanceof Array); // true
}
foo(1,2,3,4,5);
{% endhighlight %}

Evidentemente, sólo el último parámetro puede tener esta nueva sintaxis.

{% highlight js %}
function foo(bar, ...baz, ...qux) {} // SyntaxError: parameter after rest parameter
function foo(...bar, baz) {} // SyntaxError: parameter after rest parameter
{% endhighlight %}

Una vez introducidos este tipo de parámetros, no se me ocurre por que seguir usando el errático *arguments*. ¡Os damos la bienvenida, parámetros rest!

Pasemos a los **parámetros por defecto**. Cualquiera puede entenderlos sin mayor explicación.

{% highlight js %}
function foo(bar="bar", baz) {
  console.log(bar, baz);
}
foo(); // "bar" undefined
foo("miau"); // "miau" undefined
foo("miau", "woof"); // "miau" "woof"
foo(null, "woof"); // null "woof"
foo(undefined, "woof"); // "bar" "woof" <-- Al loro!
{% endhighlight %}

Además, los parámetros por defecto se evaluan en tiempo de ejecución de izquierda a derecha.

{% highlight js %}
function foo(arg1 = "bar",
             arg2 = (arg1 == "bar") ? "arg1 es bar" : "arg1 no es bar") {
  console.log(arg1, arg2);
}
foo(); // "bar" "arg1 es bar"
foo("miau"); // "miau" "arg1 no es bar"
foo("miau", "woof"); // "miau" "woof"
foo(null, "woof"); // null "woof"
foo(undefined, "woof"); // "bar" "woof"
foo("bar"); // "bar" "arg1 es bar"
{% endhighlight %}

No tengo nada más que decir de estas dos nuevas características de los parámetros.  Así que nada, ahí quedan estos dos nuevas características de JavaScript. Son dos nuevas funcionalidades bastante sencillas pero sinceramente yo creo que [ya hera ora][ya_hera_ora]. Prescindir de *arguments* hará, sin duda, que nuestros programas sean más legibles.

Por cierto, a 22 de Junio del 2015, esto aun no funciona en Google Chrome. Sin embargo, podéis trastear tranquilamente con la consola de Firefox, puesto que el navegador de Mozilla ya lo implementa.

Los lectores fieles ya sabéis lo que toca ahora: [el enlace al artículo correspondiente en Mozilla Hacks][fuente_original]

Nos vemos en unos días con la **destructuración**.

<br>

[especificacion]: https://news.ycombinator.com/item?id=9733168
[web_assembly]: https://medium.com/javascript-scene/what-is-webassembly-the-dawn-of-a-new-era-61256ec5a8f6 
[fuente_original]: https://hacks.mozilla.org/2015/05/es6-in-depth-rest-parameters-and-defaults/
[ya_hera_ora]: http://www.manolokabezabolo.es/yaheraora.html
[^1]: Si a alguien se le ocurre una buena traducción de *Rest parameters*, que la deje en los comentarios, ¡por favor!
