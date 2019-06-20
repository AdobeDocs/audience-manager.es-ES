---
description: Audience Manager recibe una enorme cantidad de datos todos los días. Esto afecta la cantidad de tiempo que se tarda en procesar los datos y generar resultados del informe. El contenido de esta sección describe cómo estos intervalos de tiempo afectan su cuenta de Audience Manager. Además, los intervalos de tiempo y las programaciones descritas aquí son sólo guías generales. Estas programaciones no constituyen Acuerdos de nivel de servicio (SLA) ni compromisos relacionados con la entrega de datos. Adobe se reserva el derecho de cambiar los intervalos de tiempo y programar en cualquier momento sin previo aviso.
seo-description: Audience Manager recibe una enorme cantidad de datos todos los días. Esto afecta la cantidad de tiempo que se tarda en procesar los datos y generar resultados del informe. El contenido de esta sección describe cómo estos intervalos de tiempo afectan su cuenta de Audience Manager. Además, los intervalos de tiempo y las programaciones descritas aquí son sólo guías generales. Estas programaciones no constituyen Acuerdos de nivel de servicio (SLA) ni compromisos relacionados con la entrega de datos. Adobe se reserva el derecho de cambiar los intervalos de tiempo y programar en cualquier momento sin previo aviso.
seo-title: Cómo afectan los datos y el procesamiento de archivos los informes
solution: Audience Manager
title: Cómo afectan los datos y el procesamiento de archivos los informes
uuid: 4 b 975512-f 67 e -4749-a 7 ef -168415597682
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# How Data Delivery and File Processing Times Affect Reports{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager recibe una enorme cantidad de datos todos los días. Esto afecta la cantidad de tiempo que se tarda en procesar los datos y generar resultados del informe. El contenido de esta sección describe cómo estos intervalos de tiempo afectan su cuenta de Audience Manager. Además, los intervalos de tiempo y las programaciones descritas aquí son sólo guías generales. Estas programaciones no constituyen Acuerdos de nivel de servicio (SLA) ni compromisos relacionados con la entrega de datos. Adobe se reserva el derecho de cambiar los intervalos de tiempo y programar en cualquier momento sin previo aviso.

## Reporting Numbers {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

La siguiente tabla enumera y describe los intervalos de tiempo en nuestros informes generales y en tiempo real.

<table id="table_73AF95DF5D3A423894486444505D816A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de datos </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Datos en tiempo real</b> </p> </td> 
   <td colname="col2"> <p> Los números en tiempo real para hoy son para las horas 00:00 a 23:59:59 UTC desde ayer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Datos generales del informe</b> </p> </td> 
   <td colname="col2"> <p>The data in the <a href="../reporting/general-reports.md#general-reports-overview"> General Reports</a> depends on the successful completion of other job processes and the amount of data received for a particular day. Most of the time, <span class="wintitle"> General Report</span> data should be updated by 18:00 UTC each day. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Inbound and Outbound File Transfers {#inbound-outbound-file-transfers}

[!DNL Audience Manager] procesa y envía transferencias de archivos salientes [!UICONTROL Server-to-Server (S2S)] y salientes según las programaciones descritas en esta sección. Dadas estas programaciones y los tiempos de corte, es posible que vea discrepancias con los nuevos segmentos entre los números de segmento en tiempo real y total.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Ingesta de archivos de entrada (datos sin conexión)</b> </p> </td> 
   <td colname="col2"> <p>El procesamiento de archivos se ejecuta dos veces al día. Estos procedimientos ingestan datos y los preparan para su entrega. </p> <p>Los tiempos de entrega de archivos varían debido a que se ven afectados por la cantidad total de datos de clientes que deben procesarse. You should expect a maximum latency of 48 hours between the moment the file is uploaded in <span class="keyword"> Audience Manager</span> and until the data is available for reporting and activation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Archivos salientes (exportar)</b> </p> </td> 
   <td colname="col2"> <p>El procesamiento y la entrega de archivos se produce una vez al día, aproximadamente a las 14:00 UTC. Tenga en cuenta que el procesamiento y la entrega se ven afectados por el número y el tamaño total de estos archivos. En algunos casos, puede haber un retraso en el procesamiento de archivos durante 24 horas. When this happens, <span class="keyword"> Audience Manager</span> will send 2 files for a particular day instead of 1. We will notify our customers in the rare case where <span class="keyword"> Audience Manager</span> has to stop processing a file altogether. Dadas estas condiciones, es difícil estimar los tiempos de entrega de los datos salientes. </p> <p>Para determinar si ha recibido un conjunto completo de archivos, marque la marca de fecha y hora y busque los días que faltan. Es una marca de hora UNIX UTC de 13 dígitos que registra la hora en la que se creó el archivo. See <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> Real-Time Outbound Data Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Preguntas frecuentes sobre la ingesta de datos de clientes de entrada](../faq/faq-inbound-data-ingestion.md)

