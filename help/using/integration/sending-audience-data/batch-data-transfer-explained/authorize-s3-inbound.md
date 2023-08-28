---
description: Para enviar datos desde su propio bloque de Amazon S3 al Audience Manager, primero debe solicitar la configuración de un rol de Amazon S3 dedicado.
solution: Audience Manager
title: Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos entrantes
feature: Inbound Data Transfers
source-git-commit: ff023fb57e2653ca65323313a37852d379e4b00c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos entrantes {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

Para enviar datos desde su propio bloque de Amazon S3 al Audience Manager, primero debe solicitar la configuración de un rol de Amazon S3 dedicado.

Para ello, siga los pasos descritos a continuación.

1. Póngase en contacto con el Servicio de atención al cliente y solicite un método alternativo para enviar archivos a Audience Manager.
2. Proporcione al Servicio de atención al cliente la [!DNL Amazon Resource Name (ARN)] para un rol en su cuenta de Amazon S3 que utilizará para enviar archivos. _Esta función debe crearse antes de ponerse en contacto con el Servicio de atención al cliente_. Una vez completada la configuración, el Servicio de atención al cliente le proporcionará el [!DNL Amazon Resource Name (ARN)] para la función recién creada.
3. Edite los permisos de la función existente de Amazon S3 para asumir la función que proporciona el Servicio de atención al cliente.

>[!NOTE]
>
>Al transferir datos de entrada al bloque de Audience Manager Amazon S3, asegúrese de utilizar el `bucket-owner-full-control` [lista de control de acceso](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) para que Audience Manager procese correctamente los datos.
><br>
>Ejemplo del comando Amazon Web Service: `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`.

