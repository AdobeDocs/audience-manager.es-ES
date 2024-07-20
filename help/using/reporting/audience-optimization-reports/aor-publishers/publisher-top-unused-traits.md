---
description: Los rasgos principales no utilizados se representan como un diagrama de dispersión de rasgos que aún no son miembros de un segmento, en función del tipo de rasgo, la fuente de datos y el rendimiento.
seo-description: Top Unused Traits are represented as a scatter diagram of traits that are not yet members of a segment, based on trait type, data source, and performance.
seo-title: Top Unused Traits
solution: Audience Manager
title: Rasgos principales no utilizados
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: Audience Optimization Reports
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 0%

---

# Rasgos principales no utilizados{#top-unused-traits}

Los rasgos principales no utilizados se representan como un diagrama de dispersión de rasgos que aún no son miembros de un segmento, en función del tipo de rasgo, la fuente de datos y el rendimiento.

## Caso de uso {#use-cases}

Con el informe [!UICONTROL Top Unused Traits], puede analizar y comparar el rendimiento de los rasgos de origen y de terceros que actualmente no están asignados a un segmento. Esta vista puede señalar los mejores rasgos que se pueden utilizar en un segmento de audiencia para la optimización de campañas o para nuevas oportunidades netas.

## Uso del informe Rasgos principales no utilizados {#using-the-report}

Utilice los controles **[!UICONTROL Data Provider Type]** para alternar entre características de origen y de terceros. Seleccione **[!UICONTROL All]** para devolver características de origen y de terceros en el informe.

Con el control deslizante **[!UICONTROL Impressions]**, puede seleccionar un valor mínimo y máximo para las impresiones devueltas. Los rasgos responsables de menos o más que los límites establecidos no se muestran en el informe.

Use los controles **[!UICONTROL Day Range]** y **[!UICONTROL Date Through]** para ajustar el intervalo retrospectivo. Tenga en cuenta que solo el periodo retrospectivo de 30 días está disponible para este informe.

Utilice el cuadro desplegable **[!UICONTROL Order]** para seleccionar las propiedades web del portafolio para las que desea devolver información.

En el cuadro desplegable **[!UICONTROL Data Provider]**, seleccione los orígenes de datos que contienen los rasgos que desea ver en el informe.

Utilice el cuadro desplegable **[!UICONTROL Traits]** para seleccionar qué características desea ver en el informe.

>[!IMPORTANT]
>
>Al habilitar [!UICONTROL Audience Optimization for Publishers], debe incluir metadatos descriptivos para [!UICONTROL Order IDs], como se describe en el paso 3 de [Importar archivos de datos de Google Ad Manager (anteriormente DFP) en el Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Al hacerlo, puede asegurarse de que el informe detalle la propiedad web como [!UICONTROL Order] en lugar de como [!UICONTROL Order ID].

## Interpretación de los resultados {#interpreting-results}

**Informe de muestra**

Su informe [!UICONTROL Top Unused Traits] podría ser similar al que se muestra a continuación. En el informe, haga clic en una burbuja para ver los datos subyacentes.

Consulte las descripciones para obtener información adicional en la tabla siguiente del informe de ejemplo.

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
   <td colname="col1"> <p>Tipo de proveedor de datos <span class="wintitle"></span> </p> </td> 
   <td colname="col2"> <p>Especifica si la fuente de datos seleccionada contiene características de origen o de terceros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID. de rasgo </span> </p> </td> 
   <td colname="col2"> <p>El ID único de este rasgo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre de característica</span> </p> </td> 
   <td colname="col2"> <p>El nombre alfanumérico que usted o el proveedor de datos asignaron a este rasgo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> pedido</span> </p> </td> 
   <td colname="col2"> <p>La propiedad web para la que está viendo este informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> impresiones</span> </p> </td> 
   <td colname="col2"> <p>El número de veces que los miembros de este rasgo han estado expuestos a su inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> rasgos únicos</span> </p> </td> 
   <td colname="col2"> <p>Número de miembros de rasgos en los últimos 30 días. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

La posición de los rasgos en un informe puede indicarle mucho sobre qué rasgos puede utilizar para optimizar los segmentos de audiencia existentes.

Los rasgos situados más arriba en el eje Impresiones son los que desea utilizar en sus campañas. En el caso de los rasgos con un número bajo de impresiones, es poco probable que llegue a esta audiencia en su propiedad web, según los datos de [!DNL Google Ad Manager].

Busque rasgos de gran precisión a la izquierda del eje [!UICONTROL Unique Trait Realizations] y a la derecha para rasgos que puedan aumentar la escala.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Posición </th> 
   <th colname="col2" class="entry"> La ubicación indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Superior Izquierda</b> </p> </td> 
   <td colname="col2"> <p>Número elevado de impresiones, número bajo de realizaciones de rasgos. </p> <p>Se trata de una audiencia de alta precisión que aún no es miembro de un segmento. Considere la posibilidad de segmentar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior izquierda</b> </p> </td> 
   <td colname="col2"> <p>Número de impresiones bajo, número bajo de realizaciones de rasgos. </p> <p> Descarte estos rasgos, ya que los miembros no contribuyen a las impresiones en las propiedades web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Superior Derecha</b> </p> </td> 
   <td colname="col2"> <p>Número elevado de impresiones, número elevado de realizaciones de rasgos. </p> <p>Un alcance alto para una audiencia que aún no está indicada en un segmento. Esta audiencia es una candidata principal para la segmentación debido al alto número de impresiones y a la escala. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior derecha</b> </p> </td> 
   <td colname="col2"> <p>Número bajo de impresiones, número alto de realizaciones de rasgos. </p> <p> Puede descartar estos rasgos, ya que los miembros no contribuyen a las impresiones en las propiedades web. </p> </td> 
  </tr> 
 </tbody> 
</table>
