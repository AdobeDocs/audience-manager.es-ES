---
description: La sección de sistema de informes del grupo de prueba devuelve información sobre las conversiones del grupo de prueba, lo que permite comparar fácilmente la eficacia del segmento de prueba. Existen numerosos filtros y dimensiones disponibles para la visualización de datos.
seo-description: La sección de sistema de informes del grupo de prueba devuelve información sobre las conversiones del grupo de prueba, lo que permite comparar fácilmente la eficacia del segmento de prueba. Existen numerosos filtros y dimensiones disponibles para la visualización de datos.
seo-title: Sistema de informes de grupo de prueba
solution: Audience Manager
title: Sistema de informes de grupo de prueba
topic: DIL API
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 2%

---


# Sistema de informes de grupo de prueba {#test-group-reporting}

La sección de sistema de informes del grupo de prueba devuelve información sobre las conversiones del grupo de prueba, lo que permite comparar fácilmente la eficacia del segmento de prueba. Existen numerosos filtros y dimensiones disponibles para la visualización de datos.

[!UICONTROL Audience Lab] devuelve información detallada del sistema de informes de los segmentos de prueba que ha creado y le permite guardar los datos del sistema de informes como  [!DNL CSV] archivos. Puede seleccionar entre **[!UICONTROL Aggregate Reporting]** y **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** devuelve los números absolutos de los segmentos de prueba. **[!UICONTROL Trend Reporting]** devuelve un gráfico de la tendencia  *durante un período* específico. Cuatro fichas le permiten personalizar los informes:

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tasa de conversión demográfica</span></b> </p> </td> 
   <td colname="col2"> <p>Devuelve el porcentaje de dispositivos pertenecientes a un segmento de prueba concreto que se han convertido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Convertidores</span></b> </p> </td> 
   <td colname="col2"> <p>Devuelve el número de dispositivos que han mostrado las características de conversión seleccionadas en los grupos de prueba. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Vea este </a> vídeo para aprender a crear características de conversión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conversiones totales</span></b> </p> </td> 
   <td colname="col2"> <p>Devuelve el número de conversiones generadas por los segmentos de prueba. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Probar poblaciones de segmentos</span></b> </p> </td> 
   <td colname="col2"> <p>Devuelve el número de dispositivos que pertenecen a los segmentos de prueba. Alternar entre <b><span class="uicontrol"> Población total</span></b> o <b><span class="uicontrol"> Población en tiempo real</span></b>. La diferencia se explica en las <a href="../../faq/faq-reporting.md"> preguntas frecuentes sobre el Sistema de informes</a> . </p> </td>
  </tr>
 </tbody>
</table>

Puede seleccionar una característica de conversión específica para la cual generar el informe o seleccionar todas las características combinadas. Puede definir un intervalo de fechas para el cual se debe devolver la información y exportar el informe como un archivo [!DNL CSV].

>[!NOTE]
>
>* El sistema de informes de un grupo de prueba se rellenará el día siguiente a la fecha de inicio.
>* Una conversión solo se contabiliza para un dispositivo después de la fecha de inicio de una prueba y después de que el dispositivo se haya agregado a un segmento de prueba. Si se produce una conversión para ese dispositivo antes de que se le asigne un grupo de prueba, la conversión no se contará.


Un gráfico **[!UICONTROL Aggregate Reporting]** devuelto podría tener este aspecto:

![](assets/aggregate-reporting.PNG)

Un gráfico devuelto **[!UICONTROL Trend Reporting]** podría ser similar al siguiente. Seleccione **[!UICONTROL Normalized]** en la casilla de verificación si desea ignorar los números absolutos y simplemente centrarse en las tendencias de los segmentos de prueba.

![](assets/trend-reporting.PNG)