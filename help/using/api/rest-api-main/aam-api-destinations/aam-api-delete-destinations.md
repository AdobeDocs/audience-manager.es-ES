---
description: DELETE y POST métodos que permiten eliminar destinos y segmento asignaciones.
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: Eliminar Destinos
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 0%

---

# Eliminar Destinos {#delete-destinations}

`DELETE` y `POST` métodos que le permiten eliminar destinos y segmento asignaciones.

<!-- r_delete_destinations_all.xml -->

## Eliminar un destino

Un método que quita `DELETE` un destino.

>[!NOTE]
>
>Debe eliminar todas las asignaciones segmento para poder eliminar un destino.

* Pedir: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Respuesta: Devuelve el código `204 No Content` si se realiza correctamente.

## Destinos de Eliminar a granel

Quitar varios destinos con este `POST` método. Pase los ID de destino ( `destinationId`) con una matriz en el cuerpo del solicitud.

* Pedir: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Respuesta: Devuelve el código `204 No Content` si se realiza correctamente.

## Eliminar asignaciones de destinos por ID de asignación de segmentos

Método `POST` que elimina las asignaciones de destino según el ID de segmento especificado.

* Pedir: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Respuesta: Devuelve el código `204 No Content` si se realiza correctamente.
