---
description: Realización de características de relleno para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de una fecha de creación de características.
seo-description: Realización de características de relleno para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de una fecha de creación de características.
seo-title: Realizaciones de rasgos de relleno
title: Realizaciones de rasgos de relleno
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---


# Realizaciones de rasgos de relleno {#backfill-trait-realizations}

Realización de características de relleno para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de una fecha de creación de características.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] es una función Premium que mejora la experiencia del Audience Manager al desbloquear casos de uso adicionales. El relleno requiere una potencia de procesamiento adicional y está disponible para todos los clientes Audience Manager a un costo incremental. Póngase en contacto con su representante de ventas de Adobe para obtener más información.

Al crear características a partir de señales no utilizadas, puede elegir rellenar las realizaciones de características durante un período de tiempo específico. [!DNL Audience Manager] captura los datos históricos sobre audiencias que cumplen los requisitos para la nueva característica y los almacena en el perfil correspondiente. Puede ver la **[!UICONTROL Backfill Options]** en la [!UICONTROL Trait Expression] sección del Generador de **[características](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Puede rellenar las realizaciones de características para las características basadas en reglas y integradas.

A continuación se muestra cómo rellenar los detalles de características:

1. Vaya a [!UICONTROL Audience Data > Signals > Search] y ejecute una búsqueda de señales o utilice el Panel [de](../../features/data-explorer/data-explorer-signals-dashboard.md) señales para identificar las señales que se utilizarán en la nueva característica.
1. Cree una nueva característica basada en las señales deseadas.
1. Utilice la **[!UICONTROL Backfill Options]** sección **[!UICONTROL Trait Expression]** para seleccionar el intervalo de tiempo para el que desea rellenar las realizaciones de características. Los intervalos de relleno predefinidos incluyen 1, 7, 14 y 30 días. También puede elegir un intervalo de fechas personalizado de hasta 30 días.

   ![relleno de características](assets/signals-trait-backfill.png)

1. (Opcional) Haga clic **[!UICONTROL Estimate Realizations]** en la **[!UICONTROL Estimated Trait Realizations]** sección para ver los valores estimados [!UICONTROL Unique Trait Realizations] y [!UICONTROL Total Trait Population] del rasgo relleno durante los últimos 7 días.

   ![estimación-características-realizaciones](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >La rellenado y estimación de características no están disponibles para características con expresiones que utilizan los siguientes operadores:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Cree la característica.

Una vez que haya terminado de crear la característica, verá las realizaciones rellenadas incluidas en las estadísticas de realización.

Vea el siguiente vídeo para ver cómo rellenar las características.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Latencia de rellenado de características {#trait-backfilling-latency}

inicio de características recién creado que captura audiencias de dos a tres horas después de la creación. Sin embargo, debido al gran volumen de datos que [!DNL Audience Manager] se obtienen diariamente, la población rellenada no se refleja inmediatamente en los gráficos [!UICONTROL Unique Trait Realizations] y [!UICONTROL Total Trait Population] .

Audience Manager actualiza la [!UICONTROL Trait Graph] información con la población rellenada en un plazo de 48 horas desde la creación de características.

## Límite de relleno de rasgos {#trait-backfilling-limit}

[!UICONTROL Data Explorer] le permite rellenar hasta 50 características por mes, con el contador de relleno restablecido el 1 día de cada mes.

>[!NOTE]
>
>La cuota de rellenado de rasgos no se transfiere de meses anteriores. Por ejemplo: si rellena 30 características este mes, la cuota de relleno de características del mes siguiente se restablece a 50, no a 70.

## Impacto en el Sistema de informes {#reporting-impact}

Las realizaciones de características rellenadas con retroceso se reflejan en las [!UICONTROL Unique Trait Realizations] métricas y [!UICONTROL Total Trait Population] , a medida que [!DNL Audience Manager] convierte las señales históricas en realizaciones de rasgos.

Sin embargo, las métricas [!UICONTROL Trait Graph], [!UICONTROL General Reports]y [!UICONTROL Trend Reports] no se actualizan retroactivamente con las métricas históricas rellenadas antes de la fecha de creación de características.