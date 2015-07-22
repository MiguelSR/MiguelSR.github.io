---
layout: post
comments: true
title:  "Europython 2015: II, Martes 21 de Julio"
date:   2015-07-22 09:00
tags: python nojs europython pyspark spark deployment juju blaze d3 pandas visualization data logging postgresql testmon pytest astpy ast.py py.test coverage.py coverage hook plugin pluggy
---

Hola de nuevo. Aquí sigo fiel a mi compromiso de ir publicando pequeños resúmenes del EuroPython. Dado que ayer ya conté acerca del evento y de la organización, hoy me centraré en las charlas. ¿Ok?

#### Conferencias

Puntual a las 8:30 llegué para disfrutar del desayuno pythónico (café con leche + algo de bollería) e ir preparándome para la Keynote del día, posiblemente una de las charlas más esperadas. Y es que ni más ni menos que **Guido Van Rossum** fue el encargado de llevarla a cabo. Nos estuvo hablando en una amena sesión de Q&A (donde el mismo se hacía algunas de las preguntas). Alguno de los temas fueron el futuro de Python, por qué deberíamos migrar a Python 3, el porqué del GIL y otras cosas, además de declararse usuario de *Emacs* y fanático de la excepción *KeyboardInterrupt*. Muy divertida charla, desde luego Guido es toda una personalidad.

Después de la pausa de rigor, [Vincent Warmerdam][vwarmerdam] nos presenta una divertídisima charla, **[PySpark and Warcraft Data][warcraft]** donde analiza un set de datos de 22GB del mercado de *World of Warcraft* con Spark.  El llamado *Data Science* es evidentemente un mundillo de moda, y esta edición de Europython está siendo una muestra palpable de ello. Vincent analiza el comportamiento de los precios en el susodicho mercado y se pregunta si cumplirá leyes básicas de economía, etc.

Me voy a ver a [Michael Foord][mfoord] de *Canonical*. Esta conferencia, de título **[To the clouds][totheclouds]**, nos recomienda por activa y por pasiva el despliegue en la nube. ¿Argumentos? Olvidarnos de las máquinas físicas, desacoplamiento, facilidad de actualización del hardware etc. Concretamente nos presentan su software *[Juju][juju]*, para orquestar servicios.

Seguimos con *Data Science*, esta vez de la mano de [Christine Doig][cdoig], que nos habla del ecosistema de Blaze en **[Scale your data, not your process][blaze]**. Una charla ilustrativa que intenta encajar el mundillo de Data Science entero (analistas, programadores, etc) con las distintas tecnologías de dicho ecosistema: Odo, Blaze, Dask, etc.

Llega la hora de comer. De nuevo pinchos variados distintos a los del primer día, el catering está muy bien! Doy una vuelta por los stands haciendo tiempo. El ambiente sigue siendo guay, los puestos con mucha gente congregada etc. A las 14.30 empieza las charlas de la tarde [Kyran Dale][kdale] con la que ahora ha sido una de mis charlas favoritas del congreso, **[Data Visualization with Python and Javascript][dataviz]**. Un enfoque práctico, adaptarse a JS si se quiere hacer visualización en el navegador, es de pura lógica. Defiende el uso de un microframework como *Flask* para crear la API y presentar los datos con *D3.js*. Para explicarlo, se ha currado una charla guay usando también Pandas y Scrapy. Muy grande.

**[A deep look at logging][logging]** es la siguiente presentación, en este caso de [Stefan Baerich][sbaerich]. Como cabe esperar, es un repaso a la librería *logging*, mostrándonos diversas opciones de configuración, niveles, filtros, etc. En el proyecto en el que trabajo le sacamos bastante partido a esta librería, así que me parece bien que se divulgue un uso adecuado de ella.

Mi intención era continua el día con una charla de **PostgreSQL**, pero desgraciadamente fue cancelada. Así que decidí decantarme por [T. Arpas][tarpas] y **[su conferencia de testing][testmon]**. En ella nos presenta su proyecto *testmon*, herramienta que monitoriza los cambios en nuestros ficheros con *ast.py*, detecta las dependencias entre ellos y ejecuta los tests a los que afecte dicho cambio. Con ello pretende reducir el tiempo de ejecución de tests que hace la vida más difícil a muchos developers (me incluyo... :( ).

Para finalizar el día (después de sucesivos pastelillos y alguna que otra partida en el stand de Google), me metí en la conferencia de [F. Bruynooghe][bruynooghe]. ¡Craso error! Creo que la charla estuvo bien, ya que recibió muchos comentarios y preguntas a su finalización. Pero sinceramente yo ya estaba un poco saturado y no presté la atención que requería, ya que trataba un tema muy técnico. Concretamente nos presentaba la **[arquitectura basada en hooks de py.test][pluggy]**. Dicha herramienta hace uso de un componente llamado pluggy por el que se comunican las distintas partes de la aplicación, siendo al parecer la práctica totalidad de la herramienta conectada de este modo. Lo investigaré por mi cuenta porque desgraciadamente la charla no la seguí mucho :(.

Pues bien, otro día finalizado. Cervecitas de rigor en la barra de Google, un paseo por la sección de Posters, donde la gente presentaba sus investigaciones. Vi por ahí posters de reconocimiento sonoro de un robot, python para niños, estadísticas de subdominios .es (por parte de ScrapingHub) y otros que no recuerdo. Después, me fui tranquilamente a dar una vuelta por Bilbao aprovechando que había escampado (no por mucho tiempo, como luego sufriría por mí mismo). Las conclusiones del martes, al igual que las del lunes, son en su práctica totalidad positivas.

Mañana jueves espero publicar el resumen del miércoles. Digo que espero hacerlo porque estoy teniendo un poco de dificultades con la WiFi últimamente, así que veremos si hay suerte. Por cierto, creo que podéis ver el streaming en directo de la sala principal en [este enlace][streaming]. Desconozco si están el resto, todo es cuestión de buscar.

[vwarmerdam]: https://ep2015.europython.eu/conference/p/-242
[warcraft]: https://ep2015.europython.eu/conference/talks/pyspark-and-warcraft-data
[mfoord]: https://ep2015.europython.eu/conference/p/-98
[totheclouds]: https://ep2015.europython.eu/conference/talks/to-the-clouds-why-you-should-deploy-to-the-cloud-even-if-you-dont-want-to
[juju]: https://jujucharms.com/
[cdoig]: https://ep2015.europython.eu/conference/p/-88
[blaze]: https://ep2015.europython.eu/conference/talks/scale-your-data-not-your-process-welcome-to-the-blaze-ecosystem
[kdale]: https://ep2015.europython.eu/conference/p/-426
[dataviz]: https://ep2015.europython.eu/conference/talks/data-visualisation-with-python-and-javascript-crafting-a-data-viz-toolchain-for-the-web
[logging]: https://ep2015.europython.eu/conference/talks/a-deep-look-at-logging
[sbaerisch]: https://ep2015.europython.eu/conference/p/stefan-baerisch
[tarpas]: https://ep2015.europython.eu/conference/p/-353
[testmon]: https://ep2015.europython.eu/conference/talks/mashing-up-pytest-coveragepy-and-astpy-to-take-tdd-to-a-new-level
[bruynooghe]: https://ep2015.europython.eu/conference/p/-253
[pluggy]: https://ep2015.europython.eu/conference/talks/the-hook-based-plugin-architecture-of-pytest
[streaming]: https://www.youtube.com/watch?v=VRGB40srFE8
