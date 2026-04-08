---
description: Ver información del historial de trabajos por lotes salientes para un destino y período de tiempo especificados.
seo-description: View outbound batch job history information for a specified destination and time period.
seo-title: Outbound File History
solution: Audience Manager
title: Historial de archivos de salida
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: Inbound and Outbound Reports
exl-id: 8072c44f-bc9a-4b40-99d9-8cb87bb58d98
TQID: https://experienceleague.adobe.com/bAoUgntw3hZBsEuyPQV6yX2ftNRFV9HIv9QbierOgmA
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 152
ht-degree: 1%

---

# Historial de archivos de salida {#outbound-file-history}

Ver información del historial de trabajos por lotes salientes para un destino y período de tiempo especificados.

<!-- 

t_reports_outbound_history.xml

 -->

1. Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**.

   ![Resultado Del Paso](assets/outbound_history.png)

1. En el cuadro **[!UICONTROL Search for a Destination]**, empiece a escribir y seleccione el destino deseado.
1. En el cuadro **[!UICONTROL Select a Date Range]**, especifique las fechas de inicio y finalización del informe y haga clic en **[!UICONTROL Apply Date Filter]**.

   ![Resultado Del Paso](assets/outbound_history_stats.png)

   La siguiente tabla contiene información correspondiente a las columnas del informe:

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Líneas </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre del archivo de sincronización de datos </td> 
   <td colname="col2"> <p>Lista de todos los archivos salientes que <span class="keyword"> Adobe</span> generó para este destino y que se procesaron juntos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Correcto </td> 
   <td colname="col2"> <p>Número de registros enviados correctamente desde <span class="keyword"> Audience Manager</span> al destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error </td> 
   <td colname="col2"> <p>Número de registros que no se pudieron enviar al destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros recibidos </td> 
   <td colname="col2"> <p>Número total de registros <span class="keyword"> Adobe</span> generados en los archivos y que intentaron enviarse al destino. En la mayoría de los casos, debe ser el número total de archivos correctos y fallidos. </p> </td> 
  </tr> 
 </tbody> 
</table>
