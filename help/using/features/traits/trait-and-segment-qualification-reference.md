---
description: La calificación de características, o la realización de características, se tratan de forma diferente en Audience Manager, según el tipo de característica. Consulte la tabla siguiente para obtener información detallada sobre la clasificación de rasgos.
keywords: Calificación de características, Realización de características, Realizaciones de características únicas, UTR, Población total de características, TTP
seo-description: Trait qualification, or trait realization, is treated differently in Audience Manager, depending on trait type. See the table below for detailed information on trait qualification.
seo-title: Trait Qualification Reference
solution: Audience Manager
title: Referencia de calificación de características
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 1%

---

# Referencia de cualificación de rasgos y segmentos {#trait-qualification-reference}

La calificación de características, o la realización de características, se tratan de forma diferente en Audience Manager, según el tipo de característica. Consulte [Calificación de rasgos por tipo de rasgos](#trait-type) para obtener más información sobre la clasificación de tipos de rasgos.

Además, consulte [Población de segmentos en tiempo real y población total de segmentos](#real-time-segment) para obtener más información sobre la calificación de segmentos.



## Calificación de rasgos por tipo de rasgos {#trait-type}

| Tipo de rasgo | Criterios de calificación |
|---|---|
| Características basadas en reglas | La calificación de características se produce en tiempo real, a medida que los usuarios cumplen los requisitos para una característica en su explorador. Los usuarios comenzarán a cumplir los requisitos para un rasgo basado en reglas aproximadamente 4 horas después de que usted [crear el rasgo](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) en la interfaz de usuario. Los rasgos basados en reglas permiten utilizar [actualización y frecuencia](../segments/recency-and-frequency.md) controles para la restricción de frecuencia de anuncio y otros casos de uso. |
| Características integradas | La calificación de características se produce después de procesar un archivo entrante, es decir, cuando el archivo entrante es [importado en el Audience Manager](../../faq/faq-inbound-data-ingestion.md) y es entonces cuando se produce la clasificación de rasgos. Debe esperar aproximadamente 4 horas después de crear un rasgo incorporado antes de cargar un archivo de entrada para procesarlo. Para los rasgos integrados, el número máximo de clasificaciones para un perfil de usuario es 1. |
| Características algorítmicas | Para rasgos algorítmicos, el número máximo de clasificaciones para un perfil de usuario es 1. |
| Características de carpeta | Un rasgo de carpeta resume las clasificaciones de rasgos de los rasgos que contiene. Leer [Acerca de los rasgos de carpeta](about-folder-traits.md) para obtener más información. |
| Rasgos de la Audiencia activa y rasgos sincronizados de la fuente de datos | Un [!UICONTROL Active Audience] Esta característica contiene todos los dispositivos que se están administrando en la cuenta de Audience Manager. [!UICONTROL Data Source Synced Traits] realizar un seguimiento de todos los usuarios asociados a una fuente de datos. Más información sobre [Rasgos de la audiencia activa y rasgos sincronizados de la fuente de datos](client-activity-synced-audience-traits.md). |

## Realizaciones de rasgos únicos y población de rasgos total {#unique-trait-realizations}

![realización de rasgos únicos](assets/trait-graph.png)

Según el tipo de resultados que desee que muestre el gráfico (filtrado por [!UICONTROL Device ID] o [!UICONTROL Cross-Device ID]), las métricas tienen diferentes significados:

Al filtrar los resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes de su dispositivo anónimo que han añadido el rasgo a su perfil en diferentes intervalos de tiempo.
* [!UICONTROL Total Trait Population] es el número de visitantes de su dispositivo anónimo que tienen este rasgo en su perfil.

Al filtrar los resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes autenticados que han agregado el rasgo a su perfil, en diferentes intervalos de tiempo.
* [!UICONTROL Total Trait Population] es el número de los visitantes autenticados que tienen este rasgo en su perfil.

Piensen en los números de esta manera. En la imagen de arriba, en el [Detalles de rasgos](../../features/traits/trait-details-page.md) ver, 90,173 representa el número de dispositivos activos, que visitaron sus propiedades ayer. El [!UICONTROL Total Trait Population] de 55.757 representa la cantidad de usuarios clasificados actualmente para este rasgo. El [!UICONTROL Total Trait Population] Esta imagen está diseñada para mostrar la cantidad total de usuarios que pueden utilizarse para la segmentación/segmentación. Normalmente, los usuarios seguirán formando parte de un rasgo durante 120 días.

Puesto que ejecutamos dos trabajos de cálculo diferentes para calcular las dos poblaciones, el [!UICONTROL Total Trait Population] siempre va por detrás del [!UICONTROL Unique Trait Realizations] por 24 horas. En el gráfico de arriba, pueden ver alrededor de 90.400 [!UICONTROL Unique Trait Realizations] y una [!UICONTROL Total Trait Population] de unos 90.300 para el 5 de febrero. Los 90.400 perfiles se añaden a la [!UICONTROL Total Trait Population] al día siguiente.

Para volver más lejos, si experimentas un pico de 10 000 visitantes en este momento, aparecerían en la de mañana [!UICONTROL Unique Trait Realizations], pero solo aparecería 24 horas más tarde en el [!UICONTROL Total Trait Population].

Cualquier cambio en las realizaciones de rasgos se refleja en las poblaciones de segmentos.

## Población de segmentos en tiempo real y población total de segmentos {#real-time-segment}

![realización de rasgos únicos](assets/segment-graph.png)

El [!UICONTROL Real-time Segment Population] cuenta el número de dispositivos que se han clasificado para el segmento seleccionado y que han alcanzado sus propiedades, dentro del intervalo de tiempo seleccionado.

El [!UICONTROL Total Segment Population] cuenta el número de dispositivos que se han clasificado para el segmento seleccionado dentro del intervalo de tiempo seleccionado. El [!UICONTROL 1 Day] representa el recuento más actualizado de la población del segmento.

Piensen en los números de esta manera. En la imagen de arriba, en el [Detalles del segmento](../../features/segments/segment-summary-view.md) view, 9993 representa el número de dispositivos activos que visitaron sus propiedades ayer y que cumplen los requisitos para el segmento. El [!UICONTROL Total Segment Population] de 699.532 representa el número total de dispositivos actualmente cualificados para este segmento. El [!UICONTROL Total Segment Population] Esta figura muestra el número total de dispositivos que se pueden utilizar para la segmentación/segmentación.

Puesto que ejecutamos dos trabajos de cálculo diferentes para calcular las dos poblaciones, el [!UICONTROL Total Segment Population] siempre va por detrás del [!UICONTROL Real-time Segment Population] por 24 horas. En el gráfico anterior, se puede ver un 8.116 [!UICONTROL Real-time Segment Population] y una [!UICONTROL Total Segment Population] de 742.000 para el 2 de febrero. Los 8.116 perfiles se añaden al [!UICONTROL Total Segment Population] al día siguiente.

Para volver más lejos, si experimentas un pico de 10 000 visitantes en este momento, aparecerían en la de mañana [!UICONTROL Real-time Segment Population], pero solo aparecería 24 horas más tarde en el [!UICONTROL Total Segment Population].

## Límite de clasificación de rasgos {#trait-qualification-limit}

Aplicamos un límite de 150 000 clasificaciones por cada perfil de usuario, ya sea un perfil autenticado ([DPUUID](../../reference/ids-in-aam.md)) o un ID de dispositivo ([UUID](../../reference/ids-in-aam.md)). Tenga en cuenta que aunque los DPUUID son únicos para una instancia específica de [!DNL Audience Manager], los UUID se comparten en el [!DNL Audience Manager] plataforma. Para [!UICONTROL UUID]Por lo tanto, imponemos una política de equidad al almacenar las clasificaciones de rasgos. Un algoritmo garantiza que una parte equitativa del [!UICONTROL UUID] El perfil de está disponible para cada instancia de [!DNL Audience Manager].
