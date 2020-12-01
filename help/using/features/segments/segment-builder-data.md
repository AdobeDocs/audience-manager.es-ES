---
description: Añada y elimine características en el Generador de segmentos para ver las poblaciones de características reales junto con los datos de población de segmentos reales y estimados. Los datos de tamaño de población estimados le ayudan a crear el segmento adecuado para su campaña.
seo-description: Añada y elimine características en el Generador de segmentos para ver las poblaciones de características reales junto con los datos de población de segmentos reales y estimados. Los datos de tamaño de población estimados le ayudan a crear el segmento adecuado para su campaña.
seo-title: Datos de tamaño de segmentos y rasgos en el Generador de segmentos
solution: Audience Manager
title: Datos de tamaño de segmentos y rasgos en el Generador de segmentos
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 2%

---


# [!UICONTROL Trait] y datos  [!UICONTROL Segment] de población en  [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

Añada y elimine [!UICONTROL traits] en [!UICONTROL Segment Builder] para ver las [!UICONTROL trait] poblaciones reales junto con los datos de población de segmentos reales y estimados. Los datos de tamaño de población estimados le ayudan a crear el segmento adecuado para su campaña.

## [!UICONTROL Trait] Datos de población  {#trait-population-data}

[!UICONTROL Segment Builder] La muestra  [!UICONTROL Total Trait Population] el último día en que se agrega un  [!UICONTROL trait] a un segmento. Estos datos aparecen en el campo azul alrededor de su [!UICONTROL trait] seleccionado en la sección [!UICONTROL Basic View].

![](assets/trait-size.png)

La tabla siguiente define las métricas de población de características:


| Métrica | Descripción |
---------|----------|
| [!UICONTROL Total Trait Population] | El número de ID únicos que tienen la característica seleccionada en su perfil. |


## Calcular las poblaciones de segmentos reales y estimados {#calculating-real-estimated-populations}

Cuando se crea un segmento nuevo o se cambia un segmento existente, el Audience Manager tarda hasta 24 horas en mostrar los resultados de las poblaciones de segmentos totales y en tiempo real.

Sin embargo, el Audience Manager puede calcular inmediatamente el tamaño de población total y en tiempo real del segmento. Estas estimaciones se basan en datos históricos de muestra y devuelven resultados en el intervalo de confianza del 95 %.

![](assets/confidence-interval.png)

En [!UICONTROL Segment Builder], una barra azul en los gráficos de población estimados indica los posibles rangos superior e inferior para el tamaño del segmento. Aunque el rendimiento anterior no garantiza resultados futuros, los datos estimados pueden ayudarle a comprender el tamaño potencial de un segmento nuevo o editado.

## Información general de datos de población de segmentos {#segment-populations}

[!UICONTROL Segment Builder] La muestra los datos de población de segmentos a medida que crea y edita segmentos.

* Para los datos de población de segmentos estimados (en tiempo real y total), [!UICONTROL Segment Builder] no actualiza los gráficos automáticamente a medida que agrega o elimina características en un segmento. Haga clic en **[!UICONTROL Calculate Estimates]** para ver (o actualizar) los números de población estimados.

* Para los datos de población de segmentos reales (reales) (en tiempo real y en total), [!UICONTROL Segment Builder] actualiza el gráfico de segmentos automáticamente al cargar un segmento existente. Para segmentos nuevos o cuando agrega nuevas características a un segmento existente, los datos de población reales no se actualizan hasta 24 horas después de crear el segmento.

![](assets/segment-data.png)

Consulte las definiciones siguientes para obtener más información sobre los datos de población de segmentos estimados y reales.

## Datos de población de segmentos estimados definidos {#estimated-segment-population}

La siguiente tabla define las métricas de población estimadas.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población estimada en tiempo real (potencial)  </span> </p> </td> 
   <td colname="col2"> <p>El número estimado de visitantes únicos vistos en tiempo real durante el intervalo de tiempo especificado y que estaban cualificados para el segmento en el momento en que los vio el Audience Manager. </p> <p>En <span class="wintitle"> Generador de segmentos</span>, las últimas poblaciones de 30 días para características (<span class="wintitle"> Total de características</span>) pueden ser diferentes para características y segmentos evaluados en tiempo real. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Para las características, la última métrica de 30 días cuenta el número de usuarios únicos que calificaron para esa característica durante los últimos 30 días. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">En el caso de los segmentos evaluados en tiempo real, la última métrica de 30 días cuenta el número de usuarios que se han clasificado para una característica (en ese segmento) en algún momento del pasado y que el Audience Manager ha vuelto a ver en los últimos 30 días. Por ejemplo, supongamos que tiene un usuario que se calificó para una característica hace 60 días y que se volvió a ver hace 10 días. En los datos, este usuario no se agregará al recuento de características porque primero calificó para la característica hace más de 30 días. Sin embargo, se incluirán en el último recuento de 30 días para los segmentos evaluados en tiempo real. Esto se debe a que cumplen los requisitos para el segmento dentro del intervalo de tiempo de 30 días. </li>
     </ul> </p> <p> <p>Nota: La métrica <span class="wintitle"> Población en tiempo real estimada</span> no incluye dispositivos que hayan calificado para un segmento en función de las conexiones proporcionadas por una <span class="wintitle"> regla de combinación de Perfiles</span> que utiliza una <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> opción de gráfico de dispositivos</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población total estimada (potencial)</span> </p> </td> 
   <td colname="col2"> <p>El número estimado de visitantes únicos que podrían estar en el segmento nuevo o modificado. Como en casi cualquier cálculo, el rendimiento anterior no garantiza resultados futuros, pero puede utilizar el total estimado para: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Ver a cuántas personas puede llegar un segmento nuevo o revisado a medida que crea un segmento. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Ajuste el segmento en función de sus objetivos. Por ejemplo, los segmentos grandes son útiles para campañas de reconocimiento de marca y los segmentos más pequeños son útiles para campañas de objetivo o redireccionamiento centrados. </li> 
     </ul> </p> <p> <p>Nota: La métrica <span class="wintitle"> Población total estimada</span> no incluye dispositivos que hayan calificado para un segmento en función de las conexiones proporcionadas por una <span class="wintitle"> regla de combinación de Perfiles</span> que utilice una <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> opción de gráfico de dispositivos</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Datos de población de segmentos existentes (reales) definidos {#existing-segment-population}

[!UICONTROL Profile Merge Rules] afectan a los números de población totales y en tiempo real. Estos totales varían en función de si el [!UICONTROL Profile Merge Rule] segmento al que pertenece utiliza una opción de gráfico de dispositivos o no. Consulte también [Opciones de regla de combinación de Perfiles definidas](../../features/profile-merge-rules/merge-rule-definitions.md).

### Datos de población de segmentos para [!UICONTROL Merge Rules] sin [!UICONTROL Device Graph Option]

La siguiente tabla define las métricas de población totales y en tiempo real cuando los segmentos son utilizados por una [!UICONTROL Profile Merge Rule] creada sin una opción [!UICONTROL device graph]. Estas son las opciones de configuración del dispositivo **[!UICONTROL No Device Options]** y **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población en tiempo real (existente)</span> </p> </td> 
   <td colname="col2"> <p>El número real de visitantes únicos que se ven en tiempo real durante el intervalo de tiempo especificado y que se califican para el segmento en el momento en que el Audience Manager los ve. </p> <p>En <span class="wintitle"> Generador de segmentos</span>, las últimas poblaciones de 30 días para características (<span class="wintitle"> Total de características</span>) pueden ser diferentes para características y segmentos evaluados en tiempo real. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Para las características, la última métrica de 30 días cuenta el número de usuarios únicos que calificaron para esa característica durante los últimos 30 días. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">En el caso de los segmentos evaluados en tiempo real, la última métrica de 30 días cuenta el número de usuarios que se han clasificado para una característica (en ese segmento) en algún momento del pasado y que el Audience Manager ha vuelto a ver en los últimos 30 días. Por ejemplo, supongamos que tiene un usuario que se calificó para una característica hace 60 días y que se volvió a ver hace 10 días. En los datos, este usuario no se agregará al recuento de características porque primero calificó para la característica hace más de 30 días. Sin embargo, se incluirán en el último recuento de 30 días para los segmentos evaluados en tiempo real. Esto se debe a que cumplen los requisitos para el segmento dentro del intervalo de tiempo de 30 días. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población total (existente)</span> </p> </td> 
   <td colname="col2"> <p>El número real de visitantes únicos que se calificaron para el segmento desde ayer. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Datos de población de segmentos para [!UICONTROL Merge Rules] con una opción [!UICONTROL Device Graph]

La siguiente tabla define las métricas de población totales y en tiempo real cuando un [!UICONTROL Profile Merge Rule] creado con una opción [!DNL device graph] utiliza los segmentos. Estas son las opciones de configuración del dispositivo para las [!UICONTROL Profile Link Device Graph], las [!DNL Adobe] [!DNL device graph] y otras [!DNL device graph] opciones de terceros que están disponibles para usted.


| Columna A | Columna B |
---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | El número real de dispositivos que se ven en tiempo real con perfiles actuales y que, cuando se combinan con hasta 100 perfiles de dispositivo conectados por el gráfico de dispositivo, contiene las características para calificar para el segmento en el momento en que lo vio el Audience Manager. |
| [!UICONTROL Total Population (Existing)] | El número total de dispositivos con perfiles que, cuando se combinaron con hasta 100 perfiles de dispositivos conectados por el gráfico de dispositivos, se calificaron para el segmento. |

### Limitaciones debidas a Expresiones de actualización y frecuencia al calcular poblaciones de segmentos

[!UICONTROL Segment Builder] admite estimaciones del tamaño del segmento para reglas de segmentos que contienen hasta 4 expresiones de frecuencia y actualización. Si se eligen más de 4 expresiones de frecuencia y actualización al crear una regla de segmento, el estimador de segmentos mostrará un error al calcular la población.

### Limitaciones debidas a [!UICONTROL Merge Rules] al calcular poblaciones de segmentos

Actualmente, existe una limitación conocida porque nuestro estimador de tamaño de segmento no tiene en cuenta [!UICONTROL profile merge rules]. Por ejemplo, observe los segmentos con la **[!UICONTROL No Authenticated Profile + Current Device Profile]** [regla de combinación](../../features/profile-merge-rules/merge-rule-definitions.md). Debido a la manera en que actualmente calculamos los números de estimación de segmentos, las poblaciones estimadas incluirán perfiles autenticados. Sin embargo, las poblaciones de segmentos existentes omitirán correctamente los perfiles autenticados.

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre las reglas de combinación de perfiles y el gráfico de dispositivos](../../faq/faq-profile-merge.md)
>* [Vínculo de perfil](../profile-merge-rules/merge-rules-overview.md)

