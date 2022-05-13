---
title: "Análisis de Sentimientos"
description: "Solutions to common problems."
lead: "Los análisis de sentimientos son la aplicación más común de todas las herramientas de PLN para examinar actitudes y emociones de los visitantes hacia cierto punto de la playa, algun servicio o el tipo de experiencia (positiva-negativa)."
date: 2020-11-12T15:22:20+01:00
lastmod: 2020-11-12T15:22:20+01:00
draft: false
images: []
menu: 
  docs:
    parent: "reportes"
weight: 620
toc: true
---

## Fundamento General

De forma general, los análisis de sentimientos intentan determinar la **actitud** de un interlocutor o usuario con respecto a algún tema, lugar, servicio, persona, experiencia, documento. La **actitud** puede ser su juicio o evaluación, estado afectivo (estado emocional del autor al momento de escribir), o la intención comunicativa emocional (el efecto emocional que el autor intenta causar a los lectores).

Hay diferentes "sabores" de análisis de sentimientos, pero una de las técnicas más utilizadas clasifica los datos (comentarios) en positivos, negativos y neutrales.

## Al alcance de Cualquiera

En el pasado, los análisis de sentimientos solían estar limitados a investigadores, ingenieros de aprendizaje automático o científicos de datos con experiencia en procesamiento de lenguaje natural (PLN). Sin embargo en los ultimos años se han creado herramientas increíbles para democratizar su acceso, hoy en día se puede usar con unas pocas líneas de código y sin ninguna experiencia previa.

## Aplicaciones

Los análisis de sentimientos se utilizan en una amplia variedad de escenarios posibles, los 3 principales serian para:

- Analizar las menciones en las redes sociales para comprender cómo las personas hablan de alguna marca-lugar-servico frente a sus competidores.

- Analizar los comentarios de las encuestas y las revisiones de productos para obtener rápidamente información sobre lo que a sus clientes les gusta y no.

- Analizar los textos escritos entrantes en tiempo real para detectar clientes-usuarios enojados y actuar en consecuencia para evitar mala imagen o deserción.

## Hugging Face y BERT

Hugging Face y Bert son 2 de las muchas tecnologías pioneras y que hay que tener en cuenta en este dominio. 

El primero es una compañía con distintas librerías aplicadas a varios campos de PLN. Ofrecen modelos basados en transformadores a través de PyTorch y Tensorflow. El objetivo de la empresa es promover el PLN y democratizarlo para que todo el mundo lo pueda usar.

Por otro lado, tenemos a BERT (Bidirectional Encoder Representations from Transformers), desarrollado por Google y usado en el complejo entramado de redes neuranales para procesar e interpretar todo tipo de lenguajes en dicho motor. BERT es un modelo extremadamente efectivo por el poderoso entrenamiento que ha tenido año tras año con inmensa cantidad de datos en todos los idiomas.

A parte de BERT, Hugging Face proporciona una serie de modelos populares por su eficacia para distintas tareas de PLN. Entre los mas destacados encontramos a RoBERTa y sus distintas presentaciones.

## Analisis de Sentimientos para Playas

Los investigadores han comenzado a aprovechar los datos de las redes sociales para evaluar cómo las personas interactúan con los paisajes costeros, aunque la mayoría de estudios se encuentran en fase piloto y se realizan a escala local. 

Los resultados destacan y son alentadores ya pueden usarse para complementar otros enfoques para el monitoreo a gran escala de las costas, incluida la identificación de áreas prioritarias para la gestión activa al utilizar un enfoque rápido, remoto y de bajo costo.

### Scraping de comentarios

Sin la materia prima no se puede hacer nada, es por eso primordial tener presente distintas técnicas para poder tomar gran cantidad de datos (comentarios). Para lograr el cometido es necesario saber de alguna librería (de python u otro lenguaje de programación) para extraer la informacion. Seria muy dificil copiar y pegar reviews.

Beautiful Soup es una biblioteca de Python ampliamente usada y conocida. A la par tambien se encuentra Selenium que es otro de los módulos con propiedades similares. 

En lo particular Beautiful Soup es el escogido en el tutorial de esta seccion y podras ver como puedes implementarlo.

### Escogencia de Modelo

Este paso es crucial ya que determina que tan acertado o confiable es un analisis. Existen diversos modelos para distintas tareas de PLN: traduccion, generacion de texto, resumenes, respuesta de preguntas o clasificacion de texto (que seria el objeto del tutorial).

Al momento de la escogencia del modelo es importante tener claras ciertas consideraciones: en que idioma van a estar los comentarios a analizar, de que plataforma se van a extraer, si van a ser evaluados como positivos-negativos-neutrales, si van a ser resultados numericos, como fue entrenado el modelo, con que tipo de datos.

### Caso particular tutorial

Se escoge un model BERT multilingue (Ingles, holandes, aleman, frances, italiano, español) entrenado con comentarios de 1 a 5. 

Aunque en el ultimo tiempo estan apareciendo mas modelos en español todavia son pocos a comparacion de los existentes en otros idiomas. 

Con los analisis de sentimientos y demas trabajos de Procesamiento de Lenguaje Natural (PLN) el proposito para un futuro es tener un modelo propio dedicado exclusivamente a playas y en español.

Si de alguna forma quieres colaborar AQUI 


















