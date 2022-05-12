---
title: "Temperatura del mar y Data Science"
description: "Como manipulas Imagenes-Datos de Ocean color derivados de un Satelite como Sentinel-3 ?"
lead: "La temperatura de la superficie del mar (SST) es una metrica comun en nuestros oceanos e importante de considerar, ya que afecta directamente a todas las especies marinas como pueden ser los corales o influye en la proliferacion de plancton o microorganismos tóxicos. El aumento del nivel del mar, erosion costera y la intensificacion de tormentas son otras problematicas asociadas a las temperaturas marinas."
date: 2020-10-06T08:49:31+00:00
lastmod: 2020-10-06T08:49:31+00:00
draft: false
images: []
menu:
  docs:
    parent: "ds"
weight: 630
toc: true
---

## Resumen

La facilidad para acceder a datos fisicos del oceano ha mejorado notoriamente y en la actualidad son accesibles a tiempo real. 

STT como se le conoce en ingles (Sea Surface Temperature) es quiza una de las métricas con maoyr registro a traves del tiempo. Es posible encontrar datos de temperaturas del mar de la decada de los 80's, incluso en algunos casos de los 70´s.

Los mecanismos actuales son muy confiables y son varios los objetos que se encargan de tomar estos registros. Tanto a nivel satelitel para despues ser validados por boyas u objetos que estan en "contacto" mas estrecho son un ejemplo.

Debido a la gran cantidad de datos espacio-temporal de temperaturas superficiales del mar, la mejor forma de para extraer informacion relevante, visualizarla y hacer pronosticos es mediante ciencia de datos.

El proposito es tomar datos de decadas pasadas y cuantificar cuanto ha aumentado la temperatura en el parque nacional marino Corales del Rosario en Colombia, caracterizado por una cobertura alta de especies coralinas pero que en los ultimos años ha disminuido debido a enfermedades (blanqueamiento) producidas por las altas temperaturas del mar.

De igual forma se haran pronosticos o predicciones a partir de las temperaturas para saber como se comportará esta variable a futuro. 

Todo lo anterior se realizara con métodos de ciencia de datos a traves de Python o librerias(frameworks) de Machine Learning como PyTorch o Prophet de Facebook.

### Pre-requisitos

- Pandas basico
- Fundamento de datos **espacio-temporales**

## Datos

### Google Earth Engine (GEE)

Si está familizarizado con Google Earth, esta herramienta es quizá muchisimo mas funcional, agrupando un catalogo extremadamente completo de imagenes satelitales y datasets.

Para usarlo solo es necesario tener una cuenta de Google y [registrarse.](https://earthengine.google.com)

Una vez inscrito puede revisar los datasets de interes. Cada uno tiene su ejemplo ya sea para trabajar con el editor de codigo de JavaScript o la API de Python. Vale la pena revisar la documentacion y fortalecer conceptos.

El dataset usado para colectar las SST o temperaturas superficales del mar es el de la [NOAA](https://developers.google.com/earth-engine/datasets/catalog/NOAA_CDR_OISST_V2_1)

En este [repositorio de GitHub](https://github.com/grammaloreto/EarthEngine/blob/main/NOAA_oiSST/SeaSurfaceTemperature_IslasRosario.js) se encuentra el codigo necesario para obtener las temperaturas en ciertos puntos especificos del parque nacional natural Corales del Rosario.

Puede cambiar las coordenadas de los puntos de interes y las fechas. De igual forma en el enlace de NOAA es posible encontrar un ejemplo y mas informacion del dataset.

Finalmente al tener los puntos o el area de interes con las temperaturas en las fechas indicadas, es posible descargar los datos en archivos CSV desde el mismo GEE.

### Transformación

En la mayoria de casos los datos con los que trabajamos no se encuentran en la forma en que queremos. Por este motivo es necesario realizar algunos procesos para poder "adecuarlos", "pulirlos" o simplemente transformarlos.

En nuestro caso particular las temperaturas que obtenemos de GEE no se estan en Grados centrigrados (°C), ademas el formato de las fechas del archivo CSV no es reconocido por Python (pandas) por lo que es necesario cambiarlas.

Empecemos con las fechas. En el notebook de trabajo importar una dependencia llamada **datetime** para de esta forma en nuestra base de datos (df) convertir la columna de Time a un tipo reconocible.

```bash
import datetime as dt

df["Time"] = pd.to_datetime(df["Time"])
```

Respecto a las temperaturas (en una columna llamada SST) lo primero que hay que hacer es transformar los datos de objetos a valores numericos.

```bash
df["sst_replace"] = df["sst"].str.replace(",","")
df["sst_replace"] = pd.to_numeric(df["sst_replace"])
```
En la primera linea de codigo se elimina la coma con la que venian las temperaturas de GEE en una columna nueva llamada *"sst_replace"*. En la segunda linea de codigo convertimos estos valores a numericos.

Para terminar, los valores resultantes del proceso anterior se multiplican por 0.01 para obtener temperaturas en grados centigrados (°C) en una columna nueva llamada *"sst"*.

```bash
df["sst"] = df["sst_replace"]*(0.01)
```

### Descripción - Visualización

Para tener una primera fotografia de las base de datos resultante despues de las transformaciones hechas puede usar la funcion *head* que muestra los primeros 5 valores. 

Si quiere tener una radiografía mas completa donde se obtenga la media, desviacion, percentiles, número de valores y otra informacion relevante use la funcion *describe*

```bash
df.head()
df.describe()
```

































