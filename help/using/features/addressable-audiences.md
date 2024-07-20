---
description: Información general sobre la función Audiencia direccionable y casos de uso.
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: Audiencias a las que se puede dirigir
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1831'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Información general sobre la característica [!UICONTROL Addressable Audience] y los casos de uso.

## ¿Qué es un [!UICONTROL Addressable Audience]? {#addressable-audience-description}

La característica [!UICONTROL Addressable Audiences] muestra la superposición entre las audiencias que ve en todas las propiedades donde [!DNL Audience Manager] recopila datos y el destino seleccionado. Para ayudarle a comprender este concepto, consulte la siguiente ilustración. La superposición entre cada círculo representa los diferentes tipos de audiencias a las que se puede dirigir.

![](assets/addressableAudienceVenn.png)


| Métrica | Descripción |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] para [!UICONTROL Destination] | Un recuento de todos los dispositivos que han interactuado con todos los [!DNL Audience Manager] clientes a nivel de plataforma durante el período retrospectivo del informe y que podrían coincidir con su [!UICONTROL destination] elegido. <br><br>Esta métrica es útil porque le muestra: <ul><li>El tamaño del total de [!UICONTROL addressable audience] a los que [!DNL Audience Manager] puede llegar en un destino particular [!UICONTROL destination].</li><li>El tamaño del grupo de perfiles [!DNL Audience Manager] para una plataforma de segmentación y el tamaño de sus audiencias.</li></ul> |
| [!UICONTROL Customer Total Audience] | Recuento de dispositivos que han obtenido un [!UICONTROL rule-based trait] en sus propiedades o un [!UICONTROL onboarded trait] de sus archivos sin conexión durante la ventana retrospectiva. |
| [!UICONTROL Customer Addressable Audience] | Recuento de superposición de dispositivos que han detectado un [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante la ventana retrospectiva y dispositivos que tienen una sincronización de ID con el [!UICONTROL destination] elegido, independientemente del tiempo de sincronización.<br><br>Esta métrica representa dispositivos que:<ul><li>Se ha dado cuenta de [!UICONTROL rule-based] o de [!UICONTROL onboarded trait] durante la ventana retrospectiva `AND`</li><li>Tienen una sincronización de ID con el(la) [!UICONTROL destination] elegido(a) independientemente del tiempo de sincronización.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] expresado como porcentaje. |
| [!UICONTROL Total Segment Population] | Un recuento de todos los dispositivos que fueron miembros de su [!UICONTROL segment] durante el período retrospectivo del informe. |
| [!UICONTROL Segment Addressable Audience] | Número de usuarios que han pertenecido a [!UICONTROL segment] durante el período retrospectivo del informe y que tienen una sincronización de ID activa en el sitio. [!UICONTROL Segments] puede incluir sus propios datos de origen y de segundo nivel y de terceros a través de [!UICONTROL traits] adquiridos en el [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Sugerencia: cuando se utiliza con el período retrospectivo de 1 día, esta métrica puede ayudarle a comprender el estado actual de su [!UICONTROL segments]. Esto se debe a que la métrica [!UICONTROL Segment Addressable Audience] representa a los usuarios que permanecieron en un(a) [!UICONTROL segment] durante el día anterior. Combine esto con el hecho de que [!DNL Audience Manager] actualiza [!UICONTROL Addressable Audiences] diariamente. La combinación de esta métrica y este período retrospectivo proporciona la instantánea más actualizada de su [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] expresado como porcentaje. |

## Interfaz de [!UICONTROL Addressable Audiences] {#addressable-audience-interface}

La característica [!UICONTROL Addressable Audience] convierte este concepto abstracto en datos cuantificables. En [!DNL Audience Manager], esta característica muestra la superposición de audiencias con visualizaciones de datos que proporcionan información rápida junto con datos numéricos en forma de tabla.

[!UICONTROL Addressable Audiences] se encuentra en **[!UICONTROL Audience Data > Destinations]**. Seleccione **[!UICONTROL Integrated Platforms > Device-Based]** para ver las métricas de audiencias a las que se puede dirigir.

![](assets/addressable-audiences-landing.png)

Las tres métricas que puede ver en la página de aterrizaje [!UICONTROL Addressable Audiences] representan:

| Métrica | Descripción |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Esta métrica representa [!UICONTROL Customer Addressable Audience] (descrito en la tabla anterior) *durante los últimos 30 días.* |
| **[!UICONTROL Match Rate]** | Esta métrica representa el(la) [!UICONTROL Addressable Audience Match Rate] (descrito(a) en la tabla anterior) *durante los últimos 30 días*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Un recuento de todos los dispositivos que han interactuado con todos los [!DNL Audience Manager] clientes a nivel de plataforma durante el período retrospectivo del informe y que podrían coincidir con este(a) [!UICONTROL destination]. Consulte [Métricas de nivel de plataforma](/help/using/features/addressable-audiences.md#platform-level-metrics) para obtener más información. |

Haga clic en el nombre de un(a) [!UICONTROL server-to-server destination] para ver sus datos de audiencia a la que se puede dirigir. Tenga en cuenta que esta característica solo devuelve datos de [!UICONTROL server-to-server destinations] y el acceso requiere permisos de administrador.

![](assets/addressableAudiences.png)

La revisión de estos datos puede ayudarle con lo siguiente:

* **Previsión y planificación:** Los datos de [!UICONTROL Segment Addressable Audience] le proporcionan una mayor granularidad en los segmentos que planea enviar a un destino para la segmentación y activación de audiencias.

* **Revisiones de rendimiento:** La característica [!UICONTROL Addressable Audiences] también es una herramienta para solucionar problemas. Permite revisar el rendimiento de la campaña, comprender el alcance de la campaña y consultar con los socios de segmentación/activación si no ve los resultados esperados.

### Prospección con datos de terceros e implicaciones para las tasas de coincidencia

Antes de comprar datos de terceros para la adquisición de audiencias, los clientes pueden validar la superposición con otros proveedores de datos. Esto puede ayudarle a tomar una decisión informada antes de comprar nuevos datos. Las sincronizaciones de ID para los datos de terceros comprados no solo dependen de la superposición de los datos, sino también de las huellas de los proveedores de terceros con todos los demás clientes de [!DNL Audience Manager]. Su consultor de [!DNL Adobe] puede ayudarle a identificar fuentes de datos relevantes adicionales para optimizar las campañas de prospección.

### Usuarios móviles y tasas de coincidencia

Hay espacios al intentar conectar [!DNL Safari] o usuarios de aplicaciones móviles donde no hay presentes [!DNL cookies] de terceros. Esto dificulta la sincronización de usuarios con algunos socios, ya que solo se proporcionan esos [!DNL Adobe] ID para [!DNL cookies] de terceros sincronizados en los registros de envío de medios. Esta es la razón por la que podría ver [tasas de coincidencia bajas](../features/addressable-audiences.md#low-match-rates) para su [!UICONTROL destinations].

## Intervalos de fechas en [!UICONTROL Addressable Audiences] y [!UICONTROL Destinations] {#date-ranges}

Lea las secciones siguientes para conocer los intervalos de fechas disponibles y cómo los datos salen de cada intervalo en los informes de un [!UICONTROL Addressable Audience] o [!UICONTROL Destination].

## Intervalos de fechas y zonas horarias disponibles {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Los informes de [!UICONTROL Addressable Audiences] y [Destinos](../features/destinations/destinations.md) usan los mismos intervalos de intervalo de fechas. Las opciones de intervalo de fechas incluyen:

* [!UICONTROL Last 1 Day] (este intervalo se ejecuta desde la medianoche hasta la medianoche del período de 24 horas anterior. No es una métrica en tiempo real o actual).
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Todas las fechas e intervalos de fechas se establecen en la zona horaria [!DNL UTC]. Consulte [Zonas horarias en el Audience Manager](../reference/aam-time-zones.md).

## Datos en intervalos de intervalo de fechas {#date-range-intervals}

Las métricas [!UICONTROL Addressable Audience] y [!UICONTROL Destination] devuelven un recuento de usuarios únicos para el intervalo de tiempo seleccionado. Por ejemplo, un visitante se cuenta solo una vez, incluso si llega al sitio varias veces. La primera visita es la visita única y se registra. Las visitas posteriores son visitas recurrentes y no se cuentan porque no son únicas.

Los intervalos de fechas contienen datos para el intervalo de tiempo seleccionado o una versión anterior. Además, los datos envejecen de cada intervalo de informe a medida que pasa el tiempo. Por ejemplo, supongamos que ve 2 visitantes después de elegir la opción [!UICONTROL Last 30 Days]. En los informes, estos visitantes:

* *Se* incluirá en los resultados devueltos por los intervalos de tiempo más largos (60 días, 90 días y vigencia).
* *No se incluirá* en los intervalos más cortos que preceden a la opción [!UICONTROL Last 30 Day] (Actual, 7 días y 14 días).

Y, el día 31, estos visitantes solo aparecen en los resultados de 60, 90 y [!UICONTROL Lifetime] días. Han envejecido fuera del intervalo de 30 días. Los visitantes no sobrepasan el intervalo de edad de [!UICONTROL Lifetime].

## [!UICONTROL Addressable Audiences] métricas {#addressable-audience-metrics}

En esta sección se describen los tipos de métricas que proporciona [!UICONTROL Addressable Audiences].

### Métricas de nivel de cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Estas métricas devuelven datos de características realizadas cuando los visitantes llegan al sitio o cuando envía archivos de datos de entrada a [!DNL Audience Manager]. Estas métricas proporcionan una vista completa del tamaño de la audiencia de su cuenta.

| Métrica | Descripción |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Recuento de superposición de dispositivos que han detectado un [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante la ventana retrospectiva y dispositivos en los que tenemos una sincronización de ID con el destino elegido independientemente del tiempo de sincronización.<br><br>Esta métrica representa dispositivos que:<ul><li>Se ha dado cuenta de [!UICONTROL rule-based] o de [!UICONTROL onboarded trait] durante la ventana retrospectiva `AND`</li><li>Tienen una sincronización de ID con el(la) [!UICONTROL destination] elegido(a) independientemente del tiempo de sincronización.</li></ul> |
| [!UICONTROL Customer Total Audience] | Recuento de dispositivos que han obtenido un [!UICONTROL rule-based trait] en sus propiedades o un [!UICONTROL onboarded trait] de sus archivos sin conexión durante la ventana retrospectiva. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] expresado como porcentaje. |

### Métricas de coincidencia a nivel de segmento {#segment-level-metrics}

Estas métricas devuelven datos sobre la pertenencia de [!UICONTROL segment]. Ayudan a proporcionar una vista más granular y precisa del tamaño de la audiencia para cada uno de sus [!UICONTROL segments].

>[!NOTE]
>
>La forma en que se aplica la ventana retrospectiva en el nivel [!UICONTROL segment] es diferente de la del nivel de cliente. Los visitantes pueden entrar al sitio y darse cuenta de un [!UICONTROL trait] hace 10 días, y podrían cumplir los requisitos para un [!UICONTROL segment] desde entonces y abandonaron el [!UICONTROL segment] hace 2 días. Cuando se aplique la retrospectiva de 7 días, estos visitantes se contarán en el nivel [!UICONTROL segment], pero no en el nivel de cliente.

| Métrica | Descripción |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Número de usuarios que han pertenecido a [!UICONTROL segment] durante el período retrospectivo del informe y que tienen una sincronización de ID activa en el sitio. Los segmentos pueden incluir sus propios datos de origen y de terceros a través de [!UICONTROL traits] adquiridos en el [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Sugerencia: cuando se utiliza con el período retrospectivo de 1 día, esta métrica puede ayudarle a comprender el estado actual de su [!UICONTROL segments]. Esto se debe a que la métrica [!UICONTROL Segment Addressable Audience] representa a los usuarios que permanecieron en un(a) [!UICONTROL segment] durante el día anterior. Combine esto con el hecho de que [!DNL Audience Manager] actualiza [!UICONTROL Addressable Audiences] diariamente. La combinación de esta métrica y este período retrospectivo proporciona la instantánea más actualizada de su [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Un recuento de todos los dispositivos que fueron miembros de su [!UICONTROL segment] durante el período retrospectivo del informe. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] expresado como porcentaje. |

### Métricas a nivel de plataforma {#platform-level-metrics}

Esta métrica devuelve datos sobre las actividades recopiladas en todos los [!DNL Audience Manager] clientes. Pueden proporcionar una vista más amplia de la audiencia del cliente en comparación con los [!DNL Audience Manager] clientes agregados.

| Métrica | Descripción |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Un recuento de todos los dispositivos que han interactuado con todos los [!DNL Audience Manager] clientes a nivel de plataforma durante el período retrospectivo del informe y que podrían coincidir con su [!UICONTROL destination] elegido. <br><br>Esta métrica es útil porque le muestra:<ul><li>El tamaño de [!UICONTROL total addressable audience] al que [!DNL Audience Manager] puede llegar en un destino de destino en particular.</li><li>El tamaño del grupo de perfiles [!DNL Audience Manager] para una plataforma de segmentación y el tamaño de sus audiencias.</li></ul> |

## Comparando [!UICONTROL Customer] y [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

No debería comparar las métricas [!UICONTROL Customer Addressable Audience] y [!UICONTROL Segment Addressable Audience] para determinar si una es más significativa que la otra. Son métricas independientes, diferentes e independientes. Como se describe en las definiciones anteriores, cada una de ellas se deriva de diferentes conjuntos de datos. Teniendo en cuenta esto, debe evitar extraer conclusiones si una métrica es más grande que la otra. Todo lo que se puede decir al comparar estos es que:

* [!UICONTROL Customer Addressable Audiences] se basa en [!UICONTROL trait] realizaciones *de sus propios datos de origen*. Esta métrica proporciona una vista amplia y completa de su integración con un socio de datos.

* [!UICONTROL Segment Addressable Audiences] se basa en las clasificaciones de segmento *para sus propios datos de origen, además de los datos de segundo nivel y de terceros*. Esta métrica proporciona una vista granular y más precisa de su [!UICONTROL addressable audiences] en una plataforma de segmentación.

## Causas de tasas de coincidencia bajas para [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementos comunes responsables de tasas de coincidencia de [!UICONTROL Addressable Audience] bajas o discrepancias en los números informados.

| Causa | Descripción |
|---|---|
| Tráfico móvil | La mayoría de las integraciones de [!UICONTROL server-to-server] se basan en procesos de sincronización facilitados por [!DNL cookies] de terceros. Sin embargo, los entornos móviles no utilizan [!DNL cookies] de terceros. Como resultado, los números de [!UICONTROL Addressable Audiences] pueden parecer bajos en comparación con el tamaño de [!UICONTROL segment]. <br><br>A partir de enero de 2018, puede activar audiencias móviles en los mismos destinos [!DNL Google] y [!DNL Adobe Advertising Cloud] configurados para audiencias [!UICONTROL cookie-based]. Aunque esto significa que puede enviar [!UICONTROL segments] con la pertenencia combinada de [!DNL cookie] y el ID móvil a sus destinos [!DNL Google] y [!DNL Advertising Cloud], tenga en cuenta que [!UICONTROL Addressable Audiences] solo muestra la superposición entre los ID y los destinos de [!DNL cookie]. [!DNL Audience Manager] envía el 100% de las audiencias móviles a [!UICONTROL destinations], pero las audiencias móviles no se miden con la métrica [!UICONTROL Addressable Audience]. <br><br>**Nota**: Por ejemplo, tome un [!UICONTROL segment] con una población de 1.000.000. Si asigna este(a) [!UICONTROL segment] a un destino [!DNL Google] o [!DNL Adobe Advertising Cloud], podría ver un(a) [!UICONTROL Addressable Audience] de 700.000 dispositivos y un(a) [!UICONTROL Match Rate] de 70%. La pertenencia a 700 000 consta de [!DNL cookie] ID que tienen una sincronización de ID con [!UICONTROL destination]. Es posible que [!UICONTROL Addressable Audience] sea mucho más alto, ya que los identificadores móviles a los que se puede dirigir no aparecen en esta métrica. |
| Tráfico de [!DNL Safari] | [!DNL Safari] bloquea [!DNL cookies] de terceros. Esto evita que [!DNL Audience Manager] sincronice los identificadores con [!UICONTROL destination]. Con la introducción de [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), puede esperar que [!UICONTROL addressable audiences] no incluya a [!DNL Safari] usuarios. |
| Impresiones de medios seguidos | Debido a las prácticas recomendadas del servidor de publicidad, las sincronizaciones de ID no se realizan dentro de las etiquetas de publicidad. Los clientes que realizan una gran cantidad de publicidad fuera del sitio no sincronizan a los usuarios con integraciones de terceros en esos entornos. Además, una gran cantidad de datos de impresiones de medios recopilados podría reducir los números de [!UICONTROL addressable audience]. |

## Solucionando problemas con [!UICONTROL Addressable Audiences] {#troubleshooting}

Además de mostrar las tasas de coincidencia, también puede usar [!UICONTROL Addressable Audiences] como herramienta de solución de problemas.

Por ejemplo, supongamos que envía un segmento a un [!UICONTROL destination] y que [!UICONTROL destination] muestra números bajos en los informes. Comprobar los resultados de [!UICONTROL Addressable Audience] le mostrará si se trata de un problema técnico o simplemente de un caso de tasas de coincidencia bajas. Una tasa de coincidencia baja muestra que [!UICONTROL destination] no es tan bueno para los segmentos seleccionados. Sin embargo, una diferencia en los números de [!UICONTROL total addressable audience] entre [!DNL Audience Manager] y [!UICONTROL destination] indica un problema técnico de integración, sincronización u otro tipo. En estos casos, póngase en contacto con el administrador de cuentas.
