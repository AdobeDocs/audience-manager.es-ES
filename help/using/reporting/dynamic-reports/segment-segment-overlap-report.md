---
description: Devuelve datos sobre cuántos usuarios únicos se comparten entre los segmentos.
seo-description: Devuelve datos sobre cuántos usuarios únicos se comparten entre los segmentos.
seo-title: Informe de solapamiento entre segmentos
solution: Audience Manager
title: Informe de solapamiento entre segmentos
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
translation-type: tm+mt
source-git-commit: a35be513c2cec40257f2df0731eaccbb98e3a000
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 4%

---


# Informe de solapamiento entre segmentos{#segment-to-segment-overlap-report}

Devuelve datos sobre cuántos usuarios únicos se comparten entre los segmentos.

>[!NOTE]
>
>Los informes Superponer del Administrador de Audiencias se ajustan a los principios de RBAC. Solo puede ver segmentos de fuentes de datos a los que tiene acceso en función del grupo [de usuarios de](/help/using/features/administration/administration-overview.md) RBAC al que pertenece.

<!-- 

c_segment_segment_overlap.xml

 -->

## Información general

El [!UICONTROL Segment-to-Segment Overlap] informe puede ayudarle a:

* Identifique los segmentos con superposición alta o baja, según sus necesidades. Las características con alta superposición le proporcionan una audiencia de objetivo, pero menos visitantes únicos. Las características con superposición baja pueden ser útiles para alcanzar un conjunto de visitantes más grande y único.
* Encuentre superposiciones inesperadas y utilice esa información para crear segmentos nuevos de alto rendimiento.

## Informe de muestra

En la siguiente ilustración se proporciona una visión general de alto nivel del [!UICONTROL Segment-to-Segment Overlap] informe.

>[!NOTE]
>
>El [!UICONTROL Segment-to-Segment Overlap] informe devuelve un campo vacío cuando compara el mismo segmento con sí mismo.

![](assets/segment-to-segment-overlap.png)

## Explorar en profundidad puntos de datos individuales

Seleccione un punto individual para los detalles de los datos de vista en una ventana emergente. Las acciones de clic actualizan automáticamente los datos mostrados en el informe.

## Campos de ventana emergente de datos de superposición de segmento a segmento definidos {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

La ventana emergente del [!UICONTROL Segment-to-Segment Overlap] informe contiene las métricas siguientes. Tenga en cuenta que la métrica de valores exclusivos de la tabla representa a los usuarios *en tiempo* real.

| Métrica | Descripción |
|---|---|
| **[!UICONTROL Base Segment ID]** | ID numérica única para el segmento que aparece en los resultados del informe. Aparece como ID de fila para el segmento. |
| **[!UICONTROL Base Segment Name]** | Nombre del segmento que aparece en la fila de resultados del informe. |
| **[!UICONTROL Overlapping Segment ID]** | ID numérica única para el segmento que seleccione al ejecutar el informe. Aparece como el ID de columna del segmento. |
| **[!UICONTROL Overlapping Segment Name]** | Nombre del segmento que seleccione al ejecutar el informe. Aparece en la columna de resultados del informe. |
| **[!UICONTROL Base Segment Uniques]** | El número de visitantes únicos en el segmento base. |
| **[!UICONTROL Base Segment Uniques]** | El número de visitantes únicos en el segmento que se superpone. |
| **[!UICONTROL Overlapping Uniques]** | Número de visitantes únicos compartidos entre segmentos comparados. |
| **[!UICONTROL Overlap %]** | Para obtener el % de superposición, el Administrador de Audiencias utiliza la fórmula siguiente: Únicos superpuestos / (únicos de segmento base + únicos de segmento superpuestos - únicos superpuestos) |



>[!MORELIKETHIS]
>
>* [Filtrar los resultados del informe con los deslizadores de datos](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, colores y tamaños utilizados en informes interactivos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Iconos y herramientas del informe explicados](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes de superposición: Actualizar programación y tamaño mínimo del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestreo de datos y tasas de error en los informes del Administrador de Audiencias seleccionado...](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)