---
description: El proceso de transferencia de datos salientes para clientes que utilizan Amazon Simple Storage Service (Amazon S3) requiere que solicitemos su clave de acceso y clave secreta de Amazon S3 para poder entregar los archivos de datos salientes a su bloque.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
TQID: https://experienceleague.adobe.com/Ji1ltYPv4eoY5-eZiX62JyQ5SJzdMjFZdKeRzJnwKZg
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 186
ht-degree: 0%

---

# Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

El proceso de [!UICONTROL Outbound Data Transfer] para clientes que usan [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) requiere que solicitemos la clave de acceso y la clave secreta [!DNL Amazon S3] para poder entregar los archivos de datos salientes al espacio.

Si prefiere no compartir su clave de acceso y clave secreta [!DNL Amazon S3] con nosotros, póngase en contacto con su asesor de [!DNL Audience Manager] o con el Servicio de atención al cliente y ellos configurarán [!DNL Cross-Account Bucket Permissions] para usted.

Solo necesita agregar su ID de cuenta [!DNL Amazon S3] a una lista de permitidos para el bloque [!DNL S3] en el que desea recibir los archivos de datos salientes, tal como se describe en la [documentación de Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Su asesor de [!DNL Audience Manager] o el Servicio de atención al cliente le proporcionarán nuestro identificador de cuenta de [!DNL Amazon S3].

>[!NOTE]
>
>Debido al límite de tamaño de objeto de Amazon S3, Audience Manager admite tamaños de división de hasta 1 TB. Si no se especifica ningún tamaño de división, se aplica automáticamente el límite de 1 TB.

