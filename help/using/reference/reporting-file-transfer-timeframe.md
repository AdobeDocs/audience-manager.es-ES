---
description: Audience Manager recibe una enorme cantidad de datos todos los días. Esto afecta la cantidad de tiempo que se tarda en procesar los datos y generar los resultados del informe. El contenido de esta sección describe cómo estos intervalos de tiempo afectan a su cuenta de Audience Manager. Además, los intervalos de tiempo y las programaciones que se describen aquí son sólo directrices generales. Estas programaciones no constituyen acuerdos de nivel de servicio (SLA) ni compromisos relacionados con la entrega de datos. Adobe se reserva el derecho de cambiar los intervalos de tiempo y las programaciones en cualquier momento sin previo aviso.
seo-description: Audience Manager recibe una enorme cantidad de datos todos los días. Esto afecta la cantidad de tiempo que se tarda en procesar los datos y generar los resultados del informe. El contenido de esta sección describe cómo estos intervalos de tiempo afectan a su cuenta de Audience Manager. Además, los intervalos de tiempo y las programaciones que se describen aquí son sólo directrices generales. Estas programaciones no constituyen acuerdos de nivel de servicio (SLA) ni compromisos relacionados con la entrega de datos. Adobe se reserva el derecho de cambiar los intervalos de tiempo y las programaciones en cualquier momento sin previo aviso.
seo-title: Cómo afectan la entrega de datos y los tiempos de procesamiento de archivos a los informes
solution: Audience Manager
title: Cómo afectan la entrega de datos y los tiempos de procesamiento de archivos a los informes
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Cómo afectan la entrega de datos y los tiempos de procesamiento de archivos a los informes{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager recibe una enorme cantidad de datos todos los días. Esto afecta la cantidad de tiempo que se tarda en procesar los datos y generar los resultados del informe. El contenido de esta sección describe cómo estos intervalos de tiempo afectan a su cuenta de Audience Manager. Además, los intervalos de tiempo y las programaciones que se describen aquí son sólo directrices generales. Estas programaciones no constituyen acuerdos de nivel de servicio (SLA) ni compromisos relacionados con la entrega de datos. Adobe se reserva el derecho de cambiar los intervalos de tiempo y las programaciones en cualquier momento sin previo aviso.

## Números de informes {#reporting-numbers}

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
   <td colname="col2"> <p> Los números en tiempo real de hoy son para las horas 00:00 a 23:59:59 UTC de ayer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Datos del informe general</b> </p> </td> 
   <td colname="col2"> <p>Los datos de los <a href="../reporting/general-reports.md#general-reports-overview"> informes</a> generales dependen de la finalización con éxito de otros procesos de trabajo y de la cantidad de datos recibidos para un día determinado. La mayoría de las veces, los datos del informe <span class="wintitle"></span> general deben actualizarse a las 18:00 UTC cada día. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Transferencias de archivos de entrada y salida {#inbound-outbound-file-transfers}

[!DNL Audience Manager] procesa y envía transferencias de [!UICONTROL Server-to-Server (S2S)] archivos entrantes y salientes según las programaciones descritas en esta sección. Dadas estas programaciones y las horas de corte, es posible que observe discrepancias con los nuevos segmentos entre los números de segmento totales y en tiempo real.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Entrada de archivos (datos sin conexión)</b> </p> </td> 
   <td colname="col2"> <p>El procesamiento de archivos se ejecuta dos veces al día. Estos procedimientos incorporan datos y los preparan para su entrega. </p> <p>Los tiempos de entrega de archivos varían porque se ven afectados por la cantidad total de datos de clientes que deben procesarse. Debe esperar una latencia máxima de 48 horas entre el momento en que se carga el archivo en <span class="keyword"> Audience Manager</span> y hasta que los datos estén disponibles para informes y activación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Archivos de salida (Exportar)</b> </p> </td> 
   <td colname="col2"> <p>El procesamiento y la entrega de archivos tienen lugar una vez al día, aproximadamente a las 14:00 UTC. Tenga en cuenta que el procesamiento y la entrega se ven afectados por el número total y el tamaño de estos archivos. En algunos casos, puede haber un retraso en el procesamiento de archivos de hasta 24 horas. Cuando esto ocurra, Audience Manager <span class="keyword"></span> enviará 2 archivos para un día en particular en lugar de 1. Notificaremos a nuestros clientes en el caso poco frecuente de que <span class="keyword"> Audience Manager</span> tenga que dejar de procesar un archivo por completo. Dadas estas condiciones, es difícil estimar los tiempos de entrega de los datos salientes. </p> <p>Para determinar si ha recibido un conjunto completo de archivos, compruebe la marca de tiempo y busque los días que faltan. Es una marca de tiempo UNIX UTC de 13 dígitos que registra la hora en que se creó el archivo. Consulte <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> Transferencias</a>de datos salientes en tiempo real. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Preguntas más frecuentes sobre la ingestión de datos de clientes entrantes](../faq/faq-inbound-data-ingestion.md)

