---
title: "Tutorial"
description: "Como manipulas Imagenes-Datos de Ocean color derivados de un Satelite como Sentinel-3 ?"
lead: "Como manipular Imagenes-Datos de Ocean color derivados de un Satelite como Sentinel-3 ?"
date: 2020-10-06T08:49:31+00:00
lastmod: 2020-10-06T08:49:31+00:00
draft: false
images: []
menu:
  docs:
    parent: "sensores-remotos"
weight: 630
toc: true
---

Es importante empezar aclarando los niveles de procesamiento en que vienen los datos/productos satelitales. 

Los niveles de procesamiento pueden ser de:

- nivel 0: que abarcan mediciones sin procesar, datos crudos.

- nivel 1: conjuntos de datos con cierto control de calidad.

- nivel 2 o superior: derivados y productos de síntesis de modelos-algoritmos.

*clave:*
**En este tutorial vamos a trabajar con datos de nivel 1 (L1) y mediante SNAP (el Software de la Agencia Espacial Europea ESA para trabajar productos sentinel) procesaremos la imagen para obtener productos de nivel 2 (concetracion de clorofila y materia total suspendida MTS)**

## Copernicus Hub

[Copernicus Hub](https://scihub.copernicus.eu/) es la plataforma para descargar productos de todas las misiones sentinel. En el link OpenHub puedes ingresar y registrarte.

### Descargar un producto Sentinel 3 nivel 1 (L1). 

Especificar en el mapa algun polígono (área) de interés. Especificar un rango de fechas (puede ser aprox por un mes para escoguer un producto sin nubes) y el tipo de instrumento, en este caso OLCI (Imagen 1).

![](hub1.PNG "Imagen 1. Especificar en el mapa un polígono (área) de interés o en el buscador fechas y el tipo de instrumento.")

La carpeta del producto tiene alrededor de 550 y 700 MB. Extraiga todo del archivo zip descargado.




