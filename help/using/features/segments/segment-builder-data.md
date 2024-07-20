---
description: Añada y elimine características en el Generador de segmentos para ver las poblaciones de características reales junto con los datos de población de segmentos reales y estimados. Los datos del tamaño estimado de la población le ayudan a crear el segmento adecuado para su campaña.
seo-description: Add and remove traits in Segment Builder to see actual trait populations along with actual and estimated segment population data. The estimated population size data helps you build the right segment for your campaign.
seo-title: Trait and Segment Population Data in Segment Builder
solution: Audience Manager
title: Datos de tamaño de segmentos y rasgos en el Generador de segmentos
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 1%

---

# [!UICONTROL Trait] y [!UICONTROL Segment] datos de población en [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

Agregue y elimine [!UICONTROL traits] en [!UICONTROL Segment Builder] para ver las poblaciones actuales de [!UICONTROL trait] junto con los datos de población de segmentos reales y estimados. Los datos del tamaño estimado de la población le ayudan a crear el segmento adecuado para su campaña.

## [!UICONTROL Trait] datos de población {#trait-population-data}

[!UICONTROL Segment Builder] le muestra [!UICONTROL Total Trait Population] del último día en que agregó un(a) [!UICONTROL trait] a un segmento. Estos datos aparecen en el campo azul alrededor de su [!UICONTROL trait] seleccionado en la sección [!UICONTROL Basic View].

![](assets/trait-size.png)

En la tabla siguiente se definen las métricas de población de rasgos:


| Métrica | Descripción |
|---------|----------|
| [!UICONTROL Total Trait Population] | El número de ID únicos que tienen el rasgo seleccionado en su perfil. |


## Cálculo de poblaciones de segmentos reales y estimados {#calculating-real-estimated-populations}

Al crear un segmento nuevo o cambiar uno existente, Audience Manager tarda hasta 24 horas en mostrar los resultados de las poblaciones de segmentos reales y totales.

Sin embargo, el Audience Manager puede estimar inmediatamente el tamaño de población total y en tiempo real del segmento. Estas estimaciones se basan en datos históricos muestreados y devuelven resultados con un intervalo de confianza del 95 %.

![](assets/confidence-interval.png)

En [!UICONTROL Segment Builder], una barra azul en los gráficos de población estimada indica los posibles intervalos superior e inferior para el tamaño del segmento. Aunque el rendimiento anterior no garantiza resultados futuros, los datos estimados pueden ayudarle a comprender el tamaño potencial de un segmento nuevo o editado.

## Resumen de datos de población de segmentos {#segment-populations}

[!UICONTROL Segment Builder] le muestra datos de población de segmentos a medida que crea y edita segmentos.

* Para los datos de población de segmentos estimados (tiempo real y total), [!UICONTROL Segment Builder] no actualiza los gráficos automáticamente a medida que agrega o elimina características en un segmento. Haga clic en **[!UICONTROL Calculate Estimates]** para ver (o actualizar) los números de población estimados.

* Para los datos reales (en tiempo real) de población de segmentos (en tiempo real y totales), [!UICONTROL Segment Builder] actualiza el gráfico de segmentos automáticamente cuando se carga un segmento existente. Para los segmentos nuevos o cuando se añaden nuevas características a un segmento existente, los datos de población reales no se actualizan hasta 24 horas después de la creación del segmento.

![](assets/segment-data.png)

Consulte las definiciones siguientes para obtener más información sobre los datos de población de segmentos estimados y reales.

## Datos de población del segmento estimados definidos {#estimated-segment-population}

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
   <td colname="col1"> <p> <span class="wintitle"> Estimación de la población en tiempo real (potencial) </span> </p> </td> 
   <td colname="col2"> <p>El número estimado de visitantes únicos vistos en tiempo real durante el intervalo de tiempo especificado y que estaban cualificados para el segmento en el momento en que fueron vistos por el Audience Manager. </p> <p>En <span class="wintitle"> Generador de segmentos</span>, las poblaciones de los últimos 30 días para características (<span class="wintitle"> Poblaciones totales de características</span>) pueden ser diferentes para características y segmentos evaluados en tiempo real. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">En el caso de los rasgos, la métrica de los últimos 30 días cuenta el número de usuarios únicos que cumplen los requisitos para ese rasgo durante los últimos 30 días. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Para los segmentos evaluados en tiempo real, la métrica de los últimos 30 días cuenta el número de usuarios que han cumplido los requisitos para una característica (en ese segmento) en algún momento del pasado y que el Audience Manager ha vuelto a ver en los últimos 30 días. Por ejemplo, supongamos que tiene un usuario que cumple los requisitos para un rasgo hace 60 días y que se vio de nuevo hace 10 días. En los datos, este usuario no se añade al recuento de rasgos porque se clasificó por primera vez para el rasgo hace más de 30 días. Sin embargo, se incluirán en el recuento de los últimos 30 días para los segmentos evaluados en tiempo real. Esto se debe a que se han clasificado para el segmento en el intervalo de tiempo de 30 días. </li>
     </ul> </p> <p> <p>Nota: La métrica <span class="wintitle"> Estimated Real-Time Population</span> no incluye dispositivos que se hayan clasificado para un segmento basado en conexiones proporcionadas por una <span class="wintitle"> Profile Merge Rule</span> que usa una opción de gráfico de dispositivos <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"></a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población total estimada (potencial)</span> </p> </td> 
   <td colname="col2"> <p>El número estimado de visitantes únicos que podrían estar en el segmento nuevo o modificado. Como con casi cualquier estimación, el rendimiento anterior no garantiza resultados futuros, pero puede utilizar el total estimado para lo siguiente: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Vea cuántas personas puede alcanzar un segmento nuevo o revisado a medida que genera un segmento. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Ajuste el segmento en función de sus objetivos. Por ejemplo, los segmentos grandes son útiles para campañas de reconocimiento de marca y los más pequeños son útiles para campañas de direccionamiento o redireccionamiento enfocadas. </li> 
     </ul> </p> <p> <p>Nota: La métrica <span class="wintitle"> Población total estimada </span> no incluye dispositivos que cumplen los requisitos para un segmento según las conexiones proporcionadas por una regla de combinación de perfiles <span class="wintitle"> </span> que usa una opción de gráfico de dispositivos <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Datos Existentes (Reales) De Población De Segmentos Definidos {#existing-segment-population}

[!UICONTROL Profile Merge Rules] afectan los números de población reales y totales. Estos totales varían dependiendo de si el [!UICONTROL Profile Merge Rule] al que pertenece un segmento usa o no una opción de gráfico de dispositivos. Vea también [Opciones definidas de reglas de combinación de perfiles](../../features/profile-merge-rules/merge-rule-definitions.md).

### Datos de población de segmentos para [!UICONTROL Merge Rules] sin [!UICONTROL Device Graph Option]

La siguiente tabla define las métricas de población reales en tiempo real y totales cuando un [!UICONTROL Profile Merge Rule] creado sin la opción [!UICONTROL device graph] usa sus segmentos. Estas son las opciones de configuración del dispositivo **[!UICONTROL No Device Options]** y **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> población en tiempo real (existente)</span> </p> </td> 
   <td colname="col2"> <p>El número real de visitantes únicos vistos en tiempo real durante el intervalo de tiempo especificado y que estaban cualificados para el segmento en el momento en que fueron vistos por el Audience Manager. </p> <p>En <span class="wintitle"> Generador de segmentos</span>, las poblaciones de los últimos 30 días para características (<span class="wintitle"> Poblaciones totales de características</span>) pueden ser diferentes para características y segmentos evaluados en tiempo real. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">En el caso de los rasgos, la métrica de los últimos 30 días cuenta el número de usuarios únicos que cumplen los requisitos para ese rasgo durante los últimos 30 días. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Para los segmentos evaluados en tiempo real, la métrica de los últimos 30 días cuenta el número de usuarios que han cumplido los requisitos para una característica (en ese segmento) en algún momento del pasado y que el Audience Manager ha vuelto a ver en los últimos 30 días. Por ejemplo, supongamos que tiene un usuario que cumple los requisitos para un rasgo hace 60 días y que se vio de nuevo hace 10 días. En los datos, este usuario no se añade al recuento de rasgos porque se clasificó por primera vez para el rasgo hace más de 30 días. Sin embargo, se incluirán en el recuento de los últimos 30 días para los segmentos evaluados en tiempo real. Esto se debe a que se han clasificado para el segmento en el intervalo de tiempo de 30 días. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Población total (existente)</span> </p> </td> 
   <td colname="col2"> <p>La cantidad real de visitantes únicos que cumplían los requisitos para el segmento a partir de ayer. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Datos de población de segmentos para [!UICONTROL Merge Rules] con la opción [!UICONTROL Device Graph]

La siguiente tabla define las métricas de población reales en tiempo real y totales cuando un [!UICONTROL Profile Merge Rule] creado con una opción [!DNL device graph] utiliza sus segmentos. Estas son las opciones de configuración del dispositivo para [!UICONTROL Profile Link Device Graph], [!DNL Adobe] [!DNL device graph] y otras opciones de terceros [!DNL device graph] que están disponibles para usted.


| Columna A | Columna B |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing)] | El número real de dispositivos vistos en tiempo real con perfiles actuales que, cuando se combinan con hasta 100 perfiles de dispositivos conectados por el gráfico del dispositivo, contienen los rasgos para calificar para el segmento en el momento en que el Audience Manager lo vio. |
| [!UICONTROL Total Population (Existing)] | El número total de dispositivos con perfiles que, cuando se combinan con hasta 100 perfiles de otros dispositivos conectados por el gráfico del dispositivo, estaban todos cualificados para el segmento. |

### Limitaciones debidas a expresiones de actualización y frecuencia al calcular las poblaciones de segmentos

[!UICONTROL Segment Builder] admite estimaciones de tamaño de segmento para reglas de segmento que contienen hasta 4 expresiones de actualización y frecuencia. La elección de más de 4 expresiones de actualización y frecuencia al crear una regla de segmento hace que el estimador de segmentos muestre un error al estimar la población.

### Limitaciones debidas a [!UICONTROL Merge Rules] al calcular las poblaciones de segmentos

Actualmente, existe una limitación conocida porque el estimador de tamaño del segmento no tiene en cuenta [!UICONTROL profile merge rules]. Por ejemplo, observe los segmentos con **[!UICONTROL No Authenticated Profile + Current Device Profile]** [regla de combinación](../../features/profile-merge-rules/merge-rule-definitions.md). Debido a la forma en que calculamos actualmente los números de estimación de segmentos, las poblaciones estimadas incluirán perfiles autenticados. Sin embargo, las poblaciones de segmentos existentes ignorarán correctamente los perfiles autenticados.

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre las reglas de combinación de perfiles y el gráfico de dispositivos](../../faq/faq-profile-merge.md)
>* [Vínculo de perfil](../profile-merge-rules/merge-rules-overview.md)
