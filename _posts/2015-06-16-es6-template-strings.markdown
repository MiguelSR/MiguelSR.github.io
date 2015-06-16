---
layout: post
comments: true
title:  "EcmaScript 6: Template strings"
date:   2015-06-16 23:20:00
tags: js es6 template strings plantillas
---

**Template strings** (en nuestro querido idioma, **plantillas de cadena de texto**). Una característica a priori no especialmente interesante para los acólitos Javascripters, creo yo. Aun así, como toda novedad de ES6, merece ser comentada en este blog.

Seguro que os suenan alguno de estos trozos de código:

{% highlight python %}
# Python
print "My name is %s and I am %d years old" % (name, age,)
{% endhighlight %}

{% highlight cpp %}
// C++
printf("My name is %s and I am %d years old", name, age);
{% endhighlight %}

{% highlight php5 startinline %}
// PHP
sprintf("My name is %s and I am %d years old", $name, $age);
{% endhighlight %}

Todo el mundo sabe lo que hacen estas instrucciones: interpreta un string dado como plantilla y sustituye los valores *%s* y *%d* por las variables *name* y *age*.

Desgraciadamente, en JavaScript no tenemos manera de hacer esto de manera inmediata, así que habitualmente se hace un apaño de este tipo.

{% highlight js %}
console.log("My name is " + name + " and I am " + age + " years old.");
{% endhighlight %}

Esto presenta una serie de desventajas, por ejemplo:

+ Sucesivas llamadas al operador "+" en lugar de usar una sola función.
+ Andar con el cuidado de dejar los espacios adecuados
+ No poder almacenar el string como una variable para luego sustituir los valores.
+ Muchas más cosas.

Con la nueva especificación de EcmaScript, podemos usar los acentos abiertos (``) para fabricar estos *template strings*.

{% highlight js %}
var name = "Miguel";
var age = 28;
console.log(`My name is ${name} and I am ${age} years old.`);
// My name is Miguel and I am 28 years old.
{% endhighlight %}

Si copiáis ese código y lo pegáis en la consola, podréis trastear un poco con la sustitución. Por ejemplo:
{% highlight js %}
var name = "Miguel";
var age = 28;
console.log(`My name is ${name + "sr"} and I am not ${age * 3} years old.`);
// My name is Miguelsr and I am not 84 years old.
{% endhighlight %}

Podemos ver que dentro de la *template substitution* se pueden meter, por tanto, cualquier tipo de expresiones de JavaScript. Incluso otra template string. Si lo que metemos no es un string, se aplicará una coerción de tipos como de manera habitual.

Bien, comentemos también otra funcionalidad, *plantillas etiquetadas*. Miren ustedes el siguiente código:

{% highlight js %}
var name = 'mengano';
var lang = 'javascript';

function Capitalizer(templateData) {
  var s = templateData[0];
  for (var i=1; i < arguments.length; i++) {
    s += arguments[i].toUpperCase();
    s += templateData[i]
  }
  return s
}

console.log(Capitalizer`Me llamo ${name} y me gusta mucho programar en ${lang}`);
// Me llamo MENGANO y me gusta mucho programar en JAVASCRIPT
{% endhighlight %}

De esta manera podemos tratar las variables a usar en las plantillas antes de renderizarlas. En este caso concreto cogemos cada argumento y lo pasamos a mayúsculas, pero se podrían hacer cosas más guays. Por ejemplo podríamos usar una función saneadora para evitar XSS y demás tretas de gente indeseable.

¿Por qué digo que no me interesa especialmente esta funcionalidad? Pues no sé, la sintaxis no me acaba de hacer, por ejemplo. Además, considero que meter cualquier código JavaScript dentro de la sustitución puede ser un poco salvaje. Para casos complejos puede que sea bastante engorroso de usar (¿cómo lo compatibilizamos con librerías de internacionalización?). En cualquier caso, si esta funcionalidad está bien diseñada o no (o si es útil o no), es algo que sólo el tiempo dirá. Por mi parte seguiré usando Handlebars (que, por cierto, me gusta mucho) salvo para cadenas bastante simples.

Para no faltar a la costumbre, os animo encarecidamente a que leáis [el artículo correspondiente en Mozilla Hacks][fuente_original], blog que entra en mucho más detalle que este. También es interesante repasar los comentarios, donde se habla de las virtudes y defectos de esta nueva característica.
[fuente_original]: https://hacks.mozilla.org/2015/05/es6-in-depth-template-strings-2/
