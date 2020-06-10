---
description: El DCS supervisa los ID que recibe y agrega los que se envían a una lista de denegación a una velocidad inusualmente alta durante un corto período de tiempo.
keywords: id;monitoring;dcs
seo-description: El DCS supervisa los ID que recibe y agrega los que se envían a una lista de denegación a una velocidad inusualmente alta durante un corto período de tiempo.
seo-title: Supervisión de ID y exclusión de listas
solution: Audience Manager
title: Supervisión de ID y exclusión de listas
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# Supervisión de ID y exclusión de listas

El [!UICONTROL DCS] supervisa los ID que recibe y agrega los que se envían a una lista de denegación a una tasa inusualmente alta durante un corto período de tiempo.

## Información general

Para proteger la infraestructura del Administrador de Audiencias contra la actividad maliciosa, el usuario [!UICONTROL DCS] utiliza un algoritmo avanzado para supervisar los ID que recibe. Pueden ser [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) o [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulte [Índice de ID en el Administrador](../../../reference/ids-in-aam.md) de Audiencias para obtener explicaciones detalladas de los ID admitidos por el Administrador de Audiencias.

El [!UICONTROL DCS] monitor supervisa la frecuencia con la que recibe estos ID para detectar posibles actividades malintencionadas. Cuando el [!UICONTROL DCS] detecta una cantidad inusualmente grande de [!UICONTROL DCS] solicitudes para un ID determinado en un corto período de tiempo, ese ID se agrega a una lista de denegación.

## Códigos de error

Puede identificar los ID agregados a una lista de denegación por los códigos de error recibidos del [!UICONTROL DCS]. Los códigos de error que puede recibir son:

* 303: ID de cliente bloqueado;
* 306: ID de dispositivo declarado bloqueado;
* 307: Operación de perfil bloqueada para ID.

Consulte Códigos de error, mensajes y ejemplos [](dcs-error-codes.md) de DCS para obtener más información sobre los códigos de error que puede recibir.

## Eliminación de ID de listas de denegación

Los ID que se han agregado para denegar listas no deben usarse en futuras solicitudes, ya que darán lugar a un sistema de informes de datos incorrecto. El [!UICONTROL DCS] no admite la eliminación de ID de listas de denegación.

## Impacto en la sincronización de ID

[!UICONTROL DCS] las llamadas pueden incluir uno o varios tipos de ID. Las llamadas que contienen un solo ID se omiten por completo si ese ID se agrega a una lista de denegación y no se produce sincronización de ID en esta situación.

Cuando una llamada de ID múltiple también incluye un ID denylist, el usuario [!UICONTROL DCS] ignora el ID denegado y solo utiliza el resto de ID permitidos para la sincronización.

## Causas y correcciones de la desvinculación de ID

La causa más frecuente de que se agreguen ID para denegar listas es la integración incorrecta entre la infraestructura del cliente y el Administrador de Audiencias. Cuando identifique un ID denlistado, asegúrese de revisar a fondo las integraciones del Administrador de Audiencias. Consulte las Guías **de** implementación e integración para obtener explicaciones detalladas sobre cómo configurar el Administrador de Audiencias para que funcione con otras soluciones de Experience Cloud o sistemas externos.

Otra causa frecuente de que se agreguen ID para denegar listas son los bots de indexación (rastreadores web), que generalmente causan un aumento en el tráfico, lo que provoca que los mismos ID se envíen a los [!UICONTROL DCS] usuarios varias veces. Si identifica los bots de indexación como el motivo por el que se agregan ID para denegar listas, debe restringir el acceso de los bots a su sitio web.

Si le resulta difícil identificar problemas de integración, no dude en ponerse en contacto con el servicio de asistencia al cliente. Antes de abrir una solicitud de soporte técnico, asegúrese de mantener el `.har` archivo del explorador preparado `HTTP` . Este archivo ayuda al equipo de soporte a identificar por qué se agregó el ID a una lista de denegación.