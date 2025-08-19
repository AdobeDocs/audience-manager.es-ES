---
description: El DCS supervisa las ID que recibe y agrega aquellas que se envían a una velocidad inusualmente alta durante un corto período de tiempo a una lista de denegación.
keywords: id;monitoreo; Dcs
seo-description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
seo-title: ID Monitoring and Denylisting
solution: Audience Manager
title: Supervisión de ID y denegación de listas
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# Supervisión de ID y denegación de listas

El [!DNL DCS] monitorea las identificaciones que recibe y agrega las que se envían a una velocidad inusualmente alta durante un corto período de tiempo a una lista de denegación.

## Información general

Para proteger la infraestructura Audience Manager contra actividad malintencionados, utiliza [!DNL DCS] un algoritmo avanzado para monitor los ID que recibe. Pueden ser [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) o [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulte [Index de ID en Audience Manager](../../../reference/ids-in-aam.md) para obtener explicaciones detalladas de los ID admitidos por Audience Manager.

El [!DNL DCS] monitorea la Frecuencia en la que recibe estos ID para detectar posibles actividad malintencionados. Cuando detecta [!DNL DCS] una cantidad inusualmente grande de solicitudes para [!DNL DCS] un ID determinado en un corto período de tiempo, ese ID se agrega a un lista de denegación.

## Códigos Error

Puede identificar los ID añadidos a un lista de denegación por los códigos de error recibidos del [!DNL DCS]archivo . Los códigos de error que puede recibir son:

* 303: ID de cliente bloqueada;
* 306: ID de dispositivos declarada bloqueada;
* 307: Se bloqueó la operación perfil para la identificación.

Consulte [DCS Error códigos, mensajes y ejemplos](dcs-error-codes.md) para obtener detalles sobre los códigos de error que puede recibir.

## Eliminación de identificadores de listas de denegación

Los ID que se han agregado a listas de denegación no deben usarse en ninguna solicitud futura, ya que posible cliente a sistema de informes de datos incorrectos. El [!DNL DCS] no admite la eliminación de ID de las listas de denegación.

## Impacto en la sincronización de ID

[!DNL DCS] las llamadas pueden incluir uno o varios tipos de ID. Las llamadas que contienen un solo ID se ignoran por completo si ese ID se agrega a una lista de denegación y no se produce ninguna sincronización de ID en esta situación.

Cuando una llamada de ID múltiple también incluye un ID denegado, el [!DNL DCS] ID ignora el ID denegado y solo utiliza los ID permitidos restantes para la sincronización.

## Causas y correcciones de la lista de denegación de ID

La causa más frecuente de que se agreguen ID a las listas de denegación es la integración incorrecta entre la infraestructura del cliente y Audience Manager. Cuando identifique un ID en la lista de denegación, asegúrese de revisar minuciosamente las integraciones de Audience Manager. Consulte **las Guías** de implementación e integración para obtener explicaciones detalladas de cómo debe configurar Audience Manager para que funcionen con otras soluciones Experience Cloud o sistemas externos.

Otra causa frecuente de que se agreguen identificadores a las listas de denegación son los bots de indexación (rastreadores web), que generalmente causan aumentos en el [!DNL DCS] tráfico, lo que lleva a que los mismos ID se envíen varias veces. Si identifica los bots de indexación como el motivo por el que se agregan ID a las listas de denegación, debe restringir bot acceso a su sitio web.

Si tiene dificultades para identificar problemas de integración, no dude en ponerse en contacto con el servicio de atención al cliente. Antes de abrir un solicitud de soporte, asegúrese de tener listo el `.har` `HTTP` archivo de su explorador. Este archivo ayuda al equipo de asistencia equipo identificar por qué se agregó el ID a una lista de denegación.
