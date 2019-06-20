---
description: La sección de informes de grupos de prueba devuelve información sobre conversiones de grupos de pruebas, lo que permite comparar fácilmente la eficacia del segmento de prueba. Hay numerosos filtros y dimensiones disponibles para la visualización de datos.
seo-description: La sección de informes de grupos de prueba devuelve información sobre conversiones de grupos de pruebas, lo que permite comparar fácilmente la eficacia del segmento de prueba. Hay numerosos filtros y dimensiones disponibles para la visualización de datos.
seo-title: Informes de grupos de prueba
solution: Audience Manager
title: Informes de grupos de prueba
topic: API DIL
uuid: 21303 c 3 e -4 c 05-4728-a 759-96 c 2 a 1 d 99 b 69
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Test Group Reporting {#test-group-reporting}

La sección de informes de grupos de prueba devuelve información sobre conversiones de grupos de pruebas, lo que permite comparar fácilmente la eficacia del segmento de prueba. Hay numerosos filtros y dimensiones disponibles para la visualización de datos.

[!UICONTROL Audience Lab] devuelve información detallada acerca de los segmentos de prueba que ha creado y permite guardar los datos de informes como [!DNL CSV] archivos. You can select between **[!UICONTROL Aggregate Reporting]** and **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** devuelve los números absolutos de los segmentos de prueba. **[!UICONTROL Trend Reporting]** devuelve un gráfico de la tendencia *durante un período específico*. Cuatro fichas permiten personalizar los informes:

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
   <td colname="col2"> <p>Devuelve el número de dispositivos que han mostrado los rasgos de conversión seleccionados en los grupos de prueba. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Vea este vídeo</a> para aprender a crear características de conversión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conversiones totales</span></b> </p> </td> 
   <td colname="col2"> <p>Devuelve el número de conversiones generadas por los segmentos de prueba. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Poblaciones de segmentos de prueba</span></b> </p> </td> 
   <td colname="col2"> <p>Devuelve el número de dispositivos pertenecientes a los segmentos de prueba. Toggle between <b><span class="uicontrol"> Total Population</span></b> or <b><span class="uicontrol"> Real-time Population</span></b>. The difference is explained in the <a href="../../faq/faq-reporting.md"> Reporting FAQ</a> . </p> </td>
  </tr>
 </tbody>
</table>

Puede seleccionar una característica de conversión específica para la cual generar el informe o seleccionar todas las características combinadas. You can define a date range for which the information should be returned and export the report as a [!DNL CSV] file.

>[!NOTE]
>
>* Los informes de un grupo de prueba rellenarán el día después de su fecha de inicio.
>* Una conversión se contabiliza solamente para un dispositivo después de la fecha de inicio de una prueba y después de agregar el dispositivo a un segmento de prueba. Si se produce una conversión para ese dispositivo antes de que se le asigne un grupo de prueba, la conversión no se contará.


A returned **[!UICONTROL Aggregate Reporting]** chart could look like this:

![](assets/aggregate-reporting.PNG)

A returned **[!UICONTROL Trend Reporting]** chart could look like the one below. Select **[!UICONTROL Normalized]** in the check box if you want to ignore the absolute numbers and simply focus on the test segments trends.

![](assets/trend-reporting.PNG)