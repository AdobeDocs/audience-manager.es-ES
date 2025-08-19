---
description: Información acerca de Amazon servicio de almacenamiento simple (Amazon S3).
seo-description: Information about Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3  About
solution: Audience Manager
title: Amazon S3 Acerca de
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Amazon S3: Acerca de{#amazon-s-about}

Información acerca de Amazon servicio de almacenamiento simple (Amazon S3).

Como práctica recomendada, recomendamos utilizar Amazon S3 en lugar de FTP como método para obtener y entregar archivos a los socios. Amazon S3 proporciona una interfaz de servicios web sencilla que se puede utilizar para tienda y recuperar cualquier cantidad de datos, en cualquier momento y desde cualquier lugar de la web.

Entre las ventajas de usar Amazon S3 se incluyen:

* **Escalabilidad:** Amazon S3 proporciona escalabilidad casi ilimitadas.
* **Fiabilidad y disponibilidad:** Amazon S3 proporciona servicios almacenamiento alta durabilidad y alta disponibilidad.
* **Velocidad:** Amazon S3 permite transferencias de datos rápidas.
* **Facilidad de uso:** Amazon S3 es muy fácil de usar y de implementar. Su implementación puede estar en funcionamiento en aproximadamente una hora. La implementación de un directorio FTP lleva mucho más tiempo.
* **Cargas de varias partes:** los archivos grandes se pueden cargar de forma rápida y eficiente como cargas de archivos de varias partes.
* **Seguridad:** Amazon S3 proporciona una seguridad sólida.

   * Todos los directorios son accesibles sólo para el cliente o cliente apropiado.
   * Compatibilidad con el protocolo HTTPS para cargas y descargas. Siempre debe usar HTTPS al transferir archivos en [!DNL Audience Manager].
   * Amazon S3 proporciona cifrado en reposo para cifrar archivos[ de ](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)datos salientes. Utilizamos el [método de cifrado SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) , que permite que las claves de cifrado sean generadas y administradas automáticamente por Amazon S3.

* **Soporte de depuración y copia de seguridad:** Amazon S3 permite [!DNL Audience Manager] conservar copias exactas de los archivos para facilitar la depuración o las retransferencias.

Para obtener más información acerca de Amazon S3, consulte los siguientes recursos:

[Amazon servicio de almacenamiento simple (Amazon S3)](https://aws.amazon.com/s3/) en el sitio web de Amazon Web Services.

[Introducción con Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) en el sitio web de AWS Documentación.
