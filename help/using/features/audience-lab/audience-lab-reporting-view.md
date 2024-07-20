---
description: La sección de creación de informes de grupos de prueba devuelve información sobre las conversiones de los grupos de prueba, lo que permite comparar fácilmente la eficacia de los segmentos de prueba. Hay numerosos filtros y dimensiones disponibles para la visualización de datos.
seo-description: The test group reporting section returns information on test group conversions, allowing an easy comparison of test segment efficacy. Numerous filters and dimensions are available for data visualization.
seo-title: Test Group Reporting
solution: Audience Manager
title: Informes de grupos de prueba
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Informes de grupos de prueba {#test-group-reporting}

La sección de creación de informes de grupos de prueba devuelve información sobre las conversiones de los grupos de prueba, lo que permite comparar fácilmente la eficacia de los segmentos de prueba. Hay numerosos filtros y dimensiones disponibles para la visualización de datos.

[!UICONTROL Audience Lab] devuelve información detallada sobre los informes para los segmentos de prueba que creó y le permite guardar los datos de informes como [!DNL CSV] archivos. Puede seleccionar entre **[!UICONTROL Aggregate Reporting]** y **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** devuelve los números absolutos de los segmentos de prueba. **[!UICONTROL Trend Reporting]** devuelve un gráfico de la tendencia *durante un período específico*. Hay cuatro pestañas que permiten personalizar los informes:

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
   <td colname="col2"> <p>Devuelve el porcentaje de dispositivos que pertenecen a un segmento de prueba concreto que se han convertido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> convertidores</span></b> </p> </td> 
   <td colname="col2"> <p>Devuelve el número de dispositivos que han mostrado los rasgos de conversión seleccionados en los grupos de prueba. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Vea este vídeo</a> para aprender a crear características de conversión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> conversiones totales</span></b> </p> </td> 
   <td colname="col2"> <p>Devuelve el número de conversiones generadas por los segmentos de prueba. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> poblaciones de segmentos de prueba</span></b> </p> </td> 
   <td colname="col2"> <p>Devuelve el número de dispositivos que pertenecen a los segmentos de prueba. Alternar entre <b><span class="uicontrol"> población total</span></b> o <b><span class="uicontrol"> población en tiempo real</span></b>. La diferencia se explica en las preguntas frecuentes sobre la creación de informes <a href="../../faq/faq-reporting.md"> </a> . </p> </td>
  </tr>
 </tbody>
</table>

Puede seleccionar un rasgo de conversión específico para el que generar el informe o puede seleccionar todos los rasgos combinados. Puede definir un intervalo de fechas para el cual se debe devolver la información y exportar el informe como un archivo de [!DNL CSV].

>[!NOTE]
>
>* Los informes de un grupo de prueba se rellenarán el día siguiente a su fecha de inicio.
>* Una conversión solo se cuenta para un dispositivo después de la fecha de inicio de una prueba y después de que el dispositivo se haya agregado a un segmento de prueba. Si se produce una conversión para ese dispositivo antes de que se le asigne un grupo de prueba, la conversión no se contará.

Un gráfico **[!UICONTROL Aggregate Reporting]** devuelto podría tener este aspecto:

![](assets/aggregate-reporting.PNG)

Un gráfico **[!UICONTROL Trend Reporting]** devuelto podría parecerse al de abajo. Seleccione **[!UICONTROL Normalized]** en la casilla de verificación si desea ignorar los números absolutos y centrarse simplemente en las tendencias de los segmentos de prueba.

![](assets/trend-reporting.PNG)
