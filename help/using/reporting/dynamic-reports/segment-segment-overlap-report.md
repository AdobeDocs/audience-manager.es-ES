---
description: Devuelve datos sobre cuántos usuarios únicos se comparten entre sus segmentos.
seo-description: Returns data on how many unique users are shared between your segments.
seo-title: Segment-to-Segment Overlap Report
solution: Audience Manager
title: Informe de solapamiento entre segmentos
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Overlap Reports
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
TQID: https://experienceleague.adobe.com/0AE4fjrc4tuDVpIqdqtYbEcS2feeO4hdNwMFf6SVoVU
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 360
ht-degree: 6%

---

# Informe de solapamiento entre segmentos{#segment-to-segment-overlap-report}

Devuelve datos sobre cuántos usuarios únicos se comparten entre sus segmentos.

>[!NOTE]
>
>Los informes de superposición de Audience Manager se adhieren a los principios de RBAC. Solo puede ver segmentos de orígenes de datos a los que tenga acceso en función del [grupo de usuarios RBAC](/help/using/features/administration/administration-overview.md) al que pertenezca.

<!-- 

c_segment_segment_overlap.xml

 -->

## Información general

El informe [!UICONTROL Segment-to-Segment Overlap] puede ayudarle a lo siguiente:

* Identifique los segmentos con una superposición alta o baja, según sus necesidades. Las características con una alta superposición le proporcionan una audiencia segmentada, pero menos visitantes únicos. Las características con poca superposición pueden resultar útiles para llegar a un conjunto de visitantes único y más grande.
* Encuentre superposiciones inesperadas y utilice esa información para crear segmentos nuevos de alto rendimiento.

## Informe de muestra

La siguiente ilustración proporciona información general de alto nivel sobre el informe [!UICONTROL Segment-to-Segment Overlap].

>[!NOTE]
>
>El informe [!UICONTROL Segment-to-Segment Overlap] devuelve un campo vacío cuando compara el mismo segmento consigo mismo.

![](assets/segment-to-segment-overlap.png)

## Profundizar en puntos de datos individuales

Seleccione un punto individual para ver los detalles de los datos en una ventana emergente. Las acciones de clic actualizan automáticamente los datos mostrados en el informe.

## Campos emergentes de datos de superposición de segmento a segmento definidos {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

La ventana emergente del informe [!UICONTROL Segment-to-Segment Overlap] contiene las métricas siguientes. Tenga en cuenta que la métrica exclusivos de la tabla representa a sus *usuarios en tiempo real*.

| Métrica | Descripción |
|---|---|
| **[!UICONTROL Base Segment ID]** | ID numérico único del segmento que aparece en los resultados del informe. Aparece como ID de fila para el segmento. |
| **[!UICONTROL Base Segment Name]** | Nombre del segmento que aparece en la fila de resultados del informe. |
| **[!UICONTROL Overlapping Segment ID]** | ID numérico único del segmento seleccionado al ejecutar el informe. Aparece como el ID de columna del segmento. |
| **[!UICONTROL Overlapping Segment Name]** | Nombre del segmento que seleccione al ejecutar el informe. Aparece en la columna de resultados del informe. |
| **[!UICONTROL Base Segment Uniques]** | La cantidad de visitantes únicos en su segmento base. |
| **[!UICONTROL Base Segment Uniques]** | La cantidad de visitantes únicos en su segmento superpuesto. |
| **[!UICONTROL Overlapping Uniques]** | El número de visitantes únicos compartidos entre segmentos comparados. |
| **[!UICONTROL Overlap %]** | Para obtener el porcentaje de superposición, Audience Manager utiliza la siguiente fórmula: Únicos superpuestos / (Únicos de segmento base + Únicos de segmento superpuestos - Únicos superpuestos) |



>[!MORELIKETHIS]
>
>* [Filtrar los resultados del informe con las barras de desplazamiento de datos](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, colores y tamaños utilizados en los informes interactivos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Iconos y herramientas de informe explicados](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes de superposición: actualizar programación y tamaño mínimo del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestreo de datos y tasas de error en los informes seleccionados de Audience Manager...](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)
