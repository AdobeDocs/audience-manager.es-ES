---
description: El informe Tendencia de segmentos devuelve datos sobre las impresiones y las tasas de pulsaciones de los segmentos asignados y no asignados a lo largo del tiempo. Un segmento asignado es un segmento que crea y envía a un destino para su segmentación. Un segmento sin asignar es un segmento que ha creado, pero que no ha enviado a un destino para la segmentación. Compare tendencias y volumen para las métricas seleccionadas a fin de tener una mejor idea de cómo se comportan las audiencias con el paso del tiempo.
seo-description: The Segment Trend report returns data on impressions and click-through rates of mapped and unmapped segments over time. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Compare trends and volume for your selected metrics to get a better picture of how your audiences behave over time.
seo-title: Segment Trend Report
solution: Audience Manager
title: Informe de tendencias del segmento
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization Reports
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---

# Informe de tendencias del segmento{#segment-trend-report}

El informe Tendencia de segmentos devuelve datos sobre las impresiones y las tasas de pulsaciones de los segmentos asignados y no asignados a lo largo del tiempo.

Un segmento asignado es un segmento que crea y envía a un destino para su segmentación. Un segmento sin asignar es un segmento que ha creado, pero que no ha enviado a un destino para la segmentación.

Compare tendencias y volumen para las métricas seleccionadas a fin de tener una mejor idea de cómo se comportan las audiencias con el paso del tiempo.

## Caso de uso {#use-cases}

Utilice el informe [!UICONTROL Segment Trend] para validar el rendimiento de un segmento a lo largo del tiempo y para identificar tendencias en función de un rendimiento o una escala sólidos.

Con este informe, puede comprender qué propiedades web muestran un descenso o un aumento defectuoso y solucionar problemas según sea necesario. Este informe es el siguiente paso después de identificar la audiencia de interés en el informe [!UICONTROL Segment Performance], para garantizar que el rendimiento alto o bajo que vio en la ficha [!UICONTROL Segment Performance] sea coherente en el tiempo.

## Uso del informe de tendencia del segmento {#using-the-report}

Cambie entre **[!UICONTROL Mapped]** y **[!UICONTROL Unmapped]** para seleccionar segmentos que estén asignados a un destino o no. Seleccione **[!UICONTROL All]** para incluir todos sus segmentos en el informe.

Ajuste la ventana retrospectiva con el regulador **[!UICONTROL Date Through]**.

Haga clic en cualquiera de los segmentos bajo el control deslizante **[!UICONTROL Date Through]** para que aparezca la opción de mantener solo ese segmento en el informe o excluirlo.

Utilice el cuadro desplegable **[!UICONTROL Line Item]** para seleccionar las propiedades del portafolio para las que desea devolver información.

En el cuadro desplegable **[!UICONTROL Segment Data Source]**, seleccione las fuentes de datos que contienen los segmentos que desea ver en el informe.

Utilice el cuadro desplegable **[!UICONTROL Segment]** para seleccionar qué segmentos desea ver en el informe.

>[!IMPORTANT]
>
>Al habilitar [!UICONTROL Audience Optimization for Publishers], debe incluir metadatos descriptivos para los identificadores de [!UICONTROL Line Item], tal como se describe en el paso 3 de [Importar archivos de datos de Google Ad Manager (anteriormente DFP) en Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Al hacerlo, puede asegurarse de que el informe detalle la propiedad web como [!UICONTROL Line Item] en lugar del ID [!UICONTROL Line Item].

## Interpretación de los resultados {#interpreting-results}

El informe [!UICONTROL Segment Trend] devuelve datos en un gráfico de líneas solo para un intervalo de 14 días. En este ejemplo, el informe muestra las tendencias de impresión y clics de un conjunto de segmentos asignados y no asignados.

Pase el ratón sobre cualquier línea para obtener más información sobre esa tendencia concreta del segmento. Consulte las descripciones para obtener información adicional en la tabla siguiente del informe de ejemplo.

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
   <td colname="col2"> <p>El nombre alfanumérico que ha asignado a este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID de segmento</span> </p> </td> 
   <td colname="col2"> <p>ID único de este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> elemento de línea</span> </p> </td> 
   <td colname="col2"> <p>La propiedad web para la que está viendo este informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> clics</span> </p> </td> 
   <td colname="col2"> <p>El número de veces que los miembros de este rasgo han hecho clic en elementos de su propiedad web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> impresiones</span> </p> </td> 
   <td colname="col2"> <p>El número de veces que los miembros de este rasgo han estado expuestos a su inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Tasa de pulsaciones. Esta métrica transmite el porcentaje de impresiones seguidas de clics. Divida los clics por impresiones para obtener esta métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> valores exclusivos de segmento</span> </p> </td> 
   <td colname="col2"> <p>El número de miembros del segmento en los últimos 30 días. </p> </td> 
  </tr> 
 </tbody> 
</table>
