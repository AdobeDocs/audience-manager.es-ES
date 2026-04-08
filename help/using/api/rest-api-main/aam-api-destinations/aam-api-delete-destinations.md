---
description: Métodos DELETE y POST que permiten eliminar destinos y asignaciones de segmentos.
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: Eliminar destinos
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
TQID: https://experienceleague.adobe.com/hONQoLCrSxcMnDY7yPf-RX22Etj3WIykBhKEx1IyRMo
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 104
ht-degree: 0%

---

# Eliminar destinos {#delete-destinations}

Métodos `DELETE` y `POST` que permiten eliminar destinos y asignaciones de segmentos.

<!-- r_delete_destinations_all.xml -->

## Eliminar un destino

Un método `DELETE` que quita un destino.

>[!NOTE]
>
>Debe quitar todas las asignaciones de segmentos para poder eliminar un destino.

* Solicitud: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Respuesta: Devuelve el código `204 No Content` si se realizó correctamente.

## Destinos de eliminación masiva

Quitar varios destinos con este método `POST`. Pase los identificadores de destino (`destinationId`) con una matriz en el cuerpo de la solicitud.

* Solicitud: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Respuesta: Devuelve el código `204 No Content` si se realizó correctamente.

## Eliminar asignaciones de destino por ID de asignación de segmento

Un método `POST` que elimina las asignaciones de destino según el ID de segmento especificado.

* Solicitud: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Respuesta: Devuelve el código `204 No Content` si se realizó correctamente.
