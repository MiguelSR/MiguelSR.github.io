---
layout: post
comments: true
title:  "EcmaScript 6: Iteradores"
date:   2015-06-02 22:00:00
tags: js es6 iteradores
---

En la primera entrada, hablaba de los bucles *for..of*. Concretamente, decía que no sólo servían para recorrer arrays, si no también strings y otras cosas llamadas sets y maps.
¿Qué pasaría si probásemos a recorrer un objeto estándar usando este *for..of*?

{% highlight js %}
for (var element of {foo: 'bar'}) {
   console.log(foo);
} // Uncaught TypeError: undefined is not a function
{% endhighlight %}

Cabe esperar por tanto, que *Object* carezca de alguna característica de la que sí disponen los tipos *Array*, *Set* y *Map*. Una característica que les permita ser recorridos usando *for..of*. Efectivamente esto es así, ya que *Array*, *Set* y *Map* implementan *Symbol.iterator* y evidentemente, *Object* no lo hace.

{% highlight js %}
console.log(typeof Array.prototype[Symbol.iterator]); // function
console.log(typeof Map.prototype[Symbol.iterator]); // function
console.log(typeof Set.prototype[Symbol.iterator]); // function
console.log(typeof Object.prototype[Symbol.iterator]); // undefined
{% endhighlight %}

A la primera pregunta, *¿qué es eso de Symbol?* no contesto, porque se sale del ámbito de este artículo.

A la segunda pregunta, *¿por qué los que hacen JavaScript han puesto un nombre tan raro en vez de, por ejemplo, "iterator"?* pues bueno, me figuro que es una manera de asegurarse una compatibilidad con programitas, apps, librerías etc, que ya tengan definida la función *iterator* en los prototipos... en cualquier caso estoy de acuerdo en que la sintaxis es bastante rara.

Si tienes la tercera pregunta *¿qué es un iterador?*, te aconsejo buscar en Google. Básicamente, un mecanismo de algunos lenguajes "serios"[^1] para recorrer secuencialmente distintas estructuras de datos. Como anécdota personal recuerdo que, en mi época en la universidad, los iteradores de la STL de C++ me parecían poco menos que la obra cumbre de la ingeniería informática.

En fin, ¿para qué nos podría interesar a nosotros crear un iterador? A bote pronto, para nada. No obstante, está bien que estén ahí.

Supongamos que fuesemos unos cracks y quisiésemos crear una librería, framework o similar con nuestros propios tipos de datos. ¿Podríamos tener una clase que implementase *Symbol.iterator* y por tanto se pudiese recorrer con *for..of*? Pues sí, hagamos el experimento.

**Mal**
{% highlight js %}
var MyClass = function() { }; // Clase simple, sólo para ilustrar
MyClass.prototype[Symbol.iterator] = function() { return this; }
m = new MyClass();
for (var foo of m) { // undefined is not a function :(
  console.log(foo);
}
{% endhighlight %}

**Mal**
{% highlight js %}
var MyClass = function() { }; // Clase simple, sólo para ilustrar
MyClass.prototype[Symbol.iterator] = function() { return this; }
MyClass.prototype.next = function() { }
m = new MyClass();
for (var foo of m) { // TypeError: Cannot read property 'done' of undefined 
  console.log(foo); 
}
{% endhighlight %}

**¿Bien?**
{% highlight js %}
var MyClass = function() { }; // Clase simple, sólo para ilustrar
MyClass.prototype[Symbol.iterator] = function() { return this; }
MyClass.prototype.next = function() {return {done: true, value: undefined} }
m = new MyClass();
for (var foo of m) {
  console.log(foo); // No hace na de na, pero funciona!! :D
}
{% endhighlight %}

Fijándonos en los tres bloques de código anteriores, no será difícil entender los siguientes dos puntos:

   * Para que un objeto sea iterable no basta con que implemente *Symbol.iterator*, si no que dicho iterator a su vez debe implementar *next*.
   * Esta función *next* debe devolver un objeto con dos valores, *done* que indica si ha terminado de iterar y *value* que devuelve el valor actual.

¡Intentemos hacer algo que devuelva valores reales!
{% highlight js %}
var i = 0;
var MyClass = function() { }; // Clase simple, sólo para ilustrar
MyClass.prototype[Symbol.iterator] = function() { return this; }
MyClass.prototype.next = function () {
    var value = this[Object.keys(this)[i]];
    var done = (i == Object.keys(this).length);
    i = i + 1;
    return {done: done, value: value};
}
m = new MyClass();
m.foo = 'foo'; m.bar = 'bar'; m.baz = 'baz'; m.qux = 'qux';
for (var foo of m) {
  console.log(foo); // ¡¡¡foo, bar, baz, qux!!!
}
{% endhighlight %}

Pues ahí tenemos una pequeña muestra de código chapucero donde recorremos un objeto con *for..of*. ¡Bravo!


Ya hemos visto como implementar algo tan serio un iterador sobre un tipo de objeto en JavaScript con esta novedad de ES6. Aquí lo dejo, espero que os haya gustado este segundo artículo. Al igual que el anterior, es una adaptación libre de [este otro][fuente_original], que debéis consultar ya que tiene mucha más información. En el próximo artículo pienso escribir acerca de los **generadores**. ¡Hasta entonces!

[fuente_original]: https://hacks.mozilla.org/2015/04/es6-in-depth-iterators-and-the-for-of-loop/
[^1]: La seriedad (o falta de ella) de JavaScript puede protagonizar -y protagoniza- un debate acalorado del que yo no voy a tomar parte aquí y ahora.
