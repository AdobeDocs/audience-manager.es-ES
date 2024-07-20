---
description: Como opción, puede comprimir archivos de datos al enviarlos al Audience Manager.
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: Compresión de archivos de transferencia de datos entrantes
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Compresión de archivos de transferencia de datos entrantes{#file-compression-for-inbound-data-transfer-files}

Puede comprimir los archivos de datos al enviarlos al Audience Manager.

<!-- inbound-file-compression.xml -->

El Audience Manager admite la compresión gzip (`.gz`) para transferencias de datos entrantes y asincrónicas.

Audience Manager también admite archivos sin comprimir.

>[!IMPORTANT]
>
>No se admite el cifrado en archivos de entrada comprimidos con gzip (`.gz`).
>
>Para cifrar y comprimir archivos entrantes, use [cifrado PGP](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). El cifrado [!DNL PGP] incluye la compresión de archivos.

## Compresión de Amazon S3

Para la entrega a [!DNL Amazon S3], debe utilizar `.gz` o archivos sin comprimir. Los archivos comprimidos deben tener 1 GB o menos. Si los archivos son más grandes, comente el proceso de archivo y transferencia con el Servicio de atención al cliente. Aunque [!DNL Audience Manager] puede administrar archivos muy grandes, puede haber maneras de reducir el tamaño del archivo o hacer que la transferencia de datos sea más eficaz.

>[!IMPORTANT]
>
>El cliente [!DNL FTP] debe usar el modo binario para transferir archivos comprimidos o cifrados. Los archivos comprimidos o cifrados enviados en modo [!DNL ASCII] dañarán el archivo de transferencia de datos.

## Prácticas recomendadas

* Los archivos deben estar comprimidos [!DNL .gzip] (y tener la extensión de archivo [!DNL .gz]).
* El tamaño máximo de archivo comprimido para un archivo comprimido de `.gz` es 1 GB.
* Los tamaños de división óptimos, para el procesamiento más rápido/más temprano de sus archivos, son aproximadamente 1 GB sin comprimir o 200-300 MB comprimidos.
* [!DNL Amazon S3] impone su propio límite de tamaño de archivo de 5 GB en los archivos cargados.
