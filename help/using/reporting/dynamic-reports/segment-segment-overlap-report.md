---
description: Devuelve datos sobre cuántos usuarios únicos se comparten entre sus segmentos.
seo-description: Devuelve datos sobre cuántos usuarios únicos se comparten entre sus segmentos.
seo-title: Informe de solapamiento entre segmentos
solution: Audience Manager
title: Informe de solapamiento entre segmentos
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Informes de superposición
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 11%

---

# Informe de solapamiento entre segmentos{#segment-to-segment-overlap-report}

Devuelve datos sobre cuántos usuarios únicos se comparten entre sus segmentos.

>[!NOTE]
>
>Los informes de superposición en el Audience Manager se adhieren a los principios de RBAC. Solo puede ver segmentos de fuentes de datos a los que tenga acceso en función del [Grupo de usuarios de RBAC](/help/using/features/administration/administration-overview.md) al que pertenezca.

<!-- 

c_segment_segment_overlap.xml

 -->

## Información general

El informe [!UICONTROL Segment-to-Segment Overlap] puede ayudarle a:

* Identifique segmentos con superposición alta o baja, según sus necesidades. Los rasgos con superposición alta le proporcionan una audiencia segmentada, pero menos visitantes únicos. Los rasgos con baja superposición pueden resultar útiles para alcanzar un conjunto de visitantes único y más grande.
* Busque superposición inesperada y utilice esa información para generar nuevos segmentos de alto rendimiento.

## Informe de ejemplo

La siguiente ilustración proporciona información general de alto nivel del informe [!UICONTROL Segment-to-Segment Overlap].

>[!NOTE]
>
>El informe [!UICONTROL Segment-to-Segment Overlap] devuelve un campo vacío cuando compara el mismo segmento con sí mismo.

![](assets/segment-to-segment-overlap.png)

## Explorar en profundidad puntos de datos individuales

Seleccione un punto individual para ver los detalles de los datos en una ventana emergente. Las acciones de clic actualizan automáticamente los datos mostrados en el informe.

## Campos emergentes de datos de superposición de segmento a segmento definidos {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

La ventana emergente del informe [!UICONTROL Segment-to-Segment Overlap] contiene las métricas siguientes. Tenga en cuenta que la métrica Únicos de la tabla representa a sus *usuarios en tiempo real*.

| Métrica | Descripción |
|---|---|
| **[!UICONTROL Base Segment ID]** | ID numérica única para el segmento que aparece en los resultados del informe. Aparece como ID de fila para el segmento. |
| **[!UICONTROL Base Segment Name]** | Nombre del segmento que aparece en la fila de resultados del informe. |
| **[!UICONTROL Overlapping Segment ID]** | ID numérica única para el segmento que seleccione al ejecutar el informe. Aparece como el ID de columna del segmento. |
| **[!UICONTROL Overlapping Segment Name]** | Nombre del segmento que seleccione al ejecutar el informe. Aparece en la columna de resultados del informe. |
| **[!UICONTROL Base Segment Uniques]** | El número de visitantes únicos en el segmento base. |
| **[!UICONTROL Base Segment Uniques]** | El número de visitantes únicos en el segmento superpuesto. |
| **[!UICONTROL Overlapping Uniques]** | Número de visitantes únicos compartidos entre segmentos comparados. |
| **[!UICONTROL Overlap %]** | Para obtener el porcentaje de superposición, el Audience Manager utiliza la fórmula siguiente: Únicos superpuestos / (Únicos de segmentos base + Únicos de segmentos superpuestos - Únicos superpuestos) |



>[!MORELIKETHIS]
>
>* [Filtrar los resultados del informe con las barras de desplazamiento de datos](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, colores y tamaños utilizados en informes interactivos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Iconos de informe y herramientas explicadas](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes de superposición: actualizar programación y tamaño mínimo del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestreo de datos y tasas de error en los informes de Audience Manager seleccionado...](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)

