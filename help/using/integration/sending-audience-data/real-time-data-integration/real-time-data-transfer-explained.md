---
description: Una visión general de cómo Audience Manager realiza transferencias de datos en tiempo real con un proveedor de contenido de terceros.
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: Proceso de transferencia de datos en tiempo real descrito
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---


# Proceso de transferencia de datos en tiempo real descrito{#real-time-data-transfer-process-described}

Una visión general de cómo Audience Manager realiza transferencias de datos en tiempo real con un proveedor de contenido de terceros.

<!-- real-time-data-transfer-explained.xml -->

## Transferencias de datos en tiempo real

Las transferencias de datos en tiempo real envían y reciben ID de segmento a medida que un usuario visita su sitio o realiza alguna acción en él. Normalmente, las transferencias sincrónicas de datos son útiles cuando necesita calificar o segmentar a los usuarios de inmediato, a medida que navegan por el inventario.

## Pasos de integración de datos

El proceso de integración de datos en tiempo real funciona de la siguiente manera:

1. Un usuario visita el sitio de un cliente que contiene código de Audience Manager.
1. El Audience Manager carga un iframe y realiza una llamada a nuestro [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. El [!DNL DCS] llama al servidor de terceros (en tiempo real) para comprobar si el proveedor tiene información de segmento sobre el usuario.
1. El proveedor de contenido devuelve al Audience Manager la información del segmento sobre ese usuario.
1. El Audience Manager recibe esta información de segmento y la pone a disposición para la segmentación y la creación de nuevas características y segmentos.

![](assets/rt_reduce70.png)