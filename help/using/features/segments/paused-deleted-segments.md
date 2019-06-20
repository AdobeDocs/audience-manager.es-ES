---
description: Describe los efectos en los usuarios segmentados, los datos y los destinos al pausar o eliminar un segmento activo mediante el Generador de segmentos.
seo-description: Describe los efectos en los usuarios segmentados, los datos y los destinos al pausar o eliminar un segmento activo mediante el Generador de segmentos.
seo-title: Segmentos en pausa y eliminados
solution: Audience Manager
title: Segmentos en pausa y eliminados
uuid: 88 efe 4 af-f 9 a 4-4 bce -920 a -352 bd 4 d 505 dd
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Paused and Deleted Segments {#paused-and-deleted-segments}

Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using [!UICONTROL Segment Builder].

## Acceso a los controles de pausa y eliminación

Hover over a segment name in the segments list to expose the **[!UICONTROL pause]** and **[!UICONTROL delete]** icons (in the [!UICONTROL Actions] column). Estas funciones afectan a los segmentos como se describe a continuación.

## Funcionalidad de segmentos en pausa

Un segmento pausado (desactivado):

* Detiene la segmentación de usuarios nuevos y cualificados.
* Retiene el estado o la pertenencia de un usuario (no elimina a un usuario del segmento).
* Permanece en la lista de segmentos y se puede reactivar.
* No envía datos a destinos asociados.
* Devuelve datos en los informes disponibles (hasta la fecha de desactivación).

## Funcionalidad de segmentos eliminada

Segmento eliminado:

* Detiene la segmentación de usuarios nuevos y cualificados.
* Elimina a los usuarios cualificados de la pertenencia a segmentos.
* Se elimina de la lista de segmentos.
* No se puede eliminar.
* No envía datos a destinos asociados.
* No devuelve datos en los informes disponibles.

>[!NOTE]
>
>You can also pause and delete segments using an [!DNL API] method. For more information, see [REST APIs](../../api/rest-api-main/rest-api-main.md).