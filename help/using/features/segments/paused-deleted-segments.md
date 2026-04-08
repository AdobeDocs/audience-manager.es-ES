---
description: Describe los efectos en los usuarios, datos y destinos segmentados cuando pone en pausa o elimina un segmento activo mediante el Generador de segmentos.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: Segmentos en pausa y eliminados
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
TQID: https://experienceleague.adobe.com/aLnmaOxB3fkGdwq4XjKz8SFKizwHI7Ll5rBUb-o34BM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: c2c33729-f309-4bc2-92ba-87c475259df3
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 0%

---

# Segmentos en pausa y eliminados {#paused-and-deleted-segments}

Describe los efectos en los usuarios, datos y destinos segmentados cuando se pone en pausa o se elimina un segmento activo mediante [!UICONTROL Segment Builder].

## Acceso a los controles de pausa y eliminación

Pase el ratón sobre un nombre de segmento en la lista de segmentos para ver los iconos **[!UICONTROL pause]** y **[!UICONTROL delete]** (en la columna [!UICONTROL Actions]). Estas funciones afectan a los segmentos como se describe a continuación.

## Funcionalidad de segmento en pausa

Un segmento en pausa (desactivado):

* Deja de segmentar usuarios nuevos y cualificados.
* Conserva el estado de segmentación/pertenencia de un usuario (no elimina a un usuario del segmento).
* Permanece en la lista de segmentos y se puede reactivar.
* No envía datos a destinos asociados.
* Devuelve datos en los informes disponibles (hasta la fecha de desactivación).

## Funcionalidad de segmento eliminada

Un segmento eliminado:

* Deja de segmentar usuarios nuevos y cualificados.
* Elimina a los usuarios cualificados del abono a segmentos.
* Se elimina de la lista de segmentos.
* No se puede deshacer la eliminación.
* No envía datos a destinos asociados.
* No devuelve datos en los informes disponibles.

>[!NOTE]
>
>También puede pausar y eliminar segmentos mediante un método [!DNL API]. Para obtener más información, consulte [API de REST](../../api/rest-api-main/rest-api-main.md).
