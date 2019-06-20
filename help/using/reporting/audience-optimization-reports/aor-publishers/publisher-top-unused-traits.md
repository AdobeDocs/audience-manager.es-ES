---
description: Las características principales no utilizadas se representan como diagramas de puntos de características que aún no son miembros de un segmento, en función del tipo de características, la fuente de datos y el rendimiento.
seo-description: Las características principales no utilizadas se representan como diagramas de puntos de características que aún no son miembros de un segmento, en función del tipo de características, la fuente de datos y el rendimiento.
seo-title: Características principales no utilizadas
solution: Audience Manager
title: Características principales no utilizadas
uuid: 90 bcd 333-41 b 8-416 e-aa 4 e-a 8661891 df 50
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Top Unused Traits{#top-unused-traits}

Las características principales no utilizadas se representan como diagramas de puntos de características que aún no son miembros de un segmento, en función del tipo de características, la fuente de datos y el rendimiento.

## Caso de uso {#use-cases}

With the [!UICONTROL Top Unused Traits] report, you can analyze and compare the performance of first and third party traits that are currently not mapped to a segment. Esta vista puede señalar las mejores características que se utilizan en un segmento de audiencia para la optimización de campañas o las nuevas oportunidades de red.

## Using the Top Unused Traits Report {#using-the-report}

Use the **[!UICONTROL Data Provider Type]** controls to toggle between first party and third party traits. Select **[!UICONTROL All]** to return first and third party traits in the report.

With the **[!UICONTROL Impressions]** slider, you can select a minimum and maximum value for returned impressions. Las características responsables de menos o más que los límites que configuró no se muestran en el informe.

Use the **[!UICONTROL Day Range]** and **[!UICONTROL Date Through]** controls to adjust your look-back range. Tenga en cuenta que solo está disponible el período de retroceso de 30 días para este informe.

Use the **[!UICONTROL Order]** drop-down box to select the web properties in your portfolio for which you want to return information.

In the **[!UICONTROL Data Provider]** drop-down box, select the data sources containing the traits you want to see in the report.

Use the **[!UICONTROL Traits]** drop-down box to select which traits you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Order IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Order] instead of the [!UICONTROL Order ID].

## Interpreting the Results {#interpreting-results}

**Informe de muestra**

Your [!UICONTROL Top Unused Traits] report could look similar to the one below. En el informe, haga clic en una burbuja para ver los datos subyacentes.

Consulte las descripciones de la información adicional en la tabla debajo del informe de muestra.

![](assets/publisher_unused_traits.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tipo de proveedor de datos</span> </p> </td> 
   <td colname="col2"> <p>Especifica si la fuente de datos seleccionada contiene características individuales o de terceros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID de característica</span> </p> </td> 
   <td colname="col2"> <p>ID exclusivo de esta característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre de característica</span> </p> </td> 
   <td colname="col2"> <p>Nombre alfanumérico que usted o el proveedor de datos asignados a esta característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Pedido</span> </p> </td> 
   <td colname="col2"> <p>La propiedad web para la cual está viendo este informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impresiones</span> </p> </td> 
   <td colname="col2"> <p>Número de veces que los miembros de esta característica han sido expuestos al inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Únicos únicos</span> </p> </td> 
   <td colname="col2"> <p>Número de miembros de características, dentro de los últimos 30 días. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

La posición de sus características en un informe puede informarle mucho sobre qué características se pueden usar para optimizar los segmentos de audiencia existentes.

Las características ubicadas más arriba en el eje Impresiones son las que desee utilizar en las campañas. Para características con un número bajo de impresiones, es poco probable que se llegue a esta audiencia en la propiedad web, en base a los datos de DFP.

Look to the left of the [!UICONTROL Unique Trait Realizations] axis for highly accurate traits and to the right for traits that can drive scale.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Posición </th> 
   <th colname="col2" class="entry"> Ubicación indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Superior izquierda</b> </p> </td> 
   <td colname="col2"> <p>Gran cantidad de impresiones, número bajo de características de características. </p> <p>Es una audiencia altamente precisa que aún no es miembro de un segmento. Considere la posibilidad de segmentar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior izquierda</b> </p> </td> 
   <td colname="col2"> <p>Número bajo de impresiones, número bajo de características de características. </p> <p> Extraiga estas características, ya que los miembros no contribuyen a las impresiones de las propiedades web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Superior derecha</b> </p> </td> 
   <td colname="col2"> <p>Gran cantidad de impresiones, número elevado de características de características. </p> <p>Alcance alto frente a una audiencia que aún no se indica en un segmento. Esta audiencia es una candidata principal para segmentación debido al gran número de impresiones y la escala. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior derecha</b> </p> </td> 
   <td colname="col2"> <p>Número bajo de impresiones, número elevado de características de características. </p> <p> Puede excluir estas características, ya que los miembros no contribuyen a las impresiones en las propiedades web. </p> </td> 
  </tr> 
 </tbody> 
</table>
