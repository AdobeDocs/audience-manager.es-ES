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
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# Monitorización de ID e Inclusión en la lista de bloqueados de

El [!DNL DCS] controla los ID que recibe y añade a una lista de bloqueados los que se envían a una tasa inusualmente alta en un corto periodo de tiempo.

## Información general

Para proteger la infraestructura del Audience Manager frente a actividades malintencionadas, la variable [!DNL DCS] utiliza un algoritmo avanzado para monitorizar los ID que recibe. Pueden ser [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), o [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulte [Índice de ID en el Audience Manager](../../../reference/ids-in-aam.md) para obtener explicaciones detalladas de los ID admitidos por Audience Manager.

El [!DNL DCS] controla la frecuencia con la que recibe estos ID para detectar posibles actividades maliciosas. Si la variable [!DNL DCS] detecta una cantidad inusualmente grande de [!DNL DCS] solicitudes de cualquier ID determinado en un corto período de tiempo, ese ID se agrega a una lista de bloqueados.

## Códigos de error

Puede identificar los ID añadidos a una lista de bloqueados mediante los códigos de error recibidos del [!DNL DCS]. Los códigos de error que puede recibir son los siguientes:

* 303: ID de cliente bloqueado;
* 306: ID de dispositivo declarado bloqueado;
* 307: Operación de perfil bloqueada para el ID.

Consulte [Códigos de error DCS, mensajes y ejemplos](dcs-error-codes.md) para obtener más información sobre los códigos de error que puede recibir.

## Eliminación de ID de listas de bloqueados

Los ID que se hayan añadido a las listas de bloqueados no deben utilizarse en ninguna solicitud futura, ya que producirán informes de datos incorrectos. El [!DNL DCS] no admite la eliminación de ID de listas de bloqueados.

## Impacto en la sincronización de ID

[!DNL DCS] Las llamadas de pueden incluir uno o varios tipos de ID. Las llamadas que contienen un solo ID se ignoran por completo si ese ID se añade a una lista de bloqueados y no se produce ninguna sincronización de ID en esta situación.

Incluida en la lista de bloqueados Cuando una llamada de ID múltiple también incluye un ID de, la variable [!DNL DCS] ignora el ID denegado y solo utiliza los ID restantes permitidos para la sincronización.

## Causas y correcciones de la Inclusión en la lista de bloqueados de ID de los

La causa más frecuente de que se añadan ID a las listas de bloqueados es la integración incorrecta entre la infraestructura del cliente y el Audience Manager. Incluida en la lista de bloqueados Cuando identifique un ID de, asegúrese de revisar a fondo las integraciones de Audience Manager. Consulte **Guías de implementación e integración** para obtener explicaciones detalladas sobre cómo debe configurar Audience Manager para que funcione con otras soluciones de Experience Cloud o sistemas externos.

Otra causa frecuente de que se añadan ID a las listas de bloqueados son los bots de indexación (rastreadores web), que generalmente provocan aumentos en el tráfico, lo que provoca que se envíen los mismos ID a [!DNL DCS] varias veces. Si identifica bots de indexación como el motivo por el que los ID se añaden a las listas de bloqueados, debe restringir el acceso de bots a su sitio web.

Si tiene dificultades para identificar los problemas de integración, no dude en ponerse en contacto con Asistencia al cliente. Antes de abrir una solicitud de asistencia, asegúrese de mantener el `.har` `HTTP` archivo de su explorador listo. Este archivo ayuda al equipo de asistencia a identificar por qué se añadió el ID a una lista de bloqueados.
