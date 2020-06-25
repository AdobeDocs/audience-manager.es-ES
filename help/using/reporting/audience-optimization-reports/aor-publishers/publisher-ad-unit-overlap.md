---
description: El informe Superposición de unidad de publicidad se muestra como un gráfico de calor que resalta superposiciones altas y bajas entre las unidades de publicidad.
seo-description: El informe Superposición de unidad de publicidad se muestra como un gráfico de calor que resalta superposiciones altas y bajas entre las unidades de publicidad.
seo-title: Superposición de unidad de publicidad
solution: Audience Manager
title: Superposición de unidad de publicidad
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---


# Superposición de unidad de publicidad{#ad-unit-overlap}

El **[!UICONTROL Ad Unit Overlap]** informe se muestra como un gráfico de calor que resalta las superposiciones altas y bajas entre las unidades de publicidad.

## Caso de uso {#use-cases}

Con el **[!UICONTROL Ad Unit Overlap]** informe, puede obtener una visión detallada sobre dónde se superpone la audiencia en las propiedades web. El informe considera las 100 propiedades relacionadas principales y muestra la superposición entre ellas.

## Uso del informe Superposición de unidad de publicidad {#using-the-report}

Utilice los controles **[!UICONTROL Top N Base Ad Units]** y **[!UICONTROL Top N Overlapping Ad Units]** para seleccionar el número deseado de unidades de publicidad para la superposición. Puede seleccionar un número máximo de 100 elementos para cada uno.

Utilice los controles Intervalo **de** días y **Fecha a través** para ajustar el intervalo retrospectivo. Tenga en cuenta que los períodos retrospectivos de 7 y 30 días solo están disponibles para las fechas de domingo.

Utilice los controles **[!UICONTROL Base Ad Unit]** y **[!UICONTROL Overlap Ad Unit]** para seleccionar qué unidades de publicidad desea mostrar en el informe de superposición.

>[!IMPORTANT]
>
>Al habilitar [!UICONTROL Audience Optimization for Publishers], debe incluir metadatos descriptivos para [!UICONTROL Ad Unit IDs], como se describe en el paso 3 de [Importar archivos de datos de DFP en Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Al hacer esto, se asegura de que el informe detalla la propiedad web como [!UICONTROL Ad Unit] en lugar de la propiedad [!UICONTROL Ad Unit ID].

## Interpretación de los resultados {#interpreting-results}

Su [!UICONTROL Ad Unit Overlap] informe podría tener un aspecto similar al de abajo. Pase el ratón sobre cualquier celda para obtener más información sobre esa superposición en particular. Consulte las descripciones para obtener información adicional en la tabla debajo del informe de muestra.

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
   <td colname="col2"> <p>El número de usuarios que han visitado los elementos de la unidad de publicidad 9 - 18. Esta información se extrae de los registros de DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento único de unidades de publicidad base</span> </p> </td> 
   <td colname="col2"> <p>El número de usuarios que han visitado los elementos de la unidad de publicidad 1 - 8. Esta información se extrae de los registros de DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento único superpuesto</span> </p> </td> 
   <td colname="col2"> <p>La superposición entre los usuarios que han visitado una unidad <span class="wintitle"> de publicidad</span> base y una unidad <span class="wintitle"> de publicidad superpuesta</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentaje de superposición</span> </p> </td> 
   <td colname="col2"> <p>La superposición entre los usuarios que han visitado una unidad <span class="wintitle"> de publicidad</span> base y una unidad <span class="wintitle"> de publicidad superpuesta</span>. Este es el <span class="wintitle"> Recuento</span>de únicos superpuestos, expresado como porcentaje de la unidad <span class="wintitle"></span>de publicidad base. </p> </td> 
  </tr> 
 </tbody> 
</table>
