---
description: El proceso de transferencia de datos de salida para clientes que utilizan Amazon Simple Almacenamiento Service (Amazon S3) requiere que pidamos la clave de acceso y la clave secreta de Amazon S3 para poder entregar los archivos de datos de salida a su bucket.
seo-description: El proceso de transferencia de datos de salida para clientes que utilizan Amazon Simple Almacenamiento Service (Amazon S3) requiere que pidamos la clave de acceso y la clave secreta de Amazon S3 para poder entregar los archivos de datos de salida a su bucket.
seo-title: Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes
solution: Audience Manager
title: Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 14%

---


# Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

El [!UICONTROL Outbound Data Transfer] proceso para los clientes que utilizan [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) nos obliga a solicitar la clave de [!DNL Amazon S3] acceso y la clave secreta para poder entregar los archivos de datos salientes a su bucket.

Si no desea compartir su clave de [!DNL Amazon S3] acceso y clave secreta con nosotros, póngase en contacto con su [!DNL Audience Manager] consultor o con el Servicio de atención al cliente y le proporcionarán la configuración [!DNL Cross-Account Bucket Permissions] correspondiente. Sólo necesita agregar nuestro ID de cuenta a una lista de permitir para el [!DNL Amazon S3] bucket donde desee recibir los archivos de datos salientes, como se describe en la documentación [!DNL S3] de [](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)Amazon S3. Su [!DNL Audience Manager] consultor o el Servicio de atención al cliente le proporcionarán nuestro ID de [!DNL Amazon S3] cuenta.