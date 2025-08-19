---
description: Preguntas frecuentes sobre los archivos de Fuente de datos de clientes (CDF).
seo-description: Frequently asked questions about Customer Data Feed (CDF) files.
seo-title: Customer Data Feed FAQ
solution: Audience Manager
title: Preguntas frecuentes sobre la Fuente de datos de clientes
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
feature: Customer Data Feeds
exl-id: a948accc-6bec-4748-bcc8-2b77acf6b96a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 98%

---

# Preguntas frecuentes sobre la Fuente de datos de clientes{#customer-data-feed-faq}

Preguntas frecuentes sobre los archivos de Fuente de datos de clientes (CDF).

## Amazon almacenamiento S3 {#amazon-s3-storage}

**¿Dónde se almacena mi archivo CDF en [!DNL Amazon]?**

El archivo CDF se almacena en el directorio raíz `aam-cdf` de un servidor de [!DNL Amazon S3]. [!DNL Audience Manager] se encarga de administrar este espacio predeterminado. Consulte también [Convenciones sobre nombres de archivos en fuentes de datos de clientes](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**¿Es seguro mi espacio de almacenamiento?**

Sí. Los clientes solo tienen acceso a su propio espacio de almacenamiento. Tendrá acceso de solo lectura a su espacio de almacenamiento. No tendrá acceso de escritura.

<br> 

**¿Puedo personalizar mi espacio de almacenamiento o almacenar archivos en otro directorio?**

No. Las opciones de personalización y almacenamiento alternativo no están disponibles.

<br> 

**A mi directorio le falta un archivo para una hora en particular. ¿Dónde está?**

La falta de un archivo significa que [!DNL Audience Manager] no pudo procesar los archivos CDF correspondientes a esa hora. Esto suele ocurrir cuando nuestros servidores se retrasan al procesar archivos CDF. En este caso, el archivo no se pierde: una vez que nuestro sistema pueda recuperar el tiempo, el archivo aparecerá en otro directorio clasificado por horas. Consulte también [Notificaciones sobre procesamiento de archivos de fuentes de datos de clientes](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**¿Cómo puedo saber si mis archivos CDF están listos?**

Consulte [Notificaciones sobre procesamiento de archivos de fuentes de datos de clientes](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## Tamaños Archivo {#file-sizes}

**¿Qué tamaños de archivo puedo esperar? ¿Cuál es el tamaño medio de un archivo CDF?**

Es difícil calcular el tamaño de los archivos. Cada archivo puede tener un tamaño diferente. Los tamaños varían cada hora y cada día. Si va a recibir archivos CDF, conviene tener la capacidad de administrar muchos datos.

<br> 

**¿Cuántos archivos recibiré?**

También es difícil calcular esto. Sin embargo, si va a recibir archivos CDF, es conveniente que esté preparado para administrar muchos datos.

<br> 

## Integridad de datos {#data-integrity}

**¿Cómo puedo comprobar la integridad de los datos cargados en Amazon S3?**

[!DNL Amazon] divide los archivos grandes en porciones más pequeñas y los sube a [!DNL Amazon S3] mediante la carga multiparte. Luego genera un valor `ETag` para la carga multiparte. En primer lugar, calcula las sumas de comprobación MD5 de cada parte cargada y, a continuación, las une en una sola cadena. A continuación, calcula la suma de comprobación MD5 de la cadena. La suma de comprobación resultante (la `ETag`) se añade con un guion e indicando el número total de partes utilizadas para la carga. Por ejemplo, la `ETag` de un archivo dividido en cinco partes durante la carga podría aparecer así: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Retención de datos {#data-retension}

**¿Durante cuánto tiempo quedan almacenados los archivos CDF?**

Los datos se eliminan a los ocho días.

<br> 

**¿Puedo obtener archivos CDF de forma retroactiva o de días anteriores?**

Solo puede generar archivos CDF de los últimos ocho días. No se pueden volver a generar los archivos CDF para periodos anteriores a los últimos ocho días.

>[!MORELIKETHIS]
>
>* [Fuentes de datos de clientes](../features/cdf-files.md)
