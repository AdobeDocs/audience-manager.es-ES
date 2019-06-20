---
description: El DCS supervisa los ID que recibe y detalla los que se envían a una tasa inusualmente alta en un corto período de tiempo.
keywords: id; monitoreo; blacklisting; dcs
seo-description: El DCS supervisa los ID que recibe y detalla los que se envían a una tasa inusualmente alta en un corto período de tiempo.
seo-title: Control de ID y lista negra
solution: Audience Manager
title: Control de ID y lista negra
uuid: 498 e 0316-cf 1 b -43 e 9-88 ba -338 ee 0 daf 225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Control de ID y lista negra

[!UICONTROL DCS] Los monitores controlan los ID que recibe y lista negra los que se envían a una tasa inusualmente alta en un corto período de tiempo.

## Información general

To protect the Audience Manager infrastructure against malicious activity, the [!UICONTROL DCS] uses an advanced algorithm to monitor the IDs it receives. These can be [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), or [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). See [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md) for detailed explanations of the IDs supported by Audience Manager.

[!UICONTROL DCS] Supervisa la frecuencia con la que recibe estos ID para detectar posibles actividades maliciosas. When the [!UICONTROL DCS] detects an unusually large amount of [!UICONTROL DCS] requests for any given ID in a short amount of time, that ID is blacklisted.

## Códigos de error

You can identify blacklisted IDs by the error codes received from the [!UICONTROL DCS]. Los códigos de error que puede recibir son:

* 303: Bloqueo del ID de cliente;
* 306: Bloqueo del ID del dispositivo declarado;
* 307: Operación de perfil bloqueada para ID.

See [DCS Error Codes, Messages, and Examples](dcs-error-codes.md) for details on the error codes that you may receive.

## Sin bloqueo

Los ID bloqueados no deben usarse en solicitudes futuras, ya que conducen a informes de datos incorrectos. The [!UICONTROL DCS] does not support un-blacklisting of IDs.

## Impacto en la sincronización de ID

[!UICONTROL DCS] puede incluir uno o varios tipos de ID. Las llamadas que contienen un único ID no se tienen en cuenta por completo si el ID está bloqueado y no se produce ninguna sincronización de ID en esta situación.

When a multiple ID call also includes a blacklisted ID, the [!UICONTROL DCS] disregards the blacklisted ID and only uses the remaining, non-blacklisted IDs for synchronization.

## Causas y correcciones para la lista negra de ID

La causa más frecuente de que los ID estén bloqueados es la integración incorrecta entre la infraestructura del cliente y Audience Manager. Cuando identifique un ID bloqueado, asegúrese de revisar minuciosamente las integraciones de Audience Manager. See **Implementation and Integration Guides** for detailed explanations of how you should configure Audience Manager to work with other Experience Cloud solutions or external systems.

Another frequent cause of blacklisted IDs are indexing bots (web crawlers), which generally cause increases in traffic, leading to the same IDs being sent to the [!UICONTROL DCS] multiple times. Si identifica la indexación de bots como la razón para el bloqueo de ID, debe restringir el acceso de bots a su sitio Web.

Si tiene un tiempo difícil para identificar los problemas de integración, no dude en ponerse en contacto con el Servicio de atención al cliente. Prior to opening a support request, make sure to keep the `.har` `HTTP` archive of your browser ready. Este archivo ayuda al equipo de asistencia a identificar por qué se produjo el bloqueo de ID.