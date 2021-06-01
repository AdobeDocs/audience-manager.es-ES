---
description: Rellene las realizaciones de rasgos para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de la fecha de creación de un rasgo.
seo-description: Rellene las realizaciones de rasgos para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de la fecha de creación de un rasgo.
seo-title: Realizaciones de rasgos de relleno
title: Realizaciones de rasgos de relleno
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: 'Explorador de datos '
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 2%

---

# Realizaciones de rasgos de relleno {#backfill-trait-realizations}

Rellene las realizaciones de rasgos para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de la fecha de creación de un rasgo.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] es una funcionalidad premium que mejora la experiencia del Audience Manager al desbloquear casos de uso adicionales. El relleno requiere potencia de procesamiento adicional y está disponible para todos los clientes Audience Manager a un coste incremental. Póngase en contacto con su representante de ventas del Adobe para obtener más información.

Al crear características a partir de señales no utilizadas, puede elegir rellenar las realizaciones de características durante un período de tiempo específico. [!DNL Audience Manager] captura los datos históricos sobre las audiencias que cumplen los requisitos para el nuevo rasgo y las almacena en el perfil correspondiente. Puede ver el **[!UICONTROL Backfill Options]** en la sección [!UICONTROL Trait Expression] del **[Generador de rasgos](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Puede rellenar las realizaciones de características para rasgos basados en reglas e incorporados.

A continuación se muestra cómo rellenar las realizaciones de rasgos:

1. Vaya a [!UICONTROL Audience Data > Signals > Search] y ejecute una búsqueda de señales o utilice el [Panel de señales](../../features/data-explorer/data-explorer-signals-dashboard.md) para identificar las señales que desea utilizar en el nuevo rasgo.
1. Cree un nuevo rasgo basado en las señales deseadas.
1. Utilice **[!UICONTROL Backfill Options]** en la sección **[!UICONTROL Trait Expression]** para seleccionar el intervalo de tiempo para el que desea rellenar las realizaciones de rasgos. Los intervalos de relleno predefinidos incluyen 1, 7, 14 y 30 días. También puede elegir un intervalo de fechas personalizado de hasta 30 días.

   ![relleno de rasgos](assets/signals-trait-backfill.png)

1. (Opcional) Haga clic **[!UICONTROL Estimate Realizations]** en la sección **[!UICONTROL Estimated Trait Realizations]** para ver los valores estimados [!UICONTROL Unique Trait Realizations] y [!UICONTROL Total Trait Population] para el rasgo rellenado en los últimos 7 días.

   ![estimación-realización de rasgos](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >El rellenado y la estimación de rasgos no están disponibles para rasgos con expresiones que utilizan los siguientes operadores:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Cree el rasgo.

Una vez que termine de crear el rasgo, verá sus realizaciones rellenadas incluidas en las estadísticas de realización.

Vea el siguiente vídeo para ver un tutorial en vídeo sobre cómo rellenar los rasgos.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Latencia de relleno de rasgos {#trait-backfilling-latency}

Los rasgos recién creados empiezan a capturar las audiencias de dos a tres horas después de la creación. Sin embargo, debido al gran volumen de datos que [!DNL Audience Manager] realiza diariamente, la población rellenada no se refleja inmediatamente en los gráficos [!UICONTROL Unique Trait Realizations] y [!UICONTROL Total Trait Population].

El Audience Manager actualiza el [!UICONTROL Trait Graph] con la población rellenada en un plazo de 48 horas a partir de la creación de características.

## Límite de relleno de rasgos {#trait-backfilling-limit}

[!UICONTROL Data Explorer] le permite rellenar hasta 50 características al mes, con el contador de relleno restablecido el 1 día de cada mes.

>[!NOTE]
>
>La cuota de rellenado de rasgos no se transfiere desde meses anteriores. Por ejemplo, si rellena 30 rasgos este mes, la cuota de relleno de rasgos para el mes siguiente se restablece a 50, no a 70.

## Impacto en los informes {#reporting-impact}

Las realizaciones de rasgos rellenadas se reflejan en las métricas [!UICONTROL Unique Trait Realizations] y [!UICONTROL Total Trait Population], ya que [!DNL Audience Manager] convierte las señales históricas en realizaciones de rasgos.

Sin embargo, [!UICONTROL Trait Graph], [!UICONTROL General Reports] y [!UICONTROL Trend Reports] no se actualizan retroactivamente con métricas históricas rellenadas antes de la fecha de creación de características.
