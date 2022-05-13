---
title: "En la práctica con Hugging Face"
description: "Como manipulas Imagenes-Datos de Ocean color derivados de un Satelite como Sentinel-3 ?"
lead: "Manos a la obra con 🤗Hugging Face🤗! una herramienta de 'transformadores' muy poderasa que nos ayuda a convertir texto (letras-palabras) a datos númericos y poder analizarlo de diferentes formas."
date: 2020-10-06T08:49:31+00:00
lastmod: 2020-10-06T08:49:31+00:00
draft: false
images: []
menu:
  docs:
    parent: "reportes"
weight: 630
toc: true
---

## Resumen

El proposito es analizar los sentimientos de comentarios escritos por usuarios en una plataforma popular de viajes sobre su experiencia en playas turísticas. 

El proceso consta basicamente de 3 pasos:

- Extracción de comentarios en la plataforma de viajes escogida. A este proceso se le denomina "web scraping".

- Organizar los comentarios en una base de datos de facil manipulacion.

- Tokenización de texto con Hugging Face🤗. Se usa un Modelo BERT multilingue por lo que es posible trabajar con otros idiomas diferentes al español. El modelo ha sido entrenado en inglés, aleman, holandes o frances, entre otros.


## Pre-requisitos

Para una mejor comprension del Análisis de Sentimientos con Hugging Face y BERT, ayudaría tener nociones basicas de **Python** y de como trabajar en un Jupyter Notebook.

Este [👉artículo.](https://grammaloreto.netlify.app/analisis-sent/) ilustra lo que vamos a hacer.

```bash
python --version # tienes python instalado?
```

## 1. Web Scraping de comentarios
Para extraer los comentarios de las playas en la plataforma de viajes escogida, se va a usar una libreria de **python** llamada *Beatiful Soup*. 

Como se mencionó en los pre-requisitos se trabajará en un **Jupyter notebook**, el cual es un entorno informático que soporta python para correr codigo por módulos. 

Estan son las librerias para el "web scraping":

```bash
from bs4 import BeautifulSoup
import requests
import re
```

**Request** es una librería que permite hacer solicitudes HTTP para interactuar y "consumir" datos de la web. En el parentesis va una URL o direccion del sitio web donde están los comentarios.

```bash
data = requests.get("https://www.tripadvisor.co/Attraction_Review-g297482-d1024602-Reviews-Johnny_Cay-San_Andres_Island_San_Andres_and_Providencia_Department.html")
```

A continuacion entra a trabajar **beautiful soup** tomando el codigo *html* de la web escogida y atrapando sólo las etiquetas que se le indican. 

```bash
soup = BeautifulSoup(data.text, 'html.parser')
for div in soup.find_all("div"):
    regex = re.compile('.*pIRBV.*')
    results = soup.find_all('div',{'class':regex})
    reviews = [result.text for result in results]
```

Despues de estas pocas lineas de codigo son extraidos todos los comentarios de la url indicada. Para confirmar, llame a los reviews y aparecerán.

```bash
reviews
```

## 2. Base de Datos (df)

Teniendo todos los comentarios en la variable *reviews* lo siguiente será agrupar/ordenar los comentarios en una Base de Datos (data frame).

Para este paso se usan 2 de las librerias mas populares de **python:** **pandas** y **numpy**.

```bash
import pandas as pd
import numpy as np
```

Con una simple linea de código quedarán todos los *reviews* en un df (data frame o base de datos).

```bash
df = pd.DataFrame(np.array(reviews), columns=['review'])
```

## 3. Tokenización de Palabras

Para tokenizar o asignarle un valor numerico a cada palabra que conforma un comentario es que utilizamos Hugging Face y los transformadores.

Para poder usar esta biblioteca es necesario instalarla primero en el notebook o en el ambiente con el que se está trabajando.

```bash
!pip install transformers 
```

Una vez instalado Hugging Face (transformadores) se pueden llamar los módulos de "tokenización".

>De igual forma se usa PyTorch, para una mejor experiencia con los transformadores.

```bash
from transformers import AutoTokenizer, AutoModelForSequenceClassification
import torch
```
### Modelo Clasificación de Texto

Hay modelos en muchos idiomas, entrenados con distintos tipos de datos. [Modelos de Clasificacion de Texto en Hugging Face.](https://huggingface.co/models?pipeline_tag=text-classification&sort=downloads)

El Modelo escogido es un BERT multilingue de nlptown entrenado con comentarios calificados de 1-5. Por este motivo nuestro analisis de sentimientos de playas tendrá una calificacion igual, de 1-5, donde 1-2 son malas experiencias, 3 neutral y 4-5 buenas experiencias.

De esta forma se incorpora el modelo BERT de nlptown a nuestro análisis:

```bash
tokenizer = AutoTokenizer.from_pretrained("nlptown/bert-base-multilingual-uncased-sentiment")

model = AutoModelForSequenceClassification.from_pretrained("nlptown/bert-base-multilingual-uncased-sentiment")
```

Ahora sí es momento de tokenizar los *reviews*:

```bash
result = model(tokens)
def sentiment_score(review):
    tokens = tokenizer.encode(review, return_tensors='pt')
    result = model(tokens)
    return int(torch.argmax(result.logits))+1
```

Al correr la función anterior se podrá usar sobre nuestra base de datos! 

Lo siguiente será adicionar una columna nueva a la df llamada **sentiment** que es donde irá la calificacion (1-5) de cada playa. Esta columan aplica el codigo anterior (sentiment-score) en base a una función lambda especificada.

```bash
df['sentiment'] = df['review'].apply(lambda x: sentiment_score(x[:512]))
```

El resultado final es una base de datos (df) con 2 columnas: la primera con los reviews o comentarios extraidos y la segunda llamada 'sentiment' con la calificación de 1 a 5 o "sentimiento" de los usuario sobre las playas.

Para una mejor comprensión de los resultados obtenidos en la columna 'sentiment' se puede realizar estadistica descriptiva basica (histogramas, medias, promedios etc) con *pandas* o *numpy* y así tener un mejor panorama de las opiniones y sentimientos asociados a las playas.

Si desea profundizar con algunos analisis de sentimientos hechos previamente de playas Latinoamericas, puede revisar este [repositorio de GitHub.](https://github.com/grammaloreto/BeachSentimentAnalysis)






































