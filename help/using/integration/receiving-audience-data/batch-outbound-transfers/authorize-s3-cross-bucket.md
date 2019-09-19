---
description: El proceso de transferencia de datos de salida para clientes que utilizan Amazon Simple Storage Service (Amazon S3) requiere que pidamos la clave de acceso y la clave secreta de Amazon S3 para poder entregar los archivos de datos de salida a su bucket.
seo-description: El proceso de transferencia de datos de salida para clientes que utilizan Amazon Simple Storage Service (Amazon S3) requiere que pidamos la clave de acceso y la clave secreta de Amazon S3 para poder entregar los archivos de datos de salida a su bucket.
seo-title: Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes
solution: Audience Manager
title: Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

El [!UICONTROL Outbound Data Transfer] proceso para los clientes que utilizan [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) nos obliga a solicitar la clave de [!DNL Amazon S3] acceso y la clave secreta para poder entregar los archivos de datos salientes a su bucket.

Si no desea compartir su clave de [!DNL Amazon S3] acceso y clave secreta con nosotros, póngase en contacto con su [!DNL Audience Manager] consultor o con el Servicio de atención al cliente y le proporcionarán la configuración [!DNL Cross-Account Bucket Permissions] correspondiente. Sólo necesita incluir en la lista blanca nuestro ID de [!DNL Amazon S3] cuenta para el [!DNL S3] bloque en el que desea recibir los archivos de datos salientes, tal como se describe en la documentación [de](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)Amazon S3. Su [!DNL Audience Manager] consultor o el Servicio de atención al cliente le proporcionarán nuestro ID de [!DNL Amazon S3] cuenta.