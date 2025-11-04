---
description: La página de resumen del segmento muestra detalles como el nombre, las características del segmento, las reglas, los datos de rendimiento y la información de asignación de destino.
seo-description: The segment summary page displays details such as name, traits in the segment, rules, performance data, and destination mapping information.
seo-title: Segment Details Page
solution: Audience Manager
title: Página Detalles del Segmento
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: desglose de tipo de identidad, desglose de identidad, informes de identidad de audiencia, entre dispositivos, ID de varios dispositivos, ID de dispositivo
feature: Segments
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# Página Detalles del Segmento {#segment-summary-view}

La página de detalles de un segmento individual proporciona información general sobre los detalles del segmento, como el nombre del segmento, el ID, las métricas de rendimiento, las reglas que definen el segmento y las asignaciones de destino. Para ver estos detalles, vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** y haga clic en el nombre del segmento con el que desea trabajar.

## Herramientas de administración de segmentos {#segment-management-tools}

La parte superior de la página de detalles del segmento aloja las herramientas que puede utilizar para administrar los segmentos:

1. **[!UICONTROL Add New]**: utilice esta opción para activar [!UICONTROL Segment Builder] y crear nuevos segmentos.
2. **[!UICONTROL Edit]**: utilice esta opción para cambiar la configuración del segmento actual.
3. **[!UICONTROL Duplicate]**: utilice esta opción para crear una copia del segmento actual.
4. **[!UICONTROL Delete]**: utilice esta opción para eliminar el segmento actual de su cuenta de Audience Manager.
5. **[!UICONTROL Marketplace Recommendations]**: use esta opción para encontrar segmentos similares al que está viendo, de [!UICONTROL Audience Marketplace] fuentes de datos a las que no está suscrito. Consulte [Audience Marketplace para compradores de datos](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) para obtener información sobre cómo navegar por el mercado y encontrar segmentos similares.

![información básica del segmento](assets/basic-segment-information.png)

## Información del segmento {#basics}

Debajo de las herramientas de administración de segmentos puede encontrar la siguiente información sobre segmentos:

1. **[!UICONTROL Basic Information]:** Muestra los detalles opcionales y requeridos especificados cuando se creó el segmento. Consulte [Generador de segmentos](segment-builder.md) para obtener una descripción detallada de lo que significan estos campos.
1. **[!UICONTROL Segment Graph]:** muestra los datos de rendimiento gráficamente y en intervalos fijos de 1, 7, 14, 30, 60 y 90 días. Explicamos los números de población de segmentos en [artículo independiente](../../features/segments/segment-builder-data.md).

   ![segmentos-gráfico](assets/segment-graph.png)

1. **[!UICONTROL Identity Type Breakdown]:** El informe muestra el número de personas o hogares que cumplen los requisitos para un segmento contando el número de ID de dispositivos cruzados o ID de gráficos de dispositivos externos vinculados a los dispositivos aptos para el segmento (mostrados por [!UICONTROL Total Segment Population]). Los ID de dispositivos cruzados y los ID de gráficos de dispositivos externos que se muestran en este informe se utilizan para combinar perfiles con la regla de combinación de perfiles que utiliza el segmento. Este informe se muestra únicamente si ha seleccionado un origen de datos entre dispositivos o un gráfico de dispositivos externos en la regla de combinación de perfiles que utiliza el segmento.

   ![segmentos-gráfico](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager solo muestra el informe [!UICONTROL Identity Type Breakdown] si cuenta con ID de varios dispositivos calificados para el segmento.

   Vea el siguiente vídeo para obtener información general sobre [!UICONTROL Identity Type Breakdown].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

1. **[!UICONTROL Segment Rules]:** Enumera los rasgos del segmento junto con las reglas de calificación.
1. **[!UICONTROL Destination Mappings]:** Enumera asignaciones de destino para el segmento.
1. **[!UICONTROL Management Tools]:** Controles que le permiten crear, editar, clonar y eliminar segmentos.
