---
description: ELIMINAR y POST que permiten eliminar destinos y asignaciones de segmentos.
seo-description: ELIMINAR y POST que permiten eliminar destinos y asignaciones de segmentos.
seo-title: Eliminar destinos
solution: Audience Manager
title: Eliminar destinos
uuid: 38 fb 2228-e 564-49 a 3-9930-3139 f 8799 a 8 f
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Delete Destinations {#delete-destinations}

`DELETE` y `POST` métodos que permiten eliminar destinos y asignaciones de segmentos.

<!-- r_delete_destinations_all.xml -->

## Eliminar un destino

`DELETE` Método que elimina un destino.

>[!NOTE]
>
>Debe quitar todas las asignaciones de segmentos para poder eliminar un destino.

* Request: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Response: Returns code `204 No Content` if successful.

## Eliminación masiva Destinos

Remove multiple destinations with this `POST` method. Pass in destination IDs ( `destinationId`) with an array in the request body.

* Solicitud: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Response: Returns code `204 No Content` if successful.

## Eliminar asignaciones de destino por ID de asignación de segmentos

`POST` Método que quita asignaciones de destino según el ID de segmento especificado.

* Request: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Response: Returns code `204 No Content` if successful.