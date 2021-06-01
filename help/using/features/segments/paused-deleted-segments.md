---
description: Describe los efectos en usuarios, datos y destinos segmentados al pausar o eliminar un segmento activo mediante el Generador de segmentos.
seo-description: Describe los efectos en usuarios, datos y destinos segmentados al pausar o eliminar un segmento activo mediante el Generador de segmentos.
seo-title: Segmentos en pausa y eliminados
solution: Audience Manager
title: Segmentos en pausa y eliminados
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: 'Segmentos '
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 6%

---

# Segmentos en pausa y eliminados {#paused-and-deleted-segments}

Describe los efectos sobre usuarios, datos y destinos segmentados cuando se pone en pausa o se elimina un segmento activo mediante [!UICONTROL Segment Builder].

## Acceso a los controles Pausa y Eliminación

Pase el ratón sobre el nombre de un segmento en la lista de segmentos para mostrar los iconos **[!UICONTROL pause]** y **[!UICONTROL delete]** (en la columna [!UICONTROL Actions]). Estas funciones afectan a los segmentos como se describe a continuación.

## Funcionalidad de segmentos en pausa

Un segmento en pausa (desactivado):

* Detiene la segmentación de usuarios nuevos cualificados.
* Conserva el estado o la pertenencia de un usuario a la segmentación (no elimina a un usuario del segmento).
* Permanece en la lista de segmentos y se puede reactivar.
* No envía datos a destinos asociados.
* Devuelve datos de los informes disponibles (hasta la fecha de desactivación).

## Funcionalidad de segmentos eliminada

Un segmento eliminado:

* Detiene la segmentación de usuarios nuevos cualificados.
* Elimina a los usuarios cualificados de la pertenencia a segmentos.
* Se elimina de la lista de segmentos.
* No se puede eliminar.
* No envía datos a destinos asociados.
* No devuelve datos en los informes disponibles.

>[!NOTE]
>
>También puede pausar y eliminar segmentos mediante un método [!DNL API]. Para obtener más información, consulte [API de REST](../../api/rest-api-main/rest-api-main.md).
