---
description: Las métricas de vínculos de Perfil proporcionan datos sobre las personas y los dispositivos que se autentican en el sitio. Los datos y los gráficos de Vínculo de Perfil se actualizan dinámicamente al crear reglas de combinación o al hacer clic en una regla existente desde el panel Reglas de combinación de Perfiles. Estas métricas pueden incluir gráficos de dispositivos de Adobe Experience Cloud Device Co-op u otras fuentes de gráficos de dispositivos de terceros.
seo-description: Las métricas de vínculos de Perfil proporcionan datos sobre las personas y los dispositivos que se autentican en el sitio. Los datos y los gráficos de Vínculo de Perfil se actualizan dinámicamente al crear reglas de combinación o al hacer clic en una regla existente desde el panel Reglas de combinación de Perfiles. Estas métricas pueden incluir gráficos de dispositivos de Adobe Experience Cloud Device Co-op u otras fuentes de gráficos de dispositivos de terceros.
seo-title: Métricas de informes para reglas de combinación de Perfiles
solution: Audience Manager
title: Métricas de informes para reglas de combinación de Perfiles
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 2%

---


# Métricas de informes para reglas de combinación de Perfiles {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] las métricas proporcionan datos sobre las personas y los dispositivos que se autentican en el sitio. Los datos y los gráficos de [!UICONTROL Profile Merge Rule Reports] se actualizan dinámicamente al crear una regla de combinación o al hacer clic en una regla existente desde el [!UICONTROL Profile Merge Rules] panel. Estas métricas pueden incluir gráficos de dispositivos de las fuentes de gráficos de dispositivos [!DNL Adobe Experience Cloud Device Co-op] u otros fabricantes.

## Combinar métricas de regla {#merge-rule-metrics}

Los informes devuelven datos en gráficos de barras contiguos cuando las reglas de combinación utilizan datos de Device Co-op [de](https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html) Adobe Experience Cloud u otros gráficos de dispositivos de terceros a los que puede tener acceso en [!DNL Audience Manager]. Esto le permite comparar los datos de origen autenticados con los datos entre dispositivos proporcionados por el gráfico [!UICONTROL Experience Cloud Device Co-op] u otro de dispositivos de terceros. Para obtener información sobre los datos devueltos por el [!UICONTROL Device Co-op], consulte [The Device Graph: Procesos internos y resultados](https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html). Estos datos se actualizan diariamente.

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
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Personas</span>activas: El número de personas que se han autenticado en el sitio durante los últimos 60 días. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Dispositivo</span>cruzado: Número total de ID <a href="merge-rules-start.md#create-data-source"> entre dispositivos</a> almacenados en la fuente <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html"> de datos del Perfil</a> autenticado <a href="merge-rule-definitions.md"></a> seleccionado durante la duración de la existencia de la fuente de datos. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % de personas</span>activas: Muestra <span class="wintitle"> Personas</span> activas como %. </li> 
    </ul> <p> <span class="wintitle"> La Actividad</span> autenticada permite comparar las fuentes de datos por actividad, volumen y porcentaje. Puede ayudarle a encontrar una fuente de datos que tenga muchas personas y un alto porcentaje de usuarios activos. O bien, puede resultar útil comparar fuentes de datos con una alta proporción de usuarios activos en comparación con el tamaño total de audiencia. Por ejemplo, a veces una fuente de datos con números de duración totales bajos y actividad alta es más valiosa que las que tienen resultados de duración altos y números de actividad bajos. </p> <p> <p>Nota: Las <span class="wintitle"> métricas de Actividad</span> autenticadas solo contienen datos del vínculo <span class="wintitle"> de</span> Perfil. Este informe no incluye <span class="wintitle"> datos de Device Graph</span> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Promedio de dispositivos por persona</span></b> </p> </td> 
   <td colname="col2"> <p> Muestra el número promedio de dispositivos que utilizan los visitantes que se han autenticado en el sitio para la fuente de datos seleccionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Dispositivos totales</span></b> </p> </td> 
   <td colname="col2"> <p>Muestra el número total de dispositivos que las personas han utilizado para autenticarse en el sitio para la fuente de datos seleccionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Total de personas</span></b> </p> </td> 
   <td colname="col2"> <p>Muestra el número total de personas que se han identificado determinísticamente para la fuente de datos seleccionada. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Métricas de Device Graph {#device-graph-metrics}

Los [!UICONTROL Merge Rules] informes también muestran datos sobre la cantidad total de personas y dispositivos que han visitado el sitio para la fuente de datos y el gráfico del dispositivo seleccionados. Estas métricas devuelven datos en función de intervalos de tiempo preestablecidos (el período retroactivo) que varían según la opción de dispositivo seleccionada al crear una regla. La siguiente tabla lista estos intervalos de informes para cada una de las opciones de gráficos de dispositivos.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción de Device Graph </th> 
   <th colname="col2" class="entry"> Intervalo de retroactividad de informes </th> 
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
   <td colname="col1"> <p><span class="wintitle"> Gráfico de dispositivos de cooperación</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">Total de personas: 180 días </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">Dispositivos totales: 180 días </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">Total de personas: 180 días </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">Dispositivos totales: 180 días </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">Total de personas: 60 días </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">Total de dispositivos 60 días </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Informes de muestra {#sample-reports}

### Informe Vínculo de Perfil estándar

Un informe estándar [!UICONTROL Profile Link] tiene el siguiente ejemplo. Las reglas de combinación que utilizan varias fuentes de datos (hasta 3, máximo) muestran gráficos en fichas independientes para cada fuente de datos. Esta regla de combinación no incluye [!UICONTROL Device Co-op] datos.

![](assets/profile-link-metrics.png)

### Informe Vínculo De Perfil Con Datos De Device Graph

Un [!UICONTROL Profile Link Device Graph] informe que incluye datos de gráficos de dispositivos del gráfico de dispositivos [!UICONTROL Adobe Experience Cloud Device Co-op] o de terceros muestra datos de gráficos de dispositivos [!UICONTROL Profile Link] y gráficos de dispositivos con gráficos de barras paralelos. Colocar estos gráficos adyacentes permite evaluar los beneficios de usar el [!UICONTROL Experience Cloud Device Co-op] comparado con [!UICONTROL Profile Link] sí mismo. Las reglas de combinación que utilizan varias fuentes de datos (hasta 3, máximo) muestran gráficos en fichas independientes para cada fuente de datos. Como recordatorio, el gráfico [!UICONTROL Authenticated Activity] y las métricas no devuelven datos del gráfico del [!DNL Adobe] dispositivo u otros gráficos de dispositivos de terceros a los que tenga acceso en [!DNL Audience Manager].

![](assets/profile-link-graph.png)

## Gráficos de tendencias de vínculos de Perfil {#profile-link-trend}

Además de las demás visualizaciones de datos, los informes incluyen un gráfico de líneas [!UICONTROL Profile Link] . El gráfico de líneas está diseñado para mostrar las tendencias a lo largo del tiempo de las reglas de perfil. Los gráficos de tendencias (y los demás informes) están disponibles al hacer clic en una regla desde la [!UICONTROL Profile Merge Rules] página de aterrizaje ( **[!UICONTROL Audience Data > Profile Merge Rules]**). Estos gráficos incluyen datos de gráficos de dispositivos si es miembro del [!UICONTROL Device Co-op] o de otros gráficos de dispositivos de terceros a los que puede tener acceso en [!DNL Audience Manager]. Haga clic en una línea de tendencias para ver los datos subyacentes.

>[!MORELIKETHIS]
>
>* [Preguntas más frecuentes sobre las reglas de combinación de Perfiles](../../faq/faq-profile-merge.md)

