---
description: Información general sobre cómo Audience Manager realiza un intercambio asincrónico de datos por lotes con un proveedor de terceros.
seo-description: A general overview of how Audience Manager performs an asynchronous batch data exchange with a third-party vendor.
seo-title: Batch Data Transfer Process Described
solution: Audience Manager
title: Proceso de transferencia de datos por lotes descrito
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 5%

---

# Proceso de transferencia de datos por lotes descrito {#batch-data-transfer-process-described}

Una visión general de cómo [!DNL Audience Manager] realiza un intercambio asincrónico de datos por lotes con un proveedor de terceros.

## Integración de datos por lotes

<!-- c_async.xml -->

El proceso de integración de datos por lotes guarda la información del visitante en nuestros servidores y sincroniza ese material con los datos enviados por un proveedor a intervalos regulares. El proceso asincrónico de transferencia de datos es útil cuando:

* No se requieren transferencias de datos inmediatas.
* Recopilación de datos para crear un gran grupo de usuarios segmentados.
* Desea reducir las discrepancias en los datos y `HTTP` llamadas de desde el explorador.

![](assets/s2s_70.png)

## Pasos de integración de datos

1. Un usuario visita un sitio de cliente.
1. [!DNL Audience Manager] y el proveedor de datos de terceros asigna al visitante un ID único (normalmente con una cookie).
1. [!DNL Audience Manager] llama al proveedor de datos de terceros para buscar coincidencias con los ID de visitante.
1. Una solicitud programada, normalmente a intervalos diarios, intercambia datos de segmentos del visitante entre [!DNL Audience Manager] y su proveedor de datos de terceros.
1. Siempre que un [!UICONTROL Server-to-Server] se procesa, se envía una confirmación por correo electrónico a las soluciones de socios y, si se configura, al socio. Para obtener más información, consulte [Mensaje de muestra a los socios después del procesamiento entrante](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
