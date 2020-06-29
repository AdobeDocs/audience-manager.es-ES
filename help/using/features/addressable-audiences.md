---
description: Información general sobre la función de Audiencia direccionable y los casos de uso.
keywords: DIL
seo-description: Información general sobre la función de Audiencia direccionable y los casos de uso.
seo-title: Audiencias a las que se puede dirigir
solution: Audience Manager
title: Audiencias a las que se puede dirigir
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1824'
ht-degree: 0%

---


# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Información general sobre la función y los casos de uso [!UICONTROL Addressable Audience] .

## What is an [!UICONTROL Addressable Audience]? {#addressable-audience-description}

La [!UICONTROL Addressable Audiences] función muestra la superposición entre las audiencias que ve en todas las propiedades donde [!DNL Audience Manager] recopila datos y el destino seleccionado. Para ayudarle a comprender este concepto, eche un vistazo a la siguiente ilustración. La superposición entre cada círculo representa los diferentes tipos de audiencias direccionables.

![](assets/addressableAudienceVenn.png)


| Métrica | Descripción |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] para un [!UICONTROL Destination] | Recuento de todos los dispositivos que han interactuado con todos [!DNL Audience Manager] los clientes a nivel de plataforma durante el período de retrospectiva del informe y que podrían coincidir con el [!UICONTROL destination]. <br><br>Esta métrica es útil porque muestra: <ul><li>El tamaño del total [!UICONTROL addressable audience] que [!DNL Audience Manager] puede alcanzar un objetivo determinado [!UICONTROL destination].</li><li>Qué tamaño tiene el grupo de [!DNL Audience Manager] perfiles para una plataforma de objetivo y el tamaño de sus audiencias.</li></ul> |
| [!UICONTROL Customer Total Audience] | Recuento de dispositivos que han realizado un [!UICONTROL rule-based trait] registro en sus propiedades o un registro [!UICONTROL onboarded trait] de los archivos sin conexión durante la ventana retroactiva. |
| [!UICONTROL Addressable Audience Match Rate] | Recuento de superposición de dispositivos que han realizado una sincronización de ID [!UICONTROL rule-based trait] o [!UICONTROL onboarded trait] durante la ventana retroactiva y dispositivos con los que se ha realizado la sincronización de ID con el dispositivo seleccionado [!UICONTROL destination] independientemente del tiempo de sincronización.<br><br>Esta métrica representa los dispositivos que:<ul><li>Se ha realizado un [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] evento durante la ventana retroactiva `AND`</li><li>Haga una sincronización de ID con el ID seleccionado [!UICONTROL destination] independientemente del tiempo de sincronización.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] expresado como porcentaje. |
| [!UICONTROL Total Segment Population] | Recuento de todos los dispositivos que fueron miembros del grupo [!UICONTROL segment] durante el período de retrospectiva del informe. |
| [!UICONTROL Segment Addressable Audience] | El número de usuarios que han pertenecido al [!UICONTROL segment] durante el período de retroceso del informe y que tienen una sincronización de ID activa en el sitio. [!UICONTROL Segments] Puede incluir sus propios datos de origen y datos de terceros y de terceros, mediante [!UICONTROL traits] los datos adquiridos en el [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Sugerencia: Cuando se utiliza con el período retrospectivo de 1 día, esta métrica puede ayudarle a comprender el estado actual de su [!UICONTROL segments]. Esto se debe a que la [!UICONTROL Segment Addressable Audience] métrica representa a los usuarios que permanecieron en una [!UICONTROL segment] durante el día anterior. Combinar esto con el hecho de que [!DNL Audience Manager] se actualiza [!UICONTROL Addressable Audiences] diariamente, la combinación de esta métrica y el período retrospectivo proporciona la instantánea más actualizada de su [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] expresado como porcentaje. |

## [!UICONTROL Addressable Audiences] Interfaz {#addressable-audience-interface}

La [!UICONTROL Addressable Audience] característica convierte este concepto abstracto en datos cuantificables. En [!DNL Audience Manager], esta función muestra solapamiento de audiencia con visualizaciones de datos que proporcionan información de un vistazo junto con datos numéricos en forma de tabla.

[!UICONTROL Addressable Audiences] en **[!UICONTROL Audience Data > Destinations]**. Seleccione **[!UICONTROL Integrated Platforms > Device-Based]** para ver las métricas de audiencias direccionables.

![](assets/addressable-audiences-landing.png)

Las tres métricas que puede ver en la [!UICONTROL Addressable Audiences] página de aterrizaje representan:

| Métrica | Descripción |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Esta métrica representa la [!UICONTROL Customer Addressable Audience] (descrita en la tabla anterior) *de los últimos 30 días.* |
| **[!UICONTROL Match Rate]** | Esta métrica representa la [!UICONTROL Addressable Audience Match Rate] (descrita en la tabla anterior) *de los últimos 30 días*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Recuento de todos los dispositivos que han interactuado con todos [!DNL Audience Manager] los clientes a nivel de plataforma durante el período de retrospectiva del informe y que podrían coincidir con esto [!UICONTROL destination]. Consulte Métricas [de nivel de](/help/using/features/addressable-audiences.md#platform-level-metrics) Platform para obtener más información. |

Haga clic en el nombre de un [!UICONTROL server-to-server destination] para vista de los datos de audiencia direccionables. Tenga en cuenta que esta función devuelve datos [!UICONTROL server-to-server destinations] únicamente y el acceso requiere permisos de administrador.

![](assets/addressableAudiences.png)

La revisión de estos datos puede ayudarle con:

* **Previsión y planificación:** [!UICONTROL Segment Addressable Audience] los datos le proporcionan más granularidad en los segmentos que está planeando enviar a un destino para la segmentación de audiencias y la activación.

* **Reseñas del rendimiento:** La [!UICONTROL Addressable Audiences] función también es una herramienta de resolución de problemas. Le permite revisar el rendimiento de la campaña, comprender el alcance de la campaña y realizar comprobaciones cruzadas con socios de objetivo/activación si no ve los resultados esperados.

### Prospecting con datos de terceros e implicaciones para tasas de coincidencia

Antes de comprar datos de terceros para la adquisición de audiencias, los clientes pueden validar la superposición con otros proveedores de datos. Esto puede ayudarle a tomar una decisión informada antes de comprar nuevos datos. La sincronización de ID para los datos de terceros adquiridos no solo depende de la superposición de los datos, sino también de las huellas de los proveedores de terceros con el resto de los [!DNL Audience Manager] clientes. El [!DNL Adobe] consultor puede ayudarle a identificar fuentes de datos relevantes adicionales para optimizar las campañas de prospección.

### Usuarios móviles y tasas de coincidencia

Hay huecos al intentar conectar [!DNL Safari] o a los usuarios de la aplicación móvil en los que no hay ningún [!DNL cookies] tercero. Esto dificulta la sincronización de usuarios con algunos socios, ya que en los registros de envío de medios solo se proporcionan [!DNL Adobe] los ID de terceros sincronizados [!DNL cookies] . Esta es una razón por la que puede ver tasas [de coincidencia](../features/addressable-audiences.md#low-match-rates) bajas para su [!UICONTROL destinations].

## Intervalos de fechas en [!UICONTROL Addressable Audiences] y [!UICONTROL Destinations] {#date-ranges}

Lea las secciones a continuación para ver los intervalos de fechas disponibles y la antigüedad de los datos de cada intervalo en los informes de un intervalo [!UICONTROL Addressable Audience] o [!UICONTROL Destination].

## Intervalos de fechas y zonas horarias disponibles {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Los informes para su [!UICONTROL Addressable Audiences] y [Destinos](../features/destinations/destinations.md) utilizan los mismos intervalos de intervalo de fechas. Las opciones de intervalo de fechas incluyen:

* [!UICONTROL Last 1 Day] (Este intervalo se extiende desde la medianoche hasta la medianoche del período de 24 horas anterior. No es una métrica en tiempo real o actual).
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Todas las fechas y los intervalos de fechas se establecen en la zona [!DNL UTC] horaria. Consulte [Husos horarios en Audience Manager](../reference/aam-time-zones.md).

## Intervalos de intervalos de fechas de datos {#date-range-intervals}

Las métricas [!UICONTROL Addressable Audience] y [!UICONTROL Destination] devuelven un recuento de usuarios únicos para el intervalo de tiempo seleccionado. Por ejemplo: un visitante se cuenta sólo una vez, incluso si llega al sitio varias veces. La primera visita es la visita única y se registra. Las visitas subsiguientes devuelven visitas y no se cuentan porque no son únicas.

Los intervalos de fechas contienen datos para el intervalo de tiempo seleccionado o anterior. Además, los datos caducan con cada intervalo de informes a medida que pasa el tiempo. Por ejemplo, supongamos que ve dos visitantes después de elegir la [!UICONTROL Last 30 Days] opción. En los informes, estos visitantes son:

* *Se incluirá* en los resultados devueltos por intervalos de tiempo más largos (60 días, 90 días y Duración).
* *No se incluirá* en los intervalos más cortos que preceden a la [!UICONTROL Last 30 Day] opción (Actual, 7 días y 14 días).

Y, el día 31, estos visitantes solo aparecen en los 60 días, 90 días, y [!UICONTROL Lifetime] los resultados. Han envejecido a partir del intervalo de 30 días. Los Visitantes no caducan fuera del [!UICONTROL Lifetime] intervalo.

## [!UICONTROL Addressable Audiences] Métricas {#addressable-audience-metrics}

Esta sección describe los tipos de métricas que proporciona [!UICONTROL Addressable Audiences].

### Métricas de nivel de cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Estas métricas devuelven datos de características realizadas cuando los visitantes llegan a su sitio o cuando envía archivos de datos de entrada a [!DNL Audience Manager]. Estas métricas proporcionan una vista completa del tamaño de audiencia de su cuenta.

| Métrica | Descripción |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Recuento de superposición de dispositivos que han realizado una sincronización de ID [!UICONTROL rule-based trait] o [!UICONTROL onboarded trait] durante la ventana retroactiva y dispositivos que tenemos una sincronización de ID con el destino elegido, independientemente del momento de la sincronización.<br><br>Esta métrica representa los dispositivos que:<ul><li>Se ha realizado un [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] evento durante la ventana retroactiva `AND`</li><li>Haga una sincronización de ID con el ID seleccionado [!UICONTROL destination] independientemente del tiempo de sincronización.</li></ul> |
| [!UICONTROL Customer Total Audience] | Recuento de dispositivos que han realizado un [!UICONTROL rule-based trait] registro en sus propiedades o un registro [!UICONTROL onboarded trait] de los archivos sin conexión durante la ventana retroactiva. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] expresado como porcentaje. |

### Métricas de coincidencia de nivel de segmento {#segment-level-metrics}

Estas métricas devuelven datos sobre [!UICONTROL segment] la pertenencia. Ayudan a proporcionar una vista más granular y precisa del tamaño de la audiencia para cada uno de los [!UICONTROL segments]usuarios.

>[!NOTE]
>
>La forma en que se aplica la ventana retroactiva en el [!UICONTROL segment] nivel es diferente a la del cliente. Los Visitantes pueden venir al sitio y darse cuenta hace [!UICONTROL trait] 10 días, y podrían cumplir con los requisitos [!UICONTROL segment] desde entonces y abandonar el sitio hace [!UICONTROL segment] 2 días. Cuando se aplica la retrospectiva de 7 días, estos visitantes se cuentan en el [!UICONTROL segment] nivel pero no en el nivel del cliente.

| Métrica | Descripción |
|---|---|
| [!UICONTROL Segment Addressable Audience] | El número de usuarios que han pertenecido al [!UICONTROL segment] durante el período de retroceso del informe y que tienen una sincronización de ID activa en el sitio. Los segmentos pueden incluir sus propios datos de origen y datos de terceros y de terceros, a través de [!UICONTROL traits] los datos adquiridos en el [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Sugerencia: Cuando se utiliza con el período retrospectivo de 1 día, esta métrica puede ayudarle a comprender el estado actual de su [!UICONTROL segments]. Esto se debe a que la [!UICONTROL Segment Addressable Audience] métrica representa a los usuarios que permanecieron en una [!UICONTROL segment] durante el día anterior. Combinar esto con el hecho de que [!DNL Audience Manager] se actualiza [!UICONTROL Addressable Audiences] diariamente, la combinación de esta métrica y el período retrospectivo proporciona la instantánea más actualizada de su [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Recuento de todos los dispositivos que fueron miembros del grupo [!UICONTROL segment] durante el período de retrospectiva del informe. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] expresado como porcentaje. |

### Métricas de nivel Platform {#platform-level-metrics}

Esta métrica devuelve datos sobre actividades recopiladas en todos los [!DNL Audience Manager] clientes. Pueden proporcionar una vista más amplia de la audiencia del cliente en comparación con los [!DNL Audience Manager] clientes agregados.

| Métrica | Descripción |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Recuento de todos los dispositivos que han interactuado con todos [!DNL Audience Manager] los clientes a nivel de plataforma durante el período de retrospectiva del informe y que podrían coincidir con el [!UICONTROL destination]. <br><br>Esta métrica es útil porque muestra:<ul><li>El tamaño del [!UICONTROL total addressable audience] que [!DNL Audience Manager] puede alcanzar un destino determinado.</li><li>Qué tamaño tiene el grupo de [!DNL Audience Manager] perfiles para una plataforma de objetivo y el tamaño de sus audiencias.</li></ul> |

## Comparación [!UICONTROL Customer] y [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

No debe comparar las métricas [!UICONTROL Customer Addressable Audience] y [!UICONTROL Segment Addressable Audience] para determinar si una es más significativa que la otra. Son métricas independientes, diferentes e independientes. Como se describe en las definiciones anteriores, cada una de ellas se deriva de diferentes conjuntos de datos. Dado esto, debe evitar extraer conclusiones si una métrica es más grande que la otra. Todo lo que se puede decir al comparar esto es que:

* [!UICONTROL Customer Addressable Audiences] se basa en [!UICONTROL trait] la realización *de sus propios datos* de origen. Esta métrica proporciona una vista amplia y completa de la integración con un socio de datos.

* [!UICONTROL Segment Addressable Audiences] se basa en las cualificaciones de los segmentos *para sus propios datos de origen, además de los datos* de terceros y de segundo nivel. Esta métrica proporciona una vista granular y más precisa de su [!UICONTROL addressable audiences] contenido en una plataforma de segmentación.

## Causas de bajas tasas de coincidencia para [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementos comunes responsables de bajas tasas de [!UICONTROL Addressable Audience] coincidencia o discrepancias en los números notificados.

| Causa | Descripción |
|---|---|
| Tráfico móvil | La mayoría de [!UICONTROL server-to-server] las integraciones dependen de procesos de sincronización facilitados por terceros [!DNL cookies]. Sin embargo, los entornos móviles no utilizan terceros [!DNL cookies]. Como resultado, sus [!UICONTROL Addressable Audiences] números pueden parecer bajos en comparación con el [!UICONTROL segment] tamaño. <br><br>A partir de enero de 2018, puede activar audiencias móviles en el mismo [!DNL Google] y [!DNL Adobe Advertising Cloud] destinos configurados para [!UICONTROL cookie-based] audiencias. Aunque esto significa que puede enviar [!UICONTROL segments] con un abono combinado [!DNL cookie] y de ID de móvil a su destino [!DNL Google] y [!DNL Advertising Cloud] , tenga en cuenta que [!UICONTROL Addressable Audiences] solo se muestra la superposición entre [!DNL cookie] ID y destinos. [!DNL Audience Manager] envía el 100 % de las audiencias móviles a [!UICONTROL destinations], pero las audiencias móviles no se miden por la [!UICONTROL Addressable Audience] métrica. <br><br>**Nota **: Por ejemplo, tomemos un[!UICONTROL segment]con una población de 1.000.000 habitantes. Si asigna esto[!UICONTROL segment]a un destino[!DNL Google]o[!DNL Adobe Advertising Cloud], es posible que vea un[!UICONTROL Addressable Audience]de 700.000 dispositivos y un[!UICONTROL Match Rate]de 70%. La membresía de 700.000 consiste en[!DNL cookie]ID que tienen una sincronización de ID con el[!UICONTROL destination]. De hecho,[!UICONTROL Addressable Audience]es posible que sea mucho mayor, ya que los ID móviles direccionables no aparecen en esta métrica. |
| [!DNL Safari] Tráfico | [!DNL Safari] bloquea a terceros [!DNL cookies]. Esto evita [!DNL Audience Manager] sincronizar los ID con los [!UICONTROL destination]. Con la introducción de [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), puede esperar [!UICONTROL addressable audiences] que no incluya a [!DNL Safari] los usuarios. |
| Impresiones de medios rastreados | Debido a las optimizaciones del servidor de publicidad, las sincronizaciones de ID no se realizan dentro de las etiquetas de publicidad. Los clientes que realizan una gran cantidad de publicidad fuera del sitio no sincronizarán a los usuarios con integraciones de terceros en esos entornos. Además, una gran cantidad de datos de impresión de medios recopilados podría reducir [!UICONTROL addressable audience] los números. |

## Resolución de problemas con [!UICONTROL Addressable Audiences] {#troubleshooting}

Además de las tasas de coincidencia de superficie, también puede utilizar [!UICONTROL Addressable Audiences] como herramienta de resolución de problemas.

Por ejemplo: supongamos que envía un segmento a un [!UICONTROL destination] y que [!UICONTROL destination] muestra números de sistema de informes bajos. Si se seleccionan los [!UICONTROL Addressable Audience] resultados, se le mostrará si se trata de un problema técnico o sólo de un caso de tasas de coincidencia bajas. La tasa de coincidencia baja muestra que [!UICONTROL destination] no es tan buena para los segmentos seleccionados. Sin embargo, una diferencia en los [!UICONTROL total addressable audience] números entre [!DNL Audience Manager] y [!UICONTROL destination] indica un problema técnico de integración, sincronización u otro tipo. En estos casos, póngase en contacto con su administrador de cuentas.
