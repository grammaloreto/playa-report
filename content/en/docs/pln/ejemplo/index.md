---
title: "Análisis de Sentimientos"
description: "Solutions to common problems."
lead: "Los análisis de sentimientos son la aplicación más común de todas las herramientas de PLN para examinar actitudes y emociones de los visitantes hacia cierto punto de la playa, algún servicio o el tipo de experiencia (positiva-negativa)."
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

## Fundamento

De forma general, los análisis de sentimientos intentan determinar la actitud de un interlocutor o usuario con respecto a algún tema, lugar, servicio, persona, experiencia, documento. La actitud puede ser su juicio o evaluación, estado afectivo (estado emocional del autor al momento de escribir), o la intención comunicativa emocional (el efecto emocional que el autor intenta causar a los lectores).

Hay diferentes "sabores" de análisis de sentimientos. Una de las técnicas más utilizadas clasifica los datos (comentarios) en positivos, negativos y neutrales.

## Al alcance de todos

En el pasado, los análisis de sentimientos solían estar limitados a investigadores, ingenieros de aprendizaje automático o científicos de datos con experiencia en procesamiento de lenguaje natural (PLN). Sin embargo, en los últimos años se han creado herramientas increíbles para democratizar su acceso, hoy en día se puede usar con unas pocas líneas de código y sin ninguna experiencia previa.

## Aplicaciones

Los análisis de sentimientos se utilizan en una amplia variedad de escenarios posibles, los 3 principales son para:

- Analizar las menciones en las redes sociales para comprender cómo las personas hablan de alguna marca-lugar-servicio frente a sus competidores.

- Analizar los comentarios de encuestas y las revisiones de productos, para obtener rápidamente información sobre lo que a sus clientes les gusta y no.

- Analizar los textos escritos entrantes en tiempo real para detectar clientes-usuarios enojados y actuar en consecuencia para evitar mala imagen o deserción.

## Hugging Face y BERT

Hugging Face y Bert son 2 de las muchas tecnologías pioneras y que hay que tener en cuenta en este dominio. 

La primera es una compañía con distintas librerías aplicadas a varios campos de PLN. Ofrecen modelos basados en transformadores a través de PyTorch y Tensorflow. El objetivo de la empresa es promover el PLN y democratizarlo para que todo el mundo lo pueda usar.

Por otro lado, está BERT (Bidirectional Encoder Representations from Transformers), desarrollado por Google y usado en el complejo entramado de redes neuranales para procesar e interpretar todo tipo de lenguajes en dicho motor. BERT es un modelo extremadamente efectivo por el poderoso entrenamiento que ha tenido año tras año con inmensa cantidad de datos en todos los idiomas.

A parte de BERT, Hugging Face proporciona otros modelos populares por su eficacia para distintas tareas de PLN. Entre los mas destacados se encuentra RoBERTa y sus distintas versiones.

## Análisis de Sentimientos para Playas

Algunos investigadores han comenzado a aprovechar los datos de las redes sociales para evaluar cómo las personas interactúan con los paisajes costeros, aunque la mayoría de estudios se encuentran en fase piloto y se realizan a escala local. 

Los resultados son alentadores ya que pueden usarse para complementar otros enfoques para el monitoreo a gran escala de las costas. Destaca la identificación de áreas prioritarias para la gestión activa, al utilizar un enfoque rápido, remoto y de bajo costo.

### "Scraping" de comentarios

Sin la materia prima no se puede hacer nada, es por eso primordial tener presente distintas técnicas para poder tomar gran cantidad de datos (comentarios). Para lograr el cometido es necesario saber de alguna herramienta para extraer dicha información. Sería muy costoso y demorado copiar y pegar reviews.

*Beautiful Soup* es una dependencia de Python ampliamente usada y conocida. A la par también se encuentra *Selenium* que es otro módulo con propiedades similares, de gran utilidad en este tipo de tareas.


### Escogencia de Modelo

Este paso es crucial ya que determina que tan acertado o confiable es un análisis. Existen diversos modelos para distintas tareas de PLN: traducción, generación de texto, resúmenes, respuesta de preguntas o clasificación de texto (que es el objeto del tutorial presentado).

Al momento de la escogencia del modelo es importante tener claras ciertas consideraciones: en que idioma van a estar los comentarios a analizar, de que plataforma se van a extraer, si van a ser evaluados como positivos-negativos-neutrales, si van a ser resultados numéricos, como fue entrenado el modelo, con qué tipo de datos.

### Hacen falta modelos en Español 

Aunque en el último tiempo están apareciendo mas modelos en español, todavía son pocos a comparación de los existentes en otros idiomas. 

Con los análisis de sentimientos y demás trabajos de Procesamiento de Lenguaje Natural (PLN) el proposito para un futuro es tener un modelo propio dedicado exclusivamente a playas y en español.

Si de alguna forma quieres colaborar, contacto [Aquí.](https://www.grammaloreto.co/es/contacto/) 


















