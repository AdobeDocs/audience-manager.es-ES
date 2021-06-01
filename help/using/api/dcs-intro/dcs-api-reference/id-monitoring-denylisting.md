---
description: El DCS supervisa los ID que recibe y añade a una lista de bloqueados aquellos que se envían a una tasa inusualmente alta durante un corto periodo de tiempo.
keywords: id;monitorización;dcs
seo-description: El DCS supervisa los ID que recibe y añade a una lista de bloqueados aquellos que se envían a una tasa inusualmente alta durante un corto periodo de tiempo.
seo-title: Monitorización de ID y Inclusión en la lista de bloqueados
solution: Audience Manager
title: Monitorización de ID y Inclusión en la lista de bloqueados
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 0%

---

# Monitorización de ID y Inclusión en la lista de bloqueados

El [!DNL DCS] supervisa los ID que recibe y agrega los que se envían a una lista de bloqueados a una tasa inusualmente alta durante un corto periodo de tiempo.

## Información general

Para proteger la infraestructura del Audience Manager contra las actividades maliciosas, el [!DNL DCS] utiliza un algoritmo avanzado para supervisar los ID que recibe. Pueden ser [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) o [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulte [Índice de ID en el Audience Manager](../../../reference/ids-in-aam.md) para obtener explicaciones detalladas de los ID admitidos por el Audience Manager.

El [!DNL DCS] supervisa la frecuencia con la que recibe estos ID para detectar posibles actividades maliciosas. Cuando [!DNL DCS] detecta una cantidad inusualmente grande de solicitudes [!DNL DCS] para cualquier ID dado en un corto periodo de tiempo, ese ID se agrega a una lista de bloqueados.

## Códigos de error

Puede identificar los ID agregados a una lista de bloqueados mediante los códigos de error recibidos del [!DNL DCS]. Los códigos de error que puede recibir son:

* 303: ID de cliente bloqueado;
* 306: ID de dispositivo declarado bloqueado;
* 307: Operación de perfil bloqueada para el ID.

Consulte [Códigos de error DCS, mensajes y ejemplos](dcs-error-codes.md) para obtener más información sobre los códigos de error que puede recibir.

## Eliminación de ID de listas de bloqueados

Los ID que se han agregado a listas de bloqueados no deben usarse en ninguna solicitud futura, ya que producirán informes de datos incorrectos. El [!DNL DCS] no admite la eliminación de ID de listas de bloqueados.

## Impacto en la sincronización de ID

[!DNL DCS] Las llamadas de pueden incluir uno o varios tipos de ID. Las llamadas que contienen un solo ID no se tienen en cuenta si ese ID se agrega a una lista de bloqueados y, en este caso, no se produce ninguna sincronización de ID.

Cuando una llamada de ID múltiple también incluye un ID incluida en la lista de bloqueados, el [!DNL DCS] ignora el ID denegado y solo utiliza los ID restantes permitidos para la sincronización.

## Causas y correcciones para la  de Inclusión en la lista de bloqueados de ID

La causa más frecuente de que se agreguen ID a listas de bloqueados es la integración incorrecta entre la infraestructura del cliente y el Audience Manager. Cuando identifique un ID incluida en la lista de bloqueados, asegúrese de revisar a fondo las integraciones de Audience Manager. Consulte **Guías de implementación e integración** para obtener explicaciones detalladas sobre cómo debe configurar el Audience Manager para que funcione con otras soluciones de Experience Cloud o sistemas externos.

Otra causa frecuente de que se agreguen ID a listas de bloqueados es la indexación de bots (rastreadores web), que generalmente provoca un aumento en el tráfico, lo que provoca que los mismos ID se envíen al [!DNL DCS] varias veces. Si identifica bots de indexación como la razón por la que se agregan ID a las listas de bloqueados, debe restringir el acceso de bots a su sitio web.

Si le resulta difícil identificar los problemas de integración, no dude en ponerse en contacto con el servicio de atención al cliente. Antes de abrir una solicitud de asistencia, asegúrese de mantener preparado el `.har` `HTTP` archivo del explorador. Este archivo ayuda al equipo de asistencia a identificar por qué se agregó el ID a una lista de bloqueados.
