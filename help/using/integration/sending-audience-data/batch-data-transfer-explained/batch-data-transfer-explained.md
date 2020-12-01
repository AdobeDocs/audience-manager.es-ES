---
description: Información general sobre cómo realiza un Audience Manager un intercambio de datos por lotes asincrónico con un proveedor de terceros.
seo-description: Información general sobre cómo realiza un Audience Manager un intercambio de datos por lotes asincrónico con un proveedor de terceros.
seo-title: Proceso de transferencia de datos por lotes descrito
solution: Audience Manager
title: Proceso de transferencia de datos por lotes descrito
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 7%

---


# Proceso de transferencia de datos por lotes descrito {#batch-data-transfer-process-described}

Información general sobre cómo [!DNL Audience Manager] realiza un intercambio de datos por lotes asincrónico con un proveedor de terceros.

## Integración de datos por lotes

<!-- c_async.xml -->

El proceso de integración de datos por lotes guarda la información de visitante en nuestros servidores y sincroniza ese material con los datos enviados por un proveedor a intervalos regulares. El proceso asincrónico de transferencia de datos resulta útil cuando:

* No se requieren transferencias de datos inmediatas.
* Recopilación de datos para crear un gran grupo de usuarios segmentados.
* Desea reducir las discrepancias de datos y las `HTTP` llamadas desde el explorador.

![](assets/s2s_70.png)

## Pasos de integración de datos

1. Un usuario visita el sitio del cliente.
1. [!DNL Audience Manager] y el proveedor de datos de terceros asigna al visitante un ID único (generalmente con una cookie).
1. [!DNL Audience Manager] llama al proveedor de datos de terceros para que coincida con los ID de visitante.
1. Una solicitud programada, normalmente a intervalos diarios, intercambia datos de segmentos de visitante entre [!DNL Audience Manager] y su proveedor de datos de terceros.
1. Cada vez que se procesa un archivo [!UICONTROL Server-to-Server] entrante, se envía un recibo por correo electrónico a las soluciones de socios y, si se configura, al socio. Para obtener más información, consulte [Mensaje de muestra a los socios después del procesamiento entrante](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
