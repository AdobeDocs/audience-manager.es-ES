---
description: La página de resumen de segmentos muestra detalles como nombre, características en el segmento, reglas, datos de rendimiento y información de asignación de destino.
seo-description: La página de resumen de segmentos muestra detalles como nombre, características en el segmento, reglas, datos de rendimiento y información de asignación de destino.
seo-title: Vista Resumen de segmentos
solution: Audience Manager
title: Vista Resumen de segmentos
uuid: e 844 e 423-9701-42 d 4-9 ba 5-d 82 f 41358 adc
translation-type: tm+mt
source-git-commit: 263c55e6bd2c9ad7159306fc889b048d800c59da

---


# Vista Resumen de segmentos {#segment-summary-view}

La [!UICONTROL Segment Summary] página muestra detalles como nombre, características en el segmento, datos de rendimiento de reglas y información de asignación de destino.

Haga clic en el nombre de un segmento del tablero principal para acceder a su página de resumen. Las secciones de resumen incluyen:

1. **[!UICONTROL Basic Information]:** Muestra los detalles opcionales y requeridos cuando se creó el segmento.
2. **[!UICONTROL Segment Graph]:** Muestra gráficamente los datos de rendimiento y los intervalos fijo 1, 7, 14, 30, 60 y 90 días. Explicamos los números de población de segmentos en un documento [independiente](../../features/segments/segment-builder-data.md).

   ![gráfico de segmentos](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:** El informe muestra el número de personas o familias que califican para un segmento contando la cantidad de ID entre dispositivos y/o ID de gráfico de dispositivos externos que están vinculados a los dispositivos que califican para el segmento (mostrado por [!UICONTROL Total Segment Population]el). Los ID entre dispositivos y los ID externos de gráficos de dispositivos que se muestran en este informe se utilizan para combinar perfiles con la regla de combinación de perfiles que utiliza el segmento. Este informe se muestra únicamente si ha seleccionado una fuente de datos entre dispositivos o un gráfico de dispositivos externos en la regla de combinación de perfiles que utiliza el segmento.

   ![gráfico de segmentos](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager solo muestra el [!UICONTROL Identity Type Breakdown] informe si tiene ID entre dispositivos calificados para el segmento.

4. **[!UICONTROL Segment Rules]:** Enumera las características del segmento junto con las reglas de cualificación.
5. **[!UICONTROL Destination Mappings]:** Enumera asignaciones de destino para el segmento.
6. **[!UICONTROL Management Tools]:** Controles que permiten crear, editar, clonar y eliminar segmentos.