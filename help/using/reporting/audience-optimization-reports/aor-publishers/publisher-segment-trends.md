---
description: El informe Tendencia del segmento devuelve datos sobre impresiones y tasas de pulsaciones de segmentos asignados y no asignados a lo largo del tiempo. Un segmento asignado es un segmento que crea y envía a un destino para su segmentación. Un segmento sin asignar es un segmento que ha creado pero que no ha enviado a un destino para su segmentación. Compare tendencias y volumen para las métricas seleccionadas a fin de obtener una mejor imagen de cómo se comportan las audiencias a lo largo del tiempo.
seo-description: El informe Tendencia del segmento devuelve datos sobre impresiones y tasas de pulsaciones de segmentos asignados y no asignados a lo largo del tiempo. Un segmento asignado es un segmento que crea y envía a un destino para su segmentación. Un segmento sin asignar es un segmento que ha creado pero que no ha enviado a un destino para su segmentación. Compare tendencias y volumen para las métricas seleccionadas a fin de obtener una mejor imagen de cómo se comportan las audiencias a lo largo del tiempo.
seo-title: Informe de Tendencia del segmento
solution: Audience Manager
title: Informe de Tendencia del segmento
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Informes de optimización de Audiencia
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 3%

---

# Informe de Tendencia del segmento{#segment-trend-report}

El informe Tendencia del segmento devuelve datos sobre impresiones y tasas de pulsaciones de segmentos asignados y no asignados a lo largo del tiempo.

Un segmento asignado es un segmento que crea y envía a un destino para su segmentación. Un segmento sin asignar es un segmento que ha creado pero que no ha enviado a un destino para su segmentación.

Compare tendencias y volumen para las métricas seleccionadas a fin de obtener una mejor imagen de cómo se comportan las audiencias a lo largo del tiempo.

## Caso de uso {#use-cases}

Utilice el informe [!UICONTROL Segment Trend] para validar el rendimiento de un segmento a lo largo del tiempo y para señalar las tendencias en función de un rendimiento o una escala sólidos.

Con este informe, puede comprender cuál de sus propiedades web muestra un descenso o un error de aumento y resolución de problemas según sea necesario. Este informe es el siguiente paso después de identificar su audiencia de interés en el informe [!UICONTROL Segment Performance], para garantizar que el rendimiento sólido o deficiente que vio en la pestaña [!UICONTROL Segment Performance] sea coherente a lo largo del tiempo.

## Uso del informe de tendencias de segmentos {#using-the-report}

Alterne entre **[!UICONTROL Mapped]** y **[!UICONTROL Unmapped]** para seleccionar segmentos asignados a un destino o no. Seleccione **[!UICONTROL All]** para incluir todos los segmentos en el informe.

Ajuste la ventana retrospectiva con el regulador **[!UICONTROL Date Through]**.

Haga clic en cualquiera de los segmentos bajo el control deslizante **[!UICONTROL Date Through]** para que aparezca la opción para mantener solo ese segmento en el informe o excluirlo.

Utilice el cuadro desplegable **[!UICONTROL Line Item]** para seleccionar las propiedades del portafolio para las que desea devolver información.

En el cuadro desplegable **[!UICONTROL Segment Data Source]**, seleccione las fuentes de datos que contengan los segmentos que desee ver en el informe.

Utilice el cuadro desplegable **[!UICONTROL Segment]** para seleccionar qué segmentos desea ver en el informe.

>[!IMPORTANT]
>
>Al habilitar [!UICONTROL Audience Optimization for Publishers], debe incluir metadatos descriptivos para [!UICONTROL Line Item] ID, tal como se describe en el paso 3 de [Importar archivos de datos de Google Ad Manager (anteriormente DFP) en el Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Al hacerlo, se asegura de que el informe detalle la propiedad web como [!UICONTROL Line Item] en lugar del ID [!UICONTROL Line Item].

## Interpretación de los resultados {#interpreting-results}

El informe [!UICONTROL Segment Trend] devuelve datos en un gráfico de líneas solo para un intervalo de 14 días. En este ejemplo, el informe muestra las tendencias de impresión y pulsaciones de un conjunto de segmentos asignados y no asignados.

Pase el ratón sobre cualquier línea para obtener más información sobre esa tendencia de segmento en particular. Consulte las descripciones para obtener información adicional en la tabla que se encuentra debajo del informe de ejemplo.

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
   <td colname="col2"> <p>El nombre alfanumérico que asignó a este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID de segmento</span> </p> </td> 
   <td colname="col2"> <p>ID exclusivo de este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Elemento de línea</span> </p> </td> 
   <td colname="col2"> <p>La propiedad web de la que verá este informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Clics</span> </p> </td> 
   <td colname="col2"> <p>Número de veces que los miembros de este rasgo han hecho clic en elementos de la propiedad web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impresiones</span> </p> </td> 
   <td colname="col2"> <p>Número de veces que los miembros de este rasgo han estado expuestos al inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Tasa de pulsaciones. Esta métrica transmite el porcentaje de impresiones seguido de clics. Divida los clics por impresiones para obtener esta métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Únicos de segmentos</span> </p> </td> 
   <td colname="col2"> <p>El número de miembros del segmento, en los últimos 30 días. </p> </td> 
  </tr> 
 </tbody> 
</table>
