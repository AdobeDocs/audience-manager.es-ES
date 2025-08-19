---
description: El informe de superposición de bloques de anuncios se muestra como un gráfico de calor que resalta las superposiciones altas y bajas entre los bloques de anuncios.
seo-description: The Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.
seo-title: Ad Unit Overlap
solution: Audience Manager
title: Superposición de bloques de anuncios
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Audience Optimization Reports
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Superposición de bloques de anuncios{#ad-unit-overlap}

El **[!UICONTROL Ad Unit Overlap]** informe se muestra como un gráfico de calor que resalta las superposiciones altas y bajas entre los bloques de anuncios.

## Caso de uso {#use-cases}

Con el **[!UICONTROL Ad Unit Overlap]** informe, puede obtener conocimiento sobre dónde se superponen los audiencia en las propiedades web. El informe tiene en cuenta las 100 propiedades más relacionadas y muestra la superposición entre ellas.

## Uso del informe de superposición de bloques de anuncios {#using-the-report}

Utilice los controles y **[!UICONTROL Top N Base Ad Units]** para seleccionar el **[!UICONTROL Top N Overlapping Ad Units]** número deseado de unidades de anuncios para la superposición. Puede seleccionar un número máximo de 100 artículos para cada uno.

Use los controles Intervalo de días y **Pulsación**&#x200B;**de fechas para ajustar el** intervalo de retroactividad. Tenga en cuenta que los períodos de retrospectiva de 7 y 30 días solo están disponibles para las fechas del domingo.

Utilice el **[!UICONTROL Base Ad Unit]** y los **[!UICONTROL Overlap Ad Unit]** controles para seleccionar cuál de las unidades de anuncios desea mostrar en el informe de superposición.

>[!IMPORTANT]
>
>Al habilitar [!UICONTROL Audience Optimization for Publishers], debe incluir metadatos descriptivos para [!UICONTROL Ad Unit IDs], tal como se describe en el paso 3 de Importar Archivos de datos de [Google Ad Manager (anteriormente DFP) en Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Al realizar esto, se asegura de que el informe detalla la Propiedad web como [!UICONTROL Ad Unit] en lugar de la [!UICONTROL Ad Unit ID].

## Interpretación de los resultados {#interpreting-results}

Su [!UICONTROL Ad Unit Overlap] informe podría ser similar al que se muestra a continuación. Desplácese sobre cualquier celda para obtener más información sobre esa superposición concreta. Consulte las descripciones para obtener información adicional en la tabla debajo del informe de muestra.

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
   <td colname="col1"> <p><span class="wintitle"> Bloque de anuncios superpuesto</span> </p> </td> 
   <td colname="col2"> <p>Nombre del inventario elemento. Por ejemplo, puede ser uno de sus sitios web o un artículo en su sitio web. En la imagen de arriba, las unidades de anuncios base son los artículos 9 - 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unidad de publicidad base</span> </p> </td> 
   <td colname="col2"> <p>Nombre del inventario elemento. Por ejemplo, puede ser uno de sus sitios web o un artículo en su sitio web. En la imagen de arriba, las unidades de anuncios base son los artículos 1 a 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento de bloques de anuncios únicos superpuestos</span> </p> </td> 
   <td colname="col2"> <p>Número de usuarios que han visitado la unidad anuncios los elementos 9 a 18. Esta información se extrae de los registros de Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Recuento único del bloque de anuncios base</span> </p> </td> 
   <td colname="col2"> <p>Número de usuarios que han visitado la unidad anuncios elementos del 1 al 8. Esta información se extrae de los registros de Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteo de solapamiento de elementos únicos</span> </p> </td> 
   <td colname="col2"> <p>La superposición entre los usuarios que han visitado un bloque<span class="wintitle"> de anuncios base y </span> un <span class="wintitle"> bloque</span> de anuncios superpuesto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Porcentaje de solapamiento</span> </p> </td> 
   <td colname="col2"> <p>La superposición entre los usuarios que han visitado un bloque<span class="wintitle"> de anuncios base y </span> un <span class="wintitle"> bloque</span> de anuncios superpuesto. Este es el <span class="wintitle"> recuento</span> de solapamiento único, expresado como porcentaje del <span class="wintitle"> bloque</span> de anuncios base. </p> </td> 
  </tr> 
 </tbody> 
</table>
