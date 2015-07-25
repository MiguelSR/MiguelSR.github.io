---
layout: post
comments: true
title:  "Europython 2015: V, Viernes 24 de Julio e impresiones generales"
date:   2015-07-25 09:00
tags: python nojs europython docker kubernetes elasticsearch type hints python3 parallelism threads asyncio multiprocessing measure optimization profiling cprofile runsnake runsnakerun snakeviz
---

¡Quinta y última entrada del **EuroPython**! Supongo que a algunos se os habrán atragantado estos artículos, pero me ha parecido interesante escribirlos y creo que ha merecido la pena. No me entretengo más y os cuento un poco como fue la última jornada pythónica.

El viernes el WiFi fue especialmente malo. Está siendo una constante durante todos los días salvo, tal vez, el primero. Horrible, pero que le vamos a hacer! Además, según llegué por la mañana tempranito no funcionaban algunos de los enchufes. Desconozco si se arregló, imagino que sí.

#### Conferencias

La keynote esta vez fue de [Mandy Waite][mandy], de Google. Nos viene a hablar de [Docker y Kubernetes][docker]. Vale, la charla está guay pero yo no la habría puesto de Keynote! Las otras cuatro habían sido mucho más generalistas, ya que a estas charlas introductorias va todo el público. Sin embargo esta era totalmente tecnológica y entrando en detalles. Me imagino que mucha de la gente que ha venido a la conferencia pero no tiene un perfil muy técnico no se habrá enterado de la misa la mitad. Como curiosidad, comentar que es la única charla a la que he asistido de **Docker**, cosa rara siendo como es una de las tecnologías del momento.

Ya había desayunado así que en el rato libre que tenía me fui a echar un **Street Fighter**, ahí es nada. Y es que hay un par de arcades con emulador de MAME y un par de futbolines para el que se quiera entretener.

Después del vicio, me decanto claramente por [Honza Král][hkral] y su charla **[Beyond the basics with ElasticSearch][elastic]**. Y es que ElasticSearch es el *new kid on the block* en **[Acceso][acceso]**, y nos fascina a la vez que intentamos dominarlo. En esta genial charla, el ponente (que por otra parte trabaja en Elastic), nos cuenta funcionalidades más avanzadas de afamado motor de búsquedas, como la agregación etc.

Seguimos con uno de los *trending topics* de estas jornadas, los *type hints* de Python 3.5, en este caso, **[cómo podemos beneficiarnos de ellos][typehints]**. Me encantó, y estoy seguro de que no solo a mí. Nos dicen que con estos type hints nuestro desarrollo con Mypy o PyCharm será más fácil. Para los que usamos Vim también nos serán de ayuda, tan pronto como Pylint implemente esta característica. Además, nos dice el ponente, son de utilidad para documentar el código. Estoy de acuerdo y me agrada este nuevo PEP. El ponente fue [Andrey Vlasovskikh][andrey].

La tercera y última charla del día (para mí), va de paralelismo. Concretamente, en [Parallelism shootout][parallelism] el conferenciante [Shahriah Tajbakhsh][shah] nos muestra un benchmark simple de un script que hace 30 peticiones a URLs. Las alternativas son: peticiones secuenciales (evidentemente la peor aproximación), threading, multiprocessing y asyncio (este os sonará, otra tendencia clara de Python). La cosa es que el tipo que expone esta charla es la hostia de gracioso, así que pasa volando. Supo meterse al público en el bolsillo y, a pesar de terminar en un tiempo record, levantó una buena ronda de preguntas tras terminar de exponer su presentación. Por cierto, el resultado no fue especialmente determinante. Con la excepción de las peticiones secuenciales (que lógicamente salieron peor paradas), las otras 3 opciones daban unos resultados similares.

¡Hora de comer! Si bien el resto de los días me parece que hemos tenido un catering de puta madre, el viernes fue lamentable. No sólo los *pintxos* eran un poco más cutres de lo habitual, si no que además nos limitaron las raciones. ¿Por qué? No lo sé, pero el personal estaba bastante mosqueado.

Como hasta ese momento sólo había ido a charlas, decidí cambiar un poco el chip el último día y meterme en un tutorial que me copó toda la tarde. Se trataba de un workshop de [optimización][optimizacion]. No hace mucho, tuve que usar *RunSnakeRun* y no solo me llevó de vuelta a los 90, si no que además me resultó totalmente marciano. Así que he aprovechado este tutorial para aprender un poquito del dichoso *RunSnakeRun* así como de *SnakeViz*, *cProfiler*, etc. La experiencia fue como volver a la universidad, estar atendiendo a las explicaciones mientras tonteaba con la terminal :'). El *profe* en este caso era [Mike Müller][muller].

Me salí del *workshop* un poco antes, porque no quería perderme la despedida. Primero explicaron como funciona el fin de semana de *sprints*. Básicamente se trata de irse a un edificio contiguo y meterse unas cuantas horas de programación entre pecho y espalda para colaborar en alguno de los proyectos propuestos. Algunos son famosos, otros no tanto. Haciendo memoria, salieron los nombres de **Django**, **Pylint**, **Cython**, **Scrapy**, etc. 

Después, las habituales **lightning talks** y la despedida en sí, muy sentida, con estadísticas interesantes, divertidas y enriquecedoras. Curioso por ejemplo que de casi 1100 asistentes, no hubiese ni 200 españoles. ¿Cómo es posible? Si es que, ¡hasta han ido más alemanes que españoles! ¿Más estadísticas guays? Los litros de café y cerveza ingeridos, la ausencia de sopas y la sobredosis de *pintxos*. También datos de la gestión del proyecto: gente involucrada, tiempo dedicado, etc.

Tras estos datos, anuncian el emplazamiento del año que viene, ¡de nuevo Bilbao!. Todos los colaboradores se suben al escenario y reciben una más que sentido aplauso que, diría yo, se alarga por varios minutos. ¡Muy emotivo! Aunque el fin de semana haya actividades, el ambiente es 100% de despedida. Secándome las lágrimas, me voy corriendo para no perder el autobús. Por una vez, lo consigo.

Cuando llegué a Bilbao el viernes hacía un sol del copón; al abandonar el congreso sin embargo estaba lloviendo. Bilbao es una ciudad con un clima complicado, pero en este caso le ha dado el necesario toque sombrío a la despedida. Ya en el autobús, meditabundo, saco el portátil y, resguardado de la lluvia y el viento, decido enumerar mis impresiones del congreso.

#### Impresiones

+ La organización ha cumplido de sobra con mis expectativas. Salvo el primer día que hubo un poco de despiste con las tarjetas perdidas, el resto no he visto el más mínimo problema.
+ Las charlas se han ido sucediendo todas con una puntualidad maravillosa. Debo reconocer que no suelo acudir a eventos *formales*, así que tal vez sea algo habitual. No obstante, insisto: me ha encantado la puntualidad constante.
+ La programación era francamente buena. Tener a ponentes de todas las empresas punteras contándome sus cosilla cara a cara ha sido una experiencia que me he gustado mucho.
+ El catering, salvo el infame último día, me ha encantado. No obstante, he leído en Twitter a gente quejándose de que fuese todo picoteo y sandwiches. Cuestión de gustos.
+ Los voluntarios y organizadores se han mostrado amigables y colaborativos en todo momento a pesar del currazo. Un 10.
+ El edificio era la hostia, perfecto para este tipo de situaciones. Muchos enchufes, muchas mesas, buena sonorización, buena situación, etc.
+ El streaming de todas las charlas, no he probado como funciona pero no he leído quejas, ¡así que seguro que ha ido perfecto!
+ Sólo una cosa mala: ¡¡¡La WiFi en muchos casos iba de culo!!!

En definitiva, el 95% de mis sensaciones son positivas. Recomiendo a cualquiera que, si puede, vaya al *Europython 2016*. Aunque el precio puede parecer un poco caro, no hay que olvidar que es una semana completa.

Espero que os haya gustado esta serie de entradas del blog. Si tenéis alguna duda o queréis comentar cualquier cosa conmigo, no dudéis en mandarme un mail, un tweet o dejarme un comentario.

¡Un saludo a todos!

[mandy]: https://ep2015.europython.eu/conference/p/mandy-waite
[docker]: https://ep2015.europython.eu/conference/talks/keynote-so-i-have-all-these-docker-containers-now-what
[hkral]: https://ep2015.europython.eu/conference/p/honza-kral
[elastic]: https://ep2015.europython.eu/conference/talks/beyond-the-basics-with-elasticsearch
[acceso]: http://www.acceso.com
[andrey]: https://ep2015.europython.eu/conference/p/andrey-vlasovskikh
[typehints]: https://ep2015.europython.eu/conference/talks/how-you-can-benefit-from-type-hints
[shah]: https://ep2015.europython.eu/conference/p/-374
[parallelism]: https://ep2015.europython.eu/conference/talks/parallelism-shootout-threads-vs-asyncio-vs-multiple-processes
[optimizacion]: https://ep2015.europython.eu/conference/talks/faster-python-programs-measure-dont-guess
[muller]: https://ep2015.europython.eu/conference/p/mike-muller
