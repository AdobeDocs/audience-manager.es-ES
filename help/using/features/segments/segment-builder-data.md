---
description: Agregue y elimine características en el Generador de segmentos para ver las poblaciones reales de características junto con los datos de población de segmentos reales y estimados. Los datos de tamaño de población estimado le ayudan a crear el segmento correcto para su campaña.
seo-description: Agregue y elimine características en el Generador de segmentos para ver las poblaciones reales de características junto con los datos de población de segmentos reales y estimados. Los datos de tamaño de población estimado le ayudan a crear el segmento correcto para su campaña.
seo-title: Datos de población de características y segmentos en el Generador de segmentos
solution: Audience Manager
title: Datos de población de características y segmentos en el Generador de segmentos
uuid: e 1 e 59 c 0 a-b 4 c 7-4 cad -8485-3667 e 0 a 95 e 83
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Trait and Segment Population Data in Segment Builder {#trait-and-segment-population-data-in-segment-builder}

Add and remove traits in [!UICONTROL Segment Builder] to see actual trait populations along with actual and estimated segment population data. Los datos de tamaño de población estimado le ayudan a crear el segmento correcto para su campaña.

## Trait Population Data {#trait-population-data}

[!UICONTROL Segment Builder] la muestra [!UICONTROL Total Trait Population] el último día cuando agrega un rasgo a un segmento. This data appears in the blue field around your selected trait in the [!UICONTROL Basic View] section.

![](assets/trait-size.png)

La tabla siguiente define las métricas de población de características

<table id="table_9D837CF9ACA04D04BEE5925EC0B4A5D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población total de características</span> </p> </td>
   <td colname="col2"> <p>Número de ID únicos que tienen el rasgo seleccionado en su perfil. </p> </td>
  </tr> 
 </tbody> 
</table>

## Calculating Real and Estimated Segment Populations {#calculating-real-estimated-populations}

Cuando crea un nuevo segmento o cambia un segmento existente, Audience Manager tarda 24 horas en mostrar los resultados para las poblaciones de segmentos totales y en tiempo real.

Sin embargo, Audience Manager puede calcular inmediatamente el tamaño de población total y en tiempo real del segmento. Estos cálculos se basan en datos históricos de muestra y arrojan resultados en el intervalo de confianza del 95%.

![](assets/confidence-interval.png)

In [!UICONTROL Segment Builder], a blue bar on the estimated population graphs indicates the possible upper and lower ranges for segment size. Aunque el rendimiento anterior no garantiza resultados futuros, los datos estimados pueden ayudarle a comprender el tamaño potencial de un segmento nuevo o editado.

## Segment Population Data Overview {#segment-populations}

[!UICONTROL Segment Builder] le muestra los datos de población de segmentos al crear y editar segmentos.

* For estimated segment population data (real-time and total), [!UICONTROL Segment Builder] does not update the graphs automatically as you add or remove traits in a segment. Click **[!UICONTROL Calculate Estimates]** to see (or refresh) the estimated population numbers.

* For actual (real) segment population data (real-time and total), [!UICONTROL Segment Builder] updates the segment graph automatically when you load an existing segment. Para nuevos segmentos, o cuando agrega nuevas características a un segmento existente, los datos reales de población no se actualizan hasta las 24 horas después de crear el segmento.

![](assets/segment-data.png)

Consulte las definiciones siguientes para obtener más información sobre los datos de población de segmentos reales y estimados.

## Estimated Segment Population Data Defined {#estimated-segment-population}

La tabla siguiente define las métricas de población estimadas.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población en tiempo real estimada (potencial) </span> </p> </td> 
   <td colname="col2"> <p>La cantidad estimada de visitantes únicos que se vieron en tiempo real durante el intervalo de tiempo especificado y que fueron calificados para el segmento en el momento en que fueron vistos por Audience Manager. </p> <p>In <span class="wintitle"> Segment Builder</span>, the last 30-day populations for traits (<span class="wintitle"> Total Trait Populations</span>), can be different for traits and segments evaluated in real-times. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Para las características, la métrica de 30 días cuenta el número de usuarios únicos que califican para esa característica durante los últimos 30 días. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Para los segmentos evaluados en tiempo real, la métrica de 30 días cuenta el número de usuarios que han calificado para una característica (en ese segmento) en algún momento del pasado y que Audience Manager volvió a ver dentro de los últimos 30 días. Por ejemplo, supongamos que tiene un usuario que califica para una característica hace 60 días y que se vio nuevamente hace 10 días. En los datos, este usuario no se agregará al recuento de rasgos porque antes se califica para la característica más de 30 días antes. Sin embargo, se incluirán en el último recuento de 30 días de los segmentos evaluados en tiempo real. Esto se debe a que se ha calificado para el segmento dentro del intervalo de tiempo de 30 días. </li>
     </ul> </p> <p> <p>Note: The <span class="wintitle"> Estimated Real-Time Population</span> metric does not include devices that have qualified for a segment based on connections provided by a <span class="wintitle"> Profile Merge Rule</span> that uses a <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> device graph option</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población total estimada (potencial)</span> </p> </td> 
   <td colname="col2"> <p>La cantidad estimada de visitantes únicos que podrían estar en el segmento nuevo o modificado. Como sucede con casi cualquier estimación, el rendimiento anterior no garantiza resultados futuros, pero puede utilizar el total estimado para: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Ver cuántas personas pueden alcanzar un segmento nuevo o revisado mientras genera un segmento. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Ajuste el segmento según sus objetivos. Por ejemplo: los segmentos grandes son útiles para campañas de sensibilización de marca y segmentos más pequeños son útiles para enfocar o volver a segmentar campañas de forma centrada. </li> 
     </ul> </p> <p> <p>Note: The <span class="wintitle"> Estimated Total Population</span> metric does not include devices that have qualified for a segment based on connections provided by a <span class="wintitle"> Profile Merge Rule</span> that uses a <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> device graph option</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Existing (Actual) Segment Population Data Defined {#existing-segment-population}

[!UICONTROL Profile Merge Rules] afectan a los números reales de población en tiempo real y total. These totals vary depending on if the [!UICONTROL Profile Merge Rule] a segment belongs to uses a device graph option or not. See also, [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md).

### Datos de población de segmentos para combinar reglas sin una opción gráfica de dispositivo

The following table defines the actual real-time and total population metrics when your segments are used by a [!UICONTROL Profile Merge Rule] created without a device graph option. These are the device options settings **[!UICONTROL No Device Options]** and **[!UICONTROL Current Device Proflie]**.

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
   <td colname="col2"> <p>El número real de visitantes únicos que se vieron en tiempo real durante el intervalo de tiempo especificado y que fueron calificados para el segmento en el momento en que fueron vistos por Audience Manager. </p> <p>In <span class="wintitle"> Segment Builder</span>, the last 30-day populations for traits (<span class="wintitle"> Total Trait Populations</span>), can be different for traits and segments evaluated in real-time. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Para las características, la métrica de 30 días cuenta el número de usuarios únicos que califican para esa característica durante los últimos 30 días. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Para los segmentos evaluados en tiempo real, la métrica de 30 días cuenta el número de usuarios que han calificado para una característica (en ese segmento) en algún momento del pasado y que Audience Manager volvió a ver dentro de los últimos 30 días. Por ejemplo, supongamos que tiene un usuario que califica para una característica hace 60 días y que se vio nuevamente hace 10 días. En los datos, este usuario no se agregará al recuento de rasgos porque antes se califica para la característica más de 30 días antes. Sin embargo, se incluirán en el último recuento de 30 días de los segmentos evaluados en tiempo real. Esto se debe a que se ha calificado para el segmento dentro del intervalo de tiempo de 30 días. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población total (existente)</span> </p> </td> 
   <td colname="col2"> <p>El número real de visitantes únicos que estuvieron calificados para el segmento desde ayer. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Datos de población de segmentos para combinar reglas con una opción gráfica de dispositivo

The following table defines the actual real-time and total population metrics when your segments are used by a [!UICONTROL Profile Merge Rule] created with a device graph option. These are the device options settings for the [!UICONTROL Profile Link Device Graph], the [!DNL Adobe] device graph, and other third-party device graph choices that are available to you.

<table id="table_157EC6E5B5C44EB899854CA10B090F60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población en tiempo real (existente)</span> </p> </td> 
   <td colname="col2"> <p>The actual number of devices seen in real-time with current profiles that, when merged with up to 3-other device profiles connected by the device graph, contains the traits to qualify for the segment the moment it was seen by <span class="keyword"> Audience Manager</span>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población total (existente)</span> </p> </td> 
   <td colname="col2"> <p>Número total de dispositivos con perfiles que, cuando se combinan con hasta tres perfiles de dispositivo conectados mediante el gráfico de dispositivos, estaban todos cualificados para el segmento. </p> </td>
  </tr>
 </tbody>
</table>

### Limitaciones debido a las expresiones de actualización y frecuencia al calcular poblaciones de segmentos

[!UICONTROL Segment Builder] admite las estimaciones de tamaño de segmento para reglas de segmentos que contienen hasta 4 expresiones de frecuencia y actualización. Si se eligen más de 4 expresiones de frecuencia y actualización al generar una regla de segmento, el estimador de segmentos mostrará un error al calcular la población.

### Limitaciones debido a Combinar reglas al calcular poblaciones de segmentos

Actualmente, existe una limitación conocida porque el estimador de tamaño de segmento no cuenta con reglas de combinación de perfiles. For example, look at segments with the **No Authenticated Profile + Current Device Profile** [merge rule](../../features/profile-merge-rules/merge-rule-definitions.md). Debido al modo en que actualmente calculamos los números de estimación de segmentos, las poblaciones estimadas incluirán perfiles autenticados. Sin embargo, las poblaciones de segmentos existentes omitirán correctamente los perfiles autenticados.

>[!MORE_ LIKE_ THIS]
>
>* [Preguntas frecuentes sobre las reglas de combinación de perfiles y Device Graph](../../faq/faq-profile-merge.md)
>* [Vínculo de perfil](../../features/profile-merge-rules/merge-rules-overview.md)

