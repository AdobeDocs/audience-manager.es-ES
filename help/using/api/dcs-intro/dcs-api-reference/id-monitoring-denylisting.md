---
description: El DCS supervisa los ID que recibe y agrega los que se envían a una lista de denegaciones a una velocidad inusualmente alta durante un corto período de tiempo.
keywords: id;monitoring;dcs
seo-description: El DCS supervisa los ID que recibe y agrega los que se envían a una lista de denegaciones a una velocidad inusualmente alta durante un corto período de tiempo.
seo-title: Supervisión de ID y exclusión de listas
solution: Audience Manager
title: Supervisión de ID y exclusión de listas
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# Supervisión de ID y exclusión de listas

El [!DNL DCS] supervisa los ID que recibe y agrega los que se envían a una lista de denegaciones a una tasa inusualmente alta durante un período de tiempo corto.

## Información general

Para proteger la infraestructura del Audience Manager contra la actividad maliciosa, el usuario [!DNL DCS] utiliza un algoritmo avanzado para supervisar los ID que recibe. Pueden ser [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) o [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulte [Índice de ID en Audience Manager](../../../reference/ids-in-aam.md) para obtener explicaciones detalladas de los ID admitidos por el Audience Manager.

El [!DNL DCS] monitor supervisa la frecuencia con la que recibe estos ID para detectar posibles actividades malintencionadas. Cuando el [!DNL DCS] detecta una cantidad inusualmente grande de [!DNL DCS] solicitudes para un ID determinado en un corto período de tiempo, ese ID se agrega a una lista de denegaciones.

## Códigos de error

Puede identificar los ID agregados a una lista de denegaciones mediante los códigos de error recibidos del [!DNL DCS]. Los códigos de error que puede recibir son:

* 303: ID de cliente bloqueado;
* 306: ID de dispositivo declarado bloqueado;
* 307: Operación de perfil bloqueada para ID.

Consulte Códigos de error, mensajes y ejemplos [](dcs-error-codes.md) de DCS para obtener más información sobre los códigos de error que puede recibir.

## Eliminación de ID de listas de denegaciones

Las ID que se han agregado a las listas de denegación no deben usarse en futuras solicitudes, ya que darán lugar a un sistema de informes de datos incorrecto. El [!DNL DCS] no admite la eliminación de ID de las listas de denegación.

## Impacto en la sincronización de ID

[!DNL DCS] las llamadas pueden incluir uno o varios tipos de ID. Las llamadas que contienen un solo ID se omiten por completo si ese ID se agrega a una lista de denegaciones y no se produce sincronización de ID en esta situación.

Cuando una llamada de ID múltiple también incluye un ID denylist, el usuario [!DNL DCS] ignora el ID denegado y solo utiliza el resto de ID permitidos para la sincronización.

## Causas y correcciones de la desvinculación de ID

La causa más frecuente de que se agreguen ID a las listas de denegación es la integración incorrecta entre la infraestructura del cliente y el Audience Manager. Cuando identifique un ID denlistado, asegúrese de revisar a fondo las integraciones de Audience Manager. Consulte las Guías **de implementación e integración** para obtener explicaciones detalladas sobre cómo configurar Audience Manager para trabajar con otras soluciones de Experience Cloud o sistemas externos.

Otra causa frecuente de que se agreguen ID a las listas de denegación son los bots de indexación (rastreadores web), que generalmente causan un aumento en el tráfico, lo que provoca que los mismos ID se envíen a las listas [!DNL DCS] varias veces. Si identifica los bots de indexación como el motivo por el que se agregan ID a las listas de denegación, debe restringir el acceso de los bots a su sitio web.

Si le resulta difícil identificar problemas de integración, no dude en ponerse en contacto con el servicio de asistencia al cliente. Antes de abrir una solicitud de soporte técnico, asegúrese de mantener el `.har` archivo del explorador preparado `HTTP` . Este archivo ayuda al equipo de soporte a identificar por qué se agregó el ID a una lista de denegación.