---
description: Una visión general de cómo Audience Manager realiza transferencias de datos en tiempo real con un proveedor de contenido de terceros.
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: Proceso de transferencia de datos en tiempo real descrito
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: a03b8192-8410-479f-a326-4cddf10757f6
    internal-label: Inbound data transfers
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%
---

# Proceso de transferencia de datos en tiempo real descrito{#real-time-data-transfer-process-described}

Una visión general de cómo Audience Manager realiza transferencias de datos en tiempo real con un proveedor de contenido de terceros.

<!-- real-time-data-transfer-explained.xml -->

## Transferencias de datos en tiempo real

Las transferencias de datos en tiempo real envían y reciben ID de segmento a medida que un usuario visita su sitio o realiza alguna acción en él. Normalmente, las transferencias sincrónicas de datos son útiles cuando necesita calificar o segmentar a los usuarios de inmediato, a medida que navegan por el inventario.

## Pasos de integración de datos

El proceso de integración de datos en tiempo real funciona de la siguiente manera:

1. Un usuario visita el sitio de un cliente que contiene código Audience Manager.
1. Audience Manager carga un iframe y realiza una llamada a nuestro [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. El [!DNL DCS] llama al servidor de terceros (en tiempo real) para comprobar si el proveedor tiene información de segmento sobre el usuario.
1. El proveedor de contenido devuelve a Audience Manager la información del segmento sobre ese usuario.
1. Audience Manager recibe esta información de segmento y la pone a disposición para la segmentación y la creación de nuevas características y segmentos.

![](assets/rt_reduce70.png)