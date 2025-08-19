---
description: El informe Superposición de segmento a bloque de anuncios se muestra como un gráfico de calor que resalta las superposiciones altas y bajas entre los bloques de anuncios y Audience Manager segmentos.
seo-description: The Segment to Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units and Audience Manager segments.
seo-title: Segment to Ad Unit Overlap
solution: Audience Manager
title: Solapamiento de segmento a unidad de publicidad
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 1%

---

# Solapamiento de segmento a unidad de publicidad{#segment-to-ad-unit-overlap}

El informe Superposición de segmento a bloque de anuncios se muestra como un gráfico de calor que resalta las superposiciones altas y bajas entre los bloques de anuncios y Audience Manager segmentos.

## Caso de uso {#use-cases}

Con el [!UICONTROL Segment to Ad Unit Overlap] informe, puede comprender qué audiencias visita sus propiedades web. El informe muestra la superposición entre los miembros de los [!DNL Audience Manager] segmentos y el número de visitantes de las propiedades web. Una mayor superposición significa que muchos miembros de una segmento visita su Propiedad web.

## Uso del informe Superposición de segmento a unidad de publicidad {#using-the-report}

Utilice los controles y **[!UICONTROL Top N Ad Units]** para seleccionar el **[!UICONTROL Top N Segments]** número deseado de unidades de anuncios y segmentos para la superposición. Puede seleccionar un número máximo de 100 artículos para cada uno.

Use los controles Intervalo de días y **Pulsación****de fechas para ajustar el** intervalo de retroactividad. Tenga en cuenta que los períodos de retrospectiva de 7 y 30 días solo están disponibles para las fechas del domingo.

Utilice las **[!UICONTROL Segment Name]** casillas y para **[!UICONTROL Ad Unit]** filtrar cualquiera de los segmentos y unidades de anuncios.

>[!IMPORTANT]
>
>Al habilitar [!UICONTROL Audience Optimization for Publishers], debe incluir metadatos descriptivos para [!UICONTROL Ad Unit IDs], tal como se describe en el paso 3 de Importar Archivos de datos de [Google Ad Manager (anteriormente DFP) en Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Al realizar esto, se asegura de que el informe detalla la Propiedad web como [!UICONTROL Ad Unit] en lugar de la [!UICONTROL Ad Unit ID].

## Interpretación de los resultados {#interpreting-results}

Su [!UICONTROL Segment to Ad Unit Overlap] informe podría ser similar al que se muestra a continuación. Desplácese sobre cualquier celda para obtener más información sobre esa superposición concreta. Consulte las descripciones para obtener información adicional en la tabla debajo del informe de muestra.

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
   <td colname="col1"> <p><span class="wintitle"> Bloque de anuncios </span> </p> </td> 
   <td colname="col2"> <p>Nombre del inventario elemento. Por ejemplo, puede ser uno de sus sitios web o un artículo en su sitio web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento de segmentos Tiempo real únicos</span> </p> </td> 
   <td colname="col2"> <p>El número de visitantes únicos vistos en tiempo real durante el intervalo de tiempo especificado y que estaban cualificados para el segmento en el momento en que fueron vistos por <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento de bloques de anuncios únicos</span> </p> </td> 
   <td colname="col2"> <p>El número de visitantes para esta unidad de anuncios específica. Esta información se extrae de los registros de Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteo de solapamiento de elementos únicos</span> </p> </td> 
   <td colname="col2"> <p>Los miembros de su segmento que estuvieron expuestos al anuncios elemento de unidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentaje de solapamiento</span> </p> </td> 
   <td colname="col2"> <p>La superposición entre anuncios unidad y segmento poblaciones. Este es el <span class="wintitle"> recuento</span> de solapamientos únicos, expresado como un porcentaje del <span class="wintitle"> segmento Tiempo real únicos</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
