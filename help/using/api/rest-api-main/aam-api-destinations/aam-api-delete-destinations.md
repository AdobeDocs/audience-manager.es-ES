---
description: Métodos de DELETE y POST que permiten eliminar destinos y asignaciones de segmentos.
seo-description: Métodos de DELETE y POST que permiten eliminar destinos y asignaciones de segmentos.
seo-title: Eliminar destinos
solution: Audience Manager
title: Eliminar destinos
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 8%

---

# Eliminar destinos {#delete-destinations}

`DELETE` y  `POST` métodos que permiten eliminar destinos y asignaciones de segmentos.

<!-- r_delete_destinations_all.xml -->

## Eliminar un destino

Método `DELETE` que elimina un destino.

>[!NOTE]
>
>Debe eliminar todas las asignaciones de segmentos antes de poder eliminar un destino.

* Solicitud: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Respuesta: Devuelve el código `204 No Content` si se realiza correctamente.

## Destinos de eliminación masiva

Elimine varios destinos con este método `POST`. Pasa los ID de destino ( `destinationId`) con una matriz en el cuerpo de la solicitud.

* Solicitud: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Respuesta: Devuelve el código `204 No Content` si se realiza correctamente.

## Eliminar asignaciones de destino por ID de asignación de segmentos

Método `POST` que elimina las asignaciones de destino según el ID de segmento especificado.

* Solicitud: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Respuesta: Devuelve el código `204 No Content` si se realiza correctamente.
