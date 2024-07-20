---
description: Rellene las realizaciones de características para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de una fecha de creación de características.
seo-description: Backfill trait realizations to capture historical audiences and avoid loss of relevant data prior to a trait creation date.
seo-title: Backfill Trait Realizations
title: Realizaciones de rasgos de relleno
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# Realizaciones de rasgos de relleno {#backfill-trait-realizations}

Rellene las realizaciones de características para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de una fecha de creación de características.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] es una funcionalidad Premium que mejora la experiencia del Audience Manager al desbloquear casos de uso adicionales. El relleno requiere una potencia de procesamiento adicional y está disponible para todos los clientes Audience Manager a un coste incremental. Póngase en contacto con el representante de ventas del Adobe para obtener más información.

Cuando crea rasgos a partir de señales no utilizadas, puede elegir rellenar las realizaciones de rasgos durante un período de tiempo específico. [!DNL Audience Manager] captura los datos históricos de las audiencias que cumplen los requisitos para el nuevo rasgo y los almacena en el perfil correspondiente. Puede ver **[!UICONTROL Backfill Options]** en la sección [!UICONTROL Trait Expression] del **[Generador de rasgos](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Puede rellenar las realizaciones de rasgos para rasgos basados en reglas e incorporados.

Así se rellenan las realizaciones de rasgos:

1. Vaya a [!UICONTROL Audience Data > Signals > Search] y ejecute una búsqueda de señales o use el [panel de señales](../../features/data-explorer/data-explorer-signals-dashboard.md) para identificar las señales que se usarán en el nuevo rasgo.
1. Cree un nuevo rasgo basado en las señales deseadas.
1. Use **[!UICONTROL Backfill Options]** en la sección **[!UICONTROL Trait Expression]** para seleccionar el intervalo de tiempo para el cual desea rellenar las realizaciones de rasgos. Los intervalos de relleno predefinidos incluyen 1, 7, 14 y 30 días. También puede elegir un intervalo de fechas personalizado de hasta 30 días.

   ![relleno de rasgo](assets/signals-trait-backfill.png)

1. (Opcional) Haga clic en **[!UICONTROL Estimate Realizations]** en la sección **[!UICONTROL Estimated Trait Realizations]** para ver los valores estimados de [!UICONTROL Unique Trait Realizations] y [!UICONTROL Total Trait Population] de la característica rellenada en los últimos 7 días.

   ![estimadas-realizaciones-de-rasgos](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >El relleno y la estimación de características no están disponibles para características con expresiones que utilizan los siguientes operadores:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`
1. Cree el rasgo.

Una vez que termine de crear el rasgo, verá sus realizaciones rellenadas incluidas en las estadísticas de realización.

Vea el siguiente vídeo para ver un tutorial sobre cómo rellenar rasgos.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Latencia de relleno de rasgos {#trait-backfilling-latency}

Los rasgos recién creados comienzan a capturar audiencias de dos a tres horas después de su creación. Sin embargo, debido al gran volumen de datos que [!DNL Audience Manager] realiza diariamente, la población rellenada no se refleja inmediatamente en los gráficos [!UICONTROL Unique Trait Realizations] y [!UICONTROL Total Trait Population].

El Audience Manager actualiza [!UICONTROL Trait Graph] con la población rellenada en un plazo de 48 horas a partir de la creación de la característica.

## Límite de relleno de rasgos {#trait-backfilling-limit}

[!UICONTROL Data Explorer] le permite rellenar hasta 50 características por mes, y el contador de relleno se restablece el 1 día de cada mes.

>[!NOTE]
>
>La cuota de relleno de rasgos no se arrastra de meses anteriores. Por ejemplo, si este mes rellena 30 características, la cuota de relleno de características del mes siguiente se restablece a 50, no a 70.

## Impacto en los informes {#reporting-impact}

Las realizaciones de características rellenadas se reflejan en las métricas [!UICONTROL Unique Trait Realizations] y [!UICONTROL Total Trait Population], a medida que [!DNL Audience Manager] convierte las señales históricas en realizaciones de características.

Sin embargo, [!UICONTROL Trait Graph], [!UICONTROL General Reports] y [!UICONTROL Trend Reports] no se actualizan de forma retroactiva con las métricas históricas rellenadas antes de la fecha de creación de la característica.
