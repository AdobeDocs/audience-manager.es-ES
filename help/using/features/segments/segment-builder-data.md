---
description: añadir y elimine características en el Generador de segmentos para ver las poblaciones de características reales junto con los datos de población segmento real y estimada. Los datos del tamaño estimado de la población ayudan a versión la segmento correcta para su campaña.
seo-description: Add and remove traits in Segment Builder to see actual trait populations along with actual and estimated segment population data. The estimated population size data helps you build the right segment for your campaign.
seo-title: Trait and Segment Population Data in Segment Builder
solution: Audience Manager
title: Datos de población de rasgos y segmentos en el Generador de segmentos
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 1%

---

# [!UICONTROL Trait] y [!UICONTROL Segment] Datos de población en [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

añadir y elimine [!UICONTROL traits] [!UICONTROL Segment Builder] para ver las poblaciones reales [!UICONTROL trait] junto con los datos de población segmento real y estimados. Los datos del tamaño estimado de la población ayudan a versión la segmento correcta para su campaña.

## [!UICONTROL Trait] Datos de población {#trait-population-data}

[!UICONTROL Segment Builder][!UICONTROL Total Trait Population] Le muestra el último día cuando agrega una [!UICONTROL trait] a una segmento. Estos datos aparecen en el campo azul alrededor de la selección [!UICONTROL trait] en la [!UICONTROL Basic View] sección.

![](assets/trait-size.png)

En la tabla siguiente se definen las métricas de población de rasgos:


| Métrica | Descripción |
|---------|----------|
| [!UICONTROL Total Trait Population] | El número de ID únicos que tienen el rasgo seleccionado en su perfil. |


## Cálculo de poblaciones de segmentos reales y estimadas {#calculating-real-estimated-populations}

Cuando se crea una nueva segmento o se cambia una segmento existente, Audience Manager tarda hasta 24 horas en mostrar los resultados de las poblaciones de segmento totales y en tiempo real.

Sin embargo, Audience Manager puede estimar inmediatamente el tamaño de la población total y en tiempo real de su segmento. Estas estimaciones se basan en datos históricos muestreadas y resultados de retorno en el 95% intervalo de confianza.

![](assets/confidence-interval.png)

En [!UICONTROL Segment Builder], una barra azul en los gráficos de población estimada indica los posibles rangos superior e inferior para el tamaño segmento. Aunque el rendimiento anterior no garantiza resultados futuros, los datos estimados pueden ayudarle a comprender el tamaño potencial de un segmento nuevo o editado.

## Descripción general de los datos de población de segmentos {#segment-populations}

[!UICONTROL Segment Builder] Muestra segmento datos de población a medida que se crean y editan segmentos.

* Para los datos de población de segmento estimados (en tiempo real y totales), [!UICONTROL Segment Builder] no actualiza los gráficos automáticamente a medida que agrega o elimina características en un segmento. Haga clic **[!UICONTROL Calculate Estimates]** para ver (o actualizar) las cifras estimadas de población.

* Para los datos de población real (real) segmento (en tiempo real y total), [!UICONTROL Segment Builder] actualiza el gráfico de segmento automáticamente al cargar un segmento existente. Para segmentos nuevos, o cuando se agregan nuevas características a un segmento existente, los datos de población reales no se actualizan hasta 24 horas después de crear el segmento.

![](assets/segment-data.png)

Consulte las definiciones siguientes para obtener más información sobre los datos de población segmento estimados y reales.

## Definición de los datos de población estimada del segmento {#estimated-segment-population}

En la tabla siguiente se definen las métricas de población estimadas.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población estimada en tiempo real (potencial) </span> </p> </td> 
   <td colname="col2"> <p>El número estimado de visitantes únicos vistos en tiempo real durante el intervalo de tiempo especificado y que estaban calificados para el segmento en el momento en que fueron vistos por Audience Manager. </p> <p>En <span class="wintitle"> el Generador de segmentos</span>, las poblaciones de los últimos 30 días para los rasgos (<span class="wintitle"> poblaciones</span> totales de rasgos) pueden ser diferentes para los rasgos y segmentos evaluados en tiempo real. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Para las características, la Métrica de los últimos 30 días cuenta el número de usuarios únicos que cumplieron los requisitos para esa característica durante los últimos 30 días. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Para los segmentos evaluados en tiempo real, el Métrica de los últimos 30 días cuenta el número de usuarios que han calificado para un rasgo (en ese segmento) en algún momento en el pasado y que han sido vistos nuevamente por Audience Manager en los últimos 30 días. Por ejemplo, supongamos que tiene un usuario que calificó para un rasgo hace 60 días y fue visto nuevamente hace 10 días. En los datos, este usuario no se agregará al recuento de rasgos porque calificaron por primera vez para el rasgo hace más de 30 días. Sin embargo, se incluirán en el recuento de los últimos 30 días para los segmentos evaluados en tiempo real. Esto se debe a que han calificado para el segmento dentro del intervalo de tiempo de 30 días. </li>
     </ul> </p> <p> <p>Nota: El <span class="wintitle"> Métrica de población</span> estimada en tiempo real no incluye dispositivos que cumplen los requisitos para una segmento en función de las conexiones proporcionadas por una <span class="wintitle"> regla</span> de combinación de perfiles que usa una opción<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> de </a> gráfico dispositivos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población total estimada (potencial)</span> </p> </td> 
   <td colname="col2"> <p>El número estimado de visitantes únicos que podrían estar en su segmento nuevo o modificado. Al igual que con casi cualquier estimación, el rendimiento anterior no garantiza resultados futuros, pero puede utilizar el total estimado para: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Vea a cuántas personas podría llegar un segmento nuevo o revisado a medida que versión un segmento. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Ajusta el segmento en función de tus objetivos. Por ejemplo, los segmentos grandes son útiles para campañas de marca y sensibilizar y los segmentos más pequeños son útiles para campañas de direccionamiento enfocada o de direccionamiento. </li> 
     </ul> </p> <p> <p>Nota: El <span class="wintitle"> Métrica de población</span> total estimada no incluye dispositivos que cumplen los requisitos para un segmento en función de las conexiones proporcionadas por una <span class="wintitle"> regla</span> de combinación de perfiles que utiliza una opción<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> de </a> gráfico dispositivos. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Definición de los datos de población de segmentos existentes (reales) {#existing-segment-population}

[!UICONTROL Profile Merge Rules] afectan a las cifras reales de población total y en tiempo real. Estos totales varían en función de si la [!UICONTROL Profile Merge Rule] segmento a la que pertenece utiliza o no una opción de gráfico dispositivos. Consulte también [Regla de combinación de perfiles Opciones definida](../../features/profile-merge-rules/merge-rule-definitions.md).

### Datos de población de segmentos para [!UICONTROL Merge Rules] Sin [!UICONTROL Device Graph Option]

En la tabla siguiente se definen las métricas de población total y en tiempo real reales cuando los segmentos los utiliza un [!UICONTROL Profile Merge Rule] creado sin opción [!UICONTROL device graph] . Estas son las opciones de dispositivos configuración **[!UICONTROL No Device Options]** y **[!UICONTROL Current Device Proflie]**.

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
   <td colname="col2"> <p>El número real de visitantes únicos vistos en tiempo real durante el intervalo de tiempo especificado y que estaban cualificados para el segmento en el momento en que fueron vistos por Audience Manager. </p> <p>En <span class="wintitle"> el Generador de segmentos</span>, las poblaciones de rasgos de los últimos<span class="wintitle"> 30 días (poblaciones</span> totales de rasgos) pueden ser diferentes para los rasgos y segmentos evaluados en tiempo real. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Para las características, la Métrica de los últimos 30 días cuenta el número de usuarios únicos que cumplieron los requisitos para esa característica durante los últimos 30 días. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Para los segmentos evaluados en tiempo real, el Métrica de los últimos 30 días cuenta el número de usuarios que han calificado para un rasgo (en ese segmento) en algún momento en el pasado y que han sido vistos nuevamente por Audience Manager en los últimos 30 días. Por ejemplo, supongamos que tiene un usuario que calificó para un rasgo hace 60 días y fue visto nuevamente hace 10 días. En los datos, este usuario no se agregará al recuento de rasgos porque calificaron por primera vez para el rasgo hace más de 30 días. Sin embargo, se incluirán en el recuento de los últimos 30 días para los segmentos evaluados en tiempo real. Esto se debe a que han calificado para el segmento dentro del intervalo de tiempo de 30 días. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población total (existente)</span> </p> </td> 
   <td colname="col2"> <p>El número real de visitantes únicos que estaban calificados para el segmento a partir de ayer. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Datos de población de segmentos para [!UICONTROL Merge Rules] con una [!UICONTROL Device Graph] opción

En la tabla siguiente se definen las métricas de población total y en tiempo real reales cuando los segmentos los utiliza un [!UICONTROL Profile Merge Rule] creado con una [!DNL device graph] opción. Estas son las opciones de configuración de dispositivos para el [!UICONTROL Profile Link Device Graph], el , y [!DNL Adobe] [!DNL device graph]otras opciones de terceros [!DNL device graph] que tiene a su disposición.


| Columna A | Columna B |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing)] | El número real de dispositivos vistos en tiempo real con perfiles actuales que, cuando se fusionan con hasta otros 100 perfiles de dispositivos conectados por el gráfico de dispositivos, contiene los rasgos para calificar para el segmento el momento en que fue visto por Audience Manager. |
| [!UICONTROL Total Population (Existing)] | El número total de dispositivos con perfiles que, cuando se fusionaron con hasta otros 100 perfiles dispositivos conectados por el gráfico dispositivos, fueron calificados para el segmento. |

### Limitaciones debidas a las expresiones de actualización y frecuencia al estimar las poblaciones de segmentos

[!UICONTROL Segment Builder] Admite estimaciones de tamaño segmento para reglas de segmento que contienen hasta 4 expresiones de Frecuencia y actualización. Si elige más de 4 expresiones de actualización y Frecuencia al crear una regla de segmento, el estimador de segmento mostrará un error al estimar la población.

### Limitaciones debidas a [!UICONTROL Merge Rules] la hora de estimar las poblaciones de segmentos

Actualmente, existe una limitación conocida porque nuestro estimador de tamaño segmento no cuenta para [!UICONTROL profile merge rules]. Por ejemplo, mire los segmentos con el **[!UICONTROL No Authenticated Profile + Current Device Profile]** [regla](../../features/profile-merge-rules/merge-rule-definitions.md) de combinación. Debido a la forma en que actualmente calculamos los números de estimación de segmento, las poblaciones estimadas incluirán perfiles autenticados. Sin embargo, las poblaciones de segmento existentes ignorarán correctamente los perfiles autenticados.

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre las reglas de combinación de perfiles y el gráfico de dispositivos](../../faq/faq-profile-merge.md)
>* [Vínculo de perfil](../profile-merge-rules/merge-rules-overview.md)
