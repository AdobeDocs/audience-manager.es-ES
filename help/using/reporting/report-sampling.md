---
description: Resumen de la metodología de muestra utilizada para algunos informes, muestra de errores de muestreo y una lista de informes que devuelven información basada en datos de muestra.
seo-description: Resumen de la metodología de muestra utilizada para algunos informes, muestra de errores de muestreo y una lista de informes que devuelven información basada en datos de muestra.
seo-title: Muestras de datos y tasas de error en informes de Audience Manager seleccionados
solution: Audience Manager
title: Muestras de datos y tasas de error en informes de Audience Manager seleccionados
uuid: 3 d 8 bd 764-a 9 da -40 f 1-8794-54304457 bb 9 a
translation-type: tm+mt
source-git-commit: d96182b0741dd31cc5ec0ffb68182ed5f8445c03

---


# Data Sampling and Error Rates in Selected Audience Manager Reports{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Resumen de la metodología de muestra utilizada para algunos informes, muestra de errores de muestreo y una lista de informes que devuelven información basada en datos de muestra.

## Data Sampling Ratio and Minimum Requirements {#data-sampling-ratio}

Some [!DNL Audience Manager] reports display results based on a sampled set of the total amount of available data. La proporción de datos de muestra es de 1:54. Para los informes que utilizan datos de muestra, los resultados se basan en 1 registro de cada conjunto de 54 registros.

Estos informes utilizan datos de muestra porque necesitan una enorme cantidad de potencia informática para generar resultados. El muestreo ayuda a equilibrar el equilibrio entre las demandas computadoras reducidas, mantener el rendimiento del sistema y proporcionar resultados precisos.

Los informes que utilizan muestras excluyen características y segmentos cuando no cumplen los requisitos mínimos de visitante único. Estos requisitos mínimos son los siguientes:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-qualification-reference.md#unique-trait-realizations) over a 14-day period.
* Segmentos: 70.000 usuarios en tiempo real durante un período de 14 días.

## Error Rates {#error-rates}

Los errores pueden producirse en informes que generan datos superpuestos. Se define un error como el porcentaje de registros que:

* No debe haberse incluido en un informe pero se agregó de todas maneras.
* Debe haberse incluido en un informe pero se ha eliminado.

It's important to note that our tests and models show that the error rate *decreases* in an inverse proportion to the number of records in your data set. Los conjuntos de datos que tienen muchos registros generan menos errores que los conjuntos con un pequeño número de registros. Observemos esta afirmación de manera más cuantitativa. Como se muestra en la tabla siguiente, para un número de registros establecido, el 95% de los resultados del informe será inferior a una tasa de error específica.

| Número de registros | Tasa de error |
|--- |--- |
| 500 - 1,000 | El 95% se encuentra bajo una tasa de error del 42%. |
| 1,000 - 1,500 | El 95% se encuentra bajo una tasa de error del 34%. |
| 10,000 - 50,000 | El 95% se encuentra bajo una tasa de error del 14%. |
| 50 000 | El 95% se encuentra bajo una tasa de error del 6%. |
| 100,000 | El 95% se encuentra bajo una tasa de error del 4%. |
| 500.000 (o más) | El 95% se encuentra bajo una tasa de error del 2%. |

## Reports That Use Sampled Data {#reports-using-sampled-data}

The [!DNL Audience Manager] reports that use sampled data include:

* [Superponga informes](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (características a características, segmentos a rasgo y segmento a segmento).
* [Datos de audiencia](../features/addressable-audiences.md) objetivo (datos de nivel de segmento y de cliente).
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
