---
description: Audience Manager recibe una enorme cantidad de datos todos los días. Esto afecta a la cantidad de tiempo que se tarda en procesar los datos y generar los resultados del informe. El contenido de esta sección describe cómo afectan estos intervalos de tiempo a su cuenta de Audience Manager. Además, los marcos de tiempo y los horarios descritos aquí son solo directrices generales. Estas programaciones no constituyen acuerdos de nivel de servicio (SLA) ni compromisos relacionados con la entrega de datos. El Adobe se reserva el derecho de cambiar los plazos y horarios en cualquier momento sin previo aviso.
seo-description: Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.
seo-title: How Data Delivery and File Processing Times Affect Reports
solution: Audience Manager
title: Cómo afecta el envío de datos y los tiempos de procesamiento de archivos a los informes
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: Reference
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 4%

---

# Cómo afecta el envío de datos y los tiempos de procesamiento de archivos a los informes{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager recibe una enorme cantidad de datos todos los días. Esto afecta a la cantidad de tiempo que se tarda en procesar los datos y generar los resultados del informe. El contenido de esta sección describe cómo afectan estos intervalos de tiempo a su cuenta de Audience Manager. Además, los marcos de tiempo y los horarios descritos aquí son solo directrices generales. Estas programaciones no constituyen acuerdos de nivel de servicio (SLA) ni compromisos relacionados con la entrega de datos. El Adobe se reserva el derecho de cambiar los plazos y horarios en cualquier momento sin previo aviso.

## Números de informes {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

En la tabla siguiente se enumeran y describen los intervalos de tiempo de nuestros informes generales y en tiempo real.


| Tipo de datos | Descripción |
|---|---|
| Datos en tiempo real | Los números en tiempo real de hoy corresponden a las horas de 00:00 a 23:59:59 UTC desde ayer. |
| Datos generales de informes | Los datos de la [Informes generales](../reporting/general-reports.md#general-reports-overview) depende de la finalización correcta de otros procesos de trabajo y de la cantidad de datos recibidos para un día concreto. La mayoría de las veces, [!UICONTROL General Report] Los datos deben actualizarse diariamente a las 18:00 UTC. |

## Transferencias de archivos entrantes y salientes {#inbound-outbound-file-transfers}

[!DNL Audience Manager] procesa y envía mensajes entrantes y salientes [!UICONTROL Server-to-Server (S2S)] las transferencias de archivos se realizan según las programaciones descritas en esta sección. Dadas estas programaciones y las horas de cierre, es posible que vea discrepancias con los nuevos segmentos entre los números de segmentos en tiempo real y totales.

| Tipo de archivo | Descripción |
|---|---|
| Ingesta de archivos entrantes (datos sin conexión) | El procesamiento de archivos se ejecuta dos veces al día. Estos procedimientos consumen datos y los preparan para su envío. Los tiempos de entrega de archivos varían porque se ven afectados por la cantidad total de datos de clientes que deben procesarse. Debería esperar una latencia máxima de 48 horas entre el momento en que el archivo se carga en Audience Manager y el momento en que los datos estén disponibles para la creación de informes y la activación. |
| Archivos de salida (exportación) | El procesamiento y la entrega de archivos tienen lugar una vez al día, aproximadamente a las 14:00 UTC. Tenga en cuenta que el procesamiento y la entrega se ven afectados por la cantidad total y el tamaño de estos archivos. En algunos casos, puede haber un retraso en el procesamiento de archivos de hasta 24 horas. Cuando esto sucede, Audience Manager envía 2 archivos para un día en particular en lugar de 1. Notificaremos a nuestros clientes en el raro caso de que el Audience Manager tenga que dejar de procesar un archivo por completo. Dadas estas condiciones, es difícil estimar los tiempos de envío de los datos salientes. Para determinar si ha recibido un conjunto completo de archivos, compruebe la marca de tiempo y busque los días que faltan. Es una marca de tiempo UNIX UTC de 13 dígitos que registra la hora en la que se creó el archivo. Consulte [Transferencias de datos salientes en tiempo real](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| Archivos de registro del servidor de publicidad | El procesamiento de archivos se ejecuta en tiempo casi real para introducir registros de archivos de registro a medida que los archivos por hora están listos. El proceso de preparación de los archivos para la creación de informes se ejecuta una vez al día. Los tiempos de entrega de archivos varían porque se ven afectados por la cantidad total de datos de clientes que deben procesarse. Debería esperar una latencia máxima de 48 horas entre el momento en que carga el archivo en Audience Manager y el momento en que los datos están disponibles para la creación de informes y la activación. |

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre la incorporación de datos de clientes entrantes](../faq/faq-inbound-data-ingestion.md)

