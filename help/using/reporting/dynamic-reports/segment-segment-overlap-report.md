---
description: Devuelve datos sobre cuántos usuarios únicos se comparten entre sus segmentos.
seo-description: Devuelve datos sobre cuántos usuarios únicos se comparten entre sus segmentos.
seo-title: Informe de solapamiento entre segmentos
solution: Audience Manager
title: Informe de solapamiento entre segmentos
uuid: 0339 eb 6 c -6355-44 a 3-9 c 46-f 159485449 d 1
translation-type: tm+mt
source-git-commit: 339d5550b22949862415d2abc812217e5479c993

---


# Informe de solapamiento entre segmentos{#segment-to-segment-overlap-report}

Devuelve datos sobre cuántos usuarios únicos se comparten entre sus segmentos.

>[!NOTE]
>
>Los informes Superponer de Audience Manager respetan los principios RBAC. You can only see segments from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_segment_segment_overlap.xml

 -->

## Información general

[!UICONTROL Segment-to-Segment Overlap] El informe puede ayudarle a:

* Identificar segmentos con superposición alta o baja, según sus necesidades. Las características con superposición alta proporcionan una audiencia segmentada, pero menos visitantes únicos. Las características con superposición baja pueden resultar útiles para alcanzar un conjunto de visitantes único y más grande.
* Busque superposición inesperada y utilice esa información para crear segmentos nuevos de alto rendimiento.

## Informe de muestra

The following illustration provides a high-level overview of the [!UICONTROL Segment-to-Segment Overlap] report.

>[!NOTE]
>
>[!UICONTROL Segment-to-Segment Overlap] El informe devuelve un campo vacío cuando compara el mismo segmento consigo mismo.

![](assets/segment-to-segment-overlap.png)

## Explorar en profundidad puntos de datos individuales

Seleccione un punto individual para ver los detalles de los datos en una ventana emergente. Las acciones de clic actualizan automáticamente los datos mostrados en el informe.

## Segment-to-Segment Overlap Data Pop Fields Defined {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

The popup for the [!UICONTROL Segment-to-Segment Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.

| Métrica | Descripción |
|---|---|
| **[!UICONTROL Segment ID1]** | ID numérica único para el segmento que aparece en los resultados del informe. aparece como ID de fila del segmento. |
| **[!UICONTROL Segment ID2]** | ID numérico único para el segmento que seleccione al ejecutar el informe. Aparece como ID de columna del segmento. |
| **[!UICONTROL Segment Name1]** | Nombre del segmento que aparece en la fila de resultados del informe. |
| **[!UICONTROL Segment Name2]** | Nombre del segmento seleccionado al ejecutar el informe. Aparece en la columna de resultados del informe. |
| **[!UICONTROL Overlap %]** | Para obtener el porcentaje de superposición %, Audience Manager utiliza la fórmula siguiente: Superposición de únicos/(únicos de segmento base + únicos de segmentos solapados - Superposición de únicos) |
| **[!UICONTROL Overlap Uniques]** | El número de visitantes únicos compartidos entre segmentos comparados. |
| **[!UICONTROL Segment Uniques1]** | Número de visitantes únicos en el segmento 1. |
| **[!UICONTROL Segment Uniques2]** | Número de visitantes únicos en el segmento 2. |

>[!MORE_ LIKE_ THIS]
>
>* [Filtrar resultados del informe con los controles deslizantes de datos](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, colores y tamaños utilizados en informes interactivos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explicación de los iconos y las herramientas del informe](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes superpuestos: Actualizar programación y tamaño mínimo de segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestras de datos y tasas de error en informes de Audience Manager seleccionados…](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)