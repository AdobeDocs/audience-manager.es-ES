---
description: Los componentes de procesamiento de datos incluyen Hadoop, Snowflake, SOLR y Tableau.
seo-description: Los componentes de procesamiento de datos incluyen Hadoop, Snowflake, SOLR y Tableau.
seo-title: Componentes de procesamiento de datos
solution: Audience Manager
title: Componentes de procesamiento de datos
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 3%

---


# Componentes de procesamiento de datos{#data-processing-components}

Los componentes de procesamiento de datos incluyen Hadoop, Snowflake, SOLR y Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager utiliza los siguientes componentes para procesar datos:

## Hadoop {#hadoop}

En [!DNL Audience Manager], Hadoop es la base de datos principal que contiene todo lo que [!DNL Audience Manager] sabe sobre un usuario. Por ejemplo, cuando [Servidores de caché de Perfil](../../reference/system-components/components-data-collection.md) crean archivos de registro que contienen datos sobre los usuarios, envía esos datos a Hadoop para su almacenamiento. Otros elementos importantes de Hadoop son:

* **Hive:** un almacén de datos para Hadoop. Hive administra consultas ad hoc a los datos almacenados en Hadoop.

* **HBase:** una base de datos de Hadoop muy grande. Procesa y administra datos entrantes y salientes, reglas de características, información de modelado algorítmico y realiza muchas otras funciones relacionadas con el almacenamiento y el traslado de datos a diferentes sistemas.

Los clientes no tienen acceso directo a estos sistemas. Sin embargo, los clientes trabajan con ellos indirectamente, ya que estos componentes almacenan datos importantes sobre los visitantes del sitio.

## Snowflake {#snowflake}

[](https://www.snowflake.net/) Snowflakakes una base de datos masiva en la nube. Proporciona datos a muchos de los gráficos de paneles y sus cuadros de texto relacionados que muestran el cambio de % para cada elemento del gráfico. Si utiliza [!DNL Audience Manager] y observa los informes de panel, está interactuando con los datos proporcionados por [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Esta no es en absoluto una lista integral, pero algunos informes comunes de panel que [!UICONTROL Snowflake] es responsable de incluir:

* [Informe de variación del rasgo diario](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Todos los informes de superposición (consulte la sección [Informes interactivos](/help/using/reporting/dynamic-reports/dynamic-reports.md) para obtener información sobre cada informe de superposición).
* [Informe de señales no utilizadas](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR es un sistema de servidor y base de datos de código abierto de Apache. Proporciona capacidades de búsqueda robustas y rápidas en nuestros grandes conjuntos de datos. Como cliente [!DNL Audience Manager], puede ver SOLR en acción al crear segmentos. Proporciona datos al informe [!UICONTROL Estimated Historic Segment Size]. La SOLR es ideal para este rol debido a su velocidad. Por ejemplo, SOLR puede actualizar los datos de tamaño histórico a medida que crea reglas y agrega nuevas características a un segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utiliza  [](https://www.tableausoftware.com/) Tabledatos de visualización automática en los informes  [interactivos y ](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) los informes  [Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md). Los informes interactivos muestran datos de rendimiento y superposición para características y segmentos. En lugar de utilizar números dispuestos en columnas y filas, devuelven datos con diferentes formas, colores y tamaños. Además, puede elegir puntos de datos individuales o grupos y explorar en profundidad los resultados del informe para obtener más detalles. Estas técnicas de visualización e interactividad de informes ayudan a que grandes cantidades de datos numéricos sean más fáciles de entender.



![](assets/advertiser_analytics.png)

