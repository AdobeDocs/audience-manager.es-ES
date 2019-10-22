---
description: La página de resumen de segmentos muestra detalles como nombre, características en el segmento, reglas, datos de rendimiento e información de asignación de destino.
seo-description: La página de resumen de segmentos muestra detalles como nombre, características en el segmento, reglas, datos de rendimiento e información de asignación de destino.
seo-title: Vista de resumen de segmentos
solution: Audience Manager
title: Vista de resumen de segmentos
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: desglose de tipo de identidad, desglose de identidad, informe de identidad de audiencia
translation-type: tm+mt
source-git-commit: 345042673a9ee7abdac994d774e5c4c893a78749

---


# Vista de resumen de segmentos {#segment-summary-view}

La [!UICONTROL Segment Summary] página muestra detalles como nombre, características en el segmento, datos de rendimiento de reglas e información de asignación de destinos.

Haga clic en el nombre de un segmento desde el tablero principal para acceder a su página de resumen. Las secciones de resumen incluyen:

1. **[!UICONTROL Basic Information]** :: Muestra los detalles opcionales y requeridos especificados cuando se creó el segmento.
2. **[!UICONTROL Segment Graph]** :: Muestra datos de rendimiento gráficamente y para intervalos fijos de 1, 7, 14, 30, 60 y 90 días. Explicamos los números de población de segmentos en un artículo [](../../features/segments/segment-builder-data.md)independiente.

   ![segmentos-gráfico](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]** :: El informe muestra el número de personas o hogares que cumplen los requisitos para un segmento contando el número de ID entre dispositivos y/o ID de gráficos de dispositivos externos que están vinculados a los dispositivos que cumplen los requisitos para el segmento (como muestra el [!UICONTROL Total Segment Population]). Los ID entre dispositivos y los ID de Device Graph externos que se muestran en este informe se utilizan para combinar perfiles con la regla de combinación de perfiles que utiliza el segmento. Este informe se muestra únicamente si seleccionó un origen de datos entre dispositivos o un gráfico de dispositivo externo en la regla de combinación de perfiles que utiliza el segmento.

   ![segmentos-gráfico](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager solo muestra el [!UICONTROL Identity Type Breakdown] informe si tiene ID entre dispositivos calificados para el segmento.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=spa)

4. **[!UICONTROL Segment Rules]** :: Enumera las características del segmento junto con las reglas de clasificación.
5. **[!UICONTROL Destination Mappings]** :: Enumera las asignaciones de destino para el segmento.
6. **[!UICONTROL Management Tools]** :: Controles que permiten crear, editar, clonar y eliminar segmentos.