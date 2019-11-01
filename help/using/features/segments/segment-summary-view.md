---
description: La página de resumen de segmentos muestra detalles como nombre, características en el segmento, reglas, datos de rendimiento e información de asignación de destino.
seo-description: La página de resumen de segmentos muestra detalles como nombre, características en el segmento, reglas, datos de rendimiento e información de asignación de destino.
seo-title: Página Detalles del segmento
solution: Audience Manager
title: Página Detalles del segmento
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: desglose de tipo de identidad, desglose de identidad, informe de identidad de audiencia
translation-type: tm+mt
source-git-commit: 51f38819bfbc72c2588f63a63fb8ba2e963919ff

---


# Página Detalles del segmento {#segment-summary-view}

La página de detalles de un segmento individual proporciona una visión general de los detalles del segmento, como el nombre del segmento, el ID, las métricas de rendimiento, las reglas que definen el segmento y las asignaciones de destino. Para ver estos detalles, vaya a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Segments]** y haga clic en el nombre del segmento con el que desee trabajar.

## Herramientas de administración de segmentos {#segment-management-tools}

En la parte superior de la página de detalles del segmento se encuentran las herramientas que puede utilizar para administrar los segmentos:

1. **[!UICONTROL Add New]**:: Utilice esta opción para activar [!UICONTROL Segment Builder] y crear nuevos segmentos.
2. **[!UICONTROL Edit]**:: Utilice esta opción para cambiar la configuración del segmento actual.
3. **[!UICONTROL Duplicate]**:: Utilice esta opción para crear una copia del segmento actual.
4. **[!UICONTROL Delete]**:: Utilice esta opción para eliminar el segmento actual de su cuenta de Audience Manager.
5. **[!UICONTROL Marketplace Recommendations]**:: Utilice esta opción para encontrar segmentos similares a los que está viendo, desde fuentes de datos a las que no está suscrito [!UICONTROL Audience Marketplace] . Consulte [Audience Marketplace for Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) para obtener información sobre cómo navegar por el mercado y encontrar segmentos similares.

![basic-segment-information](assets/basic-segment-information.png)

## Información del segmento {#basics}

Debajo de las herramientas de administración de segmentos encontrará la siguiente información de segmentos:

1. **[!UICONTROL Basic Information]** :: Muestra los detalles opcionales y requeridos especificados cuando se creó el segmento. Consulte Generador [de segmentos](segment-builder.md) para obtener información general detallada sobre el significado de estos campos.
2. **[!UICONTROL Segment Graph]** :: Muestra datos de rendimiento gráficamente y para intervalos fijos de 1, 7, 14, 30, 60 y 90 días. Explicamos los números de población de segmentos en un artículo [](../../features/segments/segment-builder-data.md)independiente.

   ![segmentos-gráfico](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]** :: El informe muestra el número de personas o hogares que cumplen los requisitos para un segmento contando el número de ID entre dispositivos y/o ID de gráficos de dispositivos externos que están vinculados a los dispositivos que cumplen los requisitos para el segmento (como muestra el [!UICONTROL Total Segment Population]). Los ID entre dispositivos y los ID de Device Graph externos que se muestran en este informe se utilizan para combinar perfiles con la regla de combinación de perfiles que utiliza el segmento. Este informe se muestra únicamente si seleccionó un origen de datos entre dispositivos o un gráfico de dispositivo externo en la regla de combinación de perfiles que utiliza el segmento.

   ![segmentos-gráfico](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager solo muestra el [!UICONTROL Identity Type Breakdown] informe si tiene ID entre dispositivos calificados para el segmento.

   Vea el siguiente vídeo para obtener información general sobre [!UICONTROL Identity Type Breakdown].
   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=spa)

4. **[!UICONTROL Segment Rules]** :: Enumera las características del segmento junto con las reglas de clasificación.
5. **[!UICONTROL Destination Mappings]** :: Enumera las asignaciones de destino para el segmento.
6. **[!UICONTROL Management Tools]** :: Controles que permiten crear, editar, clonar y eliminar segmentos.