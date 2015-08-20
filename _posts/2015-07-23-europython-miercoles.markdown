---
layout: post
comments: true
title:  "Europython 2015: III, Miércoles 22 de Julio"
date:   2015-07-23 09:00
tags: python nojs europython metaprogramation type hints typed language elasticsearch elastic pylint locks redis asyncio pyspark
---

¡Buenos días! Tercer día de conferencias del **EuroPython** terminado con éxito. Igualmente entretenido pero, siendo sinceros, el que menos he disfrutado hasta ahora. El porqué os lo cuento justo ahora.

#### Conferencias

Bien, empecemos! Como siempre puntual como un prusiano allí estaba un servidor a las 8.30, tomándome el café con bollería de rigor rodeado de mis colegas pythonistas. Este ratejo de la mañana (las charlas empiezan a las 9:15) lo aprovecho para ir modelando esta entrada del blog, leer el mail etc. Así que voy muy apretado, vaya.

Pues eso, a las 9.15 empieza la actividad y para adentro que voy. Volvemos a tener una pequeña introducción por parte de los organizadores. Sin ánimo de entrar en polémica, el inglés del chaval que lo presenta deja un poco que desear. Entiendo que esto es altruista y no se puede exigir un dominio del idioma total y absoluto. No obstante, tengo la sensación de que la gente de fuera no le sigue bien. Ahí lo dejo caer por si me leen, dicho con todo el ánimo constructivo del mundo. EL caso es que nos presenta la keynote del día [Holger Krekel][krekel], hablándonos de una [red descentralizada][decentralized]. Considera que pronto quedarán obsoletos protocolos como HTTP, IP etc y aboga por un nuevo concepto p2p: IPFS. **Inter Planetary File System**, ¡ahí es nada!

Sin haberlo asimilado del todo, me voy a darme un paseito media hora y a seguir trabajando a lo mío. A las 11 continuan las charlas, hoy, aprovechando que hacen programación en castellano y vasco, me voy a ver a [Raúl Cumplido][rcumplido], que nos habla de **[Metaprogramación en Python][metaprogramacion]**. No sé si será porque el cuerpo ya me pedía descansar un poco del inglés, pero la verdad, disfruté esta charla más de lo que pensaba. Con un carácter más divulgativo que profesional, Raúl nos habla acerca de metaclases y demás historias oscuras de Python para juguetear un poco con el código.

Continúo con las charlas, aunque ya (por mera casualidad) dejo de lado las de castellano. Tenía pensado ir a una de **mensajería en tiempo real con MAX**, pero finalmente me he dado cuenta de que [Guido Van Rossum][guido] *himself* iba a hablarnos de los **[Type Hints en Python 3.5][type_hints]**, así que me decantó por la del holandés. Como el propio nombre dice, nos presenta una característica crucial (¡y altamente controvertida!) de la próxima versión de Python: poder especificar parámetros con tipado estático (en un lenguaje tan dinámico como Python!). Como no podía ser de otra manera, la sala estaba *abarrotá*.

Como decía, entre charla y charla, y en los ratos del café intentaba ponerme con el blog, pero me resultó muuuuuuy difícil ya que la Wifi está sobrecargada. En función de la hora y del emplazamiento, resulta totalmente imposible navegar por Internet, desgraciadamente. Los días anteriores sin embargo había funcionado bastante bien, no sé el motivo.

Desvarío aparte, me decido a acudir a ver a [Antonin Lacombe][alacombe] que nos habla de como escribir su propio ElasticSearchQuery y ElasticSearchBackend para que sea compatible con Haystack, (que necesitaba usar por otra parte). También habla de las funciones *decay*. La charla se llama **[From basic distance search to a complex multi criteria search][complexsearch]** y el título ya es bastante aclarativo :). Comentar que el caso de uso del tipo era conseguir que un buscador de caravanas de alquiler diese la puntuación a los resultados puntuando en base a múltiples campos (si mal no recuerdo, número de fotos, precio...).

Pausa para comer, de nuevo magnífico catering, está todo riquísimo. Desde el día anterior han puesto cartelitos para que los carnívoros no nos comamos la comida de los vegetarianos... EuroPython en contra de la selección natural :P.

Termino de comer y me voy a ver la conferencia de [Claudiu Popa][cpopa], el tipo que desde hace un año y pico, mantiene Pylint. No en vano, la charla se titula **[12 years of Pylint][pylint]**. Nos cuenta un poco de qué va Pylint, las alternativas que hay, su historia en el proyecto y como está construido (haciendo hincapié en el uso interno de *astroid*). A mí me gusta mucho todo esto de los linters, ¡así que me alegro de haber asistido!

Teóricamente, iba a que me contasen **[lecciones aprendidas con asyncio][leccionesasyncio]**. Pero resulta que la sala estaba petada y no había modo de poder sentarse. Intentamos quedarnos a un lado y nos dicen que no podemos, cuando en el resto de charlas siempre se había hecho. Para más inri, a la siguiente charla había gente sentada a ese lado, así que no entiendo na de na. Tampoco se acaba el mundo pero es un poco raro, sin más. Por no quedarme sin hacer nada, me voy a que [Sebastian Buczyński][sbucz] me cuente movidas de **[locks y semaforos con Redis][redis]**, pero -*mea culpa*- no presto mucha atención y no aprovecho la charla todo lo que debería.

Para quitarme la espina de Asyncio, aprovecho y me meto en una que hace un repaso a **[la comunidad de asyncio un año después][asynciocomunidad]**, por [Victor Stinner][vstinner]. Esta sí que me ha gustado, tengo ganas de pasarme a Python 3 y probar esto. Pastitas, tontear por ahí y al lío con **[PySpark][pyspark]**, expuesta por [Peter Hoffmann][phoffmann]. Es un tema que creo que podría dar bastante juego, y venía con ganas, pero he de reconocer que me he aburrido un poco, tal vez porque no tenía ni idea de la materia. No obstante me ha servido para ponerme un poco al día y decidir que debo investigar por mi cuenta.

El final del día, las divertidísimas **Lightning Talks**. Charlas variadas: algunas muy serias, otras muy tontas, pero todas ellas de 5 minutos. Parte de la gracia es por el presentador, un auténtico showman que ameniza los intervalos con sus canciones, bailes, chistes y chascarrillos. Un 10. La otra parte se la llevan los propios ponentes; muchos de ellos saben de antemano el carácter festivo de estas microcharlas y buscan sacarle la carcajada al personal.

#### Desenlace

La cosa se ha alargado un poco así que salgo rápidamente del recinto, no vaya a ser que pierda el autobús. Me voy a la estación corriendo y resulta que efectivamente, lo he perdido. Dado que sigue el característico *txirimiri* me voy a tomarme una cerveza mientras espero al siguiente bus pensando en el día. ¿Cuales son las conclusiones que saco? Que ha estado de nuevo de puta madre. Eso sí, me ha quemado un poco el no poder tener wifi casi toda la mañana y también haberme perdido la primera charla de asyncio. Por lo demás, todo genial, sigo recomendado EuroPython a cualquiera que dude.

Mañana más.

[krekel]: https://ep2015.europython.eu/conference/p/-343
[decentralized]: https://ep2015.europython.eu/conference/talks/keynote-towards-a-more-effective-decentralized-web
[rcumplido]: https://ep2015.europython.eu/conference/p/raul-cumplido
[metaprogramacion]: https://ep2015.europython.eu/conference/talks/metaprogramacion-en-python
[guido]: https://ep2015.europython.eu/conference/p/guido-van-rossum
[type_hints]: https://ep2015.europython.eu/conference/talks/type-hints-for-python-35k
[alacombe]: https://ep2015.europython.eu/conference/p/antonin-lacombe
[complexsearch]: https://ep2015.europython.eu/conference/talks/from-basic-distance-search-to-a-complex-multi-criteria-search
[cpopa]: https://ep2015.europython.eu/conference/p/claudiu-popa
[pylint]: https://ep2015.europython.eu/conference/talks/12-years-of-pylint-or-how-i-stopped-worrying-and-love-the-bugs
[leccionesasyncio]: https://ep2015.europython.eu/conference/talks/lessons-learned-with-asyncio-look-ma-i-wrote-a-distributed-hash-table
[sbucz]: https://ep2015.europython.eu/conference/p/sebastian-buczynski
[redis]: https://ep2015.europython.eu/conference/talks/distributed-locks-with-python-and-redis
[asynciocomunidad]: https://ep2015.europython.eu/conference/talks/asyncio-community-one-year-later
[vstinner]: https://ep2015.europython.eu/conference/p/-358
[pyspark]: https://ep2015.europython.eu/conference/talks/pyspark-data-processing-in-python-on-top-of-apache-spark
[phoffmann]: https://ep2015.europython.eu/conference/p/peter-hoffmann
