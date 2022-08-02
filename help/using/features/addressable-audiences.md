---
description: Información general sobre la función Audiencia direccionable y los casos de uso.
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
source-wordcount: '1813'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Una descripción general del [!UICONTROL Addressable Audience] características y casos de uso.

## ¿Qué es un [!UICONTROL Addressable Audience]? {#addressable-audience-description}

La variable [!UICONTROL Addressable Audiences] muestra la superposición entre las audiencias que ve en todas las propiedades donde [!DNL Audience Manager] recopila datos y el destino seleccionado. Para ayudarle a comprender este concepto, consulte la siguiente ilustración. La superposición entre cada círculo representa los diferentes tipos de audiencias a las que se puede dirigir.

![](assets/addressableAudienceVenn.png)


| Métrica | Descripción |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] para un [!UICONTROL Destination] | Recuento de todos los dispositivos que han interactuado con todos [!DNL Audience Manager] clientes en el nivel de plataforma durante el período retrospectivo del informe y que podrían coincidir con el [!UICONTROL destination]. <br><br>Esta métrica es útil porque muestra: <ul><li>El tamaño del total [!UICONTROL addressable audience] that [!DNL Audience Manager] puede alcanzar un objetivo en particular [!UICONTROL destination].</li><li>Qué grande es el [!DNL Audience Manager] grupo de perfiles es para una plataforma de segmentación y el tamaño de sus audiencias.</li></ul> |
| [!UICONTROL Customer Total Audience] | Un recuento de dispositivos que han realizado una [!UICONTROL rule-based trait] en sus propiedades o en un [!UICONTROL onboarded trait] desde los archivos sin conexión durante la ventana retroactiva. |
| [!UICONTROL Customer Addressable Audience] | Recuento de superposición de dispositivos que han realizado una [!UICONTROL rule-based trait] o [!UICONTROL onboarded trait] durante la ventana retrospectiva y los dispositivos que tenemos una sincronización de ID con el [!UICONTROL destination] independientemente del tiempo de sincronización.<br><br>Esta métrica representa los dispositivos que:<ul><li>Se han dado cuenta de que [!UICONTROL rule-based] o [!UICONTROL onboarded trait] durante la ventana retrospectiva `AND`</li><li>Tener una sincronización de ID con el [!UICONTROL destination] independientemente del tiempo de sincronización.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] expresado como porcentaje. |
| [!UICONTROL Total Segment Population] | Un recuento de todos los dispositivos que eran miembros de su [!UICONTROL segment] durante el período retroactivo del informe. |
| [!UICONTROL Segment Addressable Audience] | El número de usuarios que han pertenecido a la variable [!UICONTROL segment] durante el período retrospectivo del informe y tener una sincronización de ID activa en el sitio. [!UICONTROL Segments] puede incluir sus propios datos de origen y de terceros, mediante [!UICONTROL traits] adquirido en el [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Sugerencia: Cuando se utiliza con el período retrospectivo de 1 día, esta métrica puede ayudarle a comprender el estado actual de su [!UICONTROL segments]. Esto se debe a que la variable [!UICONTROL Segment Addressable Audience] representa a los usuarios que permanecieron en un [!UICONTROL segment] durante el día anterior. Combine esto con el hecho de que [!DNL Audience Manager] actualiza [!UICONTROL Addressable Audiences] a diario, la combinación de esta métrica y el período retroactivo proporciona la instantánea más actualizada de su [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] expresado como porcentaje. |

## [!UICONTROL Addressable Audiences] Interfaz {#addressable-audience-interface}

La variable [!UICONTROL Addressable Audience] convierte este concepto abstracto en datos cuantificables. En [!DNL Audience Manager], esta función muestra la superposición de audiencias con visualizaciones de datos que proporcionan información rápida junto con datos numéricos en forma de tabla.

[!UICONTROL Addressable Audiences] se encuentra en **[!UICONTROL Audience Data > Destinations]**. Select **[!UICONTROL Integrated Platforms > Device-Based]** para ver las métricas de audiencias a las que se puede dirigir.

![](assets/addressable-audiences-landing.png)

Las tres métricas que puede ver en la variable [!UICONTROL Addressable Audiences] representación de la página de aterrizaje:

| Métrica | Descripción |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Esta métrica representa la variable [!UICONTROL Customer Addressable Audience] (descrito en el cuadro anterior) *durante los últimos 30 días.* |
| **[!UICONTROL Match Rate]** | Esta métrica representa la variable [!UICONTROL Addressable Audience Match Rate] (descrito en el cuadro anterior) *para los últimos 30 días*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Recuento de todos los dispositivos que han interactuado con todos [!DNL Audience Manager] clientes a nivel de plataforma durante el período retrospectivo del informe y que podrían coincidir con esto [!UICONTROL destination]. Consulte [Métricas de nivel de plataforma](/help/using/features/addressable-audiences.md#platform-level-metrics) para obtener más información. |

Haga clic en el nombre de una [!UICONTROL server-to-server destination] para ver los datos de audiencia a los que se puede dirigir. Tenga en cuenta que esta función devuelve datos para [!UICONTROL server-to-server destinations] solo y acceso requiere permisos de administrador.

![](assets/addressableAudiences.png)

La revisión de estos datos puede ayudarle con:

* **Previsión y planificación:** [!UICONTROL Segment Addressable Audience] los datos le proporcionan más granularidad en los segmentos que planea enviar a un destino para la segmentación y activación de audiencias.

* **Revisiones del rendimiento:** La variable [!UICONTROL Addressable Audiences] también es una herramienta de resolución de problemas. Permite revisar el rendimiento de la campaña, comprender el alcance de la campaña y realizar comprobaciones cruzadas con socios de objetivo/activación si no ve los resultados esperados.

### Prospecting con datos de terceros e implicaciones para tasas de coincidencia

Antes de comprar datos de terceros para la adquisición de audiencias, los clientes pueden validar la superposición con otros proveedores de datos. Esto puede ayudarle a tomar una decisión informada antes de comprar nuevos datos. Las sincronizaciones de ID para datos de terceros adquiridos no solo dependen de la superposición de los datos, sino también de las impresiones de terceros proveedores con el resto [!DNL Audience Manager] clientes. Su [!DNL Adobe] el consultor puede ayudarle a identificar fuentes de datos relevantes adicionales para optimizar las campañas de prospección.

### Usuarios móviles y tasas de coincidencia

Hay huecos al intentar conectar [!DNL Safari] o usuarios de aplicaciones móviles en los que no haya terceros [!DNL cookies] presente. Esto dificulta la sincronización de usuarios con algunos socios porque solo los [!DNL Adobe] ID de terceros sincronizados [!DNL cookies] se proporcionan en los registros de envío de contenido. Esta es la razón por la que puede ver [tasas de coincidencia bajas](../features/addressable-audiences.md#low-match-rates) para su [!UICONTROL destinations].

## Intervalos de fechas en [!UICONTROL Addressable Audiences] y [!UICONTROL Destinations] {#date-ranges}

Lea las secciones siguientes para ver los intervalos de fechas disponibles y cómo envejecen los datos de cada intervalo en los informes para [!UICONTROL Addressable Audience] o [!UICONTROL Destination].

## Intervalos de fechas y zonas horarias disponibles {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Informes para su [!UICONTROL Addressable Audiences] y [Destinos](../features/destinations/destinations.md) utilice los mismos intervalos de intervalo de fechas. Las opciones del intervalo de fechas incluyen:

* [!UICONTROL Last 1 Day] (Este intervalo va de la medianoche a la medianoche del periodo de 24 horas anterior. No es una métrica real ni en tiempo actual).
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Todas las fechas e intervalos de fechas se establecen en la variable [!DNL UTC] zona horaria. Consulte [Husos horarios en el Audience Manager](../reference/aam-time-zones.md).

## Datos en intervalos de intervalos de fechas {#date-range-intervals}

La variable [!UICONTROL Addressable Audience] y [!UICONTROL Destination] las métricas devuelven un recuento de usuarios únicos para el intervalo de tiempo seleccionado. Por ejemplo, un visitante se cuenta solo una vez, incluso si llega al sitio varias veces. La primera visita es la visita única y se registra. Las visitas siguientes devuelven visitas y no se cuentan porque no son únicas.

Los intervalos de fechas contienen datos para el intervalo de tiempo seleccionado o anterior. Además, los datos envejecen de cada intervalo de informe a medida que pasa el tiempo. Por ejemplo, supongamos que ve 2 visitantes después de elegir el [!UICONTROL Last 30 Days] . En los informes, estos visitantes:

* *Será* incluidos en los resultados devueltos por intervalos de tiempo más largos (60 días, 90 días y Duración).
* *No será* incluido en los intervalos más cortos que preceden a la variable [!UICONTROL Last 30 Day] (Actual, 7 días y 14 días).

Y, el día 31, estos visitantes solo aparecen en los 60 días, 90 días, y [!UICONTROL Lifetime] resultados. Han envejecido del intervalo de 30 días. Los visitantes no envejecen del [!UICONTROL Lifetime] intervalo.

## [!UICONTROL Addressable Audiences] Métricas {#addressable-audience-metrics}

Esta sección describe los tipos de métricas que proporciona [!UICONTROL Addressable Audiences].

### Métricas de nivel de cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Estas métricas devuelven datos sobre características realizadas cuando los visitantes llegan al sitio o cuando envía archivos de datos entrantes a [!DNL Audience Manager]. Estas métricas proporcionan una vista completa del tamaño de la audiencia para su cuenta.

| Métrica | Descripción |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Recuento de superposición de dispositivos que han realizado una [!UICONTROL rule-based trait] o [!UICONTROL onboarded trait] durante la ventana retrospectiva y los dispositivos que tienen una sincronización de ID con el destino elegido independientemente del tiempo de sincronización.<br><br>Esta métrica representa los dispositivos que:<ul><li>Se han dado cuenta de que [!UICONTROL rule-based] o [!UICONTROL onboarded trait] durante la ventana retrospectiva `AND`</li><li>Tener una sincronización de ID con el [!UICONTROL destination] independientemente del tiempo de sincronización.</li></ul> |
| [!UICONTROL Customer Total Audience] | Un recuento de dispositivos que han realizado una [!UICONTROL rule-based trait] en sus propiedades o en un [!UICONTROL onboarded trait] desde los archivos sin conexión durante la ventana retroactiva. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] expresado como porcentaje. |

### Métricas de coincidencia de nivel de segmento {#segment-level-metrics}

Estas métricas devuelven datos sobre [!UICONTROL segment] abono. Ayudan a proporcionar una vista más granular y precisa del tamaño de la audiencia para cada uno de sus [!UICONTROL segments].

>[!NOTE]
>
>La forma en que se aplica la ventana retrospectiva en la variable [!UICONTROL segment] es diferente de lo que sucede en el nivel de cliente. Los visitantes pueden llegar al sitio y realizar una [!UICONTROL trait] Hace 10 días, y podían calificar para un [!UICONTROL segment] desde entonces y abandonó el [!UICONTROL segment] Hace 2 días. Cuando se aplica la retrospectiva de 7 días, estos visitantes se cuentan en la variable [!UICONTROL segment] pero no a nivel de cliente.

| Métrica | Descripción |
|---|---|
| [!UICONTROL Segment Addressable Audience] | El número de usuarios que han pertenecido a la variable [!UICONTROL segment] durante el período retrospectivo del informe y tener una sincronización de ID activa en el sitio. Los segmentos pueden incluir sus propios datos de origen y de terceros, a través de [!UICONTROL traits] adquirido en el [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Sugerencia: Cuando se utiliza con el período retrospectivo de 1 día, esta métrica puede ayudarle a comprender el estado actual de su [!UICONTROL segments]. Esto se debe a que la variable [!UICONTROL Segment Addressable Audience] representa a los usuarios que permanecieron en un [!UICONTROL segment] durante el día anterior. Combine esto con el hecho de que [!DNL Audience Manager] actualiza [!UICONTROL Addressable Audiences] a diario, la combinación de esta métrica y el período retroactivo proporciona la instantánea más actualizada de su [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Un recuento de todos los dispositivos que eran miembros de su [!UICONTROL segment] durante el período retroactivo del informe. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] expresado como porcentaje. |

### Métricas de nivel de plataforma {#platform-level-metrics}

Esta métrica devuelve datos sobre las actividades recopiladas en todas las [!DNL Audience Manager] clientes. Pueden proporcionar una visión más amplia de la audiencia del cliente en comparación con la agregada [!DNL Audience Manager] clientes.

| Métrica | Descripción |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Recuento de todos los dispositivos que han interactuado con todos [!DNL Audience Manager] clientes en el nivel de plataforma durante el período retrospectivo del informe y que podrían coincidir con el [!UICONTROL destination]. <br><br>Esta métrica es útil porque muestra:<ul><li>El tamaño de la variable [!UICONTROL total addressable audience] that [!DNL Audience Manager] puede llegar a un destino objetivo determinado.</li><li>Qué grande es el [!DNL Audience Manager] grupo de perfiles es para una plataforma de segmentación y el tamaño de sus audiencias.</li></ul> |

## Comparación [!UICONTROL Customer] y [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

No debería comparar el [!UICONTROL Customer Addressable Audience] y [!UICONTROL Segment Addressable Audience] métricas para determinar si una es más significativa que la otra. Son métricas independientes, diferentes e independientes. Como se describe en las definiciones anteriores, cada una de ellas se deriva de diferentes conjuntos de datos. En este caso, debe evitar sacar conclusiones si una métrica es más grande que la otra. Todo lo que se puede decir al comparar esto es que:

* [!UICONTROL Customer Addressable Audiences] se basa en [!UICONTROL trait] realizaciones *para sus propios datos de origen*. Esta métrica proporciona una vista amplia y completa de su integración con un socio de datos.

* [!UICONTROL Segment Addressable Audiences] se basa en las cualificaciones de los segmentos *para sus propios datos de origen, además de datos de segundo nivel y de terceros*. Esta métrica proporciona una vista granular y más precisa de su [!UICONTROL addressable audiences] en una plataforma de segmentación.

## Causas de tasas de coincidencia bajas para [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementos comunes responsables de la baja [!UICONTROL Addressable Audience] tasas de coincidencia o discrepancias en los números notificados.

| Causa | Descripción |
|---|---|
| Tráfico móvil | Más [!UICONTROL server-to-server] las integraciones se basan en procesos de sincronización facilitados por terceros [!DNL cookies]. Sin embargo, los entornos móviles no utilizan [!DNL cookies]. Como resultado, su [!UICONTROL Addressable Audiences] los números pueden parecer bajos en comparación con [!UICONTROL segment] tamaño. <br><br>A partir de enero de 2018, puede activar audiencias móviles en el mismo [!DNL Google] y [!DNL Adobe Advertising Cloud] destinos configurados para [!UICONTROL cookie-based] audiencias. Aunque esto significa que puede enviar [!UICONTROL segments] con combinación [!DNL cookie] y la pertenencia de ID móvil a su [!DNL Google] y [!DNL Advertising Cloud] destinos, tenga en cuenta que [!UICONTROL Addressable Audiences] solo mostrar la superposición entre [!DNL cookie] ID y destinos. [!DNL Audience Manager] envía el 100 % de las audiencias móviles a [!UICONTROL destinations], pero las audiencias móviles no se miden mediante la variable [!UICONTROL Addressable Audience] métrica. <br><br>**Nota**: Por ejemplo, tome un [!UICONTROL segment] con una población de 1.000.000 habitantes. Si asigna esto [!UICONTROL segment] a [!DNL Google] o [!DNL Adobe Advertising Cloud] destino, es posible que vea una [!UICONTROL Addressable Audience] de 700.000 dispositivos y [!UICONTROL Match Rate] del 70 %. La composición de 700.000 miembros es [!DNL cookie] ID que tienen una sincronización de ID con la variable [!UICONTROL destination]. Su [!UICONTROL Addressable Audience] de hecho, podría ser mucho mayor, ya que los ID móviles a los que se puede dirigir no aparecen en esta métrica. |
| [!DNL Safari] Tráfico | [!DNL Safari] bloquea a terceros [!DNL cookies]. Esto evita que [!DNL Audience Manager] de sincronización de ID con [!UICONTROL destination]. Con la introducción de [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), puede esperar que su [!UICONTROL addressable audiences] no incluir [!DNL Safari] usuarios. |
| Impresiones de medios rastreadas | Debido a las prácticas recomendadas del servidor de publicidad, las sincronizaciones de ID no se realizan dentro de las etiquetas de publicidad. Los clientes que hagan una gran cantidad de publicidad fuera del sitio no sincronizarán a los usuarios con integraciones de terceros en esos entornos. Además, una gran cantidad de datos de impresión de medios recopilados podría reducir [!UICONTROL addressable audience] números. |

## Resolución de problemas con [!UICONTROL Addressable Audiences] {#troubleshooting}

Además de mostrar las tasas de coincidencia, también puede usar [!UICONTROL Addressable Audiences] como herramienta de resolución de problemas.

Por ejemplo, supongamos que envía un segmento a un [!UICONTROL destination] y [!UICONTROL destination] muestra números de informes bajos. Marque la [!UICONTROL Addressable Audience] los resultados le mostrarán si se trata de un problema técnico o solo de un caso de tasas de coincidencia bajas. Una tasa de coincidencia baja muestra su [!UICONTROL destination] no es tan bueno para los segmentos seleccionados. Sin embargo, una diferencia en la variable [!UICONTROL total addressable audience] números entre [!DNL Audience Manager] y [!UICONTROL destination] indica un problema técnico de integración, sincronización u otro tipo. En estos casos, póngase en contacto con su administrador de cuentas.
