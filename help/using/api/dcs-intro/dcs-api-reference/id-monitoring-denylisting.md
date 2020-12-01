---
description: El DCS supervisa los ID que recibe y agrega los que se envían a una lista de bloqueados a una velocidad inusualmente alta durante un corto período de tiempo.
keywords: id;monitoring;dcs
seo-description: El DCS supervisa los ID que recibe y agrega los que se envían a una lista de bloqueados a una velocidad inusualmente alta durante un corto período de tiempo.
seo-title: Supervisión y Inclusión en la lista de bloqueados de ID
solution: Audience Manager
title: Supervisión y Inclusión en la lista de bloqueados de ID
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# Supervisión y Inclusión en la lista de bloqueados de ID

El [!DNL DCS] supervisa los ID que recibe y agrega los que se envían a una lista de bloqueados a una velocidad inusualmente alta durante un corto período de tiempo.

## Información general

Para proteger la infraestructura del Audience Manager contra la actividad maliciosa, [!DNL DCS] utiliza un algoritmo avanzado para monitorear los ID que recibe. Pueden ser [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) o [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulte [Índice de ID en Audience Manager](../../../reference/ids-in-aam.md) para obtener explicaciones detalladas de los ID admitidos por el Audience Manager.

El [!DNL DCS] supervisa la frecuencia con la que recibe estos ID para detectar posibles actividades maliciosas. Cuando [!DNL DCS] detecta una cantidad inusualmente grande de [!DNL DCS] solicitudes para un ID determinado en un corto período de tiempo, ese ID se agrega a una lista de bloqueados.

## Códigos de error

Puede identificar los ID agregados a una lista de bloqueados mediante los códigos de error recibidos de [!DNL DCS]. Los códigos de error que puede recibir son:

* 303: ID de cliente bloqueado;
* 306: ID de dispositivo declarado bloqueado;
* 307: Operación de perfil bloqueada para ID.

Consulte [Códigos de error, mensajes y ejemplos de DCS](dcs-error-codes.md) para obtener más información sobre los códigos de error que puede recibir.

## Eliminación de ID de listas de bloqueados

Los ID que se han agregado a listas de bloqueados no deben usarse en futuras solicitudes, ya que darán lugar a un sistema de informes de datos incorrecto. El [!DNL DCS] no admite la eliminación de ID de listas de bloqueados.

## Impacto en la sincronización de ID

[!DNL DCS] las llamadas pueden incluir uno o varios tipos de ID. Las llamadas que contienen un solo ID se omiten por completo si ese ID se agrega a una lista de bloqueados y no se produce ninguna sincronización de ID en esta situación.

Cuando una llamada de ID múltiple también incluye un ID incluida en la lista de bloqueados, el [!DNL DCS] ignora el ID denegado y solo utiliza el resto de ID permitidos para la sincronización.

## Causas y correcciones para la Inclusión en la lista de bloqueados de ID

La causa más frecuente de que se agreguen ID a listas de bloqueados es la integración incorrecta entre la infraestructura del cliente y el Audience Manager. Cuando identifique un ID incluida en la lista de bloqueados, asegúrese de revisar a fondo las integraciones del Audience Manager. Consulte **Guías de implementación e integración** para obtener explicaciones detalladas sobre cómo configurar Audience Manager para trabajar con otras soluciones de Experience Cloud o sistemas externos.

Otra causa frecuente de que los ID se agreguen a listas de bloqueados son los bots de indexación (rastreadores Web), que generalmente causan un aumento en el tráfico, lo que provoca que los mismos ID se envíen al [!DNL DCS] varias veces. Si identifica los bots de indexación como el motivo por el que se agregan ID a las listas de bloqueados, debe restringir el acceso de bots a su sitio web.

Si le resulta difícil identificar problemas de integración, no dude en ponerse en contacto con el servicio de asistencia al cliente. Antes de abrir una solicitud de soporte, asegúrese de mantener preparado el archivo `.har` `HTTP` de su explorador. Este archivo ayuda al equipo de soporte a identificar por qué se agregó el ID a una lista de bloqueados.