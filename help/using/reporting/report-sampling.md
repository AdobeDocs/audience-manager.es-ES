---
description: Resumen de la metodología de muestreo utilizada para algunos informes, tasas de error de muestreo y lista de informes que devuelven información basada en datos muestreados.
seo-description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-title: Data Sampling and Error Rates in Selected Audience Manager Reports
solution: Audience Manager
title: Muestreo de datos y tasas de error en informes de Audience Manager seleccionados
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: Reporting Reference
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Muestreo de datos y tasas de error en informes de Audience Manager seleccionados{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Resumen de la metodología de muestreo utilizada para algunos informes, tasas de error de muestreo y lista de informes que devuelven información basada en datos muestreados.

## Proporción de muestreo de datos {#data-sampling-ratio}

Algunos informes de [!DNL Audience Manager] muestran los resultados basándose en un conjunto muestreado de la cantidad total de datos disponibles. La proporción de datos muestreados es de 1:54. En el caso de los informes que utilizan datos de ejemplo, los resultados se basan en 1 registro de cada conjunto de 54 registros.

Estos informes utilizan datos estadísticos muestreados porque necesitan una enorme cantidad de potencia de cálculo para generar resultados. El muestreo ayuda a lograr un equilibrio entre la reducción de las demandas informáticas, el mantenimiento del rendimiento del sistema y la obtención de resultados precisos.

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## Tasas de error {#error-rates}

Pueden producirse errores en los informes que generan datos de superposición. Un error se define como el porcentaje de registros que:

* No deberían haberse incluido en un informe, pero se agregaron de todos modos.
* Debería haberse incluido en un informe, pero no se ha incluido.

Es importante tener en cuenta que nuestras pruebas y modelos muestran que la tasa de error *disminuye* en una proporción inversa al número de registros del conjunto de datos. Los conjuntos de datos que tienen muchos registros generan menos errores que los conjuntos con un pequeño número de registros. Veamos esta afirmación de una manera más cuantitativa. Como se muestra en la tabla siguiente, para un número determinado de registros, el 95 % de los resultados del informe se encontrarán por debajo de una tasa de error específica.

| Número de registros | Tasa de error |
|--- |--- |
| De 500 a 1.000 | El 95 % tiene una tasa de error inferior al 42 %. |
| De 1.000 a 1.500 | El 95 % tiene una tasa de error inferior al 34 %. |
| De 10.000 a 50.000 | El 95 % tiene una tasa de error inferior al 14 %. |
| 50 000 | El 95 % tiene una tasa de error inferior al 6 %. |
| 100.000 | El 95 % tiene una tasa de error inferior al 4 %. |
| 500.000 (o más) | El 95 % tiene una tasa de error inferior al 2 %. |

## Uso de la metodología de muestreo Minhash {#minhash}

Basado en la metodología de muestreo [Minhash](https://en.wikipedia.org/wiki/MinHash), Audience Manager usa un nuevo método para calcular los estimadores de rasgos y segmentos sobre un boceto de datos hash de permutación única. Este nuevo método produce una variación menor que el estimador estándar para la similitud de Jaccard. Consulte la sección siguiente para ver los informes que utilizan esta metodología.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## Informes que utilizan datos de ejemplo {#reports-using-sampled-data}

Los informes de [!DNL Audience Manager] que usan datos estadísticos muestreados y la metodología de muestreo Minhash incluyen:

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| Muestreo estadístico | Metodología de muestreo de Minhash |
|--- |--- |
| Datos de [Audiencia direccionable](../features/addressable-audiences.md) (datos de nivel de cliente y de segmento). | [Informes de superposición](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (de característica a característica, de segmento a característica y de segmento a segmento) |
| La métrica [Dispositivos totales](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) para un(a) [!UICONTROL Profile Merge Rule]. | [Recomendaciones de rasgos](/help/using/features/segments/trait-recommendations.md) |
| [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) usa datos muestreados en la ficha [!UICONTROL Search] y en cualquier [!UICONTROL Saved Searches] | [Recommendations Audience Marketplace](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
