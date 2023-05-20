---
description: El informe Superposición de segmento a unidad de anuncio se muestra como un gráfico de calor que resalta las superposiciones altas y bajas entre las unidades de anuncio y los segmentos del Audience Manager.
seo-description: The Segment to Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units and Audience Manager segments.
seo-title: Segment to Ad Unit Overlap
solution: Audience Manager
title: Superposición de segmento a unidad de publicidad
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# Superposición de segmento a unidad de publicidad{#segment-to-ad-unit-overlap}

El informe Superposición de segmento a unidad de anuncio se muestra como un gráfico de calor que resalta las superposiciones altas y bajas entre las unidades de anuncio y los segmentos del Audience Manager.

## Caso de uso {#use-cases}

Con el [!UICONTROL Segment to Ad Unit Overlap] , puede comprender qué audiencias visitan las propiedades web. El informe muestra la superposición entre los miembros de su [!DNL Audience Manager] segmentos de y la cantidad de visitantes a las propiedades web. Una superposición más alta significa que muchos miembros de un segmento visitan la propiedad web.

## Uso del informe de solapamiento entre segmentos y unidades publicitarias {#using-the-report}

Utilice el **[!UICONTROL Top N Ad Units]** y **[!UICONTROL Top N Segments]** controles para seleccionar el número deseado de unidades de publicidad y segmentos para la superposición. Puede seleccionar un número máximo de 100 elementos para cada uno.

Utilice el **Intervalo de días** y **De fecha a fecha** controles para ajustar el intervalo retrospectivo. Tenga en cuenta que los períodos retrospectivos de 7 días y 30 días solo están disponibles para fechas de domingo.

Utilice el **[!UICONTROL Segment Name]** y el **[!UICONTROL Ad Unit]** para filtrar cualquiera de los segmentos y las unidades de anuncios.

>[!IMPORTANT]
>
>Al habilitar [!UICONTROL Audience Optimization for Publishers], debe incluir metadatos descriptivos para [!UICONTROL Ad Unit IDs], tal como se describe en el paso 3 de [Importar archivos de datos de Google Ad Manager (anteriormente DFP) en Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Al hacerlo, se asegura de que el informe detalla la propiedad web como [!UICONTROL Ad Unit] en lugar del [!UICONTROL Ad Unit ID].

## Interpretación de los resultados {#interpreting-results}

Su [!UICONTROL Segment to Ad Unit Overlap] El informe podría ser similar al de abajo. Pase el ratón sobre cualquier celda para obtener más información sobre esa superposición en particular. Consulte las descripciones para obtener información adicional en la tabla siguiente del informe de ejemplo.

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
   <td colname="col2"> <p>El nombre del artículo de inventario. Por ejemplo, este puede ser uno de sus sitios web o un artículo en su sitio web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento de valores exclusivos en tiempo real del segmento</span> </p> </td> 
   <td colname="col2"> <p>El número de visitantes únicos vistos en tiempo real durante el intervalo de tiempo especificado y que estaban cualificados para el segmento en el momento en que fueron vistos por <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento de valores exclusivos de unidad de publicidad</span> </p> </td> 
   <td colname="col2"> <p>El número de visitantes para esta unidad de publicidad específica. Esta información se extrae de los registros de Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento de valores exclusivos de superposición</span> </p> </td> 
   <td colname="col2"> <p>Los miembros del segmento que se expusieron al elemento de unidad de anuncio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentaje de superposición</span> </p> </td> 
   <td colname="col2"> <p>Superposición entre las poblaciones de unidades de anuncios y segmentos. Este es el <span class="wintitle"> Recuento de valores exclusivos de superposición</span>, expresado como porcentaje del <span class="wintitle"> Segmento de valores exclusivos en tiempo real</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
