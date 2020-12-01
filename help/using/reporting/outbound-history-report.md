---
description: Vista de la información del historial de trabajos por lotes salientes para un destino y período de tiempo especificados.
seo-description: Vista de la información del historial de trabajos por lotes salientes para un destino y período de tiempo especificados.
seo-title: Historial de archivos de salida
solution: Audience Manager
title: Historial de archivos de salida
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: inbound and outbound reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 7%

---


# Historial de archivos de salida {#outbound-file-history}

Vista de la información del historial de trabajos por lotes salientes para un destino y período de tiempo especificados.

<!-- 

t_reports_outbound_history.xml

 -->

1. Haga clic **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**.

   ![Resultado del paso](assets/outbound_history.png)

1. En el cuadro **[!UICONTROL Search for a Destination]**, escriba el inicio y seleccione el destino deseado.
1. En el cuadro **[!UICONTROL Select a Date Range]**, especifique el inicio y las fechas de finalización del informe y, a continuación, haga clic en **[!UICONTROL Apply Date Filter]**.

   ![Resultado del paso](assets/outbound_history_stats.png)

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
   <td colname="col2"> <p>Lista de todos los archivos salientes que <span class="keyword"> Adobe</span> generó para este destino que se procesaron juntos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Correcto </td> 
   <td colname="col2"> <p>Número de registros que se enviaron correctamente desde <span class="keyword"> Audience Manager</span> al destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error </td> 
   <td colname="col2"> <p>Número de registros que no se pudieron enviar al destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros recibidos </td> 
   <td colname="col2"> <p>Número total de registros <span class="keyword"> Adobe</span> generados en los archivos y que intentaron enviarse al destino. En la mayoría de los casos, debe ser el número total de archivos con éxito y de archivos con errores. </p> </td> 
  </tr> 
 </tbody> 
</table>
