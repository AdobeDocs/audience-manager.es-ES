---
description: Descripción general general de cómo Audience Manager realiza transferencias de datos en tiempo real con un proveedor de contenido de terceros.
seo-description: Descripción general general de cómo Audience Manager realiza transferencias de datos en tiempo real con un proveedor de contenido de terceros.
seo-title: Proceso de transferencia de datos en tiempo real descrito
solution: Audience Manager
title: Proceso de transferencia de datos en tiempo real descrito
uuid: b 68781 b 3-0 b 7 a -442 d -8 e 34-2 db 2474849 a 4
translation-type: tm+mt
source-git-commit: ea95df8531c00c183f22b09a4a78fc6b35ee279d

---


# Real-Time Data Transfer Process Described{#real-time-data-transfer-process-described}

Descripción general general de cómo Audience Manager realiza transferencias de datos en tiempo real con un proveedor de contenido de terceros.

<!-- real-time-data-transfer-explained.xml -->

## Transferencias de datos en tiempo real

Las transferencias de datos en tiempo real envían y reciben ID de segmento como visitas del usuario o realizan acciones en su sitio. Normalmente, las transferencias de datos sincrónicas resultan útiles cuando se necesita calificar o segmentar a los usuarios inmediatamente, ya que navegan por el inventario.

## Pasos de integración de datos

El proceso de integración de datos en tiempo real funciona de la siguiente manera:

1. Un usuario visita el sitio de un cliente que contiene el código de Audience Manager.
1. Audience Manager loads an iframe and makes a call to our [!UICONTROL Data Collection Server] ( [!UICONTROL DCS]).
1. [!UICONTROL DCS] Llama al servidor de terceros (en tiempo real) para comprobar si el proveedor tiene información de segmento sobre el usuario.
1. El proveedor de contenido devuelve información de segmentos sobre ese usuario a Audience Manager.
1. Audience Manager recibe esta información de segmentos y la pone a disposición para dirigir y generar nuevas características y segmentos.

![](assets/rt_reduce70.png)