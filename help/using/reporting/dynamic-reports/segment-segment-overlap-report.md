---
description: Devuelve datos sobre cuántos usuarios únicos se comparten entre sus segmentos.
seo-description: Returns data on how many unique users are shared between your segments.
seo-title: Segment-to-Segment Overlap Report
solution: Audience Manager
title: Informe de solapamiento entre segmentos
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Overlap Reports
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 10%

---

# Informe de solapamiento entre segmentos{#segment-to-segment-overlap-report}

Devuelve datos sobre cuántos usuarios únicos se comparten entre sus segmentos.

>[!NOTE]
>
>Los informes de superposición de Audience Manager se adhieren a los principios de RBAC. Solo puede ver segmentos de fuentes de datos a los que tenga acceso en función de la variable [Grupo de usuarios RBAC](/help/using/features/administration/administration-overview.md) a la que pertenece.

<!-- 

c_segment_segment_overlap.xml

 -->

## Información general

El [!UICONTROL Segment-to-Segment Overlap] Este informe puede ayudarle a lo siguiente:

* Identifique los segmentos con una superposición alta o baja, según sus necesidades. Las características con una alta superposición le proporcionan una audiencia segmentada, pero menos visitantes únicos. Las características con poca superposición pueden resultar útiles para llegar a un conjunto de visitantes único y más grande.
* Encuentre superposiciones inesperadas y utilice esa información para crear segmentos nuevos de alto rendimiento.

## Informe de muestra

La siguiente ilustración proporciona información general de alto nivel sobre [!UICONTROL Segment-to-Segment Overlap] informe.

>[!NOTE]
>
>El [!UICONTROL Segment-to-Segment Overlap] El informe devuelve un campo vacío cuando compara el mismo segmento consigo mismo.

![](assets/segment-to-segment-overlap.png)

## Profundizar en puntos de datos individuales

Seleccione un punto individual para ver los detalles de los datos en una ventana emergente. Las acciones de clic actualizan automáticamente los datos mostrados en el informe.

## Campos emergentes de datos de superposición de segmento a segmento definidos {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

La ventana emergente del [!UICONTROL Segment-to-Segment Overlap] El informe contiene las métricas siguientes. Tenga en cuenta que la métrica exclusivos de la tabla representa su *usuarios en tiempo real*.

| Métrica | Descripción |
|---|---|
| **[!UICONTROL Base Segment ID]** | ID numérico único del segmento que aparece en los resultados del informe. Aparece como ID de fila para el segmento. |
| **[!UICONTROL Base Segment Name]** | Nombre del segmento que aparece en la fila de resultados del informe. |
| **[!UICONTROL Overlapping Segment ID]** | ID numérico único del segmento seleccionado al ejecutar el informe. Aparece como el ID de columna del segmento. |
| **[!UICONTROL Overlapping Segment Name]** | Nombre del segmento que seleccione al ejecutar el informe. Aparece en la columna de resultados del informe. |
| **[!UICONTROL Base Segment Uniques]** | La cantidad de visitantes únicos en su segmento base. |
| **[!UICONTROL Base Segment Uniques]** | La cantidad de visitantes únicos en su segmento superpuesto. |
| **[!UICONTROL Overlapping Uniques]** | El número de visitantes únicos compartidos entre segmentos comparados. |
| **[!UICONTROL Overlap %]** | Para obtener el porcentaje de superposición, Audience Manager utiliza la siguiente fórmula: Uniques de superposición / (Uniques de segmento base + Uniques de segmento superpuestos - Uniques de superposición) |



>[!MORELIKETHIS]
>
>* [Filtrar los resultados del informe con las barras de desplazamiento de datos](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, colores y tamaños utilizados en los informes interactivos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Iconos y herramientas de informes explicados](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes de superposición: actualizar programación y tamaño mínimo del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestreo de datos y tasas de error en los informes de Audience Manager seleccionado...](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)

