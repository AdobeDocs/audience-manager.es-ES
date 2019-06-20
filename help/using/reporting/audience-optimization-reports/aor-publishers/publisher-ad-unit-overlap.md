---
description: El informe Superposición de unidad de publicidad se muestra como un gráfico de calor que resalta las solapas altas y bajas entre las unidades de publicidad.
seo-description: El informe Superposición de unidad de publicidad se muestra como un gráfico de calor que resalta las solapas altas y bajas entre las unidades de publicidad.
seo-title: Superposición de unidad de publicidad
solution: Audience Manager
title: Superposición de unidad de publicidad
uuid: e 4467 e 81-acbf -474 e-b 501-89 d 57395651 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ad Unit Overlap{#ad-unit-overlap}

**[!UICONTROL Ad Unit Overlap]** El informe se muestra como un gráfico de calor que resalta las solapas altas y bajas entre las unidades de publicidad.

## Caso de uso {#use-cases}

With the **[!UICONTROL Ad Unit Overlap]** report, you can gain insight into where your audience overlaps across your web properties. El informe considera las 100 propiedades principales relacionadas y muestra la superposición entre ellas.

## Using the Ad Unit Overlap Report {#using-the-report}

Use the **[!UICONTROL Top N Base Ad Units]** and **[!UICONTROL Top N Overlapping Ad Units]** controls to select your desired number of ad units for the overlap. Puede seleccionar un número máximo de 100 elementos para cada uno.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. Tenga en cuenta que los períodos de retroceso de 7 días y 30 días solo están disponibles para las fechas del domingo.

Use the **[!UICONTROL Base Ad Unit]** and the **[!UICONTROL Overlap Ad Unit]** controls to select which of your ad units you want to display in the overlap report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

Your [!UICONTROL Ad Unit Overlap] report could look similar to the one below. Pase el ratón sobre cualquier celda para obtener más información sobre esa superposición concreta. Consulte las descripciones de la información adicional en la tabla debajo del informe de muestra.

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
   <td colname="col1"> <p><span class="wintitle"> Unidad de publicidad superpuesta</span> </p> </td> 
   <td colname="col2"> <p>Nombre del elemento de inventario. Por ejemplo, puede ser uno de sus sitios web o un artículo del sitio web. En la imagen anterior, las unidades de publicidad base son Artículos 9 - 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unidad de publicidad base</span> </p> </td> 
   <td colname="col2"> <p>Nombre del elemento de inventario. Por ejemplo, puede ser uno de sus sitios web o un artículo del sitio web. En la imagen anterior, las unidades de publicidad base son Artículos 1 - 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Superposición de la unidad de anuncios únicos de unidades de publicidad</span> </p> </td> 
   <td colname="col2"> <p>El número de usuarios que han visitado los elementos de la unidad de publicidad 9 - 18. Esta información se extrae de los registros de DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento únicos de unidades de publicidad base</span> </p> </td> 
   <td colname="col2"> <p>El número de usuarios que han visitado los elementos de la unidad de publicidad 1 - 8. Esta información se extrae de los registros de DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Superponer recuento de únicos</span> </p> </td> 
   <td colname="col2"> <p>The overlap between your users who have visited a <span class="wintitle"> Base Ad Unit</span> and <span class="wintitle"> Overlap Ad Unit</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentaje superpuesto</span> </p> </td> 
   <td colname="col2"> <p>The overlap between your users who have visited a <span class="wintitle"> Base Ad Unit</span> and <span class="wintitle"> Overlap Ad Unit</span>. This is the <span class="wintitle"> Overlap Uniques Count</span>, expressed as a percentage of the <span class="wintitle"> Base Ad Unit</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
