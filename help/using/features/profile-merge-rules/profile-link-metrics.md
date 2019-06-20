---
description: Las métricas de vínculos de perfil proporcionan datos sobre las personas y los dispositivos que autentican al sitio. Los datos y los gráficos de los vínculos de perfil se actualizan dinámicamente al crear reglas de combinación o al hacer clic en una regla existente del tablero Reglas de combinación de perfiles. Estas métricas pueden incluir gráficos de dispositivos de Adobe Experience Cloud Device Co-op u otras fuentes de gráficos de dispositivos de terceros.
seo-description: Las métricas de vínculos de perfil proporcionan datos sobre las personas y los dispositivos que autentican al sitio. Los datos y los gráficos de los vínculos de perfil se actualizan dinámicamente al crear reglas de combinación o al hacer clic en una regla existente del tablero Reglas de combinación de perfiles. Estas métricas pueden incluir gráficos de dispositivos de Adobe Experience Cloud Device Co-op u otras fuentes de gráficos de dispositivos de terceros.
seo-title: Métricas de informe para reglas de combinación de perfiles
solution: Audience Manager
title: Métricas de informe para reglas de combinación de perfiles
uuid: 76 a 86 ff 0-4 c 64-4734-aec 0-0 a 8828942096
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Report Metrics for Profile Merge Rules {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Link] proporcionan datos sobre las personas y los dispositivos que autentican al sitio. The data and graphs in [!UICONTROL Profile Link] update dynamically as you create a merge rules or when you click an existing rule from the [!UICONTROL Profile Merge Rules] dashboard. These metrics can include device graph from the [!DNL Adobe Experience Cloud Device Co-op] or other third-party device graph sources.

## Merge Rule Metrics {#merge-rule-metrics}

Reports return data in side-by-side bar graphs when your merge rules use data from the [Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/) or other, third-party device graphs you may have access to in [!DNL Audience Manager]. This lets you compare your authenticated, first-party data with cross-device data provided by the [!UICONTROL Experience Cloud Device Co-op] or another, third-party device graph. For information about data returned by the [!UICONTROL Device Co-op], see [The Device Graph: Internal Processes and Output](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html). Estos datos se actualizan diariamente.

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Actividad autenticada</span></b> </p> </td> 
   <td colname="col2"> <p>Muestra: </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Personas activas</span>: El número de personas que se han autenticado en el sitio durante los últimos 60 días. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Dispositivo cruzado</span>: El número total de ID <a href="../../features/profile-merge-rules/merge-rules-start.md#create-data-source"> de dispositivo cruzado</a> almacenados en la fuente <a href="../../features/manage-datasources.md#create-data-source"> de datos</a> del perfil <a href="../../features/profile-merge-rules/merge-rule-definitions.md"> autenticado seleccionado</a> durante la duración de la fuente de datos. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % Activa Personas</span>: Muestra <span class="wintitle"> Personas activas</span> como un porcentaje. </li> 
    </ul> <p> <span class="wintitle"> La actividad autenticada</span> permite comparar fuentes de datos por actividad, volumen y porcentaje. Puede ayudarle a encontrar una fuente de datos que tenga muchas personas y un gran porcentaje de usuarios activos. O bien, puede encontrar valores para comparar fuentes de datos con una gran proporción de usuarios activos en comparación con el tamaño total de la audiencia. Por ejemplo, a veces un origen de datos con números de vida totales bajos y una actividad alta son más valiosos que los que tienen resultados de duración altos y números de actividad bajos. </p> <p> <p>Note: The <span class="wintitle"> Authenticated Activity</span> metrics contain <span class="wintitle"> Profile Link</span> data only. This report does not include <span class="wintitle"> Device Graph</span> data. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Promedio de dispositivos por persona</span></b> </p> </td> 
   <td colname="col2"> <p> Muestra el número promedio de dispositivos que utilizan los visitantes que se han autenticado en el sitio para la fuente de datos seleccionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Dispositivos totales</span></b> </p> </td> 
   <td colname="col2"> <p>Muestra el número total de dispositivos utilizados para autenticar al sitio en el origen de datos seleccionado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Total de personas</span></b> </p> </td> 
   <td colname="col2"> <p>Muestra el número total de personas identificadas de forma disuasiva para la fuente de datos seleccionada. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Device Graph Metrics {#device-graph-metrics}

[!UICONTROL Merge Rules] Los informes también muestran datos sobre el número total de personas y dispositivos que han visitado el sitio para la fuente de datos y el gráfico de dispositivos seleccionados. Estas métricas devuelven datos basados en intervalos de tiempo preestablecidos (el período de retroceso) que varían según la opción de dispositivo que seleccione al crear una regla. En la tabla siguiente se enumeran los intervalos de estos informes para cada opción de gráfico de dispositivos.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción Gráfico de dispositivo </th> 
   <th colname="col2" class="entry"> Intervalo de retroceso del informe </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Vínculo de perfil</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">Total de personas: 60 días </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">Dispositivos totales: 120 días </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Device Graph Co-op</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">Total de personas: 180 días </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">Dispositivos totales: 180 días </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Liveramp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">Total de personas: 180 días </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">Dispositivos totales: 180 días </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapa</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">Total de personas: 60 días </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">Dispositivos totales 60 días </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sample Reports {#sample-reports}

### Informe de vínculos de perfil estándar

A standard [!UICONTROL Profile Link] report looks like the following example. Combinar reglas que utilizan varias fuentes de datos (hasta 3, máximo) muestran gráficos en fichas independientes para cada fuente de datos. This merge rule does not include [!UICONTROL Device Co-op] data.

![](assets/coop-metrics1.png)

### Informe de vínculos de perfil con datos de gráficos de dispositivos

[!UICONTROL Profile Link] Informe que incluye datos de gráficos de dispositivos de un gráfico [!UICONTROL Adobe Experience Cloud Device Co-op] de dispositivos de terceros o gráficos de dispositivos de [!UICONTROL Profile Link] terceros, y gráficos de dispositivos con gráficos de barras contiguos. Placing these graphs adjacent to each other lets you evaluate the benefits of using the [!UICONTROL Experience Cloud Device Co-op] compared to [!UICONTROL Profile Link] by itself. Combinar reglas que utilizan varias fuentes de datos (hasta 3, máximo) muestran gráficos en fichas independientes para cada fuente de datos. As a reminder, the [!UICONTROL Authenticated Activity] graph and metrics do not return data from the [!DNL Adobe] device graph or other, third-party device graphs you may have access to in [!DNL Audience Manager].

![](assets/coop-metrics2.png)

## Profile Link Trend Graphs {#profile-link-trend}

In addition to the other data visualizations, [!UICONTROL Profile Link] reports include a line graph. El gráfico de líneas está diseñado para mostrar las tendencias a lo largo del tiempo para las reglas de perfil. Trend graphs (and the other reports) are available when you click a rule from the [!UICONTROL Profile Merge Rules] landing page ( **[!UICONTROL Audience Data > Profile Merge Rules]**). These graphs include device graph data if you&#39;re a member of the [!UICONTROL Device Co-op] or other, third-party device graphs you may have access to in [!DNL Audience Manager]. Haga clic en una línea de tendencias para ver los datos subyacentes.

![](assets/authenticated_trends.png)

>[!MORE_ LIKE_ THIS]
>
>* [Preguntas frecuentes sobre reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

