---
description: Métodos ELIMINAR y POST que permiten eliminar destinos y asignaciones de segmentos.
seo-description: Métodos ELIMINAR y POST que permiten eliminar destinos y asignaciones de segmentos.
seo-title: Eliminar destinos
solution: Audience Manager
title: Eliminar destinos
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Eliminar destinos {#delete-destinations}

`DELETE` y `POST` métodos que le permiten eliminar destinos y asignaciones de segmentos.

<!-- r_delete_destinations_all.xml -->

## Eliminar un destino

Un `DELETE` método que elimina un destino.

>[!NOTE]
>
>Debe eliminar todas las asignaciones de segmentos para poder eliminar un destino.

* Request: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Respuesta: Devuelve el código `204 No Content` si se realiza correctamente.

## Destinos de eliminación masiva

Elimine varios destinos con este `POST` método. Pasar los ID de destino ( `destinationId`) con una matriz en el cuerpo de la solicitud.

* Solicitud: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Respuesta: Devuelve el código `204 No Content` si se realiza correctamente.

## Eliminar asignaciones de destino por ID de asignación de segmentos

Un `POST` método que elimina las asignaciones de destino según el ID de segmento especificado.

* Request: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Respuesta: Devuelve el código `204 No Content` si se realiza correctamente.