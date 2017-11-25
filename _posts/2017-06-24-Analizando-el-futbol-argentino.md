---
layout: post
title: Analizando el fútbol argentino
date:   2017-06-23 19:16:00 -0300
categories: futbol, pca, clustering, analytics
excerpt:
         <h3>Analizando el fútbol argentino</h3>
         <p>A continaución el desarrollo</p>
---


![alt text](/images/tapa_informe.jpg)

Recientemente estuve realizando para una materia de la maestría en datamining un análisis de un set de datos de fútbol (provisto por [DataFactory](http://www.datafactory.la/) con fines académicos), más precisamente de la primera división del fútbol argentino durante el período 2013–2016. Se aplicaron técnicas de [clustering](https://es.wikipedia.org/wiki/An%C3%A1lisis_de_grupos), [PCA](https://es.wikipedia.org/wiki/An%C3%A1lisis_de_componentes_principales) y visualizaciones.

A continuación pongo algunos de los análisis que se realizaron:

## Foco en los jugadores

**Exploración de los datos sobre los jugadores**

Se analizan las características de 1353 jugadores para visualizar patrones.

![alt text](/images/grafico1.png)

Se puede observar que hay un grupo que tiene niveles más altos de atajadas, lo que identifica al grupo correspondiente a los arqueros.
Para poder identificar a futuro como ponderar a los jugadores suplentes en el rendimiento de los equipos, se generaron algunas visualizaciones para entender su participación en minutos jugados de titulares y suplentes.

![Minutos jugados por titularidad](/images/grafico2.png)

![Minutos jugados por titularidad](/images/grafico3.png)

No es lo mismo ponderar a todos los jugadores suplentes, por eso se analiza la participación de ellos según su posición.
Para los fines de este trabajo se reemplazarán las variables originales por una proporción de los minutos disputados en cada partidos, de esta manera se igualan los valores de participación de cada jugador por cada minuto disputado.

![Rol del jugador por titularidad](/images/grafico4.png)

Acá se empieza a ver datos interesantes, los entrenadores utilizan como suplentes a los delanteros en una proporción grande a los que son titulares.
Es decir, los delanteros suplentes tienen más posibilidades de ingresar a un partido que los defensores. Esto plantea también que los técnicos realizan
muy pocos cambios del tipo defensivos.

**PCA sobre los jugadores**

![alt text](/images/grafico5.png)

![alt text](/images/grafico6_pca2.png)

Se puede ver cómo en cada cuadrante se visualizan las características más destacadas de cada posición. En el cuadrante superior izquierdo se observan
las características que más se ven en defensores. En el inferior izquierdo se ven las características de los arqueros, las atajadas.
Los delanteros están en todo el eje inferior a la dimensión 2 que es donde se destacan tantos los tiros que les atajaron como los goles convertidos, los offsides (posiciones fuera de juego) que sufrieron por jugar en posiciones más adelantadas.
Por último en el cuadrante superior derecho están destacadas características de los medio campistas, los pases y las faltas tanto recibidas como realizadas.
Al estar en la zona de mayor población de jugadores se realizan la mayor scantidad de faltas.

**Clustering**

![alt text](/images/grafico9_pca_clust.png)

![alt text](/images/grafico8_hclust.png)

Lo que se ve en los distintos clusters, es que se separa a los arqueros de los demás jugadores en el “Cluster 1”. Y que los “Cluster 2” y “Cluster 3”
marcan una diferencia entre jugadores ofensivos y defensivos. Esta diferenciación es interesante ya que no siempre es fácil saber que jugadores en los roles del mediocampo tienen más orientación defensiva que ofensiva.

En la figura siguiente combinamos las variables con los clusters para reforzar
esta idea:


![alt text](/images/grafico12_biplot_clusters.png)

## Foco en los equipos

**¿Qué equipos son parecidos entre sí?**

Tenemos 33 equipos en este análisis; podemos decir que Lanús (con Almirón como DT) y San Lorenzo (con Aguirre como DT) tienen ideas similares, pero cuando comparamos varias temporadas para ver si en el tiempo se sostienen ideas, ¿podemos decir con tanta seguridad qué equipos presentan ideas parecidas?
Para esto se aplicó la técnica "caras de Chernoff", para ver de una manera más amigable que equipos se parecen entre sí y como se diferencian.

![alt text](/images/grafico21_chernoff.png)

Lo primero que resulta interesante observar es que Atlético de Tucumán es bastante particular, porque no es fácil encontrarle similitudes con el resto de los planteles. Si nos ponemos a pensar cuál fue la consecuencia de este comportamiento, la encontramos en que es la primera vez en la historia que juega la copa Libertadores. ¿Un equipo con pocos recursos necesita encontrar combinaciones distintas para poder lograr esos hitos? Es una pregunta interesante de plantear.

Entre los equipos que no tuvieron buenos rendimientos pareciera haber bastante similitudes; Sarmiento, Temperley, All Boys, Argentinos Juniors, Olimpo, Crucero del Norte. Equipos que descendieron o tuvieron muy malos torneos.

Podríamos continuar con este juego de parecidos, la realidad es que esto sirve para ver rápidamente si nuestro objetivo es parecernos al equipo campeón, que tan distintos somos, ¿somos parecidos River Plate o a Sarmiento?

##Bonus Track: Marcelo Meli como contratación

Como bonus de este informe realizaré un análisis muy individual: el objetivo es ver si Racing, que necesitaba un jugador que se desempeñe como volante por derecha terminó incorporando a Marcelo Meli, tiene más parecido con mediocampistas del tipo defensivo o con el "Huevo" Acuña, que es un jugador con mucha llegada ofensiva y aporte en lo defensivo.

Para esto se compara a Meli con Aued, Cerro, Acuña, González (alias "Pulpito"), Gastón Díaz y Videla. La primera comparación se realizó con una gráfico de radar.

![alt text](/images/grafico22_radarchart_racing.png)

Lo primero que se ve a simple vista es que Meli es muy parecido a González, lo que rescata el diario Olé de donde se tiene pensado ponerlo, ["¿Dónde jugaría Meli? Cocca lo piensa como volante por derecha en el 4–4–2 o interno en el 4–3–3 , función que más ha cumplido en su carrera."](http://www.ole.com.ar/racing/juego-Cocca_0_1724227597.html), esto podría parecer una contradicción, se busca un jugador por afuera pero no tiene características de un jugador que llegue y brinde asistencias, tampoco que llegue al gol.
Tiene características muy parecidas a Aued y a González, por lo que la posición de externo no parecería que le siente natural, ya que un jugador que tendría que tener características similares pero cumplir el rol por la derecha del campo es Acuña y no se parece a este jugador.


![alt text](/images/grafico23_chernoff_meli.png)

Chernoff parece estar de acuerdo con las primeras apreciaciones, lo que queda entonces por ver antes que comience el torneo es, ¿la capacidad del técnico para pensar que un jugador puede cumplir funciones que no viene realizando es superior a lo que los datos dicen acerca del jugador?

Este trabajo se detalla más en el siguiente link: <https://www.slideshare.net/Belsaga/analisis-de-equipos-y-jugadores-del-futbol-argentino>


