---
description: Información general sobre cómo realiza un Audience Manager un intercambio asincrónico de datos por lotes con un proveedor de terceros.
seo-description: Información general sobre cómo realiza un Audience Manager un intercambio asincrónico de datos por lotes con un proveedor de terceros.
seo-title: Proceso de transferencia de datos por lotes descrito
solution: Audience Manager
title: Proceso de transferencia de datos por lotes descrito
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Transferencias de datos de entrada
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 8%

---

# Proceso de transferencia de datos por lotes descrito {#batch-data-transfer-process-described}

Una visión general de cómo [!DNL Audience Manager] realiza un intercambio asincrónico de datos por lotes con un proveedor de terceros.

## Integración de datos por lotes

<!-- c_async.xml -->

El proceso de integración de datos por lotes guarda la información del visitante en nuestros servidores y sincroniza ese material con los datos enviados por un proveedor a intervalos regulares. El proceso asincrónico de transferencia de datos resulta útil cuando:

* No se requieren transferencias de datos inmediatas.
* Recopilación de datos para crear un grupo grande de usuarios segmentados.
* Desea reducir las discrepancias de datos y las `HTTP` llamadas desde el explorador.

![](assets/s2s_70.png)

## Pasos de la integración de datos

1. Un usuario visita un sitio del cliente.
1. [!DNL Audience Manager] y el proveedor de datos de terceros asigna al visitante un ID único (normalmente con una cookie).
1. [!DNL Audience Manager] llama al proveedor de datos de terceros para que coincida con los ID de visitante.
1. Una solicitud programada, normalmente a intervalos diarios, intercambia datos de segmentos del visitante entre [!DNL Audience Manager] y su proveedor de datos de terceros.
1. Cada vez que se procesa un archivo [!UICONTROL Server-to-Server] entrante, se envía un recibo por correo electrónico a las soluciones de socios y, si se configura, al socio. Para obtener más información, consulte [Mensaje de muestra a los socios después del procesamiento entrante](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
