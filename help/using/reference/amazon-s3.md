---
description: Información sobre Amazon Simple Storage Service (Amazon S 3).
seo-description: Información sobre Amazon Simple Storage Service (Amazon S 3).
seo-title: Amazon S 3 Acerca de
solution: Audience Manager
title: Amazon S 3 Acerca de
uuid: 8197 ecdf-df 8 f -488 d-bbc 0-d 8 d 4205 b 42 b 4
translation-type: tm+mt
source-git-commit: 212ec8641068a9ed4c620987bb18586ee8c7d519

---


# Amazon S3: About{#amazon-s-about}

Información sobre Amazon Simple Storage Service (Amazon S 3).

Se recomienda utilizar Amazon S 3 en lugar de FTP como método para obtener archivos y entregar archivos a socios. Amazon S 3 proporciona una interfaz de servicios Web sencilla que puede utilizarse para almacenar y recuperar cualquier cantidad de datos, en cualquier momento, desde cualquier lugar de la Web.

Entre los beneficios de utilizar Amazon S 3 se incluyen:

* **Escalabilidad:** Amazon S 3 proporciona escalabilidad casi ilimitada.
* **Confiabilidad y disponibilidad:** Amazon S 3 proporciona servicios de almacenamiento alta y de alta duración.
* **Velocidad:** Amazon S 3 permite transferencias rápidas de datos.
* **Facilidad de uso:** Amazon S 3 es muy fácil de utilizar y de implementar. Su implementación puede estar en funcionamiento en unas horas. La implementación de un directorio FTP tarda mucho más.
* **Cargas de varias partes:** Los archivos grandes se pueden cargar rápida y eficazmente como cargas de archivos de varias partes.
* **Seguridad:** Amazon S 3 proporciona seguridad sólida.

   * Todos los directorios son accesibles sólo para el cliente o cliente apropiado.
   * Compatibilidad con el protocolo HTTPS para cargas y descargas. You should always use HTTPS when transferring files in [!DNL Audience Manager].
   * Amazon S3 provides encryption-at-rest for encrypting [outbound data files](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). We use the [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) encryption method, which allows encryption keys to be automatically generated and managed by Amazon S3.

* **Depuración de depuración y respaldo:** Amazon S 3 permite [!DNL Audience Manager] conservar copias exactas de los archivos para facilitar la depuración o retransferencia.

Para obtener más información sobre Amazon S 3, consulte los siguientes recursos:

[Amazon Simple Storage Service (Amazon S 3)](https://aws.amazon.com/s3/) en el sitio web de Amazon Web Services.

[Póngase en marcha con Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) en el sitio web de documentación de AWS.
