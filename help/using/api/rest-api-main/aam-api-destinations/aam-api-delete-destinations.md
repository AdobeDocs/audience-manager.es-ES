---
description: Métodos de DELETE y POST que permiten eliminar destinos y asignaciones de segmentos.
seo-description: Métodos de DELETE y POST que permiten eliminar destinos y asignaciones de segmentos.
seo-title: Eliminar destinos
solution: Audience Manager
title: Eliminar destinos
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 7%

---


# Eliminar destinos {#delete-destinations}

`DELETE` y  `POST` métodos que permiten eliminar destinos y asignaciones de segmentos.

<!-- r_delete_destinations_all.xml -->

## Eliminar un destino

Un método `DELETE` que elimina un destino.

>[!NOTE]
>
>Debe eliminar todas las asignaciones de segmentos para poder eliminar un destino.

* Solicitud: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Respuesta: Devuelve el código `204 No Content` si es correcto.

## Destinos de eliminación masiva

Elimine varios destinos con este método `POST`. Pasar los ID de destino ( `destinationId`) con una matriz en el cuerpo de la solicitud.

* Solicitud: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Respuesta: Devuelve el código `204 No Content` si es correcto.

## Eliminar asignaciones de destino por ID de asignación de segmentos

Un método `POST` que elimina las asignaciones de destino según el ID de segmento especificado.

* Solicitud: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Respuesta: Devuelve el código `204 No Content` si es correcto.