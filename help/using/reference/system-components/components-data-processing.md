---
description: Los componentes de procesamiento de datos incluyen Hadoop, Snowflake, SOLR y Tableau.
seo-description: Data processing components include Hadoop, Snowflake, SOLR, and Tableau.
seo-title: Data Processing Components
solution: Audience Manager
title: Componentes de procesamiento de datos
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: System Components
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 3%

---

# Componentes de procesamiento de datos{#data-processing-components}

Los componentes de procesamiento de datos incluyen Hadoop, Snowflake, SOLR y Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager utiliza los siguientes componentes para procesar los datos:

## Hadoop {#hadoop}

Entrada [!DNL Audience Manager], el Hadoop es la base de datos principal que contiene todo [!DNL Audience Manager] conoce a un usuario. Por ejemplo, cuando la variable [Servidores de caché de perfil](../../reference/system-components/components-data-collection.md) Si crea archivos de registro que contienen datos sobre los usuarios, estos se envían al Hadoop para su almacenamiento. Otros elementos importantes del Hadoop son:

* **Subárbol:** Un almacén de datos para el Hadoop. Hive administra consultas ad hoc a los datos almacenados en el Hadoop.

* **HBase:** Una base de datos de Hadoop muy grande. Procesa y administra datos de entrada y salida, reglas de rasgos, información de modelado algorítmico y realiza muchas otras funciones relacionadas con el almacenamiento y el movimiento de datos a diferentes sistemas.

Los clientes no tienen acceso directo a estos sistemas. Sin embargo, los clientes sí trabajan con ellos indirectamente, ya que estos componentes almacenan datos importantes sobre los visitantes del sitio.

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/) es una base de datos en la nube masiva. Proporciona datos a muchos de los gráficos de tableros y a sus cuadros de texto relacionados que muestran el cambio porcentual para cada elemento del gráfico. Si utiliza [!DNL Audience Manager] y observe los informes del tablero, está interactuando con los datos proporcionados por [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Esta no es una lista completa, pero algunos informes de tableros comunes indican que [!UICONTROL Snowflake] es responsable de incluir:

* [Informe de variación del rasgo diario](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Todos los informes de superposición (consulte los [Informes interactivos](/help/using/reporting/dynamic-reports/dynamic-reports.md) para obtener información sobre cada informe de superposición).
* [Informe de señales no utilizadas](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR es una base de datos de código abierto y un sistema de servidor de Apache. Proporciona capacidades de búsqueda sólidas y rápidas en comparación con nuestros grandes conjuntos de datos. Como un [!DNL Audience Manager] cliente, puede ver el SOLR en acción cuando genere segmentos. Proporciona datos a la [!UICONTROL Estimated Historic Segment Size] informe. SOLR es ideal para este papel debido a su velocidad. Por ejemplo, SOLR puede actualizar los datos de tamaño históricos a medida que crea reglas y añade nuevas características a un segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utiliza [Tableau](https://www.tableausoftware.com/) para mostrar datos en [Informes interactivos](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) y el [Informes del Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md). Los informes interactivos muestran los datos de rendimiento y superposición de características y segmentos. En lugar de utilizar números organizados en columnas y filas, devuelven datos con diferentes formas, colores y tamaños. Además, puede elegir puntos de datos individuales o en grupos y explorar en profundidad los resultados del informe para obtener más información. Estas técnicas de visualización y la interactividad de informes ayudan a comprender grandes cantidades de datos numéricos.



![](assets/advertiser_analytics.png)
