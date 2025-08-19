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
source-wordcount: '395'
ht-degree: 1%

---

# Componentes de procesamiento de datos{#data-processing-components}

Los componentes de procesamiento de datos incluyen Hadoop, Snowflake, SOLR y Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager utiliza los siguientes componentes para procesar los datos:

## Hadoop {#hadoop}

En [!DNL Audience Manager], Hadoop es la base de datos principal que contiene todo lo [!DNL Audience Manager] que sabe sobre un usuario. Por ejemplo, cuando los servidores[ de caché de ](../../reference/system-components/components-data-collection.md)perfiles crean archivos de registro que contienen datos sobre los usuarios, envían esos datos a Hadoop para su almacenamiento. Otros elementos importantes de Hadoop incluyen:

* **Hive:** Un almacén de datos para Hadoop. Hive administra consultas anuncios hoc a los datos almacenados en Hadoop.

* **HBase:** una base de datos Hadoop muy grande. Procesa y administra datos entrantes y salientes, reglas de rasgos, información de modelado algorítmico y realiza muchas otras funciones relacionadas con el almacenamiento y movimiento de datos a diferentes sistemas.

Los clientes no tienen acceso directo a estos sistemas. Sin embargo, los clientes trabajan con ellos indirectamente, ya que estos componentes tienda datos importantes sobre los visitantes de su sitio.

## Copo de nieve {#snowflake}

[](https://www.snowflake.net/) Snowflake es una base de datos nube masiva. Proporciona datos a muchos de los gráficos de panel y sus cuadros de texto relacionados que muestran el % de cambio para cada elemento en el gráfico. Si utiliza [!DNL Audience Manager] y mira los informes panel, está interactuando con los datos proporcionados por [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Esto no es de ninguna manera un lista exhaustivo, pero algunos informes de panel comunes de los que [!UICONTROL Snowflake] es responsable incluyen:

* [Informe de variación del rasgo diario](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Todos los informes de superposición (consulte la [sección Informes](/help/using/reporting/dynamic-reports/dynamic-reports.md) interactivo para obtener información sobre cada informe de superposición).
* [Informe de señales no utilizadas](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR es una base de datos de código abierto y un sistema de servidor de Apache. Proporciona capacidades de búsqueda robustas y rápidas sobre nuestros grandes conjuntos de datos. [!DNL Audience Manager] Como cliente, puede ver SOLR en acción cuando versión segmentos. Proporciona datos al [!UICONTROL Estimated Historic Segment Size] informe. SOLR es ideal para este función debido a su velocidad. Por ejemplo, SOLR puede actualizar los datos de tamaño histórico a medida que versión reglas y agregar nuevos rasgos a un segmento.



![](assets/audsize.png)

## Cuadro {#tableau}

[!DNL Audience Manager]usa [Tableau](https://www.tableausoftware.com/) para mostrar datos en los [informes](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) interactivo y Audience Optimization[](../../reporting/audience-optimization-reports/audience-optimization-reports.md). Los informes interactivos muestran datos de rendimiento y superposición para características y segmentos. En lugar de usar números dispuestos en columnas y filas, devuelven datos usando diferentes formas, colores y tamaños. Además, puede elegir puntos de datos individuales o en grupo y explorar en profundidad en los resultados del informe para obtener más detalles. Estas técnicas de visualización y interactividad de informes ayudan a que grandes cantidades de datos de numérica sean más fáciles de entender.



![](assets/advertiser_analytics.png)
