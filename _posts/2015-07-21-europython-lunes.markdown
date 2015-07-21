---
layout: post
comments: true
title:  "Europython 2015: I, Lunes 20 de Julio"
date:   2015-07-21 08:45
tags: python nojs europython rust jenkins react machine learning pip bilbao metrics elasticsearch
---

¡Hola! Olvidaros por un momento de EcmaScript 2015 e incluso de JavaScript. Mejor imaginad que la URL de este blog es *miguelsr.py.org*. Y es que, desde [Acceso][acceso] me han enviado de emisario al evento de Python del momento, [EuroPython][europython]. A algún lector le confundirá esto, pero es que en mi día a día uso Python además de JavaScript.

Pues bien, ¡esta conferencia europea este año tiene lugar en el Euskalduna Conference Center de Bilbao! Dado que tengo alojamiento en un pueblito de aquí al lado, me he venido a pasar una semana a esta magnífico evento.

He pensado en ir haciendo cada día un resumen de lo que sucede. Así que, ¡al lío!

#### Entrada

Llegué con tiempo para recoger la entrada y estar desde el primer momento, pero por algún problema con el proveedor no habían podido tener todas las acreditaciones listas, entre ellas la mía ¡argh! No pasa nada, solventado en unos minutos y para dentro. Eso sí, esto provocó un pequeño retraso por el que se tuvo que cortar tiempo de Q&A en algunas charlas. Sin problema.

Tomé un café (muchas barras y mesas, genial gestión) y un breve desayuno y me estuve dando un paseillo por los stands de los sponsors. Todavía no estaba todo montado pero ya tenía buena pinta, Yelp, HP, SkyScanner, e-Frontiers y demás gente andaban por aquí. Tras hacer un poco de tiempo, entramos a la sala principal para la bienvenida.

#### Conferencias

Tras una breve introducción del evento por parte de la organización (con las inevitables bromas de Bilbao como centro del universo, levantamiento de piedras, etc), abrieron la jornada [las dos Olas][ola_and_ola], contándonos a modo de fábula como dos *ardillas* fundaron las Django Girls. Dibujos muy bonitos y una buena historia de lucha y superación.

Otro cafelillo y paseo y empezamos las charlas técnicas, yo me decanté por **[asyncio stack & React.js][asyncio]**, de [Igor Davydenko][igor], y es que la cabra tira al monte. Bien, en efecto la charla propone el uso de asyncio, haciendo especial hincapié en asyncio.http. Es una tecnología de moda, y estoy seguro de que no es en vano. Por la parte del frontal, se hace apología de React como framework de vistas. De nuevo es el framework del momento. Yo todavía no he tenido el placer de trabajar con él, pero espero que pronto pueda hacerlo.

Siguiente charla, me voy a que el italiano [Valerio Maggio][valerio] me cuente un poco de **[Testing en Machine Learning][machine_learning]**. La librería de Python **unittest** se queda corta para hacer testing de Machine Learning, necesitamos algo más científico. No problem, para eso está **numpy.testing** al rescate, del cual nos habla un poco Valerio, entre otras cosas.

[Xavier Fernandez][xavier] nos habla un poco de **[como funciona pip internamente][pip_internals]**. Cómo encuentra los paquetes, resuelve las dependencias, gestiona las versiones o hace caché. Interesante charla de un perfil algo más técnico.

Después, nos vamos a comer, cafelillo y hacer un poco el moñas en el stand de Google, donde han montado una especie de trivial con regalitos y una barra con cervezas para el personal. Un hurra por Google. Al respecto de la comida, aperitivos de la tierra para que nativos y forasteros estemos contentos: tortilla, pimientos rellenos, jamón, ensalada... una vez más, bien por la organización del evento.

14.30, sobremesa con [Dmtry Trofimov][dmitry] hablándonos de **[como integrar nuestro Python con Rust][rust]**, un lenguaje de Mozilla que me está llamando la atención últimamente. Python es un lenguaje fabuloso, pero a veces necesitamos velocidad extra y un lenguaje compilado como Rust podría sernos de ayuda.

Seguimos con un par de charlas que no me parecieron especialmente interesantes. Por un lado [Lynn Root][lroot] nos habló de como hacen **[Metrics driven development][mdd]** en Spotify, creando metas en función de revisiones periódicas a gráficas. Tal vez demasiado orientada al negocio para lo que buscaba. Por otra parte, [Timo Stollenwerk][timo] nos hablaba de **[CI for Django][jenkins]**, que básicamente fue una charla de Jenkins. Me gusta Jenkins pero ya lo llevo usando varios años y no me contó nada nuevo. Bueno, sí, el plugin de dashboards no lo conocía, lo tengo que probar.

Otra pausa para tomar algo y despejarnos un poco y última charla del día. Otra tecnología de moda (que también usamos en Acceso), esta vez **[Elastic Search][elastic]** por [Radosław Jankiewicz][radoslaw], introduciéndonos su uso en Python, funciones y clases útiles, etc. Instructiva. Finalizamos con las llamadas **lightning talks**, presentadas con carácter totalmente festivo, donde los ponentes explicaban sus cositas en cosa de 5 minutos. Consejos para expresiones regulares, apología de las APIs en esperanto (!!) o introducción de proyectos personales. Divertido.

#### Conclusión

Creo que todo estuvo montado muy guay. Había mucha sensación de fiesta y colegueo, cosa que por otra parte me esperaba. Stands de empresas interesantes, cerveza, comida, juegos, regalos y sorpresas. Por no hablar de la cantidad de ponentes y el emplazamiento, de primer nivel. Como única pega podría decirse que en el hall y algunas salas a veces no llegaba el Wifi bien, pero es comprensible teniendo en cuenta que había más de 1000 individuos, cada uno con su smartphone y muchos con portátiles.

Además, el clima acompañó, tal vez incluso más de la cuenta. Yo ayer me pegué un chapuzón en la playa de un pueblo aquí al lado y me quedé en la gloria. Eso sí, hoy Martes hay unos truenos que no presagian nada bueno, además del consabido *txirimiri*.

Espero que os haya interesado este mini reportaje, voy pitando a seguir con las charlas de hoy Martes :)! Seguramente mañana haga un resumen un poquito más breve de lo que ha acontecido hoy.

Por cierto, podéis ver el calendario completo de charlas [aquí][calendario_completo].

[acceso]: http://www.acceso.com
[europython]: https://ep2015.europython.eu/
[ola_and_ola]: http://blog.europython.eu/post/117337312602/our-next-keynote-ola-ola-django-girls
[asyncio]: https://ep2015.europython.eu/conference/talks/asyncio-stack-reactjs-or-development-on-the-edge
[igor]: https://ep2015.europython.eu/conference/p/igor-davydenko
[machine_learning]: https://ep2015.europython.eu/conference/talks/testing-machine-learning-code
[valerio]: https://ep2015.europython.eu/conference/p/valerio-maggio
[xavier]: https://ep2015.europython.eu/conference/p/-264
[pip_internals]: https://ep2015.europython.eu/conference/talks/pip-internals
[dmitry]: https://ep2015.europython.eu/conference/p/-351
[rust]: https://ep2015.europython.eu/conference/talks/rustify-your-python
[lroot]: https://ep2015.europython.eu/conference/p/lynn-root
[mdd]: https://ep2015.europython.eu/conference/talks/metrics-driven-development
[timo]: https://ep2015.europython.eu/conference/p/-86
[jenkins]: https://ep2015.europython.eu/conference/talks/the-butler-and-the-snake-continuous-integration-for-python
[elastic]: https://ep2015.europython.eu/conference/talks/python-and-elasticsearch-101
[radoslaw]: https://ep2015.europython.eu/conference/p/radosaw-jankiewicz
[calendario_completo]: https://ep2015.europython.eu/p3/schedule/ep2015/
