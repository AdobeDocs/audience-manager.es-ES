---
description: Ver información del historial de trabajos por lotes de salida para un destino y período de tiempo especificados.
seo-description: Ver información del historial de trabajos por lotes de salida para un destino y período de tiempo especificados.
seo-title: Historial de archivos de salida
solution: Audience Manager
title: Historial de archivos de salida
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
translation-type: tm+mt
source-git-commit: ccff7a0337d59a2e2c65c91076a1ff38814a0dd1

---


# Historial de archivos de salida {#outbound-file-history}

Ver información del historial de trabajos por lotes de salida para un destino y período de tiempo especificados.

<!-- 

t_reports_outbound_history.xml

 -->

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Outbound File History]**.

   ![Resultado del paso](assets/outbound_history.png)

1. En el **[!UICONTROL Search for a Destination]** cuadro, comience a escribir y seleccione el destino que desee.
1. En el **[!UICONTROL Select a Date Range]** cuadro, especifique las fechas de inicio y finalización del informe y haga clic en **[!UICONTROL Apply Date Filter]**.

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
   <td colname="col2"> <p>Lista de todos los archivos salientes que <span class="keyword"> Adobe</span> ha generado para este destino y que se han procesado juntos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Correcto </td> 
   <td colname="col2"> <p>Número de registros que se han enviado correctamente desde <span class="keyword"> Audience Manager</span> al destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error </td> 
   <td colname="col2"> <p>Número de registros que no se pudieron enviar al destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros recibidos </td> 
   <td colname="col2"> <p>Número total de registros que <span class="keyword"> Adobe</span> ha generado en los archivos y ha intentado enviar al destino. En la mayoría de los casos, debe ser el número total de archivos con éxito y de archivos con errores. </p> </td> 
  </tr> 
 </tbody> 
</table>
