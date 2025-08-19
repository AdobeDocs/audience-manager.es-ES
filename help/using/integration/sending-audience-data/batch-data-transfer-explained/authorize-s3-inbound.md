---
description: Para enviar datos desde su propio bucket de Amazon S3 a Audience Manager, primero debe solicitud la configuración de un función de S3 de Amazon dedicado.
solution: Audience Manager
title: Aproveche Amazon permisos de bloque entre cuentas de S3 para su Archivos entrante
feature: Inbound Data Transfers
exl-id: 56ecea5a-0621-4720-9e4c-f9086294c31f
source-git-commit: 65963c462f2a5abb1e2597b3d943628baa9d4730
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Aproveche Amazon permisos de bloque entre cuentas de S3 para su Archivos entrante {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

Para enviar datos desde su propio bucket de Amazon S3 a Audience Manager, primero debe solicitud la configuración de un función de S3 de Amazon dedicado.

Para ello, seguir los pasos que se describen a continuación.

1. Póngase en contacto con el servicio de atención al cliente y solicitud un método alternativo para enviar archivos a Audience Manager.
2. Proporcione al Servicio de atención al cliente los [!DNL Amazon Resource Name (ARN)] foros función de su Amazon cuenta S3 que utilizará para enviar archivos. _Este función debe crearse antes de ponerse en contacto con el Servicio de atención al cliente_. Una vez finalizada la configuración, el Servicio de atención al cliente le proporcionará la [!DNL Amazon Resource Name (ARN)] para el función recién creado.
3. Editar los permisos de su función de Amazon S3 existente para asumir los función proporcionados por el Servicio de atención al cliente.

>[!NOTE]
>
>Cuando transfiera datos entrantes al bucket de Audience Manager Amazon S3, asegúrese de utilizar el `bucket-owner-full-control` [lista control de acceso](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) para que Audience Manager procese correctamente los datos.
>
>Ejemplo del comando Amazon Web Services: `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`
