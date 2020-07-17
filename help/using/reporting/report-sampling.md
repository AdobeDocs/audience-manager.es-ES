---
description: Un resumen de la metodología de muestreo utilizada para algunos informes, las tasas de error de muestreo y una lista de informes que devuelven información basada en datos de muestra.
seo-description: Un resumen de la metodología de muestreo utilizada para algunos informes, las tasas de error de muestreo y una lista de informes que devuelven información basada en datos de muestra.
seo-title: Muestreo de datos y tasas de error en los informes de Audience Manager seleccionado
solution: Audience Manager
title: Muestreo de datos y tasas de error en los informes de Audience Manager seleccionado
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 8%

---


# Muestreo de datos y tasas de error en los informes de Audience Manager seleccionado{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Un resumen de la metodología de muestreo utilizada para algunos informes, las tasas de error de muestreo y una lista de informes que devuelven información basada en datos de muestra.

## Proporción de muestreo de datos y requisitos mínimos {#data-sampling-ratio}

Algunos [!DNL Audience Manager] informes muestran los resultados en función de un conjunto muestreado de la cantidad total de datos disponibles. La proporción de datos de muestra es 1:54. Para los informes que utilizan datos de muestra, esto significa que los resultados se basan en un registro de cada conjunto de 54 registros.

Estos informes utilizan datos muestreados porque necesitan una enorme capacidad informática para generar resultados. El muestreo ayuda a encontrar un equilibrio entre la reducción de las demandas computacionales, el mantenimiento del rendimiento del sistema y la obtención de resultados precisos.

Los informes que utilizan muestras excluyen características y segmentos cuando no cumplen los requisitos mínimos de visitante único. Estos requisitos mínimos son los siguientes:

* Características: 28.000 [realizaciones](/help/using/features/traits/trait-and-segment-qualification-reference.md#unique-trait-realizations) únicas de características durante un período de 14 días.
* Segmentos: 70.000 usuarios en tiempo real durante un período de 14 días.

## Tasas de error {#error-rates}

Pueden producirse errores en los informes que generan datos de superposición. Un error se define como el porcentaje de registros que:

* No debería haberse incluido en un informe pero se han agregado de todos modos.
* Debía haberse incluido en un informe, pero se les excluyó.

Es importante tener en cuenta que nuestras pruebas y modelos muestran que la tasa de error *disminuye* en una proporción inversa al número de registros del conjunto de datos. Los conjuntos de datos que tienen muchos registros generan menos errores que los conjuntos con un pequeño número de registros. Veamos esta afirmación de una manera más cuantitativa. Como se muestra en la siguiente tabla, para un número determinado de registros, el 95% de los resultados del informe estarán por debajo de una tasa de error específica.

| Número de registros | Tasa de error |
|--- |--- |
| 500 - 1,000 | El 95 % está por debajo de una tasa de error del 42 %. |
| 1,000 - 1,500 | El 95 % está por debajo de una tasa de error del 34 %. |
| 10,000 - 50,000 | El 95 % está por debajo de una tasa de error del 14 %. |
| 50 000 | El 95 % está por debajo de una tasa de error del 6 %. |
| 100,000 | El 95 % está por debajo de una tasa de error del 4 %. |
| 500.000 (o más) | El 95 % está por debajo de una tasa de error del 2 %. |

## Informes Que Utilizan Datos Muestreados {#reports-using-sampled-data}

Los [!DNL Audience Manager] informes que utilizan datos de muestra incluyen:

* [Superponer informes](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (rasgo a rasgo, segmento a rasgo y segmento a segmento).
* [Datos de Audiencia](../features/addressable-audiences.md) direccionables (datos a nivel de cliente y segmento).
* La métrica Dispositivos [](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) totales de un [!UICONTROL Profile Merge Rule].
* [El Explorador](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) de datos utiliza datos de muestra en la [!UICONTROL Search] ficha y en cualquier [!UICONTROL Saved Searches].