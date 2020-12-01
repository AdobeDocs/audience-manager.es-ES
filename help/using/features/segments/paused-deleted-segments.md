---
description: Describe los efectos en usuarios segmentados, datos y destinos cuando se pausa o elimina un segmento activo mediante el Generador de segmentos.
seo-description: Describe los efectos en usuarios segmentados, datos y destinos cuando se pausa o elimina un segmento activo mediante el Generador de segmentos.
seo-title: Segmentos en pausa y eliminados
solution: Audience Manager
title: Segmentos en pausa y eliminados
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 5%

---


# Segmentos en pausa y eliminados {#paused-and-deleted-segments}

Describe los efectos en los usuarios segmentados, los datos y los destinos al pausar o eliminar un segmento activo mediante [!UICONTROL Segment Builder].

## Acceso a los controles Pausa y Eliminar

Pase el ratón sobre el nombre de un segmento en la lista de segmentos para mostrar los iconos **[!UICONTROL pause]** y **[!UICONTROL delete]** (en la columna [!UICONTROL Actions]). Estas funciones afectan a los segmentos como se describe a continuación.

## Funcionalidad del segmento pausado

Un segmento pausado (desactivado):

* Detiene la segmentación de usuarios nuevos y cualificados.
* Conserva el estado o la pertenencia de segmentación de un usuario (no elimina a un usuario del segmento).
* Permanece en la lista del segmento y se puede reactivar.
* No envía datos a destinos asociados.
* Devuelve los datos de los informes disponibles (hasta la fecha de desactivación).

## Funcionalidad de segmento eliminada

Un segmento eliminado:

* Detiene la segmentación de usuarios nuevos y cualificados.
* Quita a los usuarios cualificados de la pertenencia a segmentos.
* Se elimina de la lista de segmentos.
* No se puede eliminar.
* No envía datos a destinos asociados.
* No devuelve datos en los informes disponibles.

>[!NOTE]
>
>También puede pausar y eliminar segmentos mediante un método [!DNL API]. Para obtener más información, consulte [API de REST](../../api/rest-api-main/rest-api-main.md).