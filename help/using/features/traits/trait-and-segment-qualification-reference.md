---
description: La calificación de rasgos, o realización de rasgos, se trata de forma diferente en el Audience Manager, según el tipo de rasgo. Consulte la siguiente tabla para obtener información detallada sobre la calificación de características.
keywords: Calificación de rasgos, Realización de rasgos, Realizaciones de rasgos únicos, UTR, Población total de rasgos, TTP
seo-description: La calificación de rasgos, o realización de rasgos, se trata de forma diferente en el Audience Manager, según el tipo de rasgo. Consulte la siguiente tabla para obtener información detallada sobre la calificación de características.
seo-title: Referencia de calificación de características
solution: Audience Manager
title: Referencia de calificación de características
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a,85c2d54f-b9d6-4c95-b4b5-466119effc2a,85c2d54f-b9d6-4c95-b4b5-466119effc2a,223f5fc6-c939-4bc6-94a3-5d953abc601a
translation-type: tm+mt
source-git-commit: e13f81df9b0d59cd958f4c2a615c31df00ce2cc5
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 2%

---

# Referencia de cualificación de rasgos y segmentos {#trait-qualification-reference}

La calificación de rasgos, o realización de rasgos, se trata de forma diferente en el Audience Manager, según el tipo de rasgo. Consulte [Clasificación de rasgos por tipo de rasgo](#trait-type) para obtener más información sobre la clasificación de tipos de rasgos.

Además, consulte [Población de segmentos en tiempo real y Población total de segmentos](#real-time-segment) para obtener más información sobre la calificación de segmentos.



## Clasificación de rasgos por tipo de rasgo {#trait-type}

| Tipo de rasgo | Criterios de cualificación |
|---|---|
| Características basadas en reglas | La calificación de características se produce en tiempo real, ya que los usuarios cumplen los requisitos para un rasgo en su navegador. Los usuarios empezarán a cumplir los requisitos para un rasgo basado en reglas aproximadamente 4 horas después de [crear el rasgo](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) en la interfaz de usuario. Los rasgos basados en reglas permiten utilizar controles [actualización y frecuencia](../segments/recency-and-frequency.md) para limitar la frecuencia de los anuncios y otros casos de uso. |
| Características integradas | La calificación de rasgos se produce después de procesar un archivo entrante, es decir, el archivo entrante se [importa en el Audience Manager](../../faq/faq-inbound-data-ingestion.md) y es ahí cuando se produce la calificación de rasgos. Debe esperar aproximadamente 4 horas después de crear un rasgo integrado antes de cargar un archivo entrante para procesarlo. Para los rasgos integrados, el número máximo de cualificaciones para un perfil de usuario es 1. |
| Características algorítmicas | Para los rasgos algorítmicos, el número máximo de clasificaciones para un perfil de usuario es 1. |
| Características de carpeta | Un rasgo de carpeta resume las clasificaciones de rasgos de los rasgos que contiene. Leer [Características de carpeta: Acerca de](about-folder-traits.md) para obtener más información. |
| Rasgos de la Audiencia activa y rasgos sincronizados de la fuente de datos | Un rasgo [!UICONTROL Active Audience] contiene todos los dispositivos que se administran en la cuenta de Audience Manager. [!UICONTROL Data Source Synced Traits] realice un seguimiento de todos los usuarios asociados a una fuente de datos. Obtenga más información sobre [Características de la audiencia activa y los rasgos sincronizados de la fuente de datos](client-activity-synced-audience-traits.md). |

## Realizaciones de rasgos únicas y población total de rasgos {#unique-trait-realizations}

![realización de rasgos únicos](assets/trait-graph.png)

Según el tipo de resultados que desee mostrar en el gráfico (filtrados por [!UICONTROL Device ID] o [!UICONTROL Cross-Device ID]), las métricas tienen diferentes significados:

Al filtrar los resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes anónimos del dispositivo que han agregado el rasgo a su perfil dentro de diferentes intervalos de tiempo.
* [!UICONTROL Total Trait Population] es el número de visitantes anónimos del dispositivo que tienen este rasgo en su perfil.

Al filtrar los resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes autenticados que han agregado el rasgo a su perfil, dentro de diferentes intervalos de tiempo.
* [!UICONTROL Total Trait Population] es el número de visitantes autenticados que tienen este rasgo en su perfil.

Piensen en los números de esta manera. En la imagen anterior, desde la vista [Detalles del rasgo](../../features/traits/trait-details-page.md), 90.173 representa el número de dispositivos activos que visitaron sus propiedades ayer. El [!UICONTROL Total Trait Population] de 55.757 representa la cantidad de usuarios calificados actualmente para este rasgo. La figura [!UICONTROL Total Trait Population] pretende mostrar la cantidad total de usuarios que podrían utilizarse para la segmentación/segmentación. Normalmente, los usuarios seguirán formando parte de un rasgo durante 120 días.

Dado que ejecutamos dos trabajos computacionales diferentes para calcular las dos poblaciones, el [!UICONTROL Total Trait Population] siempre está atrasado con respecto al [!UICONTROL Unique Trait Realizations] en 24 horas. En el gráfico de arriba, se pueden ver unos 90.400 [!UICONTROL Unique Trait Realizations] y un [!UICONTROL Total Trait Population] de unos 90.300 para el 5 de febrero. Los 90 400 perfiles se añaden al [!UICONTROL Total Trait Population] al día siguiente.

Para volver a llevar el punto a casa, si experimentó un pico de 10.000 visitantes en este momento, aparecerían en el [!UICONTROL Unique Trait Realizations] de mañana, pero solo aparecerían 24 horas después en el [!UICONTROL Total Trait Population].

Cualquier cambio en las realizaciones de rasgos se refleja en las poblaciones de segmentos.

## Población de segmentos en tiempo real y población total de segmentos {#real-time-segment}

![realización de rasgos únicos](assets/segment-graph.png)

El [!UICONTROL Real-time Segment Population] cuenta el número de dispositivos que se han clasificado para el segmento seleccionado y que han alcanzado sus propiedades, dentro del intervalo de tiempo seleccionado.

El [!UICONTROL Total Segment Population] cuenta el número de dispositivos que se han clasificado para el segmento seleccionado dentro del intervalo de tiempo seleccionado. El informe [!UICONTROL 1 Day] representa el recuento de población del segmento más actualizado.

Piensen en los números de esta manera. En la imagen anterior, desde la vista [Detalles del segmento](../../features/segments/segment-summary-view.md), 9.993 representa el número de dispositivos activos que visitaron sus propiedades ayer y calificaron para el segmento. El [!UICONTROL Total Segment Population] de 699.532 representa el número total de dispositivos cualificados actualmente para este segmento. La figura [!UICONTROL Total Segment Population] pretende mostrar el número total de dispositivos que se podrían usar para la segmentación/segmentación.

Dado que ejecutamos dos trabajos computacionales diferentes para calcular las dos poblaciones, el [!UICONTROL Total Segment Population] siempre está atrasado con respecto al [!UICONTROL Real-time Segment Population] en 24 horas. En el gráfico de arriba, puede ver un 8,116 [!UICONTROL Real-time Segment Population] y un [!UICONTROL Total Segment Population] de 742,000 para el 2 de febrero. Los 8.116 perfiles se añaden al [!UICONTROL Total Segment Population] al día siguiente.

Para volver a llevar el punto a casa, si experimentó un pico de 10.000 visitantes en este momento, aparecerían en el [!UICONTROL Real-time Segment Population] de mañana, pero solo aparecerían 24 horas después en el [!UICONTROL Total Segment Population].

## Límite de clasificación de rasgos {#trait-qualification-limit}

Imponemos un límite de 150 000 clasificaciones de rasgos para cada perfil de usuario, ya sea un perfil autenticado ([DPUUID](../../reference/ids-in-aam.md)) o un ID de dispositivo ([UUID](../../reference/ids-in-aam.md)). Tenga en cuenta que aunque los DPUUID son únicos para una instancia específica de [!DNL Audience Manager], los UUID se comparten en la plataforma [!DNL Audience Manager]. Para [!UICONTROL UUID]s, imponemos una política de equidad al almacenar las clasificaciones de rasgos. Un algoritmo garantiza que una parte igual del perfil [!UICONTROL UUID] esté disponible para cada instancia de [!DNL Audience Manager].
