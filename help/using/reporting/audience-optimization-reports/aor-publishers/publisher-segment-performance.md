---
description: El informe Rendimiento de segmento compara segmentos asignados y sin asignar por impresiones y únicos de segmentos en tiempo real. Un segmento asignado es un segmento que crea y envía a un destino para la segmentación. Un segmento sin asignar es un segmento que ha creado pero que no se ha enviado a un destino para la segmentación. La comparación de estos diferentes tipos de segmentos dentro y entre informes ayuda a optimizar las campañas existentes y encuentra los segmentos ignorados que quizá desee enviar a un destino para la segmentación.
seo-description: El informe Rendimiento de segmento compara segmentos asignados y sin asignar por impresiones y únicos de segmentos en tiempo real. Un segmento asignado es un segmento que crea y envía a un destino para la segmentación. Un segmento sin asignar es un segmento que ha creado pero que no se ha enviado a un destino para la segmentación. La comparación de estos diferentes tipos de segmentos dentro y entre informes ayuda a optimizar las campañas existentes y encuentra los segmentos ignorados que quizá desee enviar a un destino para la segmentación.
seo-title: Informe Rendimiento del segmento
solution: Audience Manager
title: Informe Rendimiento del segmento
uuid: c 9 a 1 e 9 ad -4 f 3 f -4334-a 3 ff -0 f 241 c 7303 c 4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Performance Report{#segment-performance-report}

El informe Rendimiento de segmento compara segmentos asignados y sin asignar por impresiones y únicos de segmentos en tiempo real.

Un segmento asignado es un segmento que crea y envía a un destino para la segmentación. Un segmento sin asignar es un segmento que ha creado pero que no se ha enviado a un destino para la segmentación.

La comparación de estos diferentes tipos de segmentos dentro y entre informes ayuda a optimizar las campañas existentes y encuentra los segmentos ignorados que quizá desee enviar a un destino para la segmentación.

## Casos de uso {#use-cases}

With the [!UICONTROL Segment Performance] report, you can:

* Identifique los segmentos de audiencia asignados que generan escala o rendimiento.
* Identifique los segmentos sin asignar que se introducen en futuras campañas, según la contribución de una audiencia al rendimiento anterior.

## Using the Segment Performance Report {#using-segment-performance-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. Tenga en cuenta que los períodos de retroceso de 7 días y 30 días solo están disponibles para las fechas del domingo.

Use the **[!UICONTROL Line Item]** drop-down box to select the web properties for which you want to return information.

In the **[!UICONTROL Segment Data Source]** drop-down box, select the data sources containing the segments you want to see in the report.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item ID].

## Interpreting the Results {#interpreting-results}

Your [!UICONTROL Segment Performance] report could look similar to the one below. En el informe, haga clic en una burbuja para ver los datos subyacentes. Consulte las descripciones de la información adicional en la tabla debajo del informe de muestra.

![](assets/publisher_segment_performance.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Segmento </p> </td> 
   <td colname="col2"> <p>Nombre alfanumérico asignado a este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de segmento </p> </td> 
   <td colname="col2"> <p>ID exclusivo de este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Elemento de línea </p> </td> 
   <td colname="col2"> <p>La propiedad web para la cual está viendo este informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Clics </p> </td> 
   <td colname="col2"> <p>Cantidad de veces que los miembros de esta característica han hecho clic en los elementos de su propiedad web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impresiones </p> </td> 
   <td colname="col2"> <p>Número de veces que los miembros de esta característica han sido expuestos al inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Tasa de pulsaciones. </p> <p>Esta métrica rellena el porcentaje de impresiones seguido por clics. Dividir clics por impresiones para obtener esta métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Población en segmentos en tiempo real </p> </td> 
   <td colname="col2"> <p>The actual number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## How to Read Your Mapped Segment Results {#read-mapped-segment}

La posición de los segmentos asignados en un informe puede indicarle mucho sobre qué segmentos están funcionando bien y dónde debe realizar algunos ajustes.

Para leer el informe, ayuda a dividir los resultados en cuatro secciones con líneas imaginarias (en rojo) y las categorías que se muestran en el informe de muestra siguiente. Las etiquetas del ejemplo pueden ayudarle a comprender el rendimiento de los segmentos y cómo responder a estos resultados.

![](assets/publisher_segment_performance_mapped.png)

## How to Read Your Unmapped Segment Results {#read-unmapped-segment}

Looking at unmapped segments in a [!UICONTROL Segment Performance] report is a great way to find new segments you haven&#39;t considered for targeting. De hecho, algunos de estos segmentos pueden superar los segmentos asignados.

Para leer este informe, ayuda a dividir los resultados en cuatro secciones con líneas imaginarias (en rojo) y categorías que se muestran en el informe de muestra siguiente.

![](assets/publisher_segment_performance_unmapped.png)
