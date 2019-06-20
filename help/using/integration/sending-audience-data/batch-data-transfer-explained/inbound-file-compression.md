---
description: Como opción, puede comprimir archivos de datos al enviarlos a Audience Manager.
seo-description: Como opción, puede comprimir archivos de datos al enviarlos a Audience Manager.
seo-title: Compresión de archivos para archivos de transferencia de datos entrantes
solution: Audience Manager
title: Compresión de archivos para archivos de transferencia de datos entrantes
uuid: 2 a 68 f 69 c -60 b 0-4002-863 b -302 d 2320 e 356
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File Compression for Inbound Data Transfer Files{#file-compression-for-inbound-data-transfer-files}

Como opción, puede comprimir archivos de datos al enviarlos a Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager supports gzip ( `.gz`) compression for inbound, asynchronous data transfers.

Audience Manager también admite archivos no comprimidos.

>[!IMPORTANT]
>
>Actualmente no admitimos cifrado ni compresión en el mismo archivo de datos de entrada. You can select to either [encrypt](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) or compress your inbound files.

## Compresión Amazon S 3

For delivery to [!DNL Amazon S3], you must use `.gz` or uncompressed files. Los archivos comprimidos deben ser de 1 GB o menos. Si los archivos son más grandes, analice el archivo y transfiera el proceso con el Servicio de atención al cliente. Although [!DNL Audience Manager] can handle very large files, there may be ways to reduce the file size or make transfer of data more efficient.

>[!IMPORTANT]
>
>Your [!DNL FTP] client must use binary mode to transfer compressed or encrypted files. Compressed or encrypted files sent in [!DNL ASCII] mode will corrupt the data transfer file.

## Prácticas recomendadas

* Files should be [!DNL .gzip] compressed (and have a [!DNL .gz] file extension.)
* The maximum compressed file size for a `.gz` compressed file is 1 GB.
* Los tamaños de división óptimos, para el procesamiento rápido/inicial de los archivos, tienen aproximadamente 1 GB sin comprimir o 200-300 MB comprimidos.
* [!DNL Amazon S3] impone su propio límite de tamaño de archivo 5 GB en los archivos cargados.