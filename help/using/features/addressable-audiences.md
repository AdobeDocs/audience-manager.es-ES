---
description: Información general sobre la función de audiencia a la que se puede dirigir y ejemplos de uso.
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

Una visión general de la característica y casos [!UICONTROL Addressable Audience] de uso.

## ¿Qué es un [!UICONTROL Addressable Audience]? {#addressable-audience-description}

La [!UICONTROL Addressable Audiences] función le muestra la superposición entre las audiencias que ve en todas sus propiedades donde [!DNL Audience Manager] recopila datos y el destino seleccionado. Para ayudarle a comprender este concepto, eche un vistazo a la siguiente ilustración. La superposición entre cada círculo representa los distintos tipos de audiencias a las que puede dirigirse.

![](assets/addressableAudienceVenn.png)


| Métrica | Descripción |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] para un [!UICONTROL Destination] | Un recuento de todos los dispositivos que han interactuado con todos los [!DNL Audience Manager] clientes a nivel de plataforma durante el período retrospectivo del informe y que podrían coincidir con los que haya elegido [!UICONTROL destination]. <br><br>Este Métrica resulta útil porque le muestra: <ul><li>El tamaño del total [!UICONTROL addressable audience] que [!DNL Audience Manager] puede alcanzar en un direccionamiento [!UICONTROL destination]concreto.</li><li>Qué tan grande es el [!DNL Audience Manager] grupo de perfil para una plataforma direccionamiento y el tamaño de sus audiencias.</li></ul> |
| [!UICONTROL Customer Total Audience] | Un recuento de dispositivos que se han dado cuenta de sus [!UICONTROL rule-based trait] propiedades o [!UICONTROL onboarded trait] de sus archivos de sin conexión durante la ventana retrospectiva. |
| [!UICONTROL Customer Addressable Audience] | Un recuento de superposición de dispositivos que se han realizado durante [!UICONTROL rule-based trait] [!UICONTROL onboarded trait] la ventana retrospectiva y dispositivos que tenemos un ID sincronizar con el elegido [!UICONTROL destination] , independientemente del tiempo de sincronización.<br><br>Este Métrica representa dispositivos que:<ul><li>Haber realizado una [!UICONTROL rule-based] o una [!UICONTROL onboarded trait] durante la ventana retrospectiva `AND`</li><li>Tener un ID sincronizar con el elegido [!UICONTROL destination] , independientemente del tiempo de sincronización.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience][!UICONTROL Customer Total Audience]÷ expresado como porcentaje. |
| [!UICONTROL Total Segment Population] | Un recuento de todos los dispositivos que fueron miembros suyos [!UICONTROL segment] durante el período retrospectivo del informe. |
| [!UICONTROL Segment Addressable Audience] | El número de usuarios que han pertenecido al [!UICONTROL segment] durante el período retrospectivo del informe y tienen un sincronizar de ID activo en el sitio. [!UICONTROL Segments] Puede incluir sus propios datos de origen y datos de segundos y terceros, a través de adquiridos [!UICONTROL traits] en el [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Sugerencia: Cuando se utiliza con el período de retrospectiva de 1 día, este Métrica puede ayudarle a comprender el estado actual de su [!UICONTROL segments]. Esto se debe a que el [!UICONTROL Segment Addressable Audience] Métrica representa a los usuarios que permanecieron en un [!UICONTROL segment] durante todo el día anterior. Combine esto con el hecho de que [!DNL Audience Manager] se [!UICONTROL Addressable Audiences] actualiza diariamente, la combinación de este período de Métrica y retrospectiva proporciona la instantánea más actualizada de su [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience][!UICONTROL Total Segment Population]÷ expresado como porcentaje. |

## [!UICONTROL Addressable Audiences] Interfaz {#addressable-audience-interface}

La [!UICONTROL Addressable Audience] característica convierte este concepto abstracto en datos cuantificables. En [!DNL Audience Manager], esta función muestra audiencia superposición con visualizaciones de datos que proporcionan información rápida junto con datos numérica en forma de tabla.

[!UICONTROL Addressable Audiences] se encuentra en **[!UICONTROL Audience Data > Destinations]**. Seleccione esta opción **[!UICONTROL Integrated Platforms > Device-Based]** para ver las métricas de audiencias a las que puede dirigirse.

![](assets/addressable-audiences-landing.png)

Las tres métricas que puede ver en la [!UICONTROL Addressable Audiences] página de aterrizaje representan:

| Métrica | Descripción |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Esta Métrica representa los [!UICONTROL Customer Addressable Audience] (descritos en la tabla anterior) *de los últimos 30 días.* |
| **[!UICONTROL Match Rate]** | Este Métrica representa los [!UICONTROL Addressable Audience Match Rate] (descritos en la tabla anterior) *de los últimos 30 días*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Un recuento de todos los dispositivos que han interactuado con todos [!DNL Audience Manager] los clientes a nivel de plataforma durante el período retrospectivo del informe y que podrían coincidir con esto [!UICONTROL destination]. Consulte [Métricas](/help/using/features/addressable-audiences.md#platform-level-metrics) de nivel Platform para obtener más información. |

Haga clic en el nombre de a [!UICONTROL server-to-server destination] para vista los datos del audiencia direccionable. Tenga en cuenta que esta función devuelve datos solo para [!UICONTROL server-to-server destinations] y el acceso requiere permisos de administrador.

![](assets/addressableAudiences.png)

La revisión de estos datos puede ayudarle a:

* **Previsión y planificación:** [!UICONTROL Segment Addressable Audience] los datos le dan más Granularidad sobre los segmentos que planea enviar a un destino para audiencia direccionamiento y activación.

* **Revisiones de rendimiento:** La [!UICONTROL Addressable Audiences] función también es un herramienta de solución de problemas. Le permite revisar rendimiento de la campaña, comprender campaña alcance y le permite verificar con socios direccionamiento / activación si no ve los resultados que espera.

### Prospección con datos de terceros e implicaciones para las tasas de coincidencia

Antes de comprar datos de terceros para audiencia Adquisición, los clientes pueden validar la superposición con otros proveedores de datos. Esto puede ayudarle a tomar una decisión informada antes de comprar nuevos datos. Las sincronizaciones de ID para los datos de terceros comprados dependen no solo de la superposición de sus datos, sino también de las huellas de terceros proveedores con todos los demás [!DNL Audience Manager] clientes. El [!DNL Adobe] consultor puede ayudarle a identificar fuentes de datos relevantes adicionales para optimizar las campañas de prospección.

### Usuarios móviles y tasas de coincidencia

Hay brechas al intentar conectarse [!DNL Safari] o usuarios de aplicaciones móviles donde no hay terceros [!DNL cookies] presentes. Esto dificulta la sincronizar de los usuarios con algunos socios, ya que en el registros de envío de medios solo [!DNL Adobe] se proporcionan los ID para terceros [!DNL cookies] sincronizados. Esta es una razón por la que es posible que vea [tasas](../features/addressable-audiences.md#low-match-rates) de coincidencia bajas para su [!UICONTROL destinations]archivo .

## Intervalos de fechas en [!UICONTROL Addressable Audiences] y [!UICONTROL Destinations] {#date-ranges}

Lea las secciones siguientes para conocer los intervalos de fechas disponibles y la antigüedad de los datos a partir de cada intervalo en los informes de un [!UICONTROL Addressable Audience] o [!UICONTROL Destination].

## Intervalos de fechas y zonas horarias disponibles {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Los informes para usted [!UICONTROL Addressable Audiences] y [para los destinos](../features/destinations/destinations.md) utilizan los mismos intervalos de intervalo de fecha. Las intervalo de fecha opciones incluyen:

* [!UICONTROL Last 1 Day] (Este intervalo va de medianoche a medianoche del período de 24 horas anterior. No es un Métrica real o actual).
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Todas las fechas e intervalos de fechas se establecen en la [!DNL UTC] zona horaria. Consulte [Husos horarios en Audience Manager](../reference/aam-time-zones.md).

## Datos en intervalos de intervalos de fechas {#date-range-intervals}

La [!UICONTROL Addressable Audience] métrica y [!UICONTROL Destination] devuelve un recuento de usuarios únicos para el intervalo de tiempo seleccionado. Por ejemplo: un visitante se cuenta solo una vez, igualado si llegan a su sitio muchas veces. El primer visita es el único visita y se registra. Las visitas subsiguientes son visitas que devuelven visitas y no se contabilizan porque no son únicas.

Los intervalos de fechas contienen datos para el intervalo de tiempo seleccionado o posterior. Además, los datos van desapareciendo de cada intervalo del informe con el transcurso del tiempo. Por ejemplo, supongamos que ve 2 visitantes después de elegir la [!UICONTROL Last 30 Days] opción. En los informes, estos visitantes:

* *Se* incluirá en los resultados devueltos por los intervalos de tiempo más largos (60 días, 90 días y Duración).
* *No se* incluirá en los intervalos más cortos que preceden a la [!UICONTROL Last 30 Day] opción (actual, 7 días y 14 días).

Y, en el día 31, estos visitantes solo aparecen en los 60 días, 90 días y [!UICONTROL Lifetime] resultados. Han envejecido fuera del intervalo de 30 días. Los visitantes no envejecen fuera del [!UICONTROL Lifetime] intervalo.

## [!UICONTROL Addressable Audiences] Métricas {#addressable-audience-metrics}

En esta sección se describen los tipos de métricas proporcionados por [!UICONTROL Addressable Audiences].

### Métricas de nivel de cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Estas métricas devuelven datos de características obtenidas cuando los visitantes llegan al sitio o cuando envía archivos de datos de entrada a [!DNL Audience Manager]. Estos Métrica proporcionan una vista completa de tamaño audiencia para su cuenta.

| Métrica | Descripción |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Un recuento de superposición de dispositivos que se han dado cuenta de una [!UICONTROL rule-based trait] o una [!UICONTROL onboarded trait] durante la ventana retrospectiva y dispositivos que tenemos un ID sincronizar con el destino elegido independientemente del tiempo de sincronización.<br><br>Este Métrica representa dispositivos que:<ul><li>Haber realizado una [!UICONTROL rule-based] o una [!UICONTROL onboarded trait] durante la ventana retrospectiva `AND`</li><li>Tener un ID sincronizar con el elegido [!UICONTROL destination] , independientemente del tiempo de sincronización.</li></ul> |
| [!UICONTROL Customer Total Audience] | Un recuento de dispositivos que se han dado cuenta de sus [!UICONTROL rule-based trait] propiedades o [!UICONTROL onboarded trait] de sus archivos de sin conexión durante la ventana retrospectiva. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience][!UICONTROL Customer Total Audience]÷ expresado como porcentaje. |

### Métricas de coincidencia en el nivel de segmento {#segment-level-metrics}

Estas métricas devuelven datos sobre [!UICONTROL segment] abono. Ayudan a proporcionar una vista más granular y precisa del tamaño del audiencia para cada uno de sus [!UICONTROL segments].

>[!NOTE]
>
>La forma en la que se aplica la ventana retrospectiva en el [!UICONTROL segment] nivel es diferente a la del nivel del cliente. Los visitantes pueden venir al sitio y darse cuenta hace 10 [!UICONTROL trait] días, y podrían calificar para un [!UICONTROL segment] desde entonces y abandonaron el [!UICONTROL segment] hace 2 días. Cuando se aplica la retrospectiva de 7 días, estos visitantes se contabilizan en el nivel pero [!UICONTROL segment] no en el nivel del cliente.

| Métrica | Descripción |
|---|---|
| [!UICONTROL Segment Addressable Audience] | El número de usuarios que han pertenecido al [!UICONTROL segment] durante el período retrospectivo del informe y tienen un sincronizar de ID activo en el sitio. Los segmentos pueden incluir sus propios datos de origen y datos de segundos y terceros, a través de los [!UICONTROL traits] adquiridos en el [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Sugerencia: Cuando se utiliza con el período de retrospectiva de 1 día, este Métrica puede ayudarle a comprender el estado actual de su [!UICONTROL segments]. Esto se debe a que el [!UICONTROL Segment Addressable Audience] Métrica representa a los usuarios que permanecieron en un [!UICONTROL segment] durante todo el día anterior. Combine esto con el hecho de que [!DNL Audience Manager] se [!UICONTROL Addressable Audiences] actualiza diariamente, la combinación de este período de Métrica y retrospectiva proporciona la instantánea más actualizada de su [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Un recuento de todos los dispositivos que fueron miembros suyos [!UICONTROL segment] durante el período retrospectivo del informe. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience][!UICONTROL Total Segment Population]÷ expresado como porcentaje. |

### Métricas de nivel Platform {#platform-level-metrics}

Esta Métrica devuelve datos sobre las actividades recopiladas entre todos los [!DNL Audience Manager] clientes. Pueden proporcionar una vista más amplia de la audiencia del cliente en comparación con los clientes agregados [!DNL Audience Manager] .

| Métrica | Descripción |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Un recuento de todos los dispositivos que han interactuado con todos los [!DNL Audience Manager] clientes a nivel de plataforma durante el período retrospectivo del informe y que podrían coincidir con los que haya elegido [!UICONTROL destination]. <br><br>Este Métrica resulta útil porque le muestra:<ul><li>El tamaño de la [!UICONTROL total addressable audience] que [!DNL Audience Manager] puede alcanzar en un destino de direccionamiento particular.</li><li>Qué tan grande es el [!DNL Audience Manager] grupo de perfil para una plataforma direccionamiento y el tamaño de sus audiencias.</li></ul> |

## Comparación [!UICONTROL Customer] y [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

No debe comparar las [!UICONTROL Customer Addressable Audience] métricas y [!UICONTROL Segment Addressable Audience] para determinar si una es más importante que la otra. Estas métricas son independientes, diferentes e independientes. Como se describe en las definiciones anteriores, cada uno de ellos se deriva de diferentes conjuntos de datos. Dado esto, debe evitar derivar conclusiones si una Métrica es más grande que la otra. Todo lo que puede decir al comparar estos es que:

* [!UICONTROL Customer Addressable Audiences] se basa en [!UICONTROL trait] la realización de sus *propios datos* de origen. Este Métrica proporciona una vista amplia y completa de su integración con un socio de datos.

* [!UICONTROL Segment Addressable Audiences] se basa en segmento cualificaciones *para sus propios datos de origen, además de datos* de segundos y terceros. Este Métrica proporciona una vista granular y más precisa de su [!UICONTROL addressable audiences] en una plataforma direccionamiento.

## Causas de las bajas tasas de coincidencia para [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementos comunes responsables de tasas de coincidencia bajas [!UICONTROL Addressable Audience] o discrepancias en los números reportados.

| Causa | Descripción |
|---|---|
| Tráfico móvil | La mayoría [!UICONTROL server-to-server] de las integraciones se basan en procesos de sincronización facilitados por terceros [!DNL cookies]. Sin embargo, los entornos móviles no utilizan terceros [!DNL cookies]. Como resultado, sus números pueden parecer bajos en comparación con el [!UICONTROL Addressable Audiences] [!UICONTROL segment] tamaño. <br><br>A partir de enero de 2018, puede activar las audiencias móviles en el mismo [!DNL Google] y [!DNL Adobe Advertising Cloud] los destinos configurados para [!UICONTROL cookie-based] las audiencias. Si bien esto significa que puede enviar [!UICONTROL segments] con abono de ID combinados [!DNL cookie] y móviles a sus [!DNL Google] destinos y [!DNL Advertising Cloud] destinos, tenga en cuenta que [!UICONTROL Addressable Audiences] solo se muestra la superposición entre [!DNL cookie] ID y destinos. [!DNL Audience Manager] envía el 100 % de las audiencias móviles a [!UICONTROL destinations], aunque las audiencias móviles no las mide el [!UICONTROL Addressable Audience] Métrica. <br><br>**Nota**: Por ejemplo, tome un [!UICONTROL segment] con una población de 1,000,000. Si asigna esto [!UICONTROL segment] a un [!DNL Google] destino o [!DNL Adobe Advertising Cloud] , es posible que vea un [!UICONTROL Addressable Audience] destino de 700,000 dispositivos y un [!UICONTROL Match Rate] de 70%. El abono de 700.000 consiste en [!DNL cookie] identificaciones que tienen una sincronizar de identificación con el [!UICONTROL destination]. De hecho, es [!UICONTROL Addressable Audience] posible que su valor sea mucho mayor, ya que los ID móviles direccionables no aparecen en este Métrica. |
| [!DNL Safari] Tráfico | [!DNL Safari] bloques terceros [!DNL cookies]. Esto evita [!DNL Audience Manager] que se sincronicen los ID con el [!UICONTROL destination]. Con la introducción de [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), puede esperar [!UICONTROL addressable audiences] que no incluya [!DNL Safari] usuarios. |
| Impresiones de medios rastreadas | Debido a servidor de anuncios prácticas recomendadas, las sincronizaciones de ID no se realizan dentro de etiquetas anuncios. Los clientes que realizan una gran cantidad de publicidad externa no sincronizarán a los usuarios con terceros integraciones en esos entornos. Además, una gran cantidad de datos recopilados de medios impresión podría reducir [!UICONTROL addressable audience] las cifras. |

## Solución de problemas con [!UICONTROL Addressable Audiences] {#troubleshooting}

Además de mostrar las tasas de coincidencia, también puede utilizarlas [!UICONTROL Addressable Audiences] como herramienta de solución de problemas.

Por ejemplo, supongamos que envía una segmento a un [!UICONTROL destination] y muestra [!UICONTROL destination] números de sistema de informes bajos. La verificación de los [!UICONTROL Addressable Audience] resultados le mostrará si se trata de un problema técnico o simplemente un caso de bajas tasas de coincidencia. Una tasa de coincidencia baja muestra [!UICONTROL destination] que su no es tan bueno para los segmentos seleccionados. Sin embargo, una diferencia en los [!UICONTROL total addressable audience] números entre [!DNL Audience Manager] y el [!UICONTROL destination] indica una integración, sincronización u otros problema técnicos. En estos casos, póngase en contacto con su Administrador de cuentas.
