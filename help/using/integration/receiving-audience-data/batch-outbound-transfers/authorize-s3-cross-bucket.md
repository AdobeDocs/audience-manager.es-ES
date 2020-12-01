---
description: El proceso de transferencia de datos de salida para clientes que utilizan el servicio de Almacenamiento simple de Amazon (Amazon S3) requiere que pidamos la clave de acceso y la clave secreta de Amazon S3 para poder entregar los archivos de datos de salida a su bucket.
seo-description: El proceso de transferencia de datos de salida para clientes que utilizan el servicio de Almacenamiento simple de Amazon (Amazon S3) requiere que pidamos la clave de acceso y la clave secreta de Amazon S3 para poder entregar los archivos de datos de salida a su bucket.
seo-title: Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes
solution: Audience Manager
title: Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 14%

---


# Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

El proceso [!UICONTROL Outbound Data Transfer] para los clientes que utilizan [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) requiere que solicitemos su clave de acceso y clave secreta [!DNL Amazon S3] para poder entregar los archivos de datos salientes a su bucket.

Si prefiere no compartir su clave de acceso y clave secreta [!DNL Amazon S3] con nosotros, póngase en contacto con su [!DNL Audience Manager] consultor o con el Servicio de atención al cliente y le configurarán [!DNL Cross-Account Bucket Permissions]. Sólo necesita agregar nuestro [!DNL Amazon S3] ID de cuenta a una lista de permitidos para el bloque [!DNL S3] donde desee recibir los archivos de datos salientes, como se describe en la [documentación de Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Su [!DNL Audience Manager] asesor o Servicio de atención al cliente le proporcionará nuestro [!DNL Amazon S3] ID de cuenta.