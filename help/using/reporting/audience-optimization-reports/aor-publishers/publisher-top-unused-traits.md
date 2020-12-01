---
description: Las características no utilizadas principales se representan como un diagrama de puntos de características que aún no son miembros de un segmento, según el tipo de característica, la fuente de datos y el rendimiento.
seo-description: Las características no utilizadas principales se representan como un diagrama de puntos de características que aún no son miembros de un segmento, según el tipo de característica, la fuente de datos y el rendimiento.
seo-title: Rasgos principales no utilizados
solution: Audience Manager
title: Rasgos principales no utilizados
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 2%

---


# Rasgos principales no utilizados{#top-unused-traits}

Las características no utilizadas principales se representan como un diagrama de puntos de características que aún no son miembros de un segmento, según el tipo de característica, la fuente de datos y el rendimiento.

## Caso de uso {#use-cases}

Con el informe [!UICONTROL Top Unused Traits], puede analizar y comparar el rendimiento de las características de origen y de terceros que actualmente no están asignadas a un segmento. Esta vista puede señalar las mejores características que se utilizarán en un segmento de audiencia para la optimización de campañas o para nuevas oportunidades netas.

## Uso del informe Principales características no utilizadas {#using-the-report}

Utilice los controles **[!UICONTROL Data Provider Type]** para alternar entre características de origen y de terceros. Seleccione **[!UICONTROL All]** para devolver características de origen y de terceros en el informe.

Con el deslizador **[!UICONTROL Impressions]**, puede seleccionar un valor mínimo y máximo para las impresiones devueltas. En el informe no se muestran las características responsables de menos o más de los límites establecidos.

Utilice los controles **[!UICONTROL Day Range]** y **[!UICONTROL Date Through]** para ajustar el rango de retrospectiva. Tenga en cuenta que este informe solo tiene disponible el período de retrospectiva de 30 días.

Utilice el cuadro desplegable **[!UICONTROL Order]** para seleccionar las propiedades web de su portafolio para las que desea devolver información.

En el cuadro desplegable **[!UICONTROL Data Provider]**, seleccione las fuentes de datos que contengan las características que desee ver en el informe.

Utilice el cuadro desplegable **[!UICONTROL Traits]** para seleccionar qué características desea ver en el informe.

>[!IMPORTANT]
>
>Al habilitar [!UICONTROL Audience Optimization for Publishers], debe incluir metadatos descriptivos para [!UICONTROL Order IDs], tal como se describe en el paso 3 de [Importar archivos de datos de Google Ad Manager (anteriormente DFP) en Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Al hacer esto, se asegura de que el informe detalla la propiedad web como [!UICONTROL Order] en lugar de [!UICONTROL Order ID].

## Interpretación de los resultados {#interpreting-results}

**Informe de muestra**

Su informe [!UICONTROL Top Unused Traits] podría tener un aspecto similar al de abajo. En el informe, haga clic en una burbuja para vista de los datos subyacentes.

Consulte las descripciones para obtener información adicional en la tabla debajo del informe de muestra.

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
   <td colname="col2"> <p>Especifica si el origen de datos seleccionado contiene características de origen o de terceros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID de característica</span> </p> </td> 
   <td colname="col2"> <p>ID única de esta característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre de característica</span> </p> </td> 
   <td colname="col2"> <p>El nombre alfanumérico que usted o el proveedor de datos asignaron a esta característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Pedido</span> </p> </td> 
   <td colname="col2"> <p>La propiedad web para la cual está viendo este informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impresiones</span> </p> </td> 
   <td colname="col2"> <p>El número de veces que los miembros de esta característica han estado expuestos al inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Características únicas</span> </p> </td> 
   <td colname="col2"> <p>El número de miembros de características, en los últimos 30 días. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

La posición de las características en un informe puede indicarle muchas cosas sobre qué características podría utilizar para optimizar los segmentos de audiencia existentes.

Las características situadas en la parte superior del eje Impresiones son las que desea utilizar en sus campañas. Para las características con un número bajo de impresiones, es poco probable que llegue a esta audiencia en la propiedad web, en función de los datos [!DNL Google Ad Manager].

Busque a la izquierda del eje [!UICONTROL Unique Trait Realizations] características muy precisas y a la derecha las características que pueden impulsar la escala.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Posición </th> 
   <th colname="col2" class="entry"> La ubicación indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Superior izquierda</b> </p> </td> 
   <td colname="col2"> <p>Gran número de impresiones, bajo número de realizaciones de características. </p> <p>Se trata de una audiencia muy precisa que aún no es miembro de un segmento. Considere la posibilidad de establecer objetivos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior izquierda</b> </p> </td> 
   <td colname="col2"> <p>Bajo número de impresiones, bajo número de realizaciones de características. </p> <p> Elimine estas características, ya que los miembros no contribuyen a las impresiones en las propiedades web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Superior derecha</b> </p> </td> 
   <td colname="col2"> <p>Gran número de impresiones, gran número de realizaciones de características. </p> <p>Alcance alto contra una audiencia que aún no está indicada en un segmento. Esta audiencia es una de las principales candidatas para la determinación de objetivos debido al gran número de impresiones y la escala. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior derecha</b> </p> </td> 
   <td colname="col2"> <p>Bajo número de impresiones, alto número de realizaciones de características. </p> <p> Puede descartar estas características, ya que los miembros no contribuyen a las impresiones en las propiedades web. </p> </td> 
  </tr> 
 </tbody> 
</table>
