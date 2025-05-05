---
description: Las métricas de vínculos de perfil proporcionan datos sobre las personas y los dispositivos que se autentican en el sitio. Los datos y gráficos del vínculo de perfil se actualizan dinámicamente al crear reglas de combinación o al hacer clic en una regla existente del panel Reglas de combinación de perfiles. Estas métricas pueden incluir gráficos de dispositivos de otras fuentes de gráficos de dispositivos de terceros.
seo-description: Profile Link metrics provide data about people and devices that authenticate to your site. The data and graphs in Profile Link update dynamically as you create a merge rules or when you click an existing rule from the Profile Merge Rules dashboard. These metrics can include device graph from other third-party device graph sources.
seo-title: Report Metrics for Profile Merge Rules
solution: Audience Manager
title: Métricas de informes para reglas de combinación de perfiles
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: Profile Merge
exl-id: 2af59c60-2448-44af-90d2-eccc52f7ff02
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 0%

---

# Métricas de informes para reglas de combinación de perfiles {#report-metrics-for-profile-merge-rules}

Las métricas de [!UICONTROL Profile Merge Rule] proporcionan datos sobre personas y dispositivos que se autentican en el sitio. Los datos y gráficos de [!UICONTROL Profile Merge Rule Reports] se actualizan dinámicamente al crear una regla de combinación o al hacer clic en una regla existente del panel [!UICONTROL Profile Merge Rules]. Estas métricas pueden incluir gráficos de dispositivos de otras fuentes de gráficos de dispositivos de terceros.

## Combinar métricas de reglas {#merge-rule-metrics}

Los informes devuelven datos en gráficos de barras paralelos cuando las reglas de combinación utilizan datos de gráficos de dispositivos de terceros a los que puede tener acceso en [!DNL Audience Manager]. Esto le permite comparar los datos de origen autenticados con los datos entre dispositivos proporcionados por gráficos de dispositivos de terceros. Estos datos se actualizan a diario.

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> actividad autenticada</span></b> </p> </td> 
   <td colname="col2"> <p>Muestra: </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> personas activas</span>: El número de personas que se autenticaron en el sitio durante los últimos 60 días. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> entre dispositivos</span>: El número total de <a href="merge-rules-start.md#create-data-source"> identificadores entre dispositivos</a> almacenados en el <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html?lang=es"> Data Source</a> del <a href="merge-rule-definitions.md"> perfil autenticado </a> seleccionado durante toda la vida que ha existido el origen de datos. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % de personas activas</span>: muestra <span class="wintitle"> personas activas</span> como un %. </li> 
    </ul> <p> <span class="wintitle"> Actividad autenticada</span> le permite comparar orígenes de datos por actividad, volumen y porcentaje. Puede ayudarle a encontrar una fuente de datos que tenga muchas personas y un alto porcentaje de usuarios activos. O puede encontrar valor en la comparación de fuentes de datos con una alta proporción de usuarios activos en comparación con el tamaño total de la audiencia. Por ejemplo, a veces una fuente de datos con números totales de duración bajos y actividad alta es más valiosa que las que tienen resultados de duración altos y números de actividad bajos. </p> <p> <p>Nota: Las métricas de <span class="wintitle"> actividad autenticada</span> contienen solo datos de <span class="wintitle"> vínculo de perfil</span>. Este informe no incluye datos de <span class="wintitle"> Device Graph</span>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> dispositivos promedio por persona</span></b> </p> </td> 
   <td colname="col2"> <p> Muestra el número promedio de dispositivos que utilizan los visitantes que se han autenticado en el sitio para la fuente de datos seleccionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> dispositivos totales</span></b> </p> </td> 
   <td colname="col2"> <p>Muestra el número total de dispositivos que se han utilizado para autenticarse en el sitio para la fuente de datos seleccionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> personas en total</span></b> </p> </td> 
   <td colname="col2"> <p>Muestra el número total de personas que se han identificado de forma determinista para la fuente de datos seleccionada. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Métricas del gráfico del dispositivo {#device-graph-metrics}

Los informes de [!UICONTROL Merge Rules] también muestran datos sobre la cantidad total de personas y dispositivos que visitaron el sitio en relación con el origen de datos y el gráfico de dispositivos seleccionados. Estas métricas devuelven datos basados en intervalos de tiempo preestablecidos (el período retroactivo) que varían según la opción de dispositivo que seleccione al crear una regla. En la tabla siguiente se enumeran estos intervalos de informes para cada una de las opciones del gráfico de dispositivos.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción de gráfico de dispositivo </th> 
   <th colname="col2" class="entry"> Intervalo de retrospectiva de informe </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> vínculo de perfil</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">Total de personas: 60 días </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">Total de dispositivos: 120 días </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">Total de personas: 180 días </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">Total de dispositivos: 180 días </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">Total de personas: 60 días </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">Total de dispositivos en 60 días </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Informes de muestra {#sample-reports}

### Informe de vínculo de perfil estándar

Un informe [!UICONTROL Profile Link] estándar es similar al siguiente ejemplo. Las reglas de combinación que utilizan varias fuentes de datos (hasta un máximo de 3) muestran gráficos en pestañas independientes para cada fuente de datos. Esta regla de combinación no incluye datos de [!UICONTROL external device graph].

![](assets/profile-link-metrics.png)

### Informe De Vínculo De Perfil Con Datos De Gráfico De Dispositivo

Un informe [!UICONTROL Profile Link Device Graph] que incluye datos de gráficos de dispositivos de terceros muestra [!UICONTROL Profile Link] y datos de gráficos de dispositivos con gráficos de barras en paralelo. Colocar estos gráficos adyacentes entre sí le permite evaluar los beneficios de utilizar gráficos de dispositivos externos en comparación con [!UICONTROL Profile Link] por sí mismo. Las reglas de combinación que utilizan varias fuentes de datos (hasta un máximo de 3) muestran gráficos en pestañas independientes para cada fuente de datos. Como recordatorio, el gráfico y las métricas de [!UICONTROL Authenticated Activity] no devuelven datos del gráfico del dispositivo [!DNL Adobe] u otros gráficos de dispositivos de terceros a los que pueda tener acceso en [!DNL Audience Manager].

![](assets/profile-link-graph.png)

## Gráficos de tendencia de vínculos de perfil {#profile-link-trend}

Además de las demás visualizaciones de datos, los informes de [!UICONTROL Profile Link] incluyen un gráfico de líneas. El gráfico de líneas está diseñado para mostrar las tendencias a lo largo del tiempo de las reglas de perfil. Los gráficos de tendencias (y los demás informes) están disponibles al hacer clic en una regla desde la página de aterrizaje [!UICONTROL Profile Merge Rules] ( **[!UICONTROL Audience Data > Profile Merge Rules]**). Estos gráficos incluyen datos de gráficos de dispositivos si es miembro de gráficos de dispositivos de terceros a los que puede tener acceso en [!DNL Audience Manager]. Haga clic en una línea de tendencia para ver los datos subyacentes.

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre reglas de combinación de perfiles](../../faq/faq-profile-merge.md)
