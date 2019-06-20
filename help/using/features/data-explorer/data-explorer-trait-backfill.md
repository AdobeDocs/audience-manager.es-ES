---
description: Características de características de relleno para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de una fecha de creación de características.
seo-description: Características de características de relleno para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de una fecha de creación de características.
seo-title: Realización de características de relleno
title: Realización de características de relleno
uuid: 8 b 0 ef 4 e 6-d 16 a -4 d 1 d -94 f 1-b 84 eebffa 9 a 5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Backfill Trait Realizations {#backfill-trait-realizations}

Características de características de relleno para capturar audiencias históricas y evitar la pérdida de datos relevantes antes de una fecha de creación de características.

[!UICONTROL Data Explorer Trait Backfill] es una funcionalidad Premium que mejora la experiencia de Audience Manager al desbloquear casos de uso adicionales. El relleno requiere una potencia de procesamiento adicional y está disponible para todos los clientes de Audience Manager a un coste incremental. Comuníquese con el representante de ventas de Adobe para obtener más información.

Cuando crea características a partir de señales no utilizadas, puede elegir rellenar las características de características en un período de tiempo específico. [!DNL Audience Manager] captura los datos históricos sobre audiencias que califican para el nuevo rasgo y las almacena en el perfil correspondiente. You can see the **[!UICONTROL Backfill Options]** in the [!UICONTROL Trait Expression] section of the **[Trait Builder](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Puede rellenar características de características para características basadas en reglas e integradas.

He aquí cómo rellenar características de características:

1. Go to [!UICONTROL Audience Data > Signals > Search] amd run a Signals Search or use the [Signals Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) to identify the signals to use in the new trait.
1. Cree un nuevo rasgo basado en las señales que desee.
1. Use the **[!UICONTROL Backfill Options]** in the **[!UICONTROL Trait Expression]** section to select the time interval for which you want to backfill trait realizations. Los intervalos de relleno predefinidos incluyen 1, 7, 14 y 30 días. También puede elegir un intervalo de fechas personalizado de hasta 30 días.
   ![](assets/signals-trait-backfill.png)
1. (Optional) Click **[!UICONTROL Estimate Realizations]** in the **[!UICONTROL Estimated Trait Realizations]** section to see the estimated [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] values for the backfilled trait over the last 7 days.
   ![](assets/estimate-trait-realizations.png)
   >[!IMPORTANT]
   >
   >El rellenado y la estimación de características no están disponibles para características con expresiones que usan los siguientes operadores:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Cree la característica.

Una vez que haya terminado de crear la característica, verá las características rellenadas que se incluyen en las estadísticas de realización.

## Trait Backfilling Latency {#trait-backfilling-latency}

Las características recién creadas empiezan a capturar audiencias entre dos y tres horas después de la creación. However, due to the large volume of data that [!DNL Audience Manager] performs on a daily basis, the backfilled population is not immediately reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] graphs.

Audience Manager updates the [!UICONTROL Trait Graph] with the backfilled population within 48 hours from trait creation.

## Trait Backfilling Limit {#trait-backfilling-limit}

[!UICONTROL Data Explorer] permite rellenar hasta 50 características al mes, y el contador de relleno se restablece el 1 día de cada mes.

>[!NOTE]
>
>La cuota de rellenado de características no se transfiere de meses anteriores. Por ejemplo, si rellena 30 características este mes, la cuota de relleno de características del mes siguiente se restablece a 50, no a 70.

## Impact on Reporting {#reporting-impact}

Backfilled trait realizations are reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] metrics, as [!DNL Audience Manager] turns historical signals into trait realizations.

However, the [!UICONTROL Trait Graph], [!UICONTROL General Reports], and [!UICONTROL Trend Reports] are not updated retroactively with historical metrics backfilled before the trait creation date.