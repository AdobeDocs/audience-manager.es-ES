---
description: Las métricas de vínculos de perfil proporcionan datos sobre personas y dispositivos que se autentican en el sitio. Los datos y los gráficos del vínculo de perfil se actualizan de forma dinámica a medida que se crean reglas de combinación o cuando se hace clic en una regla existente del panel Reglas de combinación de perfiles . Estas métricas pueden incluir gráficos de dispositivos de Adobe Experience Cloud Device Co-op u otras fuentes de gráficos de dispositivos de terceros.
seo-description: Las métricas de vínculos de perfil proporcionan datos sobre personas y dispositivos que se autentican en el sitio. Los datos y los gráficos del vínculo de perfil se actualizan de forma dinámica a medida que se crean reglas de combinación o cuando se hace clic en una regla existente del panel Reglas de combinación de perfiles . Estas métricas pueden incluir gráficos de dispositivos de Adobe Experience Cloud Device Co-op u otras fuentes de gráficos de dispositivos de terceros.
seo-title: Métricas de informes para reglas de combinación de Perfiles
solution: Audience Manager
title: Métricas de informes para reglas de combinación de Perfiles
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: Combinación de perfiles
exl-id: 2af59c60-2448-44af-90d2-eccc52f7ff02
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 2%

---

# Métricas de informes para reglas de combinación de Perfiles {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] Las métricas proporcionan datos sobre personas y dispositivos que se autentican en el sitio. Los datos y gráficos de [!UICONTROL Profile Merge Rule Reports] se actualizan dinámicamente al crear una regla de combinación o al hacer clic en una regla existente del tablero [!UICONTROL Profile Merge Rules]. Estas métricas pueden incluir gráficos de dispositivos de [!DNL Adobe Experience Cloud Device Co-op] u otras fuentes de gráficos de dispositivos de terceros.

## Combinar métricas de reglas {#merge-rule-metrics}

Los informes devuelven datos en gráficos de barras contiguos cuando las reglas de combinación utilizan datos de [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html) u otros gráficos de dispositivos de terceros a los que puede tener acceso en [!DNL Audience Manager]. Esto le permite comparar sus datos de origen autenticados con los datos entre dispositivos proporcionados por el [!UICONTROL Experience Cloud Device Co-op] u otro gráfico de dispositivos de terceros. Para obtener información sobre los datos devueltos por [!UICONTROL Device Co-op], consulte [Device Graph: Procesos internos y salida](https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html). Estos datos se actualizan diariamente.

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
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Personas</span> activas: El número de personas que se han autenticado en el sitio durante los últimos 60 días. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Entre dispositivos</span>: El número total de  <a href="merge-rules-start.md#create-data-source"> ID de varios dispositivos </a> almacenados en la fuente  <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html"> de </a> datos del  <a href="merge-rule-definitions.md">  </a> perfil autenticado seleccionado durante toda la duración de la existencia de la fuente de datos. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % de personas</span> activas: Muestra  <span class="wintitle"> Personas </span> activas como %. </li> 
    </ul> <p> <span class="wintitle"> La </span> actividad autenticada permite comparar las fuentes de datos por actividad, volumen y porcentaje. Puede ayudarle a encontrar una fuente de datos que tenga mucha gente y un alto porcentaje de usuarios activos. O puede que le resulte útil comparar fuentes de datos con una alta proporción de usuarios activos en comparación con el tamaño total de audiencia. Por ejemplo, a veces una fuente de datos con números de duración totales bajos y actividad alta es más valiosa que las que tienen resultados de duración elevados y números de actividad bajos. </p> <p> <p>Nota: Las métricas <span class="wintitle"> Actividad autenticada</span> solo contienen datos de <span class="wintitle"> Vínculo de perfil</span>. Este informe no incluye datos de <span class="wintitle"> Device Graph</span>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Promedio de dispositivos por persona</span></b> </p> </td> 
   <td colname="col2"> <p> Muestra el número promedio de dispositivos que utilizan los visitantes que se han autenticado en el sitio para la fuente de datos seleccionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Dispositivos totales</span></b> </p> </td> 
   <td colname="col2"> <p>Muestra la cantidad total de dispositivos que se han utilizado para autenticarse en el sitio para la fuente de datos seleccionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Personas totales</span></b> </p> </td> 
   <td colname="col2"> <p>Muestra el número total de personas que se han identificado determinísticamente para la fuente de datos seleccionada. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Métricas de gráfico de dispositivos {#device-graph-metrics}

Los informes [!UICONTROL Merge Rules] también muestran datos sobre la cantidad total de personas y dispositivos que visitaron el sitio para la fuente de datos y el gráfico de dispositivos seleccionados. Estas métricas devuelven datos en función de intervalos de tiempo preconfigurados (el período retroactivo) que varían según la opción de dispositivo que seleccione al crear una regla. En la tabla siguiente se enumeran estos intervalos de informes para cada una de las opciones de gráfico de dispositivos.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción Device Graph </th> 
   <th colname="col2" class="entry"> Intervalo de retrospectiva de informes </th> 
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

### Informe de vínculo de perfil estándar

Un informe estándar [!UICONTROL Profile Link] se parece al siguiente ejemplo. Las reglas de combinación que utilizan varias fuentes de datos (hasta 3, como máximo) muestran gráficos en fichas independientes para cada fuente de datos. Esta regla de combinación no incluye datos [!UICONTROL Device Co-op].

![](assets/profile-link-metrics.png)

### Informe Vínculo de perfil con datos de Device Graph

Un informe [!UICONTROL Profile Link Device Graph] que incluye datos de gráficos de dispositivos del [!UICONTROL Adobe Experience Cloud Device Co-op] o de un gráfico de dispositivos de terceros muestra [!UICONTROL Profile Link] y datos de gráficos de dispositivos con gráficos de barras contiguos. Colocar estos gráficos adyacentes entre sí le permite evaluar los beneficios de utilizar el [!UICONTROL Experience Cloud Device Co-op] en comparación con [!UICONTROL Profile Link] por sí solo. Las reglas de combinación que utilizan varias fuentes de datos (hasta 3, como máximo) muestran gráficos en fichas independientes para cada fuente de datos. Como recordatorio, el gráfico y las métricas [!UICONTROL Authenticated Activity] no devuelven datos del gráfico de dispositivos [!DNL Adobe] u otros gráficos de dispositivos de terceros a los que puede tener acceso en [!DNL Audience Manager].

![](assets/profile-link-graph.png)

## Gráficos de tendencia de vínculos de perfil {#profile-link-trend}

Además de las otras visualizaciones de datos, los informes [!UICONTROL Profile Link] incluyen un gráfico de líneas. El gráfico de líneas está diseñado para mostrar las tendencias a lo largo del tiempo para las reglas de perfil. Los gráficos de tendencias (y los demás informes) están disponibles al hacer clic en una regla desde la página de aterrizaje [!UICONTROL Profile Merge Rules] ( **[!UICONTROL Audience Data > Profile Merge Rules]**). Estos gráficos incluyen datos de gráficos de dispositivos si es miembro de los [!UICONTROL Device Co-op] u otros gráficos de dispositivos de terceros a los que puede tener acceso en [!DNL Audience Manager]. Haga clic en una línea de tendencia para ver los datos subyacentes.

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre las reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

