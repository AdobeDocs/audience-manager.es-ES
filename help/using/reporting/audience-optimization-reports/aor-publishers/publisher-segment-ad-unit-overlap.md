---
description: El informe Superposición de segmento a unidad de publicidad se muestra como un gráfico de calor que resalta superposiciones altas y bajas entre las unidades de publicidad y los segmentos de Audience Manager.
seo-description: El informe Superposición de segmento a unidad de publicidad se muestra como un gráfico de calor que resalta superposiciones altas y bajas entre las unidades de publicidad y los segmentos de Audience Manager.
seo-title: Superposición de segmento a unidad de publicidad
solution: Audience Manager
title: Superposición de segmento a unidad de publicidad
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Superposición de segmento a unidad de publicidad{#segment-to-ad-unit-overlap}

El informe Superposición de segmento a unidad de publicidad se muestra como un gráfico de calor que resalta superposiciones altas y bajas entre las unidades de publicidad y los segmentos de Audience Manager.

## Caso de uso {#use-cases}

Con el [!UICONTROL Segment to Ad Unit Overlap] informe, puede comprender qué audiencias visitan las propiedades web. El informe muestra la superposición entre los miembros de los [!DNL Audience Manager] segmentos y el número de visitantes a las propiedades web. Una superposición mayor significa que muchos miembros de un segmento visitan la propiedad web.

## Uso del informe Superposición de segmentos a unidades de publicidad {#using-the-report}

Utilice los controles **[!UICONTROL Top N Ad Units]** y **[!UICONTROL Top N Segments]** para seleccionar el número deseado de unidades de publicidad y segmentos para la superposición. Puede seleccionar un número máximo de 100 elementos para cada uno.

Utilice los controles Intervalo **de** días y **Fecha a través** para ajustar el intervalo retrospectivo. Tenga en cuenta que los períodos retrospectivos de 7 y 30 días solo están disponibles para las fechas de domingo.

Utilice los cuadros **[!UICONTROL Segment Name]** y **[!UICONTROL Ad Unit]** y para filtrar cualquiera de los segmentos y las unidades de publicidad.

>[!IMPORTANT]
>
>Al habilitar [!UICONTROL Audience Optimization for Publishers], debe incluir metadatos descriptivos para [!UICONTROL Ad Unit IDs], como se describe en el paso 3 de [Importar archivos de datos de DFP en Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Al hacer esto, se asegura de que el informe detalle la propiedad web como [!UICONTROL Ad Unit] en lugar de la [!UICONTROL Ad Unit ID].

## Interpretación de los resultados {#interpreting-results}

Su [!UICONTROL Segment to Ad Unit Overlap] informe podría tener un aspecto similar al de abajo. Pase el ratón sobre cualquier celda para obtener más información sobre esa superposición en particular. Consulte las descripciones para obtener información adicional en la tabla debajo del informe de muestra.

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
   <td colname="col2"> <p>Nombre del artículo de inventario. Por ejemplo, puede ser uno de los sitios web o un artículo del sitio web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento de únicos en tiempo real de segmentos</span> </p> </td> 
   <td colname="col2"> <p>El número de visitantes únicos que se vieron en tiempo real durante el intervalo de tiempo especificado y que se calificaron para el segmento en el momento en que <span class="keyword"> Audience Manager</span>los vio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento exclusivo de unidades de publicidad</span> </p> </td> 
   <td colname="col2"> <p>El número de visitantes para esta unidad de publicidad específica. Esta información se extrae de los registros de DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento único superpuesto</span> </p> </td> 
   <td colname="col2"> <p>Miembros del segmento que estuvieron expuestos al elemento de unidad de publicidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentaje de superposición</span> </p> </td> 
   <td colname="col2"> <p>La superposición entre las poblaciones de segmentos y unidades de publicidad. Este es el <span class="wintitle"> Recuento</span>de valores únicos superpuestos, expresado como porcentaje de los valores exclusivos <span class="wintitle"> en tiempo real del</span>segmento. </p> </td> 
  </tr> 
 </tbody> 
</table>

