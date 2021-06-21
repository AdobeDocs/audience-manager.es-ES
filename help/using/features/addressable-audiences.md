---
description: Información general sobre la función Audiencia direccionable y los casos de uso.
keywords: DIL
seo-description: Información general sobre la función Audiencia direccionable y los casos de uso.
seo-title: Audiencias a las que se puede dirigir
solution: Audience Manager
title: Audiencias a las que se puede dirigir
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Combinar tasas
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1827'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Información general sobre la función [!UICONTROL Addressable Audience] y los casos de uso.

## ¿Qué es un [!UICONTROL Addressable Audience]? {#addressable-audience-description}

La función [!UICONTROL Addressable Audiences] le muestra la superposición entre las audiencias que ve en todas sus propiedades, donde [!DNL Audience Manager] recopila datos y el destino seleccionado. Para ayudarle a comprender este concepto, consulte la siguiente ilustración. La superposición entre cada círculo representa los diferentes tipos de audiencias a las que se puede dirigir.

![](assets/addressableAudienceVenn.png)


| Métrica | Descripción |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] para un  [!UICONTROL Destination] | Recuento de todos los dispositivos que han interactuado con todos los clientes [!DNL Audience Manager] a nivel de plataforma durante el período retrospectivo del informe y que podrían coincidir con el [!UICONTROL destination] que haya elegido. <br><br>Esta métrica es útil porque muestra: <ul><li>El tamaño del total [!UICONTROL addressable audience] al que [!DNL Audience Manager] puede llegar en un objetivo determinado [!UICONTROL destination].</li><li>Qué tamaño tiene el grupo de perfiles [!DNL Audience Manager] para una plataforma de segmentación y el tamaño de sus audiencias.</li></ul> |
| [!UICONTROL Customer Total Audience] | Recuento de dispositivos que han realizado un [!UICONTROL rule-based trait] en sus propiedades o un [!UICONTROL onboarded trait] desde los archivos sin conexión durante la ventana retrospectiva. |
| [!UICONTROL Addressable Audience Match Rate] | Recuento de superposición de dispositivos que han realizado un [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante la ventana retrospectiva y dispositivos que tienen una sincronización de ID con el [!UICONTROL destination] seleccionado independientemente del tiempo de sincronización.<br><br>Esta métrica representa los dispositivos que:<ul><li>Se han realizado un [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante la ventana retrospectiva `AND`</li><li>Tenga una sincronización de ID con el [!UICONTROL destination] seleccionado independientemente del tiempo de sincronización.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷  [!UICONTROL Customer Total Audience] expresado como porcentaje. |
| [!UICONTROL Total Segment Population] | Recuento de todos los dispositivos que fueron miembros de su [!UICONTROL segment] durante el período retrospectivo del informe. |
| [!UICONTROL Segment Addressable Audience] | El número de usuarios que han pertenecido a [!UICONTROL segment] durante el período retrospectivo del informe y que tienen una sincronización de ID activa en el sitio. [!UICONTROL Segments] puede incluir sus propios datos de origen y de terceros, a través de los  [!UICONTROL traits] adquiridos en el  [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Sugerencia: Cuando se utiliza con el período retrospectivo de 1 día, esta métrica puede ayudarle a comprender el estado actual de su  [!UICONTROL segments]. Esto se debe a que la métrica [!UICONTROL Segment Addressable Audience] representa a los usuarios que permanecieron en [!UICONTROL segment] durante el día anterior. Combine esto con el hecho de que [!DNL Audience Manager] actualiza [!UICONTROL Addressable Audiences] diariamente, la combinación de esta métrica y el período retrospectivo proporciona la instantánea más actualizada de su [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷  [!UICONTROL Total Segment Population] expresado como porcentaje. |

## [!UICONTROL Addressable Audiences] Interfaz {#addressable-audience-interface}

La función [!UICONTROL Addressable Audience] convierte este concepto abstracto en datos cuantificables. En [!DNL Audience Manager], esta función muestra la superposición de audiencias con visualizaciones de datos que proporcionan información rápida junto con datos numéricos en forma de tabla.

[!UICONTROL Addressable Audiences] está en  **[!UICONTROL Audience Data > Destinations]**. Seleccione **[!UICONTROL Integrated Platforms > Device-Based]** para ver las métricas de audiencias a las que se puede dirigir.

![](assets/addressable-audiences-landing.png)

Las tres métricas que puede ver en la página de aterrizaje [!UICONTROL Addressable Audiences] representan:

| Métrica | Descripción |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Esta métrica representa el [!UICONTROL Customer Addressable Audience] (descrito en la tabla anterior) *durante los últimos 30 días.* |
| **[!UICONTROL Match Rate]** | Esta métrica representa el [!UICONTROL Addressable Audience Match Rate] (descrito en la tabla anterior) *para los últimos 30 días*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Recuento de todos los dispositivos que han interactuado con todos los clientes [!DNL Audience Manager] a nivel de plataforma durante el período retrospectivo del informe y que podrían coincidir con este [!UICONTROL destination]. Consulte [Métricas de nivel de plataforma](/help/using/features/addressable-audiences.md#platform-level-metrics) para obtener más información. |

Haga clic en el nombre de un [!UICONTROL server-to-server destination] para ver los datos de audiencia a los que puede dirigirse. Tenga en cuenta que esta función solo devuelve datos para [!UICONTROL server-to-server destinations] y el acceso requiere permisos de administrador.

![](assets/addressableAudiences.png)

La revisión de estos datos puede ayudarle con:

* **Previsión y planificación:** [!UICONTROL Segment Addressable Audience] los datos le proporcionan más granularidad en los segmentos que planea enviar a un destino para la segmentación y activación de audiencias.

* **Revisiones de rendimiento:** La  [!UICONTROL Addressable Audiences] función también es una herramienta de resolución de problemas. Permite revisar el rendimiento de la campaña, comprender el alcance de la campaña y realizar comprobaciones cruzadas con socios de objetivo/activación si no ve los resultados esperados.

### Prospecting con datos de terceros e implicaciones para tasas de coincidencia

Antes de comprar datos de terceros para la adquisición de audiencias, los clientes pueden validar la superposición con otros proveedores de datos. Esto puede ayudarle a tomar una decisión informada antes de comprar nuevos datos. Las sincronizaciones de ID para los datos de terceros adquiridos no solo se basan en la superposición de los datos, sino también en las impresiones de terceros proveedores con el resto de clientes [!DNL Audience Manager]. Su asesor de [!DNL Adobe] puede ayudarle a identificar fuentes de datos relevantes adicionales para optimizar las campañas de prospección.

### Usuarios móviles y tasas de coincidencia

Hay huecos al intentar conectar [!DNL Safari] o a los usuarios de aplicaciones móviles en los que no hay [!DNL cookies] de terceros presentes. Esto dificulta la sincronización de usuarios con algunos socios, ya que solo los [!DNL Adobe] ID de terceros sincronizados [!DNL cookies] se proporcionan en los registros de envío de medios. Este es un motivo por el que podría ver [tasas de coincidencia bajas](../features/addressable-audiences.md#low-match-rates) para su [!UICONTROL destinations].

## Intervalos de fechas en [!UICONTROL Addressable Audiences] y [!UICONTROL Destinations] {#date-ranges}

Lea las secciones siguientes para ver los intervalos de fechas disponibles y cómo envejecen los datos de cada intervalo en los informes para [!UICONTROL Addressable Audience] o [!UICONTROL Destination].

## Intervalos de fechas y zonas horarias disponibles {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Los informes de [!UICONTROL Addressable Audiences] y [Destinations](../features/destinations/destinations.md) utilizan los mismos intervalos de intervalo de fechas. Las opciones del intervalo de fechas incluyen:

* [!UICONTROL Last 1 Day] (Este intervalo va de la medianoche a la medianoche del periodo de 24 horas anterior. No es una métrica real ni en tiempo actual).
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Todas las fechas e intervalos de fechas se establecen en el huso horario [!DNL UTC]. Consulte [Zonas horarias en el Audience Manager](../reference/aam-time-zones.md).

## Datos en intervalos de intervalo de fechas {#date-range-intervals}

Las métricas [!UICONTROL Addressable Audience] y [!UICONTROL Destination] devuelven un recuento de usuarios únicos para el intervalo de tiempo seleccionado. Por ejemplo, un visitante se cuenta solo una vez, incluso si llega al sitio varias veces. La primera visita es la visita única y se registra. Las visitas siguientes devuelven visitas y no se cuentan porque no son únicas.

Los intervalos de fechas contienen datos para el intervalo de tiempo seleccionado o anterior. Además, los datos envejecen de cada intervalo de informe a medida que pasa el tiempo. Por ejemplo, supongamos que ve 2 visitantes después de elegir la opción [!UICONTROL Last 30 Days]. En los informes, estos visitantes:

* *Se* incluirá en los resultados devueltos en intervalos de tiempo más largos (60 días, 90 días y Duración).
* *No* se incluye en los intervalos más cortos que preceden a la  [!UICONTROL Last 30 Day] opción (Actual, 7 días y 14 días).

Y, el día 31, estos visitantes solo aparecen en los resultados de 60 días, 90 días y [!UICONTROL Lifetime]. Han envejecido del intervalo de 30 días. Los visitantes no envejecen fuera del intervalo [!UICONTROL Lifetime].

## [!UICONTROL Addressable Audiences] Métricas {#addressable-audience-metrics}

En esta sección se describen los tipos de métricas que proporciona [!UICONTROL Addressable Audiences].

### Métricas de nivel de cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Estas métricas devuelven datos sobre características realizadas cuando los visitantes llegan al sitio o cuando envía archivos de datos entrantes a [!DNL Audience Manager]. Estas métricas proporcionan una vista completa del tamaño de la audiencia para su cuenta.

| Métrica | Descripción |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Recuento de superposición de dispositivos que han realizado una [!UICONTROL rule-based trait] o una [!UICONTROL onboarded trait] durante la ventana retrospectiva y dispositivos que tienen una sincronización de ID con el destino elegido independientemente del tiempo de sincronización.<br><br>Esta métrica representa los dispositivos que:<ul><li>Se han realizado un [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante la ventana retrospectiva `AND`</li><li>Tenga una sincronización de ID con el [!UICONTROL destination] seleccionado independientemente del tiempo de sincronización.</li></ul> |
| [!UICONTROL Customer Total Audience] | Recuento de dispositivos que han realizado un [!UICONTROL rule-based trait] en sus propiedades o un [!UICONTROL onboarded trait] desde los archivos sin conexión durante la ventana retrospectiva. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷  [!UICONTROL Customer Total Audience] expresado como porcentaje. |

### Métricas de coincidencia de nivel de segmento {#segment-level-metrics}

Estas métricas devuelven datos sobre la pertenencia a [!UICONTROL segment]. Ayudan a proporcionar una vista más granular y precisa del tamaño de la audiencia para cada uno de sus [!UICONTROL segments].

>[!NOTE]
>
>La forma en que se aplica la ventana retrospectiva en el nivel [!UICONTROL segment] es diferente a la del nivel de cliente. Los visitantes pueden venir al sitio y darse cuenta de un [!UICONTROL trait] hace 10 días, y podrían cumplir los requisitos para un [!UICONTROL segment] desde entonces y dejar el [!UICONTROL segment] hace 2 días. Cuando se aplica la retrospectiva de 7 días, estos visitantes se cuentan en el nivel [!UICONTROL segment] pero no en el nivel de cliente.

| Métrica | Descripción |
|---|---|
| [!UICONTROL Segment Addressable Audience] | El número de usuarios que han pertenecido a [!UICONTROL segment] durante el período retrospectivo del informe y que tienen una sincronización de ID activa en el sitio. Los segmentos pueden incluir sus propios datos de origen y de terceros, a través de [!UICONTROL traits] adquiridos en el [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Sugerencia: Cuando se utiliza con el período retrospectivo de 1 día, esta métrica puede ayudarle a comprender el estado actual de su  [!UICONTROL segments]. Esto se debe a que la métrica [!UICONTROL Segment Addressable Audience] representa a los usuarios que permanecieron en [!UICONTROL segment] durante el día anterior. Combine esto con el hecho de que [!DNL Audience Manager] actualiza [!UICONTROL Addressable Audiences] diariamente, la combinación de esta métrica y el período retrospectivo proporciona la instantánea más actualizada de su [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Recuento de todos los dispositivos que fueron miembros de su [!UICONTROL segment] durante el período retrospectivo del informe. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷  [!UICONTROL Total Segment Population] expresado como porcentaje. |

### Métricas de nivel de plataforma {#platform-level-metrics}

Esta métrica devuelve datos sobre las actividades recopiladas entre todos los clientes de [!DNL Audience Manager]. Pueden proporcionar una visión más amplia de la audiencia del cliente en comparación con los clientes agregados [!DNL Audience Manager].

| Métrica | Descripción |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Recuento de todos los dispositivos que han interactuado con todos los clientes [!DNL Audience Manager] a nivel de plataforma durante el período retrospectivo del informe y que podrían coincidir con el [!UICONTROL destination] que haya elegido. <br><br>Esta métrica es útil porque muestra:<ul><li>El tamaño del [!UICONTROL total addressable audience] al que [!DNL Audience Manager] puede llegar en un destino objetivo determinado.</li><li>Qué tamaño tiene el grupo de perfiles [!DNL Audience Manager] para una plataforma de segmentación y el tamaño de sus audiencias.</li></ul> |

## Comparación de [!UICONTROL Customer] y [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

No debe comparar las métricas [!UICONTROL Customer Addressable Audience] y [!UICONTROL Segment Addressable Audience] para determinar si una es más significativa que la otra. Son métricas independientes, diferentes e independientes. Como se describe en las definiciones anteriores, cada una de ellas se deriva de diferentes conjuntos de datos. En este caso, debe evitar sacar conclusiones si una métrica es más grande que la otra. Todo lo que se puede decir al comparar esto es que:

* [!UICONTROL Customer Addressable Audiences] se basa en  [!UICONTROL trait] realizaciones  *para sus propios datos* de origen. Esta métrica proporciona una vista amplia y completa de su integración con un socio de datos.

* [!UICONTROL Segment Addressable Audiences] se basa en las cualificaciones de segmentos  *para sus propios datos de origen, además de los datos de segundo nivel y de terceros*. Esta métrica proporciona una vista granular más precisa de su [!UICONTROL addressable audiences] en una plataforma de segmentación.

## Causas de tasas de coincidencia bajas para [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementos comunes responsables de bajas [!UICONTROL Addressable Audience] tasas de coincidencia o discrepancias en los números notificados.

| Causa | Descripción |
|---|---|
| Tráfico móvil | La mayoría de las integraciones [!UICONTROL server-to-server] se basan en procesos de sincronización facilitados por [!DNL cookies] de terceros. Sin embargo, los entornos móviles no utilizan [!DNL cookies] de terceros. Como resultado, los números [!UICONTROL Addressable Audiences] pueden parecer bajos en comparación con el tamaño [!UICONTROL segment]. <br><br>A partir de enero de 2018, puede activar audiencias móviles en el mismo  [!DNL Google] y configurar  [!DNL Adobe Advertising Cloud] destinos para las  [!UICONTROL cookie-based] audiencias. Aunque esto significa que puede enviar [!UICONTROL segments] con [!DNL cookie] y membresía de ID de móvil combinada a sus destinos [!DNL Google] y [!DNL Advertising Cloud], tenga en cuenta que [!UICONTROL Addressable Audiences] solo muestra la superposición entre [!DNL cookie] ID y destinos. [!DNL Audience Manager] envía el 100 % de las audiencias móviles a  [!UICONTROL destinations], pero las audiencias móviles no se miden mediante la  [!UICONTROL Addressable Audience] métrica. <br><br>**Nota**: Por ejemplo, tomemos un  [!UICONTROL segment] con una población de 1.000.000 habitantes. Si asigna este [!UICONTROL segment] a un destino [!DNL Google] o [!DNL Adobe Advertising Cloud], es posible que vea un [!UICONTROL Addressable Audience] de 700.000 dispositivos y un [!UICONTROL Match Rate] del 70%. La membresía de 700.000 consiste en [!DNL cookie] ID que tienen una sincronización de ID con [!UICONTROL destination]. Su [!UICONTROL Addressable Audience] puede ser, de hecho, mucho mayor, ya que los ID móviles a los que se puede dirigir no aparecen en esta métrica. |
| [!DNL Safari] Tráfico | [!DNL Safari] bloquea terceros  [!DNL cookies]. Esto evita que [!DNL Audience Manager] sincronice los ID con [!UICONTROL destination]. Con la introducción de [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), puede esperar que su [!UICONTROL addressable audiences] no incluya [!DNL Safari] usuarios. |
| Impresiones de medios rastreadas | Debido a las prácticas recomendadas del servidor de publicidad, las sincronizaciones de ID no se realizan dentro de las etiquetas de publicidad. Los clientes que hagan una gran cantidad de publicidad fuera del sitio no sincronizarán a los usuarios con integraciones de terceros en esos entornos. Además, una gran cantidad de datos de impresión de contenido recopilados podría reducir los [!UICONTROL addressable audience] números. |

## Solución de problemas con [!UICONTROL Addressable Audiences] {#troubleshooting}

Además de mostrar las tasas de coincidencia, también puede utilizar [!UICONTROL Addressable Audiences] como herramienta de resolución de problemas.

Por ejemplo, supongamos que envía un segmento a un [!UICONTROL destination] y que [!UICONTROL destination] muestra números de informes bajos. La comprobación de los resultados de [!UICONTROL Addressable Audience] le mostrará si se trata de un problema técnico o solo de un caso de tasas de coincidencia bajas. Una tasa de coincidencia baja muestra que el [!UICONTROL destination] no es tan bueno para los segmentos seleccionados. Sin embargo, una diferencia en los números [!UICONTROL total addressable audience] entre [!DNL Audience Manager] y [!UICONTROL destination] indica un problema técnico de integración, sincronización u otro tipo. En estos casos, póngase en contacto con su administrador de cuentas.
