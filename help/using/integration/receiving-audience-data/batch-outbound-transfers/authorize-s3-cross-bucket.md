---
description: El proceso de transferencia de datos salientes para clientes que utilizan Amazon Simple Storage Service (Amazon S3) requiere que solicitemos su clave de acceso y clave secreta de Amazon S3 para poder entregar los archivos de datos salientes a su bloque.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 7302fafa537ad15144a64cc96f7150c5b0233c12
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 12%

---

# Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

El [!UICONTROL Outbound Data Transfer] proceso para clientes que utilizan [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) requiere que preguntemos por su [!DNL Amazon S3] clave de acceso y clave secreta, para enviar los archivos de datos salientes al bloque.

Si prefiere no compartir su [!DNL Amazon S3] clave de acceso y clave secreta con nosotros, póngase en contacto con su [!DNL Audience Manager] o al Servicio de atención al cliente, y configurarán [!DNL Cross-Account Bucket Permissions] para usted.

Solo tiene que añadir nuestra [!DNL Amazon S3] ID de cuenta de a una lista de permitidos de [!DNL S3] contenedor donde desee recibir los archivos de datos salientes, tal como se describe en la sección [Documentación de Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Su [!DNL Audience Manager] Un asesor de o el Servicio de atención al cliente le proporcionarán nuestra [!DNL Amazon S3] ID de cuenta.
