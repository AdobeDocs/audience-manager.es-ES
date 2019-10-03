---
description: Rellene las realizaciones de características para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de la fecha de creación de características.
seo-description: Rellene las realizaciones de características para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de la fecha de creación de características.
seo-title: Realizaciones de características de relleno
title: Realizaciones de características de relleno
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# Realizaciones de características de relleno {#backfill-trait-realizations}

Rellene las realizaciones de características para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de la fecha de creación de características.

[!UICONTROL Data Explorer Trait Backfill] es una función Premium que mejora la experiencia de Audience Manager al desbloquear casos de uso adicionales. El relleno requiere potencia de procesamiento adicional y está disponible para todos los clientes de Audience Manager a un coste incremental. Póngase en contacto con su representante de ventas de Adobe para obtener más información.

Al crear características a partir de señales no utilizadas, puede elegir rellenar las realizaciones de características durante un período de tiempo específico. [!DNL Audience Manager] captura los datos históricos sobre audiencias que cumplen los requisitos para la nueva característica y los almacena en el perfil correspondiente. Puede ver la **[!UICONTROL Backfill Options]** en la [!UICONTROL Trait Expression] sección del Generador de **[características](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Puede rellenar las realizaciones de características para características basadas en reglas y integradas.

A continuación se muestra cómo rellenar los detalles de características:

1. Vaya a [!UICONTROL Audience Data > Signals > Search] y ejecute una búsqueda de señales o utilice el panel de [señales](../../features/data-explorer/data-explorer-signals-dashboard.md) para identificar las señales que se utilizarán en la nueva característica.
1. Create a new trait based on the desired signals.
1. Use the  in the  section to select the time interval for which you want to backfill trait realizations. **[!UICONTROL Backfill Options]****[!UICONTROL Trait Expression]** Predefined backfill intervals include 1, 7, 14, and 30 days. You can also choose a custom date range of up to 30 days.

   ![trait-backfill](assets/signals-trait-backfill.png)

1. (Optional) Click  in the  section to see the estimated  and  values for the backfilled trait over the last 7 days.**[!UICONTROL Estimate Realizations]****[!UICONTROL Estimated Trait Realizations]**[!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population]

   ![estimate-trait-realizations](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Trait backfilling and estimation are not available for traits with expressions that use the following operators:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Create the trait.

Once you finish creating the trait, you'll see its backfilled realizations included in the realization statistics.

Watch the video below for a video walkthrough of how to backfill traits.

>[!VIDEO](https://video.tv.adobe.com/v/25169/?captions=spa)

## Latencia de rellenado de características {#trait-backfilling-latency}

Las características creadas recientemente empiezan a capturar audiencias dos o tres horas después de la creación. Sin embargo, debido al gran volumen de datos que [!DNL Audience Manager] se obtienen diariamente, la población rellenada no se refleja inmediatamente en los gráficos [!UICONTROL Unique Trait Realizations] y [!UICONTROL Total Trait Population] .

Audience Manager actualiza el [!UICONTROL Trait Graph] con la población rellenada en un plazo de 48 horas desde la creación de características.

## Límite de relleno de rasgos {#trait-backfilling-limit}

[!UICONTROL Data Explorer] le permite rellenar hasta 50 características por mes, con el contador de relleno restablecido el 1 día de cada mes.

>[!NOTE]
>
>La cuota de rellenado de rasgos no se transfiere de meses anteriores. Por ejemplo: si rellena 30 características este mes, la cuota de relleno de características del mes siguiente se restablece a 50, no a 70.

## Impacto en los informes {#reporting-impact}

Las realizaciones de características rellenadas con retroceso se reflejan en las [!UICONTROL Unique Trait Realizations] métricas y [!UICONTROL Total Trait Population] , a medida que [!DNL Audience Manager] convierte las señales históricas en realizaciones de rasgos.

Sin embargo, las métricas [!UICONTROL Trait Graph], [!UICONTROL General Reports]y [!UICONTROL Trend Reports] no se actualizan retroactivamente con métricas históricas rellenadas antes de la fecha de creación de características.