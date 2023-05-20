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
source-wordcount: '1813'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Una descripción general de la [!UICONTROL Addressable Audience] y casos de uso.

## ¿Qué es un? [!UICONTROL Addressable Audience]? {#addressable-audience-description}

El [!UICONTROL Addressable Audiences] Esta función muestra la superposición entre las audiencias que ve en todas las propiedades donde [!DNL Audience Manager] recopila datos y el destino seleccionado. Para ayudarle a comprender este concepto, consulte la siguiente ilustración. La superposición entre cada círculo representa los diferentes tipos de audiencias a las que se puede dirigir.

![](assets/addressableAudienceVenn.png)


| Métrica | Descripción |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] para un [!UICONTROL Destination] | Un recuento de todos los dispositivos que han interactuado con todos los [!DNL Audience Manager] clientes a nivel de plataforma durante el periodo retrospectivo del informe y que podrían coincidir con el elegido [!UICONTROL destination]. <br><br>Esta métrica es útil porque muestra lo siguiente: <ul><li>El tamaño del total [!UICONTROL addressable audience] que [!DNL Audience Manager] puede alcanzar un objetivo en particular [!UICONTROL destination].</li><li>Qué tan grande es el [!DNL Audience Manager] El grupo de perfiles es para una plataforma de segmentación y el tamaño de sus audiencias.</li></ul> |
| [!UICONTROL Customer Total Audience] | Un recuento de dispositivos que han realizado una [!UICONTROL rule-based trait] en sus propiedades o un [!UICONTROL onboarded trait] desde los archivos sin conexión durante la ventana retroactiva. |
| [!UICONTROL Customer Addressable Audience] | Recuento de superposición de dispositivos que han realizado una [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante la ventana retrospectiva y los dispositivos en los que tenemos una sincronización de ID con el elegido [!UICONTROL destination] independientemente del tiempo de sincronización.<br><br>Esta métrica representa dispositivos que:<ul><li>Se han dado cuenta de que [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante la ventana retrospectiva `AND`</li><li>Tienen una sincronización de ID con el elegido [!UICONTROL destination] independientemente del tiempo de sincronización.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] expresado como porcentaje. |
| [!UICONTROL Total Segment Population] | Un recuento de todos los dispositivos que eran miembros de su [!UICONTROL segment] durante el período retrospectivo del informe. |
| [!UICONTROL Segment Addressable Audience] | El número de usuarios que han pertenecido a [!UICONTROL segment] durante el período retrospectivo del informe y tenga una sincronización de ID activa en el sitio. [!UICONTROL Segments] puede incluir sus propios datos de origen y de segundo nivel y de terceros mediante [!UICONTROL traits] adquirido en el [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Sugerencia: Cuando se utiliza con el periodo retrospectivo de 1 día, esta métrica puede ayudarle a comprender el estado actual de su [!UICONTROL segments]. Esto se debe a que [!UICONTROL Segment Addressable Audience] representa a los usuarios que permanecieron en un [!UICONTROL segment] durante el día anterior. Combine esto con el hecho de que [!DNL Audience Manager] actualizaciones [!UICONTROL Addressable Audiences] a diario, la combinación de esta métrica y el período retrospectivo proporciona la instantánea más actualizada de su [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] expresado como porcentaje. |

## [!UICONTROL Addressable Audiences] Interfaz {#addressable-audience-interface}

El [!UICONTROL Addressable Audience] convierte este concepto abstracto en datos cuantificables. Entrada [!DNL Audience Manager]Sin embargo, esta función muestra la superposición de audiencias con visualizaciones de datos que proporcionan información de un vistazo junto con datos numéricos en forma de tabla.

[!UICONTROL Addressable Audiences] se encuentra en **[!UICONTROL Audience Data > Destinations]**. Seleccionar **[!UICONTROL Integrated Platforms > Device-Based]** para ver las métricas de audiencias a las que se puede dirigir.

![](assets/addressable-audiences-landing.png)

Las tres métricas que puede ver en la [!UICONTROL Addressable Audiences] Página de aterrizaje representa:

| Métrica | Descripción |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Esta métrica representa el [!UICONTROL Customer Addressable Audience] (descrito en la tabla anterior) *durante los últimos 30 días.* |
| **[!UICONTROL Match Rate]** | Esta métrica representa el [!UICONTROL Addressable Audience Match Rate] (descrito en la tabla anterior) *durante los últimos 30 días*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Un recuento de todos los dispositivos que han interactuado con todos los [!DNL Audience Manager] clientes a nivel de plataforma durante el período retrospectivo del informe y que podrían coincidir con este [!UICONTROL destination]. Consulte [Métricas a nivel de plataforma](/help/using/features/addressable-audiences.md#platform-level-metrics) para obtener más información. |

Haga clic en el nombre de una [!UICONTROL server-to-server destination] para ver los datos de audiencias a las que se puede dirigir. Tenga en cuenta que esta función devuelve datos para [!UICONTROL server-to-server destinations] solo y el acceso requiere permisos de administrador.

![](assets/addressableAudiences.png)

La revisión de estos datos puede ayudarle con lo siguiente:

* **Previsión y planificación:** [!UICONTROL Segment Addressable Audience] Los datos de le proporcionan una mayor granularidad en los segmentos que planea enviar a un destino para la segmentación y activación de audiencias.

* **Revisiones de rendimiento:** El [!UICONTROL Addressable Audiences] Esta función también es una herramienta para solucionar problemas. Permite revisar el rendimiento de la campaña, comprender el alcance de la campaña y consultar con los socios de segmentación/activación si no ve los resultados esperados.

### Prospección con datos de terceros e implicaciones para las tasas de coincidencia

Antes de comprar datos de terceros para la adquisición de audiencias, los clientes pueden validar la superposición con otros proveedores de datos. Esto puede ayudarle a tomar una decisión informada antes de comprar nuevos datos. La sincronización de ID para los datos de terceros adquiridos no solo se basa en la superposición de los datos, sino también en las huellas de los proveedores de terceros con todas las demás [!DNL Audience Manager] clientes. Su [!DNL Adobe] Un consultor de puede ayudarle a identificar fuentes de datos relevantes adicionales para optimizar las campañas de prospección.

### Usuarios móviles y tasas de coincidencia

Hay huecos al intentar conectarse [!DNL Safari] o usuarios de aplicaciones móviles en los que no haya terceros [!DNL cookies] presente. Esto dificulta la sincronización de usuarios con algunos socios porque solo los [!DNL Adobe] ID de terceros sincronizados [!DNL cookies] se proporcionan en los registros de envío de medios. Esta es una razón por la que podría ver [tasas de coincidencia bajas](../features/addressable-audiences.md#low-match-rates) para su [!UICONTROL destinations].

## Intervalos de fechas en [!UICONTROL Addressable Audiences] y [!UICONTROL Destinations] {#date-ranges}

Lea las secciones siguientes para ver los intervalos de fechas disponibles y cómo salen los datos de cada intervalo en los informes para ver un [!UICONTROL Addressable Audience] o [!UICONTROL Destination].

## Intervalos de fechas y zonas horarias disponibles {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Informes para su [!UICONTROL Addressable Audiences] y [Destinos](../features/destinations/destinations.md) utilice los mismos intervalos de intervalo de fechas. Las opciones de intervalo de fechas incluyen:

* [!UICONTROL Last 1 Day] (Este intervalo va de la medianoche a la medianoche del período de 24 horas anterior. No es una métrica en tiempo real o actual).
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Todas las fechas e intervalos de fechas se establecen en la variable [!DNL UTC] zona horaria. Consulte [Husos horarios en Audience Manager](../reference/aam-time-zones.md).

## Datos en intervalos de intervalo de fechas {#date-range-intervals}

El [!UICONTROL Addressable Audience] y [!UICONTROL Destination] las métricas devuelven un recuento de usuarios únicos para el intervalo de tiempo seleccionado. Por ejemplo, un visitante se cuenta solo una vez, incluso si llega al sitio varias veces. La primera visita es la visita única y se registra. Las visitas posteriores son visitas recurrentes y no se cuentan porque no son únicas.

Los intervalos de fechas contienen datos para el intervalo de tiempo seleccionado o una versión anterior. Además, los datos envejecen de cada intervalo de informe a medida que pasa el tiempo. Por ejemplo, supongamos que ve 2 visitantes después de elegir la variable [!UICONTROL Last 30 Days] opción. En los informes, estos visitantes:

* *Será* se incluye en los resultados devueltos por los intervalos de tiempo más largos (60 días, 90 días y Lifetime).
* *No se eliminará* incluido en los intervalos más cortos que preceden al [!UICONTROL Last 30 Day] (Actual, 7 días y 14 días).

Y, en el día 31, estos visitantes solo aparecen en los 60 días, 90 días y [!UICONTROL Lifetime] resultados. Han envejecido fuera del intervalo de 30 días. Los visitantes no envejecen fuera del [!UICONTROL Lifetime] intervalo.

## [!UICONTROL Addressable Audiences] Métricas {#addressable-audience-metrics}

En esta sección se describen los tipos de métricas que proporciona [!UICONTROL Addressable Audiences].

### Métricas de nivel de cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Estas métricas devuelven datos de características realizadas cuando los visitantes llegan al sitio o cuando envía archivos de datos de entrada a [!DNL Audience Manager]. Estas métricas proporcionan una vista completa del tamaño de la audiencia de su cuenta.

| Métrica | Descripción |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Recuento de superposición de dispositivos que han realizado una [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante la ventana retrospectiva y los dispositivos en los que tenemos una sincronización de ID con el destino elegido independientemente del tiempo de sincronización.<br><br>Esta métrica representa dispositivos que:<ul><li>Se han dado cuenta de que [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante la ventana retrospectiva `AND`</li><li>Tienen una sincronización de ID con el elegido [!UICONTROL destination] independientemente del tiempo de sincronización.</li></ul> |
| [!UICONTROL Customer Total Audience] | Un recuento de dispositivos que han realizado una [!UICONTROL rule-based trait] en sus propiedades o un [!UICONTROL onboarded trait] desde los archivos sin conexión durante la ventana retroactiva. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] expresado como porcentaje. |

### Métricas de coincidencia a nivel de segmento {#segment-level-metrics}

Estas métricas devuelven datos sobre [!UICONTROL segment] abono. Ayudan a proporcionar una vista más granular y precisa del tamaño de la audiencia para cada uno de sus [!UICONTROL segments].

>[!NOTE]
>
>La forma en que se aplica la ventana retrospectiva en la [!UICONTROL segment] es diferente de la del nivel de cliente. Los visitantes pueden llegar al sitio y darse cuenta de que [!UICONTROL trait] Hace 10 días, y podrían calificar para una [!UICONTROL segment] desde entonces y abandonó el [!UICONTROL segment] Hace 2 días. Cuando se aplica la retrospectiva de 7 días, estos visitantes se contarán en la [!UICONTROL segment] nivel de cliente, pero no en el nivel de cliente.

| Métrica | Descripción |
|---|---|
| [!UICONTROL Segment Addressable Audience] | El número de usuarios que han pertenecido a [!UICONTROL segment] durante el período retrospectivo del informe y tenga una sincronización de ID activa en el sitio. Los segmentos pueden incluir sus propios datos de origen y de terceros, a través de [!UICONTROL traits] adquirido en el [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Sugerencia: Cuando se utiliza con el periodo retrospectivo de 1 día, esta métrica puede ayudarle a comprender el estado actual de su [!UICONTROL segments]. Esto se debe a que [!UICONTROL Segment Addressable Audience] representa a los usuarios que permanecieron en un [!UICONTROL segment] durante el día anterior. Combine esto con el hecho de que [!DNL Audience Manager] actualizaciones [!UICONTROL Addressable Audiences] a diario, la combinación de esta métrica y el período retrospectivo proporciona la instantánea más actualizada de su [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Un recuento de todos los dispositivos que eran miembros de su [!UICONTROL segment] durante el período retrospectivo del informe. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] expresado como porcentaje. |

### Métricas a nivel de plataforma {#platform-level-metrics}

Esta métrica devuelve datos sobre las actividades recopiladas en todas las [!DNL Audience Manager] clientes. Pueden proporcionar una vista más amplia de la audiencia del cliente en comparación con la audiencia acumulada [!DNL Audience Manager] clientes.

| Métrica | Descripción |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Un recuento de todos los dispositivos que han interactuado con todos los [!DNL Audience Manager] clientes a nivel de plataforma durante el periodo retrospectivo del informe y que podrían coincidir con el elegido [!UICONTROL destination]. <br><br>Esta métrica es útil porque muestra lo siguiente:<ul><li>El tamaño de la [!UICONTROL total addressable audience] que [!DNL Audience Manager] puede acceder a un destino de destino concreto.</li><li>Qué tan grande es el [!DNL Audience Manager] El grupo de perfiles es para una plataforma de segmentación y el tamaño de sus audiencias.</li></ul> |

## Comparación [!UICONTROL Customer] y [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

No debería comparar el [!UICONTROL Customer Addressable Audience] y [!UICONTROL Segment Addressable Audience] métricas para determinar si una es más significativa que la otra. Son métricas independientes, diferentes e independientes. Como se describe en las definiciones anteriores, cada una de ellas se deriva de diferentes conjuntos de datos. Teniendo en cuenta esto, debe evitar extraer conclusiones si una métrica es más grande que la otra. Todo lo que se puede decir al comparar estos es que:

* [!UICONTROL Customer Addressable Audiences] se basa en [!UICONTROL trait] realizaciones *para sus propios datos de origen*. Esta métrica proporciona una vista amplia y completa de su integración con un socio de datos.

* [!UICONTROL Segment Addressable Audiences] se basa en las cualificaciones del segmento *para sus propios datos de origen, además de los datos de segundo nivel y de terceros*. Esta métrica proporciona una vista granular y más precisa de su [!UICONTROL addressable audiences] en una plataforma de segmentación.

## Causas de tasas de coincidencia bajas para [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementos comunes responsables de las bajas [!UICONTROL Addressable Audience] tasas de coincidencia o discrepancias en los números del informe.

| Causa | Descripción |
|---|---|
| Tráfico móvil | Más [!UICONTROL server-to-server] las integraciones se basan en procesos de sincronización facilitados por terceros [!DNL cookies]. Sin embargo, los entornos móviles no utilizan entornos de terceros [!DNL cookies]. Como resultado, su [!UICONTROL Addressable Audiences] los números pueden parecer bajos en comparación con [!UICONTROL segment] tamaño. <br><br>A partir de enero de 2018, puede activar audiencias móviles en el mismo [!DNL Google] y [!DNL Adobe Advertising Cloud] destinos configurados para [!UICONTROL cookie-based] audiencias. Aunque esto significa que puede enviar [!UICONTROL segments] con combinados [!DNL cookie] y la pertenencia al ID móvil a su [!DNL Google] y [!DNL Advertising Cloud] destinos, tenga en cuenta que [!UICONTROL Addressable Audiences] mostrar solo la superposición entre [!DNL cookie] ID y destinos. [!DNL Audience Manager] envía el 100 % de las audiencias móviles a [!UICONTROL destinations], pero las audiencias móviles no se miden con la variable [!UICONTROL Addressable Audience] métrica. <br><br>**Nota**: Por ejemplo, tome una [!UICONTROL segment] con una población de 1.000.000. Si asigna esto [!UICONTROL segment] a un [!DNL Google] o [!DNL Adobe Advertising Cloud] destino, es posible que vea un [!UICONTROL Addressable Audience] de 700.000 dispositivos y una [!UICONTROL Match Rate] del 70%. La membresía de 700.000 miembros consta de [!DNL cookie] ID que tienen una sincronización de ID con [!UICONTROL destination]. Su [!UICONTROL Addressable Audience] puede, de hecho, ser mucho mayor, ya que los ID móviles a los que se puede dirigir no aparecen en esta métrica. |
| [!DNL Safari] Tráfico | [!DNL Safari] bloquea a terceros [!DNL cookies]. Esto evita [!DNL Audience Manager] de sincronización de ID con [!UICONTROL destination]. Con la introducción de [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), ya puede esperar su [!UICONTROL addressable audiences] no incluir [!DNL Safari] usuarios. |
| Impresiones de medios seguidos | Debido a las prácticas recomendadas del servidor de publicidad, las sincronizaciones de ID no se realizan dentro de las etiquetas de publicidad. Los clientes que realizan una gran cantidad de publicidad fuera del sitio no sincronizan a los usuarios con integraciones de terceros en esos entornos. Además, una gran cantidad de datos recopilados de impresiones de medios podría reducir [!UICONTROL addressable audience] números. |

## Solución de problemas con [!UICONTROL Addressable Audiences] {#troubleshooting}

Además de mostrar las tasas de coincidencia, también puede utilizar [!UICONTROL Addressable Audiences] como herramienta de resolución de problemas.

Por ejemplo, supongamos que envía un segmento a un [!UICONTROL destination] y que [!UICONTROL destination] muestra números de informes bajos. Comprobación de la [!UICONTROL Addressable Audience] Los resultados le mostrarán si se trata de un problema técnico o simplemente de un caso de tasas de coincidencia bajas. Una tasa de coincidencia baja muestra su [!UICONTROL destination] no es tan bueno para los segmentos seleccionados. Sin embargo, una diferencia en el [!UICONTROL total addressable audience] números entre [!DNL Audience Manager] y el [!UICONTROL destination] indica una integración, sincronización u otro problema técnico. En estos casos, póngase en contacto con el administrador de cuentas.
