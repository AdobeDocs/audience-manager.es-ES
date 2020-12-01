---
description: Información sobre Amazon Simple Almacenamiento Service (Amazon S3).
seo-description: Información sobre Amazon Simple Almacenamiento Service (Amazon S3).
seo-title: Amazon S3 Acerca De
solution: Audience Manager
title: Amazon S3 Acerca De
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 1%

---


# Amazon S3: Acerca de{#amazon-s-about}

Información sobre Amazon Simple Almacenamiento Service (Amazon S3).

Como práctica recomendada, recomendamos utilizar Amazon S3 en lugar de FTP como método para obtener archivos de los socios y enviarlos. Amazon S3 proporciona una interfaz de servicios Web sencilla que puede utilizarse para almacenar y recuperar cualquier cantidad de datos, en cualquier momento y desde cualquier lugar de la web.

Las ventajas de utilizar Amazon S3 incluyen:

* **Escalabilidad:** Amazon S3 proporciona una escalabilidad casi ilimitada.
* **Fiabilidad y disponibilidad:** Amazon S3 ofrece servicios de almacenamiento de alta durabilidad y alta disponibilidad.
* **Velocidad:** Amazon S3 permite transferencias de datos rápidas.
* **Facilidad de uso:** Amazon S3 es muy fácil de usar e implementar. La implementación puede estar activa y en ejecución en aproximadamente una hora. Implementar un directorio FTP lleva mucho más tiempo.
* **Cargas de varias partes:los archivos** grandes se pueden cargar rápida y eficazmente a medida que se cargan archivos de varias partes.
* **Seguridad:** Amazon S3 proporciona una seguridad sólida.

   * Todos los directorios son accesibles únicamente para el cliente o cliente correspondiente.
   * Compatibilidad con el protocolo HTTPS para cargas y descargas. Siempre debe utilizar HTTPS cuando transfiera archivos en [!DNL Audience Manager].
   * Amazon S3 proporciona cifrado en reposo para cifrar [archivos de datos salientes](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Utilizamos el método de cifrado [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html), que permite que Amazon S3 genere y administre automáticamente las claves de cifrado.

* **Compatibilidad con Depuración y Backup:** Amazon S3 permite  [!DNL Audience Manager] conservar copias exactas de los archivos para facilitar la depuración o las retransferencias.

Para obtener más información sobre Amazon S3, consulte los siguientes recursos:

[Servicio de Almacenamiento simple de Amazon (Amazon S3)](https://aws.amazon.com/s3/) en el sitio web de servicios web de Amazon.

[Introducción a Amazon Simple Almacenamiento ](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) Services en el sitio web de documentación de AWS.
