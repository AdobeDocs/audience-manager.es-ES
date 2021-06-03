---
description: Los componentes de procesamiento de datos incluyen Hadoop, Snowflake, SOLR y Tableau.
seo-description: Los componentes de procesamiento de datos incluyen Hadoop, Snowflake, SOLR y Tableau.
seo-title: Componentes de procesamiento de datos
solution: Audience Manager
title: Componentes de procesamiento de datos
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: 'Componentes del sistema '
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 4%

---

# Componentes de procesamiento de datos{#data-processing-components}

Los componentes de procesamiento de datos incluyen Hadoop, Snowflake, SOLR y Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager utiliza los siguientes componentes para procesar los datos:

## Hadoop {#hadoop}

En [!DNL Audience Manager], el Hadoop es la base de datos principal que contiene todo lo que [!DNL Audience Manager] sabe sobre un usuario. Por ejemplo, cuando los [Servidores de caché de perfil](../../reference/system-components/components-data-collection.md) crean archivos de registro que contienen datos sobre los usuarios, estos se envían a Hadoop para su almacenamiento. Otros elementos de Hadoop importantes son:

* **Hive:** almacén de datos para el Hadoop. Hive administra consultas ad hoc a los datos almacenados en Hadoop.

* **HBase:** una base de datos de Hadoop muy grande. Procesa y gestiona los datos entrantes y salientes, las reglas de características y la información de modelado algorítmico, y realiza muchas otras funciones relacionadas con el almacenamiento y el traslado de datos a distintos sistemas.

Los clientes no tienen acceso directo a estos sistemas. Sin embargo, los clientes trabajan con ellos de forma indirecta, ya que estos componentes almacenan datos importantes sobre los visitantes del sitio.

## Snowflake {#snowflake}

[](https://www.snowflake.net/) Snowflakak es una base de datos en la nube masiva. Proporciona datos a muchos de los gráficos de tablero y sus cuadros de texto relacionados que muestran el cambio de % para cada elemento del gráfico. Si utiliza [!DNL Audience Manager] y observa los informes del panel, está interactuando con los datos proporcionados por [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Esta no es en absoluto una lista completa, pero algunos informes de panel comunes de los que [!UICONTROL Snowflake] es responsable incluyen:

* [Informe de variación del rasgo diario](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Todos los informes de superposición (consulte la sección [Informes interactivos](/help/using/reporting/dynamic-reports/dynamic-reports.md) para obtener información sobre cada informe de superposición).
* [Informe de señales no utilizadas](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR es un sistema de servidor y base de datos de código abierto de Apache. Proporciona funciones de búsqueda sólidas y rápidas en nuestros grandes conjuntos de datos. Como cliente [!DNL Audience Manager], puede ver SOLR en acción cuando genera segmentos. Proporciona datos al informe [!UICONTROL Estimated Historic Segment Size]. La SOLR es ideal para este rol debido a su velocidad. Por ejemplo, SOLR puede actualizar los datos de tamaño histórico a medida que genera reglas y agrega nuevas características a un segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utiliza datos de visualización  [](https://www.tableausoftware.com/) Tableauto en los informes  [interactivos ](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) y en los informes  [Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md). Los informes interactivos muestran el rendimiento y superponen los datos de características y segmentos. En lugar de utilizar números organizados en columnas y filas, devuelven datos con diferentes formas, colores y tamaños. Además, puede elegir puntos de datos individuales o grupos y explorar en profundidad los resultados del informe para obtener más detalles. Estas técnicas de visualización e interactividad de los informes ayudan a facilitar la comprensión de las grandes cantidades de datos numéricos.



![](assets/advertiser_analytics.png)
