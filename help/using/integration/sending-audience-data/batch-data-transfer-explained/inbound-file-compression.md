---
description: Como opción, puede comprimir archivos de datos al enviarlos a Audience Manager.
seo-description: Como opción, puede comprimir archivos de datos al enviarlos a Audience Manager.
seo-title: Compresión de archivos para archivos de transferencia de datos de entrada
solution: Audience Manager
title: Compresión de archivos para archivos de transferencia de datos de entrada
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
translation-type: tm+mt
source-git-commit: 8d2d841f8e94fd67c2165eb280b85ab18001d77e

---


# Compresión de archivos para archivos de transferencia de datos de entrada{#file-compression-for-inbound-data-transfer-files}

Como opción, puede comprimir archivos de datos al enviarlos a Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager admite la compresión gzip ( `.gz`) para transferencias de datos entrantes y asincrónicas.

Audience Manager también admite archivos sin comprimir.

>[!IMPORTANT]
>
>Actualmente no se admite el cifrado y la compresión en el mismo archivo de datos de entrada. Puede elegir entre [cifrar](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) o comprimir los archivos de entrada.
>
> Sin embargo, tenga en cuenta que el cifrado PGP incluye compresión incorporada.

## Compresión de Amazon S3

Para la entrega a [!DNL Amazon S3], debe utilizar `.gz` o descomprimir archivos. Los archivos comprimidos deben tener 1 GB o menos. Si los archivos son más grandes, consulte el proceso de transferencia y archivo con el Servicio de atención al cliente. Aunque [!DNL Audience Manager] puede manejar archivos muy grandes, puede haber maneras de reducir el tamaño del archivo o hacer que la transferencia de datos sea más eficiente.

>[!IMPORTANT]
>
>El [!DNL FTP] cliente debe utilizar el modo binario para transferir archivos comprimidos o cifrados. Los archivos comprimidos o cifrados enviados en [!DNL ASCII] modo dañarán el archivo de transferencia de datos.

## Prácticas recomendadas

* Los archivos deben [!DNL .gzip] comprimirse (y tener una extensión [!DNL .gz] de archivo).
* El tamaño máximo de archivo comprimido para un archivo `.gz` comprimido es de 1 GB.
* Los tamaños de división óptimos, para el procesamiento más rápido y más temprano de los archivos, son de aproximadamente 1 GB sin comprimir o de 200 a 300 MB comprimidos.
* [!DNL Amazon S3] impone su propio límite de tamaño de archivo de 5 GB en los archivos cargados.
