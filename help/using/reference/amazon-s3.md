---
description: Información sobre Amazon Simple Storage Service (Amazon S3).
seo-description: Información sobre Amazon Simple Storage Service (Amazon S3).
seo-title: Acerca de Amazon S3
solution: Audience Manager
title: Acerca de Amazon S3
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Amazon S3: Acerca de{#amazon-s-about}

Información sobre Amazon Simple Storage Service (Amazon S3).

Se recomienda utilizar Amazon S3 en lugar de FTP como método para obtener archivos de y enviar archivos a los socios. Amazon S3 proporciona una sencilla interfaz de servicios web que puede utilizarse para almacenar y recuperar cualquier cantidad de datos, en cualquier momento y desde cualquier lugar de la web.

Las ventajas de utilizar Amazon S3 incluyen:

* **Escalabilidad:** Amazon S3 proporciona una escalabilidad casi ilimitada.
* **Confiabilidad y Disponibilidad:** Amazon S3 proporciona servicios de almacenamiento de información de alta durabilidad y alta disponibilidad.
* **Velocidad:** Amazon S3 permite transferencias de datos rápidas.
* **Facilidad de uso:** Amazon S3 es muy fácil de usar e implementar. La implementación puede estar en funcionamiento en aproximadamente una hora. La implementación de un directorio FTP tarda mucho más.
* **Cargas de varias partes:** los archivos grandes se pueden cargar de forma rápida y eficaz a medida que se cargan archivos de varias partes.
* **Seguridad:** Amazon S3 proporciona una seguridad sólida.

   * Todos los directorios son accesibles solamente para el cliente o cliente apropiado.
   * Compatibilidad con el protocolo HTTPS para cargas y descargas. Siempre debe utilizar HTTPS cuando transfiera archivos en [!DNL Audience Manager].
   * Amazon S3 proporciona cifrado en reposo para cifrar [archivos de datos salientes](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Utilizamos el método de cifrado [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) , que permite que Amazon S3 genere y administre automáticamente las claves de cifrado.

* **Compatibilidad con Debug y Backup:** Amazon S3 permite conservar  [!DNL Audience Manager] las copias exactas de los archivos para facilitar la depuración o las retransferencias.

Para obtener más información sobre Amazon S3, consulte los siguientes recursos:

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/)  en el sitio web de Amazon Web Services.

[Introducción a Amazon Simple Storage ](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) Service en el sitio web de documentación de AWS.
