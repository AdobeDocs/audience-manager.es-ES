---
description: El proceso de transferencia de datos de salida para los clientes que utilizan Amazon Simple Storage Service (Amazon S3) requiere que solicitemos su clave de acceso y clave secreta de Amazon S3 para entregar los archivos de datos de salida a su bucket.
seo-description: El proceso de transferencia de datos de salida para los clientes que utilizan Amazon Simple Storage Service (Amazon S3) requiere que solicitemos su clave de acceso y clave secreta de Amazon S3 para entregar los archivos de datos de salida a su bucket.
seo-title: Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes
solution: Audience Manager
title: Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Transferencias de datos de salida
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 14%

---

# Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

El proceso [!UICONTROL Outbound Data Transfer] para los clientes que usan [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) requiere que solicitemos su clave de acceso y clave secreta [!DNL Amazon S3] para poder enviar los archivos de datos salientes a su bucket.

Si no desea compartir su clave de acceso y clave secreta [!DNL Amazon S3] con nosotros, póngase en contacto con su asesor [!DNL Audience Manager] o con el Servicio de atención al cliente y le configurarán [!DNL Cross-Account Bucket Permissions]. Solo debe añadir nuestro [!DNL Amazon S3] ID de cuenta a una lista de permitidos para el bloque [!DNL S3] donde desea recibir los archivos de datos salientes, tal como se describe en la [documentación de Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Su [!DNL Audience Manager] asesor o el Servicio de atención al cliente le proporcionarán nuestro [!DNL Amazon S3] ID de cuenta.
