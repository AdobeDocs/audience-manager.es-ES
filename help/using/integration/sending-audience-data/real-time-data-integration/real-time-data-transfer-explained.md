---
description: Información general sobre cómo realiza el Audience Manager las transferencias de datos en tiempo real con un proveedor de contenido de terceros.
seo-description: Información general sobre cómo realiza el Audience Manager las transferencias de datos en tiempo real con un proveedor de contenido de terceros.
seo-title: Proceso de transferencia de datos en tiempo real descrito
solution: Audience Manager
title: Proceso de transferencia de datos en tiempo real descrito
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Transferencias de datos de entrada
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 1%

---


# Proceso de transferencia de datos en tiempo real descrito{#real-time-data-transfer-process-described}

Información general sobre cómo realiza el Audience Manager las transferencias de datos en tiempo real con un proveedor de contenido de terceros.

<!-- real-time-data-transfer-explained.xml -->

## Transferencias de datos en tiempo real

Las transferencias de datos en tiempo real envían y reciben ID de segmento a medida que un usuario visita el sitio o realiza una acción en él. Normalmente, las transferencias de datos sincrónicas son útiles cuando necesita clasificar o segmentar a los usuarios de inmediato, ya que navegan por su inventario.

## Pasos de la integración de datos

El proceso de integración de datos en tiempo real funciona de la siguiente manera:

1. Un usuario visita el sitio de un cliente que contiene código de Audience Manager.
1. El Audience Manager carga un iframe y realiza una llamada a nuestro [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. El [!DNL DCS] llama al servidor de terceros (en tiempo real) para comprobar si el proveedor tiene información de segmento sobre el usuario.
1. El proveedor de contenido devuelve al Audience Manager información de segmento sobre ese usuario.
1. Audience Manager recibe esta información de segmento y la pone a disposición para la definición de objetivos y la generación de nuevos rasgos y segmentos.

![](assets/rt_reduce70.png)