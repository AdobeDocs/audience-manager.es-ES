---
description: Como opción, puede comprimir los archivos de datos al enviarlos a Audience Manager.
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: Archivo Compresión para Archivos de transferencia de datos de entrada
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Archivo Compresión para Archivos de transferencia de datos de entrada{#file-compression-for-inbound-data-transfer-files}

Puede comprimir los archivos de datos al enviarlos a Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager admite la compresión gzip (`.gz`) para transferencias de datos entrantes y asincrónicas.

Audience Manager también admite archivos sin comprimir.

>[!IMPORTANT]
>
>No se admite el cifrado en archivos entrantes comprimidos con gzip (`.gz`).
>
>Para cifrar y comprimir archivos entrantes, utilice [el cifrado](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) PGP. [!DNL PGP] El cifrado incluye la compresión de archivos.

## Amazon Compresión de S3

Para envío a [!DNL Amazon S3], debe utilizar `.gz` archivos o descomprimir. Los archivos comprimidos deben tener 1 GB o menos. Si los archivos son más grandes, hable sobre el proceso de archivo y transferencia con Atención al cliente. Aunque [!DNL Audience Manager] puede manejar archivos muy grandes, puede haber formas de reducir el tamaño del archivo o hacer que la transferencia de datos sea más eficiente.

>[!IMPORTANT]
>
>Su [!DNL FTP] cliente debe utilizar el modo binario para transferir archivos comprimidos o encriptados. Los archivos comprimidos o cifrados enviados en [!DNL ASCII] modo dañarán el archivo de transferencia de datos.

## Prácticas recomendadas

* Archivos debe estar [!DNL .gzip] comprimido (y tener una extensión de [!DNL .gz] archivo).
* El tamaño máximo de archivo comprimido para un `.gz` archivo comprimido es de 1 GB.
* Los tamaños de división óptimos, para el procesamiento más rápido / temprano de sus archivos, son aproximadamente 1 GB sin comprimir o 200-300 MB comprimidos.
* [!DNL Amazon S3] impone su propio límite de tamaño de archivo de 5 GB en los archivos cargados.
