---
description: Características de características de relleno para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de una fecha de creación de características.
seo-description: Características de características de relleno para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de una fecha de creación de características.
seo-title: Realización de características de relleno
title: Realización de características de relleno
uuid: 8 b 0 ef 4 e 6-d 16 a -4 d 1 d -94 f 1-b 84 eebffa 9 a 5
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Realización de características de relleno {#backfill-trait-realizations}

Características de características de relleno para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de una fecha de creación de características.

[!UICONTROL Data Explorer Trait Backfill] es una funcionalidad Premium que mejora la experiencia de Audience Manager al desbloquear casos de uso adicionales. El relleno requiere una potencia de procesamiento adicional y está disponible para todos los clientes de Audience Manager a un coste incremental. Comuníquese con el representante de ventas de Adobe para obtener más información.

Cuando crea características a partir de señales no utilizadas, puede elegir rellenar las características de características en un período de tiempo específico. [!DNL Audience Manager] captura los datos históricos sobre audiencias que califican para el nuevo rasgo y las almacena en el perfil correspondiente. Puede ver la **[!UICONTROL Backfill Options]** sección en [!UICONTROL Trait Expression] el Generador **[de rasgos](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Puede rellenar características de características para características basadas en reglas e integradas.

He aquí cómo rellenar características de características:

1. Vaya a [!UICONTROL Audience Data > Signals > Search] amd ejecutar una búsqueda de señales o utilice el [panel de señales](../../features/data-explorer/data-explorer-signals-dashboard.md) para identificar las señales que se utilizarán en el nuevo rasgo.
1. Cree un nuevo rasgo basado en las señales que desee.
1. Utilice la **[!UICONTROL Backfill Options]** sección de la **[!UICONTROL Trait Expression]** sección para seleccionar el intervalo de tiempo para el que desea rellenar características. Los intervalos de relleno predefinidos incluyen 1, 7, 14 y 30 días. También puede elegir un intervalo de fechas personalizado de hasta 30 días.

   ![trait-back backfill](assets/signals-trait-backfill.png)

1. (Opcional) Haga clic en **[!UICONTROL Estimate Realizations]** la **[!UICONTROL Estimated Trait Realizations]** sección para ver la estimación [!UICONTROL Unique Trait Realizations] y [!UICONTROL Total Trait Population] los valores de la característica rellenada durante los últimos 7 días.

   ![estimaciones-características](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >El rellenado y la estimación de características no están disponibles para características con expresiones que usan los siguientes operadores:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Cree la característica.

Una vez que haya terminado de crear la característica, verá las características rellenadas que se incluyen en las estadísticas de realización.

## Rellenado de relleno de rasgos {#trait-backfilling-latency}

Las características recién creadas empiezan a capturar audiencias entre dos y tres horas después de la creación. Sin embargo, debido al gran volumen de datos [!DNL Audience Manager] que se realiza diariamente, la población rellenada no se refleja inmediatamente en los gráficos y en [!UICONTROL Unique Trait Realizations] los [!UICONTROL Total Trait Population] gráficos.

Audience Manager actualiza [!UICONTROL Trait Graph] la población con relleno en 48 horas a partir de la creación de características.

## Límite de rellenado de características {#trait-backfilling-limit}

[!UICONTROL Data Explorer] permite rellenar hasta 50 características al mes, y el contador de relleno se restablece el 1 día de cada mes.

>[!NOTE]
>
>La cuota de rellenado de características no se transfiere de meses anteriores. Por ejemplo, si rellena 30 características este mes, la cuota de relleno de características del mes siguiente se restablece a 50, no a 70.

## Impacto en los informes {#reporting-impact}

Las características de características rellenadas se reflejan en las métricas [!UICONTROL Unique Trait Realizations] y en [!UICONTROL Total Trait Population] las métricas, ya que [!DNL Audience Manager] transforma señales históricas en características de características.

Sin embargo, no [!UICONTROL Trait Graph][!UICONTROL General Reports]se actualiza [!UICONTROL Trend Reports] retroactivamente con métricas históricas rellenadas antes de la fecha de creación de características.