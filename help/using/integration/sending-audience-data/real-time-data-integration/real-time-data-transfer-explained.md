---
description: Información general sobre cómo realiza el Audience Manager las transferencias de datos en tiempo real con un proveedor de contenido de terceros.
seo-description: Información general sobre cómo realiza el Audience Manager las transferencias de datos en tiempo real con un proveedor de contenido de terceros.
seo-title: Proceso de transferencia de datos en tiempo real descrito
solution: Audience Manager
title: Proceso de transferencia de datos en tiempo real descrito
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Proceso de transferencia de datos en tiempo real descrito{#real-time-data-transfer-process-described}

Información general sobre cómo realiza el Audience Manager las transferencias de datos en tiempo real con un proveedor de contenido de terceros.

<!-- real-time-data-transfer-explained.xml -->

## Transferencias de datos en tiempo real

Las transferencias de datos en tiempo real envían y reciben ID de segmentos a medida que un usuario visita el sitio o realiza acciones en él. Generalmente, las transferencias de datos sincrónicas son útiles cuando necesita clasificar o segmentar a los usuarios de inmediato, a medida que navegan por el inventario.

## Pasos de integración de datos

El proceso de integración de datos en tiempo real funciona de la siguiente manera:

1. Un usuario visita el sitio de un cliente que contiene código de Audience Manager.
1. Audience Manager carga un iframe y realiza una llamada a nuestro [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. El [!DNL DCS] llama al servidor de terceros (en tiempo real) para comprobar si el proveedor tiene información de segmento sobre el usuario.
1. El proveedor de contenido devuelve al Audience Manager la información de segmentos sobre ese usuario.
1. Audience Manager recibe esta información de segmento y la pone a disposición para dirigir y generar nuevas características y segmentos.

![](assets/rt_reduce70.png)