---
description: El DCS supervisa los ID que recibe y añade a una lista de bloqueados los que se envían a una tasa inusualmente alta en un corto período de tiempo.
keywords: id;monitorización;dcs
seo-description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
seo-title: ID Monitoring and Denylisting
solution: Audience Manager
title: Monitorización de ID e Inclusión en la lista de bloqueados de
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
TQID: https://experienceleague.adobe.com/Aie0--aKCVUpPA5pySiDy08Uia8byRLcwVqRe3XEHp0
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 487
ht-degree: 0%

---

# Monitorización de ID e Inclusión en la lista de bloqueados de

El [!DNL DCS] supervisa los identificadores que recibe y agrega a una lista de bloqueados los que se envían a una tasa inusualmente alta en un corto período de tiempo.

## Información general

Para proteger la infraestructura de Audience Manager contra actividades malintencionadas, [!DNL DCS] usa un algoritmo avanzado para supervisar los identificadores que recibe. Pueden ser [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) o [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulte [Índice de ID en Audience Manager](../../../reference/ids-in-aam.md) para obtener una explicación detallada de los ID compatibles con Audience Manager.

[!DNL DCS] supervisa la frecuencia con la que recibe estos identificadores para detectar posibles actividades malintencionadas. Cuando [!DNL DCS] detecta una cantidad inusualmente grande de [!DNL DCS] solicitudes para cualquier ID determinado en un corto período de tiempo, ese ID se agrega a una lista de bloqueados.

## Códigos de error

Puede identificar los identificadores agregados a una lista de bloqueados por los códigos de error recibidos del [!DNL DCS]. Los códigos de error que puede recibir son los siguientes:

* 303: ID de cliente bloqueado;
* 306: ID de dispositivo declarado bloqueado;
* 307: Operación de perfil bloqueada para el ID.

Consulte [Códigos de error DCS, mensajes y ejemplos](dcs-error-codes.md) para obtener más información sobre los códigos de error que puede recibir.

## Eliminación de ID de listas de bloqueados

Los ID que se hayan añadido a las listas de bloqueados no deben utilizarse en ninguna solicitud futura, ya que producirán informes de datos incorrectos. [!DNL DCS] no admite la eliminación de identificadores de listas de bloqueados.

## Impacto en la sincronización de ID

[!DNL DCS] llamadas pueden incluir uno o varios tipos de ID. Las llamadas que contienen un solo ID se ignoran por completo si ese ID se añade a una lista de bloqueados y no se produce ninguna sincronización de ID en esta situación.

Cuando una llamada de ID múltiple también incluye un ID de, [!DNL DCS] ignora el ID denegado y solo utiliza los ID restantes permitidos para la sincronización.

## Causas y correcciones de la Inclusión en la lista de bloqueados de ID de la

La causa más frecuente de que se añadan ID a las listas de bloqueados es la integración incorrecta entre la infraestructura del cliente y Audience Manager. Cuando identifique un ID de, asegúrese de revisar a fondo las integraciones de Audience Manager. Consulte **Guías de implementación e integración** para obtener explicaciones detalladas sobre cómo debe configurar Audience Manager para que funcione con otras soluciones de Experience Cloud o sistemas externos.

Otra causa frecuente de que se agreguen ID a las listas de bloqueados son los bots de indexación (rastreadores web), que generalmente provocan aumentos en el tráfico, lo que lleva a que los mismos ID se envíen a [!DNL DCS] varias veces. Si identifica bots de indexación como el motivo por el que los ID se añaden a las listas de bloqueados, debe restringir el acceso de bots a su sitio web.

Si tiene dificultades para identificar los problemas de integración, no dude en ponerse en contacto con Asistencia al cliente. Antes de abrir una solicitud de soporte técnico, asegúrese de mantener preparado el archivo `.har` `HTTP` de su explorador. Este archivo ayuda al equipo de asistencia a identificar por qué se añadió el ID a una lista de bloqueados.
