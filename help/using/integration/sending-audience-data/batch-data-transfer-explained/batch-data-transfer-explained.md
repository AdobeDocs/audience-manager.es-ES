---
description: Descripción general general de cómo Audience Manager realiza un intercambio de datos asíncrono con un proveedor de terceros.
seo-description: Descripción general general de cómo Audience Manager realiza un intercambio de datos asíncrono con un proveedor de terceros.
seo-title: Proceso de transferencia de datos por lotes descrito
solution: Audience Manager
title: Proceso de transferencia de datos por lotes descrito
uuid: a 9 eee 940-151 c -44 f 8-9 fe 9-8 ab 47 d 8 fa 45 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Batch Data Transfer Process Described {#batch-data-transfer-process-described}

Descripción general general de cómo Audience Manager realiza un intercambio de datos asíncrono con un proveedor de terceros.

## Integración de datos por lotes

<!-- c_async.xml -->

El proceso de integración de datos por lotes guarda la información de los visitantes en nuestros servidores y sincroniza dicho material con los datos enviados por un proveedor a intervalos regulares. El proceso asincrónico de transferencia de datos es útil cuando:

* No se requieren transferencias de datos inmediatas.
* Recopilación de datos para crear un gran grupo de usuarios segmentados.
* You want to reduce data discrepancies and `HTTP` calls from the browser.

![](assets/s2s_70.png)

## Pasos de integración de datos

1. Un usuario visita un sitio de clientes.
1. Audience Manager y el proveedor de datos de terceros asignan al visitante un ID único (generalmente con una cookie).
1. Audience Manager llama al proveedor de datos de terceros para que coincida con las ID de los visitantes.
1. Una solicitud programada, generalmente en intervalo diario, intercambia los datos de segmento de visitantes entre Audience Manager y el proveedor de datos de terceros.
1. Whenever an inbound [!UICONTROL Server-to-Server] file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner. For more information, see [Sample Message to Partners after Inbound Processing](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).