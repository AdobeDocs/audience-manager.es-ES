---
description: Como opción, puede comprimir archivos de datos al enviarlos al Audience Manager.
seo-description: Como opción, puede comprimir archivos de datos al enviarlos al Audience Manager.
seo-title: Compresión de archivos de transferencia de datos entrantes
solution: Audience Manager
title: Compresión de archivos de transferencia de datos entrantes
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Transferencias de datos de entrada
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 11%

---

# Compresión de archivos de transferencia de datos entrantes{#file-compression-for-inbound-data-transfer-files}

Puede comprimir los archivos de datos al enviarlos al Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager admite la compresión gzip (`.gz`) para transferencias de datos entrantes y asincrónicas.

Audience Manager también admite archivos sin comprimir.

>[!IMPORTANT]
>
>No se admite el cifrado en archivos entrantes comprimidos con gzip (`.gz`).
>
>Para cifrar y comprimir archivos entrantes, utilice [PGP encryption](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] el cifrado incluye la compresión de archivos.

## Compresión de Amazon S3

Para el envío a [!DNL Amazon S3], debe utilizar `.gz` o archivos sin comprimir. Los archivos comprimidos deben tener 1 GB o menos. Si los archivos son más grandes, hable del proceso de archivo y transferencia con el Servicio de atención al cliente. Aunque [!DNL Audience Manager] puede manejar archivos muy grandes, puede haber maneras de reducir el tamaño del archivo o hacer que la transferencia de datos sea más eficiente.

>[!IMPORTANT]
>
>El cliente [!DNL FTP] debe utilizar el modo binario para transferir archivos comprimidos o cifrados. Los archivos comprimidos o cifrados enviados en modo [!DNL ASCII] dañarán el archivo de transferencia de datos.

## Prácticas recomendadas

* Los archivos deben estar [!DNL .gzip] comprimidos (y tener una [!DNL .gz] extensión de archivo).
* El tamaño máximo del archivo comprimido para un archivo comprimido `.gz` es de 1 GB.
* El tamaño de división óptimo, para el procesamiento más rápido/temprano de sus archivos, es aproximadamente de 1 GB sin comprimir o de 200 a 300 MB comprimidos.
* [!DNL Amazon S3] impone su propio límite de tamaño de archivo de 5 GB en los archivos cargados.
