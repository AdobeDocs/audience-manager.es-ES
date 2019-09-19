---
description: El DCS supervisa los ID que recibe y pone en la lista negra los que se envían a una velocidad inusualmente alta durante un corto período de tiempo.
keywords: id;supervisión;lista negra;dcs
seo-description: El DCS supervisa los ID que recibe y pone en la lista negra los que se envían a una velocidad inusualmente alta durante un corto período de tiempo.
seo-title: Supervisión de ID y lista negra
solution: Audience Manager
title: Supervisión de ID y lista negra
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Supervisión de ID y lista negra

El [!UICONTROL DCS] supervisa los ID que recibe y pone en negro los que se envían a una velocidad inusualmente alta durante un corto período de tiempo.

## Información general

Para proteger la infraestructura de Audience Manager contra actividades malintencionadas, el usuario [!UICONTROL DCS] utiliza un algoritmo avanzado para supervisar los ID que recibe. Pueden ser [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) o [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulte [Índice de ID en Audience Manager](../../../reference/ids-in-aam.md) para obtener explicaciones detalladas de los ID admitidos por Audience Manager.

El [!UICONTROL DCS] monitor supervisa la frecuencia con la que recibe estos ID para detectar posibles actividades maliciosas. Cuando el [!UICONTROL DCS] detecta una cantidad inusualmente grande de [!UICONTROL DCS] solicitudes para un ID determinado en un corto período de tiempo, ese ID se bloquea.

## Códigos de error

Puede identificar los ID bloqueados por los códigos de error recibidos de la [!UICONTROL DCS]. Los códigos de error que puede recibir son:

* 303: ID de cliente bloqueado;
* 306: ID de dispositivo declarado bloqueado;
* 307: Operación de perfil bloqueada para ID.

Consulte Códigos de error, mensajes y ejemplos [](dcs-error-codes.md) de DCS para obtener más información sobre los códigos de error que puede recibir.

## Cancelar la lista negra

Los ID bloqueados no deben usarse en futuras solicitudes, ya que generarán informes de datos incorrectos. El [!UICONTROL DCS] no admite la eliminación de la lista negra de ID.

## Impacto en la sincronización de ID

[!UICONTROL DCS] las llamadas pueden incluir uno o varios tipos de ID. Las llamadas que contienen un solo ID no se tienen en cuenta si ese ID está bloqueado y no se produce sincronización de ID en este caso.

Cuando una llamada de ID múltiple también incluye un ID bloqueado, el usuario [!UICONTROL DCS] ignora el ID bloqueado y solo utiliza el resto de ID no bloqueados para la sincronización.

## Causas y correcciones de la lista negra de ID

La causa más frecuente de que se bloqueen los ID es la integración incorrecta entre la infraestructura del cliente y Audience Manager. Cuando identifique un ID bloqueado, asegúrese de revisar a fondo las integraciones de Audience Manager. Consulte las Guías **de implementación e integración** para obtener explicaciones detalladas sobre cómo configurar Audience Manager para que funcione con otras soluciones de Experience Cloud o sistemas externos.

Otra causa frecuente de los ID bloqueados son los bots de indexación (rastreadores web), que generalmente causan un aumento en el tráfico, lo que provoca que los mismos ID se envíen a los [!UICONTROL DCS] usuarios varias veces. Si identifica los bots de indexación como el motivo de la lista negra de ID, debe restringir el acceso de los bots a su sitio web.

Si le resulta difícil identificar problemas de integración, no dude en ponerse en contacto con el servicio de asistencia al cliente. Antes de abrir una solicitud de soporte técnico, asegúrese de mantener el `.har` archivo del explorador preparado `HTTP` . Este archivo ayuda al equipo de soporte a identificar el motivo por el que se produjo la lista negra de ID.