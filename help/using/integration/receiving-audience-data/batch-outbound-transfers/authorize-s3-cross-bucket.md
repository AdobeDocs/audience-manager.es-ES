---
description: El proceso de transferencia de datos salientes para clientes que utilizan Amazon Simple Storage Service (Amazon S3) requiere que solicitemos su clave de acceso y clave secreta de Amazon S3 para poder entregar los archivos de datos salientes a su bloque.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 9c0254e8a29ffeb0353ed6faa898b74bcae7cef1
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

El proceso de [!UICONTROL Outbound Data Transfer] para clientes que usan [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) requiere que solicitemos la clave de acceso y la clave secreta [!DNL Amazon S3] para poder entregar los archivos de datos salientes al espacio.

Si prefiere no compartir su clave de acceso y clave secreta [!DNL Amazon S3] con nosotros, póngase en contacto con su asesor de [!DNL Audience Manager] o con el Servicio de atención al cliente y ellos configurarán [!DNL Cross-Account Bucket Permissions] para usted.

Solo necesita agregar su ID de cuenta [!DNL Amazon S3] a una lista de permitidos para el bloque [!DNL S3] en el que desea recibir los archivos de datos salientes, tal como se describe en la [documentación de Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Su asesor de [!DNL Audience Manager] o el Servicio de atención al cliente le proporcionarán nuestro identificador de cuenta de [!DNL Amazon S3].

>[!NOTE]
>
>Debido al límite de tamaño de objeto de Amazon S3, Audience Manager admite tamaños de división de hasta 1 TB. Si no se especifica ningún tamaño de división, se aplica automáticamente el límite de 1 TB.

