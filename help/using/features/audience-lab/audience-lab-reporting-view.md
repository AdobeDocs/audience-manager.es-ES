---
description: La sección grupo sistema de informes prueba devuelve información sobre prueba grupo conversiones, lo que permite comparar fácilmente prueba segmento eficacia. Numerosas filtros y dimensiones están disponibles para la visualización de datos.
seo-description: The test group reporting section returns information on test group conversions, allowing an easy comparison of test segment efficacy. Numerous filters and dimensions are available for data visualization.
seo-title: Test Group Reporting
solution: Audience Manager
title: Informes de grupo de prueba
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Informes de grupo de prueba {#test-group-reporting}

La sección grupo sistema de informes prueba devuelve información sobre prueba grupo conversiones, lo que permite comparar fácilmente prueba segmento eficacia. Numerosas filtros y dimensiones están disponibles para la visualización de datos.

[!UICONTROL Audience Lab] Devuelve información de sistema de informes detallada de los segmentos de prueba creado y permite guardar los datos sistema de informes como [!DNL CSV] archivos. Puede seleccionar entre **[!UICONTROL Aggregate Reporting]** y **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** Devuelve los números absolutos de los segmentos prueba. **[!UICONTROL Trend Reporting]** Devuelve un gráfico de la tendencia *durante un período* específico. Cuatro fichas permiten personalizar los informes:

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tasa de conversión de población</span></b> </p> </td> 
   <td colname="col2"> <p>Devuelve el porcentaje de dispositivos pertenecientes a un segmento de prueba concreto, que se han convertido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Convertidores</span></b> </p> </td> 
   <td colname="col2"> <p>Devuelve el número de dispositivos que han exhibido los rasgos Conversión seleccionados en los grupos prueba. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Vea este vídeo</a> para aprender a crear Conversión rasgos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conversiones totales</span></b> </p> </td> 
   <td colname="col2"> <p>Devuelve el número de conversiones generadas por los segmentos prueba. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Poblaciones de segmentos de prueba</span></b> </p> </td> 
   <td colname="col2"> <p>Devuelve el número de dispositivos pertenecientes a los segmentos prueba. Alternar entre <b><span class="uicontrol"> Población</span></b> total o <b><span class="uicontrol"> Población</span></b> en tiempo real. La diferencia se explica en Preguntas frecuentes<a href="../../faq/faq-reporting.md"> sobre informes</a>. </p> </td>
  </tr>
 </tbody>
</table>

Puede seleccionar una característica Conversión específica para la que generar el informe o puede seleccionar todas las características combinadas. Puede definir una intervalo de fecha para la cual se debe devolver la información y exportar el informe como un [!DNL CSV] archivo.

>[!NOTE]
>
>* Los informes de una prueba grupo se completarán el día siguiente a su fecha inicio.
>* Un Conversión solo se cuenta durante un dispositivos después de la fecha de inicio de un prueba y después de que el dispositivos se haya agregado a un segmento prueba. Si se produce un Conversión para ese dispositivos antes de que se le asigne un grupo prueba, el Conversión no se contabilizará.

Un gráfico devuelto **[!UICONTROL Aggregate Reporting]** podría verse gustar esto:

![](assets/aggregate-reporting.PNG)

Un gráfico devuelto **[!UICONTROL Trend Reporting]** podría verse gustar el de abajo. Seleccione **[!UICONTROL Normalized]** en la casilla de verificación si desea ignorar los números absolutos y limitarse a enfocar las tendencias de los segmentos prueba.

![](assets/trend-reporting.PNG)
