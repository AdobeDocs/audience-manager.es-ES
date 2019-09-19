---
description: Los componentes de procesamiento de datos incluyen Hadoop, Snowflake, SOLR y Tableau.
seo-description: Los componentes de procesamiento de datos incluyen Hadoop, Snowflake, SOLR y Tableau.
seo-title: Componentes de procesamiento de datos
solution: Audience Manager
title: Componentes de procesamiento de datos
uuid: d458d869-7a23-4016-871d-0b994cf4af06
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Componentes de procesamiento de datos{#data-processing-components}

Los componentes de procesamiento de datos incluyen Hadoop, Snowflake, SOLR y Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager utiliza los siguientes componentes para procesar datos:

## Hadoop {#hadoop}

En [!DNL Audience Manager], Hadoop es la base de datos maestra que contiene todo lo que [!DNL Audience Manager] sabe sobre un usuario. Por ejemplo, cuando los servidores [de caché de](../../reference/system-components/components-data-collection.md) perfiles crean archivos de registro que contienen datos sobre los usuarios, envía esos datos a Hadoop para su almacenamiento. Otros elementos importantes de Hadoop son:

* **** Hive: Un almacén de datos para Hadoop. Hive administra consultas ad hoc a los datos almacenados en Hadoop.

* **** HBase: Una base de datos Hadoop muy grande. Procesa y administra datos entrantes y salientes, reglas de características, información de modelado algorítmico y realiza muchas otras funciones relacionadas con el almacenamiento y el traslado de datos a diferentes sistemas.

Los clientes no tienen acceso directo a estos sistemas. Sin embargo, los clientes trabajan con ellos indirectamente, ya que estos componentes almacenan datos importantes sobre los visitantes del sitio.

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/) es una base de datos masiva en la nube. Proporciona datos a muchos de los gráficos de tableros y sus cuadros de texto relacionados que muestran el cambio de % para cada elemento del gráfico. Si utiliza [!DNL Audience Manager] y observa los informes de tablero, está interactuando con los datos proporcionados por [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Esta lista no es completa, pero algunos informes de tablero comunes que [!UICONTROL Snowflake] son responsables de:

* [Informe Variación de la característica diaria](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* [Informe de rendimiento y entrega](/help/using/reporting/dynamic-reports/delivery-performance-report.md)
* Todos los informes de superposición (consulte la sección Informes [](/help/using/reporting/dynamic-reports/dynamic-reports.md) interactivos para obtener información sobre cada informe de superposición).
* [Informe Señales no utilizadas](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR es un sistema de servidor y base de datos de código abierto de Apache. Proporciona capacidades de búsqueda robustas y rápidas en nuestros grandes conjuntos de datos. Como [!DNL Audience Manager] cliente, puede ver SOLR en acción al crear segmentos. Proporciona datos al [!UICONTROL Estimated Historic Segment Size] informe. La SOLR es ideal para este rol por su velocidad. Por ejemplo, SOLR puede actualizar los datos de tamaño histórico a medida que crea reglas y agrega nuevas características a un segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utiliza [Tableau](https://www.tableausoftware.com/) para mostrar datos en los informes [](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) interactivos y en los informes [de optimización de](../../reporting/audience-optimization-reports/audience-optimization-reports.md)audiencia. Los informes interactivos muestran datos de rendimiento y superposición para características y segmentos. En lugar de utilizar números dispuestos en columnas y filas, devuelven datos con diferentes formas, colores y tamaños. Además, puede elegir puntos de datos individuales o grupos y explorar en profundidad los resultados del informe para obtener más detalles. Estas técnicas de visualización e interactividad de informes ayudan a que grandes cantidades de datos numéricos sean más fáciles de entender.



![](assets/advertiser_analytics.png)

