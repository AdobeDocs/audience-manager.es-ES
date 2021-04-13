---
description: El informe Superposición de segmento a unidad de publicidad se muestra como un gráfico de calor que resalta superposiciones altas y bajas entre las unidades de publicidad y los segmentos del Audience Manager.
seo-description: El informe Superposición de segmento a unidad de publicidad se muestra como un gráfico de calor que resalta superposiciones altas y bajas entre las unidades de publicidad y los segmentos del Audience Manager.
seo-title: Superposición de segmento a unidad de publicidad
solution: Audience Manager
title: Superposición de segmento a unidad de publicidad
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Informes de optimización de Audiencia
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 5%

---

# Superposición de segmento a unidad de publicidad{#segment-to-ad-unit-overlap}

El informe Superposición de segmento a unidad de publicidad se muestra como un gráfico de calor que resalta superposiciones altas y bajas entre las unidades de publicidad y los segmentos del Audience Manager.

## Caso de uso {#use-cases}

Con el informe [!UICONTROL Segment to Ad Unit Overlap], puede comprender qué audiencias visitan las propiedades web. El informe muestra la superposición entre los miembros de los segmentos [!DNL Audience Manager] y el número de visitantes a las propiedades web. Una superposición mayor significa que muchos miembros de un segmento visitan la propiedad web.

## Uso del informe de superposición de segmento a unidad de publicidad {#using-the-report}

Utilice los controles **[!UICONTROL Top N Ad Units]** y **[!UICONTROL Top N Segments]** para seleccionar el número deseado de unidades de anuncios y segmentos para la superposición. Puede seleccionar un número máximo de 100 elementos para cada uno.

Utilice los controles **Day Range** y **Date Through** para ajustar el intervalo retrospectivo. Tenga en cuenta que los periodos retrospectivos de 7 días y 30 días solo están disponibles para las fechas de domingo.

Utilice los cuadros **[!UICONTROL Segment Name]** y **[!UICONTROL Ad Unit]** para filtrar cualquiera de los segmentos y unidades de anuncios.

>[!IMPORTANT]
>
>Al habilitar [!UICONTROL Audience Optimization for Publishers], debe incluir metadatos descriptivos para [!UICONTROL Ad Unit IDs], tal como se describe en el paso 3 de [Importar archivos de datos de Google Ad Manager (anteriormente DFP) en el Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Al hacerlo, se asegura de que el informe detalle la propiedad web como [!UICONTROL Ad Unit] en lugar de [!UICONTROL Ad Unit ID].

## Interpretación de los resultados {#interpreting-results}

Su informe [!UICONTROL Segment to Ad Unit Overlap] puede tener un aspecto similar al que se muestra a continuación. Pase el ratón sobre cualquier celda para obtener más información sobre esa superposición en particular. Consulte las descripciones para obtener información adicional en la tabla que se encuentra debajo del informe de ejemplo.

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
   <td colname="col1"> <p><span class="wintitle"> Unidad de publicidad  </span> </p> </td> 
   <td colname="col2"> <p>El nombre del artículo de inventario. Por ejemplo, puede ser uno de los sitios web o un artículo del sitio web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento de únicos en tiempo real de segmentos</span> </p> </td> 
   <td colname="col2"> <p>El número de visitantes únicos vistos en tiempo real durante el intervalo de tiempo especificado y que fueron calificados para el segmento en el momento en que fueron vistos por el <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento único de unidad de publicidad</span> </p> </td> 
   <td colname="col2"> <p>El número de visitantes para esta unidad de publicidad específica. Esta información se extrae de los registros de Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento único superpuesto</span> </p> </td> 
   <td colname="col2"> <p>Los miembros del segmento expuestos al elemento de unidad de publicidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentaje de superposición</span> </p> </td> 
   <td colname="col2"> <p>Superposición entre las poblaciones de segmentos y unidades publicitarias. Este es el <span class="wintitle"> Recuento único superpuesto</span>, expresado como un porcentaje de los <span class="wintitle"> Segmentos únicos en tiempo real</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
