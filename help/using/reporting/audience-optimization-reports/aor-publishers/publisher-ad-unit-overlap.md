---
description: El informe Superposición de unidad de anuncio se muestra como un gráfico de calor que resalta las superposiciones altas y bajas entre las unidades de anuncio.
seo-description: The Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.
seo-title: Ad Unit Overlap
solution: Audience Manager
title: Superposición de unidad de publicidad
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Audience Optimization Reports
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 2%

---

# Superposición de unidad de publicidad{#ad-unit-overlap}

El **[!UICONTROL Ad Unit Overlap]** El informe se muestra como un gráfico de calor que resalta las superposiciones altas y bajas entre las unidades de publicidad.

## Caso de uso {#use-cases}

Con el **[!UICONTROL Ad Unit Overlap]** , puede obtener información sobre dónde se superpone la audiencia en las propiedades web. El informe tiene en cuenta las 100 propiedades relacionadas principales y muestra la superposición entre ellas.

## Uso del informe de superposición de unidades de publicidad {#using-the-report}

Utilice el **[!UICONTROL Top N Base Ad Units]** y **[!UICONTROL Top N Overlapping Ad Units]** controles para seleccionar el número deseado de unidades de publicidad para la superposición. Puede seleccionar un número máximo de 100 elementos para cada uno.

Utilice el **Intervalo de días** y **De fecha a fecha** controles para ajustar el intervalo retrospectivo. Tenga en cuenta que los períodos retrospectivos de 7 días y 30 días solo están disponibles para fechas de domingo.

Utilice el **[!UICONTROL Base Ad Unit]** y el **[!UICONTROL Overlap Ad Unit]** controles para seleccionar cuál de las unidades de anuncios desea mostrar en el informe de superposición.

>[!IMPORTANT]
>
>Al habilitar [!UICONTROL Audience Optimization for Publishers], debe incluir metadatos descriptivos para [!UICONTROL Ad Unit IDs], tal como se describe en el paso 3 de [Importar archivos de datos de Google Ad Manager (anteriormente DFP) en Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Al hacerlo, se asegura de que el informe detalla la propiedad web como [!UICONTROL Ad Unit] en lugar del [!UICONTROL Ad Unit ID].

## Interpretación de los resultados {#interpreting-results}

Su [!UICONTROL Ad Unit Overlap] El informe podría ser similar al de abajo. Pase el ratón sobre cualquier celda para obtener más información sobre esa superposición en particular. Consulte las descripciones para obtener información adicional en la tabla siguiente del informe de ejemplo.

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
   <td colname="col2"> <p>El nombre del artículo de inventario. Por ejemplo, este puede ser uno de sus sitios web o un artículo en su sitio web. En la imagen anterior, la base y las unidades son los artículos 9 a 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unidad de anuncio base</span> </p> </td> 
   <td colname="col2"> <p>El nombre del artículo de inventario. Por ejemplo, este puede ser uno de sus sitios web o un artículo en su sitio web. En la imagen anterior, la base y las unidades son los artículos 1 a 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento de valores exclusivos de unidad de anuncios superpuestos</span> </p> </td> 
   <td colname="col2"> <p>Número de usuarios que han visitado los elementos de la unidad de publicidad 9 - 18. Esta información se extrae de los registros de Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento de valores exclusivos de unidad de anuncio base</span> </p> </td> 
   <td colname="col2"> <p>El número de usuarios que han visitado los elementos de la unidad de publicidad 1 a 8. Esta información se extrae de los registros de Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento de valores exclusivos de superposición</span> </p> </td> 
   <td colname="col2"> <p>La superposición entre los usuarios que han visitado un <span class="wintitle"> Unidad de anuncio base</span> y <span class="wintitle"> Superponer unidad de publicidad</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentaje de superposición</span> </p> </td> 
   <td colname="col2"> <p>La superposición entre los usuarios que han visitado un <span class="wintitle"> Unidad de anuncio base</span> y <span class="wintitle"> Superponer unidad de publicidad</span>. Este es el <span class="wintitle"> Recuento de valores exclusivos de superposición</span>, expresado como porcentaje del <span class="wintitle"> Unidad de anuncio base</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
