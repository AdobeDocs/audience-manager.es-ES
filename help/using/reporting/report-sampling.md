---
description: Un resumen de la metodología de muestreo utilizada para algunos informes, las tasas de error de muestreo y una lista de informes que devuelven información basada en datos de muestra.
seo-description: Un resumen de la metodología de muestreo utilizada para algunos informes, las tasas de error de muestreo y una lista de informes que devuelven información basada en datos de muestra.
seo-title: Muestreo de datos y tasas de error en los informes de Audience Manager seleccionado
solution: Audience Manager
title: Muestreo de datos y tasas de error en los informes de Audience Manager seleccionado
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: reporting reference
translation-type: tm+mt
source-git-commit: 397be3f44bf865633140bb45630a78be0a0d2219
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 7%

---


# Muestreo de datos y tasas de error en los informes de Audience Manager seleccionado{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Un resumen de la metodología de muestreo utilizada para algunos informes, las tasas de error de muestreo y una lista de informes que devuelven información basada en datos de muestra.

## Tasa de muestreo de datos {#data-sampling-ratio}

Algunos informes [!DNL Audience Manager] muestran resultados basados en un conjunto muestreado de la cantidad total de datos disponibles. La proporción de datos de muestra es 1:54. Para los informes que utilizan datos de muestra, esto significa que los resultados se basan en un registro de cada conjunto de 54 registros.

Estos informes utilizan datos estadísticos de muestra porque necesitan una enorme capacidad informática para generar resultados. El muestreo ayuda a encontrar un equilibrio entre la reducción de las demandas computacionales, el mantenimiento del rendimiento del sistema y la obtención de resultados precisos.

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

* No debería haberse incluido en un informe pero se han agregado de todos modos.
* Debía haberse incluido en un informe, pero se les excluyó.

Es importante tener en cuenta que nuestras pruebas y modelos muestran que la tasa de error *disminuye* en una proporción inversa a la cantidad de registros del conjunto de datos. Los conjuntos de datos que tienen muchos registros generan menos errores que los conjuntos con un pequeño número de registros. Veamos esta afirmación de una manera más cuantitativa. Como se muestra en la siguiente tabla, para un número determinado de registros, el 95% de los resultados del informe estarán por debajo de una tasa de error específica.

| Número de registros | Tasa de error |
|--- |--- |
| 500 - 1.000 | El 95 % está por debajo de una tasa de error del 42 %. |
| De 1.000 a 1.500 | El 95 % está por debajo de una tasa de error del 34 %. |
| 10.000 - 50.000 | El 95 % está por debajo de una tasa de error del 14 %. |
| 50 000 | El 95 % está por debajo de una tasa de error del 6 %. |
| 100.000 | El 95 % está por debajo de una tasa de error del 4 %. |
| 500.000 (o más) | El 95 % está por debajo de una tasa de error del 2 %. |

## Uso de la metodología de muestreo Minhash {#minhash}

Según la metodología de muestreo [Minhash](https://en.wikipedia.org/wiki/MinHash), el Audience Manager utiliza un método novedoso para calcular los estimadores de características y segmentos sobre un esbozo de datos con hash de una permutación. Este nuevo método produce una varianza inferior a la del estimador estándar para la similitud de Jaccard. Consulte la sección siguiente para ver los informes que utilizan esta metodología.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## Informes que utilizan datos mostrados {#reports-using-sampled-data}

Los informes [!DNL Audience Manager] que utilizan datos estadísticos de muestra y la metodología de muestreo Minhash incluyen:

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| Muestreo estadístico | Metodología de muestreo de minerales |
|--- |--- |
| [Datos de ](../features/addressable-audiences.md) audiencia direccionables (datos a nivel de cliente y segmento). | [Superponer informes](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)  (rasgo a rasgo, segmento a rasgo y segmento a segmento) |
| La métrica [Dispositivos totales](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) para un [!UICONTROL Profile Merge Rule]. | [Recomendaciones de rasgos](/help/using/features/segments/trait-recommendations.md) |
| [Data ](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) Explorer utiliza datos de muestra en la  [!UICONTROL Search] ficha y en cualquier  [!UICONTROL Saved Searches] | [Audience Marketplace Recommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
