---
description: Información sobre Amazon Simple Storage Service (Amazon S3).
seo-description: Information about Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3  About
solution: Audience Manager
title: Acerca de Amazon S3
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Amazon S3: Acerca de{#amazon-s-about}

Información sobre Amazon Simple Storage Service (Amazon S3).

Se recomienda utilizar Amazon S3 en lugar de FTP como método para obtener archivos de los socios y enviarlos. Amazon S3 proporciona una interfaz de servicios web sencilla que se puede utilizar para almacenar y recuperar cualquier cantidad de datos, en cualquier momento y desde cualquier lugar de la web.

Entre las ventajas de utilizar Amazon S3 se incluyen las siguientes:

* **Escalabilidad:** Amazon S3 ofrece una escalabilidad casi ilimitada.
* **Fiabilidad y disponibilidad:** Amazon S3 proporciona servicios de almacenamiento de alta disponibilidad y gran durabilidad.
* **Velocidad:** Amazon S3 permite transferencias de datos rápidas.
* **Facilidad de uso:** Amazon S3 es muy fácil de usar e implementar. Su implementación puede estar en funcionamiento en aproximadamente una hora. La implementación de un directorio FTP tarda mucho más.
* **Cargas de varias partes:** Los archivos grandes se pueden cargar de forma rápida y eficaz como cargas de archivos de varias partes.
* **Seguridad:** Amazon S3 proporciona una seguridad sólida.

   * Todos los directorios solo son accesibles para el cliente o cliente apropiado.
   * Compatibilidad con el protocolo HTTPS para cargas y descargas. Siempre debe usar HTTPS al transferir archivos en [!DNL Audience Manager].
   * Amazon S3 proporciona cifrado en reposo para cifrar [archivos de datos salientes](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Utilizamos el método de cifrado [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html), que permite que Amazon S3 genere y administre automáticamente las claves de cifrado.

* **Compatibilidad con depuración y copia de seguridad:** Amazon S3 permite que [!DNL Audience Manager] conserve copias exactas de los archivos para facilitar la depuración o las retransferencias.

Para obtener más información sobre Amazon S3, consulte los siguientes recursos:

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) en el sitio web de Amazon Web Service.

[Introducción al servicio Amazon Simple Storage](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) en el sitio web de documentación de AWS.
