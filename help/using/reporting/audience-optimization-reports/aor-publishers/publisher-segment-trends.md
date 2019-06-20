---
description: El informe Tendencia de segmento devuelve datos sobre impresiones y tasas de pulsaciones de segmentos asignados y sin asignar a lo largo del tiempo. Un segmento asignado es un segmento que crea y envía a un destino para la segmentación. Un segmento sin asignar es un segmento que ha creado pero que no se ha enviado a un destino para la segmentación. Compare tendencias y volumen de las métricas seleccionadas para obtener una mejor imagen de cómo se comportan las audiencias con el paso del tiempo.
seo-description: El informe Tendencia de segmento devuelve datos sobre impresiones y tasas de pulsaciones de segmentos asignados y sin asignar a lo largo del tiempo. Un segmento asignado es un segmento que crea y envía a un destino para la segmentación. Un segmento sin asignar es un segmento que ha creado pero que no se ha enviado a un destino para la segmentación. Compare tendencias y volumen de las métricas seleccionadas para obtener una mejor imagen de cómo se comportan las audiencias con el paso del tiempo.
seo-title: Informe Tendencia del segmento
solution: Audience Manager
title: Informe Tendencia del segmento
uuid: f 84 e 8 d 0 a -74 e 5-430 c-b 61 c-efb 696 faee 93
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Trend Report{#segment-trend-report}

El informe Tendencia de segmento devuelve datos sobre impresiones y tasas de pulsaciones de segmentos asignados y sin asignar a lo largo del tiempo.

Un segmento asignado es un segmento que crea y envía a un destino para la segmentación. Un segmento sin asignar es un segmento que ha creado pero que no se ha enviado a un destino para la segmentación.

Compare tendencias y volumen de las métricas seleccionadas para obtener una mejor imagen de cómo se comportan las audiencias con el paso del tiempo.

## Caso de uso {#use-cases}

Use the [!UICONTROL Segment Trend] report to validate a segment&#39;s performance over time and to pinpoint trends based on strong performance or scale.

Con este informe, puede saber qué propiedades web muestran una caída o un aumento defecty y solucionar los problemas según sea necesario. This report is the next step after you identify your audience of interest in the [!UICONTROL Segment Performance] report, to ensure that the strong or poor performance you saw in the [!UICONTROL Segment Performance] tab is consistent over time.

## Using the Segment Trend Report {#using-the-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Adjust the look-back window with the **[!UICONTROL Date Through]** slider.

Click any of the segments under the **[!UICONTROL Date Through]** slider to bring up the option to keep only that segment in the report or exclude it.

Use the **[!UICONTROL Line Item]** drop-down box to select the properties in your portfolio for which you want to return information.

In the **[!UICONTROL Segment Data Source]** drop-down box, select the data sources containing the segments you want to see in the report.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item] IDs, as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item] ID.

## Interpreting the Results {#interpreting-results}

[!UICONTROL Segment Trend] El informe devuelve datos en un gráfico de líneas solamente para un intervalo de 14 días. En este ejemplo, el informe muestra las tendencias de impresión y pulsaciones de un conjunto de segmentos asignados y sin asignar.

Pase el ratón sobre cualquier línea para obtener más información sobre esa tendencia de segmento en particular. Consulte las descripciones de la información adicional en la tabla debajo del informe de muestra.

![](assets/publisher_segment_trend.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmento</span> </p> </td> 
   <td colname="col2"> <p>Nombre alfanumérico asignado a este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID de segmento</span> </p> </td> 
   <td colname="col2"> <p>ID exclusivo de este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Elemento de línea</span> </p> </td> 
   <td colname="col2"> <p>La propiedad web para la cual está viendo este informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Clics</span> </p> </td> 
   <td colname="col2"> <p>Cantidad de veces que los miembros de esta característica han hecho clic en los elementos de su propiedad web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impresiones</span> </p> </td> 
   <td colname="col2"> <p>Número de veces que los miembros de esta característica han sido expuestos al inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Tasa de pulsaciones. Esta métrica rellena el porcentaje de impresiones seguido por clics. Dividir clics por impresiones para obtener esta métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Únicos de segmentos</span> </p> </td> 
   <td colname="col2"> <p>Número de miembros del segmento, dentro de los últimos 30 días. </p> </td> 
  </tr> 
 </tbody> 
</table>
