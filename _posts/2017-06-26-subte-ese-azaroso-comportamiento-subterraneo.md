---
layout: post
title: Subte, ese azaroso comportamiento
categories: opendata
excerpt:
         <h3>Qué dicen los datos del subte en la ciudad de Buenos Aires</h3>
---

Situación: llegás al subterraneo linea D de buenos aires, calculás 15 minutos top para combinar con linea H. Algo pasa, el D demora, tarda mucho entre cada estación, esuchás demora, no sabés por qué?

Por qué siempre tengo la mala suerte (?) de que ande mal el subte?

Para esto se utilizaron datos del 2015 al 2016, que se encuentran en <https://data.buenosaires.gob.ar/dataset/subte-trenes-despachados>

Veamos la cantidad de flotas en servicio:

<div class="embed-responsive-c"><iframe width="900" height="800" frameborder="0" scrolling="no" src="//plot.ly/~pmtempone/14.embed"></iframe></div>

Hasta acá parece lógico que la D y la B sean las que más lineas tengan y que la A y la C la sigan.

Entonces escuchás por el altavoz “la linea D se encuentra con demora por la avería de…” y vos tipo:

<iframe width="560" height="315" src="https://www.youtube.com/embed/pnDjjtgYtMA" frameborder="0" allowfullscreen></iframe>

**Flotas con problemas:**

<div class="embed-responsive-c"><iframe width="900" height="800" frameborder="0" scrolling="no" src="//plot.ly/~pmtempone/20.embed"></iframe></div>

La D tiene más problemas que  la B en varias oportunidades, eso quiere decir que si tiene más problemas y tiene menos trenes en servicio puede andar peor.

Peor aún la linea E!, alguno la tomo?, yo varias veces, es como entrar a un sauna del que no tenes tiempo de ingreso ni de salida. La E tiene más problemas que D a veces, y repasemos cuantos trenes tiene en servicio, apenas más que la H! **¡¡¡DANGER!!!**

Así se puede seguir con varios datos más, frecuencias por linea, dan miedo esos números.

**Demoras:**

Ahora veamos las demoras, la B claramente tiene problemas en algunos días, estas se midieron cada vez que salía un subte y se demoraba en salir en su horario. Si tenemos en cuenta que sale uno y el que sigue tiene que salir a un tiempo pautado y no sale por alguna razón eso genera demoras o se debe a una demora anterior. Por lo que para el usuario eso es una demora.

![alt text](/images/demoras.png)

El promedio de demoras diarias en septiembre del 2016 fue de 23!!. No hace falta ser Tuckey o Laplace para saber que las probabilidades de que tengamos problemas en el subte son altas.

A mayo del 2017 el subte E por suerte cambio...no, mentira, sigue siendo igual de malo, y estos datos hace cuanto se saben?, son públicos y libres.