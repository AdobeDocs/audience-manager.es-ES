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

Información general sobre la función [!UICONTROL Addressable Audience] y los casos de uso.

## ¿Qué es un [!UICONTROL Addressable Audience]? {#addressable-audience-description}

La función [!UICONTROL Addressable Audiences] muestra la superposición entre las audiencias que ve en todas las propiedades donde [!DNL Audience Manager] recopila datos y el destino seleccionado. Para ayudarle a comprender este concepto, eche un vistazo a la siguiente ilustración. La superposición entre cada círculo representa los diferentes tipos de audiencias direccionables.

![](assets/addressableAudienceVenn.png)


| Métrica | Descripción |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] para un  [!UICONTROL Destination] | Recuento de todos los dispositivos que han interactuado con todos los clientes [!DNL Audience Manager] a nivel de plataforma durante el período de retrospectiva del informe y que se pueden comparar con el [!UICONTROL destination] elegido. <br><br>Esta métrica es útil porque muestra: <ul><li>El tamaño del total [!UICONTROL addressable audience] al que [!DNL Audience Manager] puede llegar con un objetivo [!UICONTROL destination] en particular.</li><li>Qué tamaño tiene el grupo de perfiles [!DNL Audience Manager] para una plataforma de objetivo y el tamaño de sus audiencias.</li></ul> |
| [!UICONTROL Customer Total Audience] | Recuento de dispositivos que han realizado una [!UICONTROL rule-based trait] en sus propiedades o una [!UICONTROL onboarded trait] desde los archivos sin conexión durante la ventana retroactiva. |
| [!UICONTROL Addressable Audience Match Rate] | Recuento de superposición de dispositivos que han realizado una [!UICONTROL rule-based trait] o una [!UICONTROL onboarded trait] durante la ventana retroactiva y dispositivos que tienen una sincronización de ID con la [!UICONTROL destination] elegida independientemente del tiempo de sincronización.<br><br>Esta métrica representa los dispositivos que:<ul><li>Se ha realizado un [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante la ventana retroactiva `AND`</li><li>Tenga una sincronización de ID con el [!UICONTROL destination] elegido independientemente del tiempo de sincronización.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷  [!UICONTROL Customer Total Audience] expresado como porcentaje. |
| [!UICONTROL Total Segment Population] | Recuento de todos los dispositivos que fueron miembros de su [!UICONTROL segment] durante el período de retrospectiva del informe. |
| [!UICONTROL Segment Addressable Audience] | El número de usuarios que han pertenecido a [!UICONTROL segment] durante el período de retroceso del informe y que tienen una sincronización de ID activa en el sitio. [!UICONTROL Segments] Puede incluir sus propios datos de origen y datos de terceros y de terceros, a través de  [!UICONTROL traits] los datos adquiridos en el  [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Sugerencia: Cuando se utiliza con el período retrospectivo de 1 día, esta métrica puede ayudarle a comprender el estado actual de su  [!UICONTROL segments]. Esto se debe a que la métrica [!UICONTROL Segment Addressable Audience] representa a los usuarios que permanecieron en [!UICONTROL segment] durante el día anterior. Combine esto con el hecho de que [!DNL Audience Manager] actualiza [!UICONTROL Addressable Audiences] diariamente, combinando esta métrica y el período retrospectivo proporciona la instantánea más actualizada de su [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷  [!UICONTROL Total Segment Population] expresado como porcentaje. |

## [!UICONTROL Addressable Audiences] Interfaz {#addressable-audience-interface}

La función [!UICONTROL Addressable Audience] convierte este concepto abstracto en datos cuantificables. En [!DNL Audience Manager], esta función muestra la superposición de audiencia con visualizaciones de datos que proporcionan información de un vistazo junto con datos numéricos en forma de tabla.

[!UICONTROL Addressable Audiences] en  **[!UICONTROL Audience Data > Destinations]**. Seleccione **[!UICONTROL Integrated Platforms > Device-Based]** para ver las métricas de audiencias direccionables.

![](assets/addressable-audiences-landing.png)

Las tres métricas que puede ver en la página de aterrizaje [!UICONTROL Addressable Audiences] representan:

| Métrica | Descripción |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Esta métrica representa el [!UICONTROL Customer Addressable Audience] (descrito en la tabla anterior) *para los últimos 30 días.* |
| **[!UICONTROL Match Rate]** | Esta métrica representa el [!UICONTROL Addressable Audience Match Rate] (descrito en la tabla anterior) *para los últimos 30 días*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Recuento de todos los dispositivos que han interactuado con todos los clientes [!DNL Audience Manager] en el nivel de plataforma durante el período de retrospectiva del informe y que podrían coincidir con este [!UICONTROL destination]. Consulte [Métricas de nivel de plataforma](/help/using/features/addressable-audiences.md#platform-level-metrics) para obtener más información. |

Haga clic en el nombre de un [!UICONTROL server-to-server destination] para vista de los datos de audiencia direccionables. Tenga en cuenta que esta función solo devuelve datos para [!UICONTROL server-to-server destinations] y el acceso requiere permisos de administrador.

![](assets/addressableAudiences.png)

La revisión de estos datos puede ayudarle con:

* **Previsión y planificación:** [!UICONTROL Segment Addressable Audience] los datos le proporcionan más granularidad en los segmentos que está planeando enviar a un destino para la segmentación y activación de audiencias.

* **Revisiones de rendimiento:** La  [!UICONTROL Addressable Audiences] función también es una herramienta de resolución de problemas. Le permite revisar el rendimiento de la campaña, comprender el alcance de la campaña y realizar comprobaciones cruzadas con socios de objetivo/activación si no ve los resultados esperados.

### Prospecting con datos de terceros e implicaciones para tasas de coincidencia

Antes de comprar datos de terceros para la adquisición de audiencias, los clientes pueden validar la superposición con otros proveedores de datos. Esto puede ayudarle a tomar una decisión informada antes de comprar nuevos datos. La sincronización de ID para datos de terceros adquiridos no solo depende de la superposición de los datos, sino también de las huellas de los proveedores de terceros con el resto de clientes [!DNL Audience Manager]. Su [!DNL Adobe] consultor puede ayudarle a identificar fuentes de datos relevantes adicionales para optimizar las campañas de prospección.

### Usuarios móviles y tasas de coincidencia

Hay huecos al intentar conectar [!DNL Safari] o usuarios de aplicaciones móviles donde no hay [!DNL cookies] terceros presentes. Esto dificulta la sincronización de usuarios con algunos socios, ya que en los registros de envío de medios solo se proporcionan los [!DNL Adobe] ID de terceros sincronizados [!DNL cookies]. Este es un motivo por el que puede ver [tasas de coincidencia bajas](../features/addressable-audiences.md#low-match-rates) para su [!UICONTROL destinations].

## Intervalos de fechas en [!UICONTROL Addressable Audiences] y [!UICONTROL Destinations] {#date-ranges}

Lea las secciones a continuación para ver los intervalos de fechas disponibles y la antigüedad de los datos de cada intervalo en los informes para [!UICONTROL Addressable Audience] o [!UICONTROL Destination].

## Intervalos de fechas y zonas horarias disponibles {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Los informes de [!UICONTROL Addressable Audiences] y [Destinations](../features/destinations/destinations.md) utilizan los mismos intervalos de intervalo de fechas. Las opciones de intervalo de fechas incluyen:

* [!UICONTROL Last 1 Day] (Este intervalo se extiende desde la medianoche hasta la medianoche del período de 24 horas anterior. No es una métrica en tiempo real o actual).
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Todas las fechas e intervalos de fechas se establecen en la zona horaria [!DNL UTC]. Consulte [Husos horarios en Audience Manager](../reference/aam-time-zones.md).

## Intervalos de intervalos de fechas de datos {#date-range-intervals}

Las métricas [!UICONTROL Addressable Audience] y [!UICONTROL Destination] devuelven un recuento de usuarios únicos para el intervalo de tiempo seleccionado. Por ejemplo: un visitante se cuenta sólo una vez, incluso si llega al sitio varias veces. La primera visita es la visita única y se registra. Las visitas subsiguientes devuelven visitas y no se cuentan porque no son únicas.

Los intervalos de fechas contienen datos para el intervalo de tiempo seleccionado o anterior. Además, los datos caducan con cada intervalo de informes a medida que pasa el tiempo. Por ejemplo: supongamos que ve 2 visitantes después de elegir la opción [!UICONTROL Last 30 Days]. En los informes, estos visitantes son:

* *Se* incluirá en los resultados devueltos por intervalos de tiempo más largos (60 días, 90 días y Duración).
* *No* se incluirá en los intervalos más cortos que preceden a la  [!UICONTROL Last 30 Day] opción (Actual, 7 días y 14 días).

Y, el día 31, estos visitantes solo aparecen en los resultados de 60 días, 90 días y [!UICONTROL Lifetime]. Han envejecido a partir del intervalo de 30 días. Los visitantes no caducan en el intervalo [!UICONTROL Lifetime].

## [!UICONTROL Addressable Audiences] Métricas {#addressable-audience-metrics}

Esta sección describe los tipos de métricas proporcionadas por [!UICONTROL Addressable Audiences].

### Métricas de nivel de cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Estas métricas devuelven datos de características realizadas cuando los visitantes llegan a su sitio o cuando envía archivos de datos de entrada a [!DNL Audience Manager]. Estas métricas proporcionan una vista completa del tamaño de audiencia de su cuenta.

| Métrica | Descripción |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Recuento de superposición de dispositivos que han realizado una [!UICONTROL rule-based trait] o una [!UICONTROL onboarded trait] durante la ventana retroactiva y dispositivos que tienen una sincronización de ID con el destino elegido independientemente del tiempo de sincronización.<br><br>Esta métrica representa los dispositivos que:<ul><li>Se ha realizado un [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante la ventana retroactiva `AND`</li><li>Tenga una sincronización de ID con el [!UICONTROL destination] elegido independientemente del tiempo de sincronización.</li></ul> |
| [!UICONTROL Customer Total Audience] | Recuento de dispositivos que han realizado una [!UICONTROL rule-based trait] en sus propiedades o una [!UICONTROL onboarded trait] desde los archivos sin conexión durante la ventana retroactiva. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷  [!UICONTROL Customer Total Audience] expresado como porcentaje. |

### Métricas de coincidencia de nivel de segmento {#segment-level-metrics}

Estas métricas devuelven datos sobre la pertenencia [!UICONTROL segment]. Ayudan a proporcionar una vista más granular y precisa del tamaño de la audiencia para cada uno de sus [!UICONTROL segments].

>[!NOTE]
>
>La forma en que se aplica la ventana retroactiva en el nivel [!UICONTROL segment] es diferente a la del nivel de cliente. Los visitantes pueden llegar al sitio y darse cuenta de un [!UICONTROL trait] hace 10 días, y desde entonces podrían calificar para un [!UICONTROL segment] y dejar el [!UICONTROL segment] hace 2 días. Cuando se aplica la retrospectiva de 7 días, estos visitantes se cuentan en el nivel [!UICONTROL segment] pero no en el nivel del cliente.

| Métrica | Descripción |
|---|---|
| [!UICONTROL Segment Addressable Audience] | El número de usuarios que han pertenecido a [!UICONTROL segment] durante el período de retroceso del informe y que tienen una sincronización de ID activa en el sitio. Los segmentos pueden incluir sus propios datos de origen y datos de terceros y de terceros, a través de [!UICONTROL traits] adquiridos en el [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Sugerencia: Cuando se utiliza con el período retrospectivo de 1 día, esta métrica puede ayudarle a comprender el estado actual de su  [!UICONTROL segments]. Esto se debe a que la métrica [!UICONTROL Segment Addressable Audience] representa a los usuarios que permanecieron en [!UICONTROL segment] durante el día anterior. Combine esto con el hecho de que [!DNL Audience Manager] actualiza [!UICONTROL Addressable Audiences] diariamente, combinando esta métrica y el período retrospectivo proporciona la instantánea más actualizada de su [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Recuento de todos los dispositivos que fueron miembros de su [!UICONTROL segment] durante el período de retrospectiva del informe. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷  [!UICONTROL Total Segment Population] expresado como porcentaje. |

### Métricas de nivel de plataforma {#platform-level-metrics}

Esta métrica devuelve datos sobre actividades recopiladas en todos los clientes [!DNL Audience Manager]. Pueden proporcionar una vista más amplia de la audiencia del cliente en comparación con los [!DNL Audience Manager] clientes agregados.

| Métrica | Descripción |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Recuento de todos los dispositivos que han interactuado con todos los clientes [!DNL Audience Manager] a nivel de plataforma durante el período de retrospectiva del informe y que se pueden comparar con el [!UICONTROL destination] elegido. <br><br>Esta métrica es útil porque muestra:<ul><li>El tamaño del [!UICONTROL total addressable audience] al que [!DNL Audience Manager] puede llegar en un destino de objetivo concreto.</li><li>Qué tamaño tiene el grupo de perfiles [!DNL Audience Manager] para una plataforma de objetivo y el tamaño de sus audiencias.</li></ul> |

## Comparando [!UICONTROL Customer] y [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

No debe comparar las métricas [!UICONTROL Customer Addressable Audience] y [!UICONTROL Segment Addressable Audience] para determinar si una es más significativa que la otra. Son métricas independientes, diferentes e independientes. Como se describe en las definiciones anteriores, cada una de ellas se deriva de diferentes conjuntos de datos. Dado esto, debe evitar extraer conclusiones si una métrica es más grande que la otra. Todo lo que se puede decir al comparar esto es que:

* [!UICONTROL Customer Addressable Audiences] se basa en  [!UICONTROL trait] realizaciones  *para sus propios datos* de origen. Esta métrica proporciona una vista amplia y completa de la integración con un socio de datos.

* [!UICONTROL Segment Addressable Audiences] se basa en las cualificaciones de los segmentos  *para sus propios datos de origen, además de los datos* de terceros y de segundo nivel. Esta métrica proporciona una vista granular y más precisa de su [!UICONTROL addressable audiences] en una plataforma de objetivo.

## Causas de bajas tasas de coincidencia para [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementos comunes responsables de bajas tasas de coincidencia [!UICONTROL Addressable Audience] o discrepancias en los números notificados.

| Causa | Descripción |
|---|---|
| Tráfico móvil | La mayoría de las integraciones [!UICONTROL server-to-server] dependen de procesos de sincronización facilitados por [!DNL cookies] terceros. Sin embargo, los entornos móviles no utilizan [!DNL cookies] de terceros. Como resultado, los números [!UICONTROL Addressable Audiences] pueden parecer bajos en comparación con el tamaño [!UICONTROL segment]. <br><br>A partir de enero de 2018, puede activar audiencias móviles en el mismo  [!DNL Google] y  [!DNL Adobe Advertising Cloud] destinos configurados para  [!UICONTROL cookie-based] audiencias. Aunque esto significa que puede enviar [!UICONTROL segments] con [!DNL cookie] e identificación móvil combinados a sus destinos [!DNL Google] y [!DNL Advertising Cloud], tenga en cuenta que [!UICONTROL Addressable Audiences] sólo muestra la superposición entre [!DNL cookie] ID y destinos. [!DNL Audience Manager] envía el 100 % de las audiencias móviles a  [!UICONTROL destinations], pero las audiencias móviles no se miden por la  [!UICONTROL Addressable Audience] métrica. <br><br>**Nota**: Por ejemplo, tomemos un  [!UICONTROL segment] con una población de 1.000.000 habitantes. Si asigna este [!UICONTROL segment] a un destino [!DNL Google] o [!DNL Adobe Advertising Cloud], puede ver un [!UICONTROL Addressable Audience] de 700.000 dispositivos y un [!UICONTROL Match Rate] del 70%. La membresía de 700.000 consiste en [!DNL cookie] ID que tienen una sincronización de ID con [!UICONTROL destination]. Su [!UICONTROL Addressable Audience] puede, de hecho, ser mucho mayor, porque los ID móviles direccionables no aparecen en esta métrica. |
| [!DNL Safari] Tráfico | [!DNL Safari] bloquea a terceros  [!DNL cookies]. Esto evita que [!DNL Audience Manager] sincronice los ID con [!UICONTROL destination]. Con la introducción de [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), puede esperar que su [!UICONTROL addressable audiences] no incluya [!DNL Safari] usuarios. |
| Impresiones de medios rastreados | Debido a las optimizaciones del servidor de publicidad, las sincronizaciones de ID no se realizan dentro de las etiquetas de publicidad. Los clientes que realizan una gran cantidad de publicidad fuera del sitio no sincronizarán a los usuarios con integraciones de terceros en esos entornos. Además, una gran cantidad de datos de impresión de medios recopilados podría reducir los números [!UICONTROL addressable audience]. |

## Solución de problemas con [!UICONTROL Addressable Audiences] {#troubleshooting}

Además de las tasas de coincidencia de la aparición, también puede utilizar [!UICONTROL Addressable Audiences] como herramienta de solución de problemas.

Por ejemplo: supongamos que envía un segmento a [!UICONTROL destination] y que [!UICONTROL destination] muestra números de sistema de informes bajos. Si se seleccionan los resultados de [!UICONTROL Addressable Audience], se le mostrará si se trata de un problema técnico o sólo de un caso de tasas de coincidencia bajas. Una tasa de coincidencia baja muestra que [!UICONTROL destination] no es tan bueno para los segmentos seleccionados. Sin embargo, una diferencia en los números [!UICONTROL total addressable audience] entre [!DNL Audience Manager] y [!UICONTROL destination] indica un problema técnico de integración, sincronización u otro tipo. En estos casos, póngase en contacto con su administrador de cuentas.
