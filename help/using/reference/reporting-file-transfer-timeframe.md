---
description: Audience Manager recibe una enorme cantidad de datos todos los días. Esto afecta a la cantidad de tiempo que se tarda en procesar los datos y generar los resultados del informe. El contenido de esta sección describe cómo estos intervalos de tiempo afectan su cuenta de Audience Manager. Además, los intervalos de tiempo y las programaciones que se describen aquí son sólo directrices generales. Estas programaciones no constituyen Acuerdos de Nivel de Servicio (SLA, Service Level Agreements) ni compromisos relacionados con el envío de datos. Adobe se reserva el derecho de cambiar los plazos y los calendarios en cualquier momento sin previo aviso.
seo-description: Audience Manager recibe una enorme cantidad de datos todos los días. Esto afecta a la cantidad de tiempo que se tarda en procesar los datos y generar los resultados del informe. El contenido de esta sección describe cómo estos intervalos de tiempo afectan su cuenta de Audience Manager. Además, los intervalos de tiempo y las programaciones que se describen aquí son sólo directrices generales. Estas programaciones no constituyen Acuerdos de Nivel de Servicio (SLA, Service Level Agreements) ni compromisos relacionados con el envío de datos. Adobe se reserva el derecho de cambiar los plazos y los calendarios en cualquier momento sin previo aviso.
seo-title: Cómo afecta el envío de datos y los tiempos de procesamiento de archivos a los informes
solution: Audience Manager
title: Cómo afecta el envío de datos y los tiempos de procesamiento de archivos a los informes
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 5%

---


# Cómo afecta el envío de datos y los tiempos de procesamiento de archivos a los informes{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager recibe una enorme cantidad de datos todos los días. Esto afecta a la cantidad de tiempo que se tarda en procesar los datos y generar los resultados del informe. El contenido de esta sección describe cómo estos intervalos de tiempo afectan su cuenta de Audience Manager. Además, los intervalos de tiempo y las programaciones que se describen aquí son sólo directrices generales. Estas programaciones no constituyen Acuerdos de Nivel de Servicio (SLA, Service Level Agreements) ni compromisos relacionados con el envío de datos. Adobe se reserva el derecho de cambiar los plazos y los calendarios en cualquier momento sin previo aviso.

## Números de sistema de informes {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

La siguiente tabla lista y describe los intervalos de tiempo en nuestros informes generales y en tiempo real.


| Tipo de datos | Descripción |
|---|---|
| Datos en tiempo real | Los números en tiempo real de hoy son para las horas 00:00 a 23:59:59 UTC de ayer. |
| Datos del informe general | Los datos de los [Informes generales](../reporting/general-reports.md#general-reports-overview) dependen de la finalización exitosa de otros procesos de trabajo y de la cantidad de datos recibidos para un día en particular. La mayoría de las veces, los datos [!UICONTROL General Report] deben actualizarse a las 18:00 UTC cada día. |

## Transferencias de archivos entrantes y salientes {#inbound-outbound-file-transfers}

[!DNL Audience Manager] procesa y envía transferencias de  [!UICONTROL Server-to-Server (S2S)] archivos entrantes y salientes según las programaciones descritas en esta sección. Dadas estas programaciones y las horas de corte, es posible que observe discrepancias con los nuevos segmentos entre los números de segmento totales y en tiempo real.

| Tipo de archivo | Descripción |
|---|---|
| Entrada de archivos (datos sin conexión) | El procesamiento de archivos se ejecuta dos veces al día. Estos procedimientos ingieren datos y los preparan para el envío. Los tiempos de envío de archivos varían porque se ven afectados por la cantidad total de datos de clientes que deben procesarse. Debe esperar una latencia máxima de 48 horas entre el momento en que se carga el archivo en el Audience Manager y hasta que los datos estén disponibles para sistema de informes y activación. |
| Archivos de salida (Exportar) | El procesamiento y envío de archivos se realiza una vez al día, aproximadamente a las 14:00 UTC. Tenga en cuenta que el procesamiento y el envío se ven afectados por el número total y el tamaño de estos archivos. En algunos casos, puede haber un retraso en el procesamiento de archivos de hasta 24 horas. Cuando esto sucede, el Audience Manager enviará 2 archivos para un día en particular en lugar de 1. Notificaremos a nuestros clientes en el caso poco frecuente de que el Audience Manager tenga que dejar de procesar un archivo por completo. Dadas estas condiciones, es difícil estimar los tiempos de envío de los datos salientes. Para determinar si ha recibido un conjunto completo de archivos, compruebe la marca de tiempo y busque los días que faltan. Es una marca de tiempo UNIX UTC de 13 dígitos que registra la hora en que se creó el archivo. Consulte [Transferencias de datos salientes en tiempo real](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| Archivos de registro del servidor de publicidad | El procesamiento de archivos se ejecuta casi en tiempo real para ingestar registros de archivos de registro a medida que los archivos por hora están listos. El proceso de preparación de los archivos para sistema de informes se ejecuta una vez al día. Los tiempos de envío de archivos varían porque se ven afectados por la cantidad total de datos de clientes que deben procesarse. Debe esperar una latencia máxima de 48 horas entre el momento en que carga el archivo al Audience Manager y el momento en que los datos están disponibles para sistema de informes y activación. |

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre la incorporación de datos de clientes entrantes](../faq/faq-inbound-data-ingestion.md)

