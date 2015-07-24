---
layout: post
comments: true
title:  "Europython 2015: IV, Jueves 23 de Julio"
date:   2015-07-24 09:00
tags: python nojs europython educacion tornado asyncio python3 decoradores numpy code review pair programming restful api django rest framework gil diversidad trans minorias
---

De nuevo entrada del **EuroPython**. Para aquel al que esta serie de artículos se le estén haciendo pesados, que no se preocupe, puesto que ya estamos en el jueves, **penúltimo día de conferencias**. ¡Vamos allá!

El caso es que ayer Jueves volvió a ser un día de conferencias de puta madre, como viene siendo la costumbre. Y también como viene siendo la costumbre, con un ritmo frenético de no parar ni un segundo.

#### Conferencias

9.15, café tomado y desayuno también[^1]. ¡Vamos a las charlas! Esta vez la presentadora de la keynote está preocupada por el futuro de la educación. Propone maneras de enseñar Python a los más pequeñajos y anima a los pythonistas presentes a que nos involucremos y ayudemos a la causa. Me parece excelente, yo ya me he apuntado a [la lista de correo][listacorreo]. Ovaciones para la ponente, mini pausa y a otra cosa.

Seguimos con una charla que interesaría también a javascripters, y es que el tema va de peticiones asíncronas. Concretamente aquí [Anton Caceres][acaceres] nos habla de **[Código asíncrono con Tornado y Python 3][tornado]**. Evidentemente, vuelve a salir como tema **asyncio**, uno de los *trending topics* de las conferencias. Hace unos benchmarks comparando el rendimiento de una mini app implementada con tres tecnologías: Tornado + Python 3, Node.js y Scala. Gana Scala, eso sí. Node da unos resultados tirando a malos, pero el ponente admite que puede que no lo haya configurado del todo bien. En cualquier caso, la charla es muy guay y sirve como ejemplo introductorio a asyncio y Tornado.

El carismático [Pablo Enfedaque][pablo] nos sorprende con una **[charla de decoradores][decorators]** en la que los decoradores no son nombrados literalmente hasta el último minuto. La charla recoge carcajadas y aplausos a partes iguales. Pablo se curra unos ejemplos de funciones Fibonacci con un closure memoizer a modo de decorador. Seguro que los javascripters también habrían seguido el rollo a esta :). ¡Por cierto, muy bien explicado!

Antes del almuerzo voy a que [Ekaterina Tuzova][ekaterina] me hable de **[Numpy][numpy]** ya que tenía curiosidad. Debo reconocer que me aburrí. No sé si es que ya tendría hambre, pero me ha parecido que le faltaba algo de chispa a la presentación y que se centraba demasiado en detalles concretos de la librería.

¡A comer! La comida sigue muy bien, hoy han puesto una especie de rollitos de chorizo que han causado furor. Hay que reconocer que está muy guay que vayan cambiando de *pintxos* cada día, así no se aburre el personal.

Desgraciadamente, la otra charla de APIs REST para aplicaciones JS (que, por cierto, me interesaba bastante), se tuvo que cancelar, no sé por qué. Una auténtica lástima. En su lugar, me metí en una tertulia de cinco ponentes (de Canonical, Google y no recuerdo qué más) hablando del **Code Review, Pair Programming, etc**. No ha sido un mal plan alternativo, aunque habría preferido la charla que estaba planificada.

Como había quedado con ganas de APIs, me decanté por la charla **[What it's really like building RESTful APIs with Django][restful]** de [Paul Hallett][phallet]. Ha centrado la charla en **Django Rest Framework** y nos ha contado sus virtudes, así como algunos consejos en cuanto a APIs en general. Paul se define como un fanático de las APIs, y ha hecho algunas interesantes de [Pokemon][pokeapi] y [Star Wars][swapi]. Yo en mi trabajo sigo usando *Tastypie* y aunque está bien, es cierto que es bastante viejecilla. Deberíamos ir pensando en movernos a Django Rest Framework.

Después de la charla RESTful, no tenía dudas: Me había encantado la *lightning talk* del día anterior de [Larry Hastings][larry] y me apetecía ponerme al día acerca del **[Infame GIL de Python][gil]**. Para el que no lo sepa, esto es una tara que llevaba arrastrando Python desde el principio de los tiempos que básicamente hace que no pueda aprovechar los multiprocesadores. ¡Ups!

Podría haber seguido con el asunto del GIL, ya que después tenía pensado ir a **[The GIL is dead: PyPy-STM][gildead]**. Pero en un arrebato de última hora, decidí que mejor lo investigaré por mi cuenta. En su lugar, me fui a la charla de [Naomi Ceder][naomi], de temática más social que tecnológica. Un alegato **[en pro de la diversidad][antipatterns]** que no me esperaba en absoluto. A la gente le ha encantado. A mí me ha parecido que ha estado bien, pero no me ha sugerido nada nuevo ni me ha cambiado mi manera de ver las cosas. Sólo me ha reafirmado lo que ya sé: la mayoría de los programadores somos hombres y somos blancos.

La charla llega a su fin y me voy directo a las **Lightning Talks**. Esta vez no me estaban interesando demasiado así que me fui un poco antes. Eso sí, acojonante el chiste del tractor. Después, me he tomado una cerveza en el stand de google y por culpa de eso he vuelto a perder el autobús. *C'est la vie!*

En otro orden de cosas y como conclusión, ¡ha vuelto el calor a Bilbao! No sé por cuanto tiempo, eso sí. Pero me vine con pantalón y manga larga (tras dos días lloviznando, confiado de mí) y casi me da un jamacuco al salir del recinto, madre mía.

En fin, después de este mini informe meteorológico lo dejo por hoy. Mañana colgaré la que será la entrada del último día de conferencias. Todavía tengo que decidir qué hacer el fin de semana, así que no puedo garantizar si será o no será la última entrada hablando de **EuroPython**. En cualquier caso, la semana que viene volveré con el ritmo y temática habituales (es decir, frecuencia semanal, temática EcmaScript 2015).

¡Hasta mañana!

[^1]: Vaya sobredosis de azúcar estos días. Bien por el catering por proveernos constantemente de fruta, así de vez en cuando puedo evitar la tentación de la bollería insana.
[listacorreo]: https://mail.python.org/mailman/listinfo/pythonedu-wg
[acaceres]: https://ep2015.europython.eu/conference/p/anton-caceres
[tornado]: https://ep2015.europython.eu/conference/talks/better-asynchronous-code-with-tornado-and-python-3
[pablo]: https://ep2015.europython.eu/conference/p/pablo-enfedaque
[decorators]: https://ep2015.europython.eu/conference/talks/decorators-demystified
[ekaterina]: https://ep2015.europython.eu/conference/p/ekaterina-tuzova
[numpy]: https://ep2015.europython.eu/conference/talks/numpy-vectorize-your-brain
[phallet]: https://ep2015.europython.eu/conference/p/paul-hallett
[restful]: https://ep2015.europython.eu/conference/talks/what-its-really-like-building-restful-apis-with-django
[pokeapi]: http://pokeapi.co/
[swapi]: http://swapi.co/
[larry]: https://ep2015.europython.eu/conference/p/larry-hastings
[gil]: https://ep2015.europython.eu/conference/talks/pythons-infamous-gil
[gildead]: https://ep2015.europython.eu/conference/talks/the-gil-is-dead-pypy-stm
[naomi]: https://ep2015.europython.eu/conference/p/naomi-ceder
[antipatterns]: https://ep2015.europython.eu/conference/talks/antipatterns-for-diversity-stop-doing-the-same-thing-but-expecting-different-results
