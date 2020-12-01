---
description: La cualificación de rasgos, o realización de rasgos, se trata de forma diferente en el Audience Manager, según el tipo de rasgo. Consulte la tabla siguiente para obtener información detallada sobre la calificación de rasgos.
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: La cualificación de rasgos, o realización de rasgos, se trata de forma diferente en el Audience Manager, según el tipo de rasgo. Consulte la tabla siguiente para obtener información detallada sobre la calificación de rasgos.
seo-title: Referencia de calificación de características
solution: Audience Manager
title: Referencia de calificación de características
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 2%

---


# Referencia de cualificación de rasgos y segmentos {#trait-qualification-reference}

La cualificación de rasgos, o realización de rasgos, se trata de forma diferente en el Audience Manager, según el tipo de rasgo. Consulte [Calificación de rasgo por tipo de rasgo](#trait-type) para obtener más información sobre la calificación del tipo de rasgo.

Además, consulte [Población de segmentos en tiempo real y Población total de segmentos](#real-time-segment) para obtener más información sobre la calificación de segmentos.



## Calificación de características por tipo de característica {#trait-type}

| Tipo de característica | Criterios de cualificación |
|---|---|
| Características basadas en reglas | La calificación de características se realiza en tiempo real, ya que los usuarios cumplen los requisitos para una característica en su explorador. Los usuarios tendrán un inicio de cumplir los requisitos para una característica basada en reglas aproximadamente 4 horas después de que [cree la característica](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) en la interfaz de usuario. Las características basadas en reglas le permiten utilizar los controles [de actualización y frecuencia](../segments/recency-and-frequency.md) para el límite de frecuencia de publicidad y otros casos de uso. |
| Características integradas | La calificación de características se produce después de procesar un archivo de entrada, es decir, el archivo de entrada se [importa en Audience Manager](../../faq/faq-inbound-data-ingestion.md) y es cuando se produce la calificación de características. Debe esperar aproximadamente 4 horas después de crear una característica integrada antes de cargar un archivo de entrada para su procesamiento. Para las características integradas, el número máximo de cualificaciones para un perfil de usuario es 1. |
| Características algorítmicas | Para las características algorítmicas, el número máximo de cualificaciones para un perfil de usuario es 1. |
| Características de la carpeta | Una característica de carpeta resume las calificaciones de características de las características que contiene. Leer [Características de la carpeta: Acerca de](about-folder-traits.md) para obtener más información. |
| Rasgos de la Audiencia activa y rasgos sincronizados de la fuente de datos | Una característica [!UICONTROL Active Audience] contiene todos los dispositivos que se administran en la cuenta de Audience Manager. [!UICONTROL Data Source Synced Traits] realizar un seguimiento de todos los usuarios asociados a un origen de datos. Obtenga más información sobre [características de Audiencia activa y características sincronizadas con fuentes de datos](client-activity-synced-audience-traits.md). |

## Realizaciones de características únicas y población total de características {#unique-trait-realizations}

![realización de características únicas](assets/trait-graph.png)

Según el tipo de resultados que desee que muestre el gráfico (filtrado por [!UICONTROL Device ID] o [!UICONTROL Cross-Device ID]), las métricas tienen significados diferentes:

Al filtrar los resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes anónimos de dispositivos que han agregado la característica a su perfil dentro de diferentes intervalos de tiempo.
* [!UICONTROL Total Trait Population] es el número de visitantes de dispositivos anónimos que tienen esta característica en su perfil.

Al filtrar los resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes autenticados que han agregado la característica a su perfil, dentro de diferentes intervalos de tiempo.
* [!UICONTROL Total Trait Population] es el número de visitantes autenticados que tienen esta característica en su perfil.

Piensen en los números de esta manera. En la imagen anterior, de la vista [Detalles de características](../../features/traits/trait-details-page.md), 90.173 representa el número de dispositivos activos que visitaron sus propiedades ayer. El [!UICONTROL Total Trait Population] de 55.757 representa la cantidad de usuarios calificados actualmente para esta característica. La figura [!UICONTROL Total Trait Population] está pensada para mostrar la cantidad total de usuarios que podrían utilizarse para segmentación/segmentación. Normalmente, los usuarios permanecerán como parte de una característica durante 120 días.

Debido a que ejecutamos dos trabajos computacionales diferentes para calcular las dos poblaciones, el [!UICONTROL Total Trait Population] siempre está por debajo del [!UICONTROL Unique Trait Realizations] en 24 horas. En el gráfico de arriba, se pueden ver unos 90.400 [!UICONTROL Unique Trait Realizations] y un [!UICONTROL Total Trait Population] de unos 90.300 para el 5 de febrero. Los 90.400 perfiles se agregan al [!UICONTROL Total Trait Population] al día siguiente.

Para llevar más allá el punto a casa, si experimentara un pico de 10.000 visitantes en este momento, aparecerían en el [!UICONTROL Unique Trait Realizations] de mañana, pero sólo aparecerían 24 horas más tarde en el [!UICONTROL Total Trait Population].

Cualquier cambio en la realización de rasgos se refleja en las poblaciones de segmentos.

## Población de segmentos en tiempo real y población total de segmentos {#real-time-segment}

![realización de características únicas](assets/segment-graph.png)

El [!UICONTROL Real-time Segment Population] cuenta el número de dispositivos que se han cualificado para el segmento seleccionado y han alcanzado sus propiedades, dentro del intervalo de tiempo seleccionado.

El [!UICONTROL Total Segment Population] cuenta el número de dispositivos que se han cualificado para el segmento seleccionado dentro del intervalo de tiempo seleccionado. El informe [!UICONTROL 1 Day] representa el recuento de población de segmentos más actualizado.

Piensen en los números de esta manera. En la imagen anterior, desde la vista [Detalles del segmento](../../features/segments/segment-summary-view.md), 9.993 representa el número de dispositivos activos que visitaron sus propiedades ayer y calificaron para el segmento. El [!UICONTROL Total Segment Population] de 699.532 representa el número total de dispositivos cualificados actualmente para este segmento. La figura [!UICONTROL Total Segment Population] está pensada para mostrar el número total de dispositivos que se pueden usar para segmentación/segmentación.

Debido a que ejecutamos dos trabajos computacionales diferentes para calcular las dos poblaciones, el [!UICONTROL Total Segment Population] siempre está por debajo del [!UICONTROL Real-time Segment Population] en 24 horas. En el gráfico de arriba, puede ver un 8.116 [!UICONTROL Real-time Segment Population] y un [!UICONTROL Total Segment Population] de 742.000 para el 2 de febrero. Los 8.116 perfiles se agregan al [!UICONTROL Total Segment Population] al día siguiente.

Para llevar más allá el punto a casa, si experimentara un pico de 10.000 visitantes en este momento, aparecerían en el [!UICONTROL Real-time Segment Population] de mañana, pero sólo aparecerían 24 horas más tarde en el [!UICONTROL Total Segment Population].

## Límite de calificación de características {#trait-qualification-limit}

Imponemos un límite de 150.000 cualificaciones de características para cada perfil de usuario, ya sea un perfil autenticado ([DPUUID](../../reference/ids-in-aam.md)) o un ID de dispositivo ([UUID](../../reference/ids-in-aam.md)). Tenga en cuenta que, aunque los DPUUID son exclusivos de una instancia específica de [!DNL Audience Manager], los UUID se comparten en la plataforma [!DNL Audience Manager]. Para [!UICONTROL UUID]s, imponemos una política de equidad al almacenar las calificaciones de características. Un algoritmo garantiza que una parte igual del perfil [!UICONTROL UUID] esté disponible para cada instancia de [!DNL Audience Manager].

