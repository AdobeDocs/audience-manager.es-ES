---
description: Preguntas más frecuentes sobre los archivos de Fuente de datos de clientes (CDF).
seo-description: Preguntas más frecuentes sobre los archivos de Fuente de datos de clientes (CDF).
seo-title: Preguntas frecuentes sobre fuentes de datos de clientes
solution: Audience Manager
title: Preguntas frecuentes sobre fuentes de datos de clientes
uuid: 7183 b 3 e 2-e 999-4 e 1 e -892 f -2 bab 335 c 13 b 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feed FAQ{#customer-data-feed-faq}

Preguntas más frecuentes sobre los archivos de Fuente de datos de clientes (CDF).

## Amazon S3 Storage {#amazon-s3-storage}

**¿En dónde se almacena el archivo[!DNL Amazon]CDF?**

Your CDF file is stored in the `aam-cdf` root directory on an [!DNL Amazon S3] server. This default bucket is managed by [!DNL Audience Manager]. See also [Customer Data Feed File Naming Conventions](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**¿Es seguro el bloque de almacenamiento?**

Sí. Los clientes solo tienen acceso a su propio espacio de almacenamiento. Tendrá acceso de solo lectura a su bloque de almacenamiento. No tendrá acceso de escritura.

<br> 

**¿Puedo personalizar el bloque de almacenamiento o almacenar archivos en otro directorio?**

No. Las opciones de personalización y almacenamiento alternativo no están disponibles.

<br> 

**A mi directorio le falta un archivo para una hora determinada. Where is it?**

A missing file means [!DNL Audience Manager] was not able to process your CDF files for that hour. Esto suele ocurrir cuando nuestros servidores se retrasan en procesar archivos CDF. En este caso, el archivo no se pierde. Aparecerá en un directorio por hora posterior después de que nuestro sistema tenga la oportunidad de ponerse en contacto. See also, [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**¿Cómo sé cuándo mis archivos CDF están listos?**

See [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## File Sizes {#file-sizes}

**¿Qué tipo de tamaños de archivo espero? How big is an average CDF file?**

Es difícil estimar los tamaños de archivo. Cada archivo puede tener un tamaño distinto. Los tamaños variarán de una hora a otra y día a día. Si va a recibir archivos CDF, ayuda a administrar muchos datos.

<br> 

**¿Cuántos archivos recibirá?**

Nuevamente, es difícil estimar esto. Sin embargo, si va a recibir archivos CDF, ayuda a administrar muchos datos.

<br> 

## Data Integrity {#data-integrity}

**¿Cómo puedo verificar la integridad de los datos cargados en Amazon S 3?**

Files exceeding 16MiB in size are split into 16MiB chunks and uploaded to [!DNL Amazon S3] using multi-part upload.

[!DNL Amazon] genera `ETag` un valor para cargas de varias partes. Primero calcula las sumas de comprobación individuales MD 5 de cada parte cargada y las concatena en una sola cadena. A continuación, calcula la suma de comprobación MD 5 de la cadena. The resulting checksum (the `ETag`) is then appended with a hyphen and the total number of parts used for upload. For instance, the `ETag` for a file that was split into 5 parts during upload could look something like this: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**¿Cuánto tiempo almacena los archivos CDF?**

Los datos se eliminan después de 8 (ocho) días.

<br> 

**¿Puedo obtener archivos CDF de forma retroactiva o de días anteriores?**

Solo puede generar archivos CDF para los últimos 8 días. No se pueden volver a generar los archivos CDF para intervalos anteriores a los últimos 8 días.

>[!MORE_ LIKE_ THIS]
>
>* [Fuentes de datos de clientes](../features/cdf-files.md)

