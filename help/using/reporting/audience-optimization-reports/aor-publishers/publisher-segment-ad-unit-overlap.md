---
description: El informe de superposición de segmento a unidad de publicidad se muestra como un gráfico de calor que resalta las solapas altas y bajas entre los segmentos de las unidades de publicidad y de Audience Manager.
seo-description: El informe de superposición de segmento a unidad de publicidad se muestra como un gráfico de calor que resalta las solapas altas y bajas entre los segmentos de las unidades de publicidad y de Audience Manager.
seo-title: Superposición de segmento a unidad de publicidad
solution: Audience Manager
title: Superposición de segmento a unidad de publicidad
uuid: aaa 20163-58 aa -42 c 9-8 f 72-a 1 dfb 0 d 20 e 57
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment to Ad Unit Overlap{#segment-to-ad-unit-overlap}

El informe de superposición de segmento a unidad de publicidad se muestra como un gráfico de calor que resalta las solapas altas y bajas entre los segmentos de las unidades de publicidad y de Audience Manager.

## Caso de uso {#use-cases}

With the [!UICONTROL Segment to Ad Unit Overlap] report, you can understand which audiences visit your web properties. The report displays the overlap between members of your [!DNL Audience Manager] segments and the number of visitors to your web properties. Una superposición más alta significa que muchos miembros de un segmento visitan su propiedad web.

## Using the Segment to Ad Unit Overlap Report {#using-the-report}

Use the **[!UICONTROL Top N Ad Units]** and **[!UICONTROL Top N Segments]** controls to select your desired number of ad units and segments for the overlap. Puede seleccionar un número máximo de 100 elementos para cada uno.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. Tenga en cuenta que los períodos de retroceso de 7 días y 30 días solo están disponibles para las fechas del domingo.

Use the **[!UICONTROL Segment Name]** and the **[!UICONTROL Ad Unit]** boxes to filter any of segments and ad units.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

Your [!UICONTROL Segment to Ad Unit Overlap] report could look similar to the one below. Pase el ratón sobre cualquier celda para obtener más información sobre esa superposición concreta. Consulte las descripciones de la información adicional en la tabla debajo del informe de muestra.

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unidad de publicidad </span> </p> </td> 
   <td colname="col2"> <p>Nombre del elemento de inventario. Por ejemplo, puede ser uno de sus sitios web o un artículo del sitio web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento de únicos en tiempo real del segmento</span> </p> </td> 
   <td colname="col2"> <p>The number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Número únicos de unidades de publicidad</span> </p> </td> 
   <td colname="col2"> <p>Número de visitantes para esta unidad de publicidad específica. Esta información se extrae de los registros de DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Superponer recuento de únicos</span> </p> </td> 
   <td colname="col2"> <p>Los miembros del segmento que estaban expuestos al elemento de unidad de publicidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentaje superpuesto</span> </p> </td> 
   <td colname="col2"> <p>La superposición entre las poblaciones de publicidades y segmentos. This is the <span class="wintitle"> Overlap Uniques Count</span>, expressed as a percentage of the <span class="wintitle"> Segment Real Time Uniques</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

