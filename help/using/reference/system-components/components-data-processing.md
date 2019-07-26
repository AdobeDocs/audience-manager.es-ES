---
description: Los componentes de procesamiento de datos incluyen Hadoop, Snow Flake, SOLR y Tableau.
seo-description: Los componentes de procesamiento de datos incluyen Hadoop, Snow Flake, SOLR y Tableau.
seo-title: Componentes de procesamiento de datos
solution: Audience Manager
title: Componentes de procesamiento de datos
uuid: d 458 d 869-7 a 23-4016-871 d -0 b 994 cf 4 af 06
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Processing Components{#data-processing-components}

Los componentes de procesamiento de datos incluyen Hadoop, Snow Flake, SOLR y Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager utiliza los componentes siguientes para procesar datos:

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop is the master database that contains everything [!DNL Audience Manager] knows about a user. For example, when the [Profile Cache Servers](../../reference/system-components/components-data-collection.md) create log files that contain data about your users, it sends that data to Hadoop for storage. Otros elementos importantes de Hadoop incluyen:

* **Hive:** Almacén de datos para Hadoop. Hive administra consultas ad hoc a los datos almacenados en Hadoop.

* **Hbase:** Una base de datos Hadoop muy grande. Procesa y gestiona datos entrantes y salientes, reglas de características, información de modelado algorítmico y realiza muchas otras funciones relacionadas con almacenar y mover datos a distintos sistemas.

Los clientes no tienen acceso directo a estos sistemas. Sin embargo, los clientes trabajan con ellos indirectamente, ya que estos componentes almacenan datos importantes sobre los visitantes del sitio.

## Snowflake {#snowflake}

[Copo de nieve](https://www.snowflake.net/) es una base de datos nube masiva. Proporciona datos a muchos de los gráficos de tableros y a sus cuadros de texto relacionados que muestran el cambio de % para cada elemento del gráfico. If you use [!DNL Audience Manager] and look at the dashboard reports, you're interacting with data provided by [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

This is by no means a comprehensive list, but some common dashboard reports that [!UICONTROL Snowflake] is responsible for include:

* [Informe Variación de características diarias](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* [Informe de entrega y rendimiento](/help/using/reporting/dynamic-reports/delivery-performance-report.md)
* All the overlap reports (see the [Interactive Reports](/help/using/reporting/dynamic-reports/dynamic-reports.md) section for information about each overlap report).
* [Informe Señales no utilizadas](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR es un sistema de base de datos y servidor de código abierto desde Apache. Proporciona capacidades de búsqueda rápidas y rápidas sobre nuestros grandes conjuntos de datos. As an [!DNL Audience Manager] customer, you can see SOLR in action when you build segments. It provides data to the [!UICONTROL Estimated Historic Segment Size] report. SOLR es ideal para esta función debido a su velocidad. Por ejemplo, SOLR puede actualizar los datos de tamaño histórico a medida que genera reglas y agrega nuevas características a un segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utiliza [Tableau](https://www.tableausoftware.com/) para mostrar los datos en los informes [interactivos](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) y en los informes de optimización [de audiencias](../../reporting/audience-optimization-reports/audience-optimization-reports.md). Los informes interactivos muestran el rendimiento y superponen datos para características y segmentos. En lugar de utilizar números organizados en columnas y filas, devuelven datos utilizando distintas formas, colores y tamaños. Además, puede elegir individuales o grupos de puntos de datos y explorar en profundidad los resultados del informe para obtener más detalles. Estas técnicas de visualización y la interactividad de informes ayudan a comprender más fácilmente las grandes cantidades de datos numéricos.



![](assets/advertiser_analytics.png)

