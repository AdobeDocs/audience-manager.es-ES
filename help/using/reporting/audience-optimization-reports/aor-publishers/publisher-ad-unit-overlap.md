---
description: El informe Superposición de unidad de publicidad se muestra como un gráfico de calor que resalta superposiciones altas y bajas entre las unidades de publicidad.
seo-description: El informe Superposición de unidad de publicidad se muestra como un gráfico de calor que resalta superposiciones altas y bajas entre las unidades de publicidad.
seo-title: Superposición de unidad de publicidad
solution: Audience Manager
title: Superposición de unidad de publicidad
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 3%

---


# Superposición de unidad de publicidad{#ad-unit-overlap}

El informe **[!UICONTROL Ad Unit Overlap]** se muestra como un gráfico de calor que resalta las superposiciones altas y bajas entre las unidades de publicidad.

## Caso de uso {#use-cases}

Con el informe **[!UICONTROL Ad Unit Overlap]**, puede obtener una perspectiva sobre dónde se superpone la audiencia en las propiedades web. El informe considera las 100 propiedades relacionadas principales y muestra la superposición entre ellas.

## Uso del informe Superposición de unidades de publicidad {#using-the-report}

Utilice los controles **[!UICONTROL Top N Base Ad Units]** y **[!UICONTROL Top N Overlapping Ad Units]** para seleccionar el número deseado de unidades de publicidad para la superposición. Puede seleccionar un número máximo de 100 elementos para cada uno.

Utilice los controles **Intervalo de días** y **Pasar a la fecha** para ajustar el intervalo retrospectivo. Tenga en cuenta que los períodos retrospectivos de 7 y 30 días solo están disponibles para las fechas de domingo.

Utilice los controles **[!UICONTROL Base Ad Unit]** y **[!UICONTROL Overlap Ad Unit]** para seleccionar qué unidades de publicidad desea mostrar en el informe de superposición.

>[!IMPORTANT]
>
>Al habilitar [!UICONTROL Audience Optimization for Publishers], debe incluir metadatos descriptivos para [!UICONTROL Ad Unit IDs], tal como se describe en el paso 3 de [Importar archivos de datos de Google Ad Manager (anteriormente DFP) en Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Al hacer esto, se asegura de que el informe detalla la propiedad web como [!UICONTROL Ad Unit] en lugar de [!UICONTROL Ad Unit ID].

## Interpretación de los resultados {#interpreting-results}

Su informe [!UICONTROL Ad Unit Overlap] podría tener un aspecto similar al de abajo. Pase el ratón sobre cualquier celda para obtener más información sobre esa superposición en particular. Consulte las descripciones para obtener información adicional en la tabla debajo del informe de muestra.

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Superponer unidad de publicidad</span> </p> </td> 
   <td colname="col2"> <p>El nombre del artículo de inventario. Por ejemplo, puede ser uno de los sitios web o un artículo del sitio web. En la imagen anterior, las unidades de publicidad base son los artículos 9 a 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unidad de publicidad base</span> </p> </td> 
   <td colname="col2"> <p>El nombre del artículo de inventario. Por ejemplo, puede ser uno de los sitios web o un artículo del sitio web. En la imagen anterior, las unidades de publicidad base son los artículos 1 a 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento exclusivo de unidades de publicidad superpuestas</span> </p> </td> 
   <td colname="col2"> <p>El número de usuarios que han visitado los elementos de la unidad de publicidad 9 - 18. Esta información se extrae de los registros del Administrador de publicidad de Google. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento único de unidades de publicidad base</span> </p> </td> 
   <td colname="col2"> <p>El número de usuarios que han visitado los elementos de la unidad de publicidad 1 - 8. Esta información se extrae de los registros del Administrador de publicidad de Google. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento único superpuesto</span> </p> </td> 
   <td colname="col2"> <p>La superposición entre los usuarios que han visitado una <span class="wintitle"> unidad de publicidad base</span> y <span class="wintitle"> unidad de publicidad superpuesta</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentaje de superposición</span> </p> </td> 
   <td colname="col2"> <p>La superposición entre los usuarios que han visitado una <span class="wintitle"> unidad de publicidad base</span> y <span class="wintitle"> unidad de publicidad superpuesta</span>. Se trata del <span class="wintitle"> Recuento de valores exclusivos superpuestos</span>, expresado como porcentaje de la <span class="wintitle"> Unidad de publicidad base</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
