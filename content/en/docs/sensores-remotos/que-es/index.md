---
title: "Qué es?"
description: "Base teórica de Sensores Remotos, enfatizando en los Satélites."
lead: "Los Sensores remotos abarcan todo lo referente a la obtención de información de un objeto, fenómeno o entorno sin realizar contacto físico directo (en la mayoría de casos). Es un campo amplio y sus técnicas se utilizan en diferentes áreas como la geografía, meteorología, ecología y el resto de ciencias de la tierra, aunque no se limita sólo a ellas ya que también tiene usos en aplicaciones militares, comerciales, o económicas."
date: 2020-11-12T13:26:54+01:00
lastmod: 2020-11-12T13:26:54+01:00
draft: false
images: []
menu:
  docs:
    parent: "sensores-remotos"
weight: 610
toc: true
---

{{< alert icon="💡" text="También se conoce como Remote Sensing o <a href=\"https://es.wikipedia.org/wiki/Teledetecci%C3%B3n\">Teledetección</a>." />}}

## Tipos

Dependiendo del tipo de información que se desea capturar se utilizan diferentes medios. Para imágenes de muy alta resolución, cubriendo áreas pequeñas se utilizan UAVs (vehículos aéreos no tripulados) o drones. 

Cuando se necesitan imágenes de alta resolución, pero con una mayor cobertura se utilizan aviones y helicópteros. 

De igual forma, cuando hay que cubrir áreas muy amplias se usan satélites, de baja, media o alta órbita terrestre en los que encontramos resoluciones de todo tipo. 

No obstante, cuando hablamos de *Remote Sensing* generalmente nos referimos a la información que se obtiene a través de los diferentes sensores que utilizan los satélites para obtener datos de la tierra. Desde la atmósfera y los océanos a ciudades o zonas terrestres, ya que ofrecen una mayor cobertura espacial.

![](marine-sources.PNG "Sensores Remotos para registrar datos marinos: boyas, vehículos no tripulados, satélites, sondas argos, cables submarinos de fibra óptica, entre otros. (Imagen de la European Marine Board).")

## Datos Satelitales, una revolución cada vez mas accesible 

Pese a que los Sensores Remotos generan muchos tipos de datos, los más comunes son las imágenes satelitales. Sin embargo, estas "fotografías" contienen mucha más información que las que acostumbramos a obtener con cámaras normales, tanto en resolución espacial como espectral. 


### Bandas Espectrales 

Al aumentar el área de cobertura se suele perder resolución espacial, pero hay satélites capaces de obtener resoluciones de 50 cm por píxel. 

En cuanto a la resolución espectral, se podría hablar de imágenes multiespectrales, es decir, que contiene varias bandas con información que el sensor es capaz de captar en un conjunto de longitudes de onda; o hiperespectrales, que contiene bandas con muchas menos longitudes de onda, pero con cientos o miles de estas.


### Sentinel 3, único en su especie 

[Sentinel 3](https://www.esa.int/Space_in_Member_States/Spain/Sentinel-3_Vision_panoramica_para_Copernico) de la ESA (Agencia Espacial Europea) puede ser considerado como uno de los satélites mas aplicables al océano y su estudio, ya que cuenta con un sensor único en su clase denominado OLCI (Ocean and Land Colour Instrument).

>OLCI contiene 21 bandas espectrales (400 - 1.020 nm) con un haz de 1.270 km

Por ejemplo, la banda 1 de OLCI capta longitudes de onda alrededor de los 400 nm (nanometros), encargadas de la corrección de aerosoles y recuperación mejorada de componentes del agua.

La banda 8 se ubica en los 665 nm y es la que toma los componentes de clorofila, sedimentos y substancias de color amarillo. 

Para conseguir información específica se toman conjuntos de bandas (por ejemplo 8, 6 y 4) que contienen números o datos crudos. Mediante procesos establecidos a través de software, ecuaciones (algoritmos) se obtienen los valores deseados, ej: concentración de clorofila.










