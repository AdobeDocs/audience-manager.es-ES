---
description: Preguntas más frecuentes sobre los archivos de Fuente de datos del cliente (CDF).
seo-description: Preguntas más frecuentes sobre los archivos de Fuente de datos del cliente (CDF).
seo-title: Preguntas más frecuentes sobre la fuente de datos del cliente
solution: Audience Manager
title: Preguntas más frecuentes sobre la fuente de datos del cliente
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
feature: Customer Data Feeds
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 0%

---


# Preguntas más frecuentes sobre la fuente de datos del cliente{#customer-data-feed-faq}

Preguntas más frecuentes sobre los archivos de Fuente de datos del cliente (CDF).

## Almacenamiento Amazon S3 {#amazon-s3-storage}

**¿Dónde se almacena mi archivo CDF en[!DNL Amazon]?**

El archivo CDF se almacena en el directorio `aam-cdf` raíz de un [!DNL Amazon S3] servidor. Este bloque predeterminado es administrado por [!DNL Audience Manager]. Consulte también Convenciones [de nombres de archivos de fuentes de datos de clientes](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**¿Es seguro mi cubo de almacenamiento?**

Sí. Los clientes solo tienen acceso a su propio espacio de almacenamiento. Tendrá acceso de sólo lectura a su cubo de almacenamiento. No tendrá acceso de escritura.

<br> 

**¿Puedo personalizar mi contenedor de almacenamiento o almacenar archivos en otro directorio?**

No. Las opciones de personalización y almacenamiento alternativo no están disponibles.

<br> 

**A mi directorio le falta un archivo para una hora en particular. ¿Dónde está?**

Un archivo que falta significa que no [!DNL Audience Manager] pudo procesar los archivos CDF durante esa hora. Esto suele suceder cuando nuestros servidores se quedan atrás en el procesamiento de archivos CDF. En este caso, el archivo no se pierde. Aparecerá en un directorio por hora después de que nuestro sistema tenga la oportunidad de ponerse al día. Consulte también Notificaciones [de procesamiento de archivos de fuentes de datos de](../features/cdf-files.md#cdf-file-processing-notifications)clientes.

<br> 

**¿Cómo puedo saber cuándo mis archivos CDF están listos?**

Consulte Notificaciones [de procesamiento de archivos de fuentes de datos de clientes](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## Tamaños de archivo {#file-sizes}

**¿Qué tipo de tamaños de archivo debo esperar? ¿Qué tamaño tiene un archivo CDF promedio?**

Es difícil estimar el tamaño de los archivos. Y cada archivo puede tener un tamaño diferente. Los tamaños varían de hora a hora y día. Si va a recibir archivos CDF, le resultará útil estar preparado para administrar muchos datos.

<br> 

**¿Cuántos archivos recibiré?**

Una vez más, es difícil estimar esto. Sin embargo, si va a recibir archivos CDF, le resultará útil estar preparado para administrar muchos datos.

<br> 

## Integridad de los datos {#data-integrity}

**¿Cómo puedo comprobar la integridad de los datos cargados en Amazon S3?**

[!DNL Amazon] divide los archivos grandes en partes más pequeñas y los carga [!DNL Amazon S3] mediante la carga de varias partes. A continuación, genera un `ETag` valor para la carga de varias partes. En primer lugar, calcula las sumas de comprobación MD5 individuales de cada artículo cargado y, a continuación, las concatena en una sola cadena. A continuación, calcula la suma de comprobación MD5 de la cadena. La suma de comprobación resultante (la `ETag`) se anexa con un guión y el número total de piezas utilizadas para la carga. Por ejemplo, la `ETag` imagen de un archivo dividido en 5 partes durante la carga podría tener este aspecto: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**¿Cuánto tiempo almacena los archivos CDF?**

Los datos se eliminan pasados 8 (ocho) días.

<br> 

**¿Puedo obtener archivos CDF de forma retroactiva o en días anteriores?**

Sólo puede generar archivos CDF durante los últimos 8 días. No se pueden volver a generar los archivos CDF para intervalos anteriores a los últimos 8 días.

>[!MORELIKETHIS]
>
>* [Fuentes de datos del cliente](../features/cdf-files.md)

