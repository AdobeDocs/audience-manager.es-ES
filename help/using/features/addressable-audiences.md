---
description: Información general sobre la característica Audiencia objetivo y casos de uso.
keywords: DIL
seo-description: Información general sobre la característica Audiencia objetivo y casos de uso.
seo-title: Audiencias a las que se puede dirigir
solution: Audience Manager
title: Audiencias a las que se puede dirigir
topic: API DIL
uuid: 3 eb 1335 a -6949-452 b-b 77 a -697 c 22856 cb 3
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Addressable Audience {#addressable-audiences}

Información general sobre la característica Audiencia objetivo y casos de uso.

## What is an Addressable Audience? {#addressable-audience-description}

The [!UICONTROL Addressable Audiences] feature shows you the overlap between the audiences you see across all of your properties where [!DNL Audience Manager] collects data and your selected destination. Para ayudarle a comprender este concepto, vea la siguiente ilustración. La solapa entre cada círculo representa los distintos tipos de audiencias direccionables.

![](assets/addressableAudienceVenn.png)

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
    <tr> 
   <td colname="col1"> <p> <b>Audiencia direccionable de Audience Manager para un destino</b> </p> </td> 
   <td colname="col2"> <p>Recuento de todos los dispositivos que interactuaron con todos los clientes de Audience Manager en el nivel de plataforma durante el período de retroceso del informe y que podrían coincidir con el destino elegido. </p> <p>Esta métrica es útil porque muestra: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> The size of the total addressable audience that <span class="keyword"> Audience Manager</span> can reach on a particular targeting destination. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">How big the <span class="keyword"> Audience Manager</span> profile pool is for a targeting platform and the size of their audiences. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audiencia total del cliente</b> </p> </td> 
   <td colname="col2"> <p>Recuento de dispositivos que han obtenido una característica basada en reglas de sus propiedades o un rasgo integrado de sus archivos sin conexión durante la ventana de retroceso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasa de coincidencia de audiencias objetivo</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Recuento de superposición de dispositivos que han obtenido una característica basada en reglas o un rasgo onbotado durante la ventana de retroceso y los dispositivos que se sincronizan con el destino seleccionado independientemente del tiempo de sincronización. </p> 
    </draft-comment> <p>Esta métrica representa los dispositivos que: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Tenga una sincronización de ID con el destino elegido independientemente del tiempo de sincronización. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasa de coincidencia de clientes</b> </p> </td> 
   <td colname="col2"> <p>Audiencia a la que puede dirigirse el cliente ÷ Audiencia total del cliente expresada como %. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>Población total de segmentos</b> </p> </td> 
   <td colname="col2"> <p>Recuento de todos los dispositivos que eran miembros del segmento durante el período de retroceso del informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audiencia objetivo para segmentos</b> </p> </td> 
   <td colname="col2"> <p>El número de usuarios que pertenecen al segmento durante el período de retroceso del informe y tienen una sincronización de ID activa en el sitio. Segments can include your own first-party data and second party and third party data, via traits acquired in the <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Sugerencia: Cuando se utiliza con el período de retroceso de 1 día, esta métrica puede ayudarle a comprender el estado actual de los segmentos. This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasa de coincidencia de segmentos</b> </p> </td> 
   <td colname="col2"> <p>Audiencia objetivo para segmentos ÷ Población total del segmento expresada como un %. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Addressable Audience Interface {#addressable-audience-interface}

The [!UICONTROL Addressable Audience] feature turns this abstract concept into quantifiable data. In [!DNL Audience Manager], this feature displays audience overlap with data visualizations that provide at-a-glance information along with numeric data in tabular form.

[!UICONTROL Addressable Audiences] está ubicado **[!UICONTROL Audience Data > Destinations]** en. Select **[!UICONTROL Integrated Platforms > Device-Based]** to see addressable audiences metrics.

![](assets/addressable-audiences-landing.png)

Las tres métricas que se pueden ver en la página de aterrizaje Audiencias objetivo representan:

| Métrica | Descripción |
---------|----------|
| **Audiencia objetivo (dispositivos)** | This metric represents the Customer Addressable Audience (described in the table above) *for the last 30 days.* |
| **Tasa de coincidencia** | This metric represents the Addressable Audience Match Rate (described in the table above) *for the last 30 days*. |
| **Audiencia a la que se puede dirigir (dispositivos)** | Recuento de todos los dispositivos que interactuaron con todos los clientes de Audience Manager en el nivel de plataforma durante el período de retroceso del informe y que podrían coincidir con este destino. See [Platform-Level Metrics](/help/using/features/addressable-audiences.md#platform-level-metrics) for more information. |

Haga clic en el nombre de un destino servidor a servidor para ver los datos de audiencia direccionables. Tenga en cuenta que esta función devuelve datos para destinos de servidor a servidor y el acceso requiere permisos de administrador.

![](assets/addressableAudiences.png)

La revisión de estos datos puede ayudarle con:

* **Previsión y planificación:**[!UICONTROL Segment Addressable Audience] proporciona más granularidad en los segmentos que está planeando enviar a un destino para la segmentación y activación de audiencias.

* **Revisiones de rendimiento:** La [!UICONTROL Addressable Audiences] función también es una herramienta de solución de problemas. Permite revisar el rendimiento de las campañas, comprender el alcance de la campaña y realizar una comprobación cruzada con los socios de segmentación o activación si no ve los resultados esperados.

### Publicación con datos de terceros e implicaciones para tasas de coincidencia

Antes de comprar datos de terceros para la adquisición de audiencia, los clientes pueden validar la superposición con otros proveedores de datos. Esto puede ayudarle a tomar una decisión fundamentada antes de comprar nuevos datos. The ID syncs for purchased third-party data rely not only on the overlap of your data but also on third-party providers’ footprints with all other [!DNL Audience Manager] customers. [!DNL Adobe] Su asesor puede ayudarle a identificar fuentes de datos relevantes adicionales para optimizar las campañas de publicación.

### Usuarios móviles y Tasas de coincidencia

There are gaps when trying to connect [!DNL Safari] or mobile app users where there are no third-party cookies present. That makes it difficult to sync users with some partners because only those [!DNL Adobe] IDs for synced third-party cookies are provided in the media delivery logs. This is a reason why you might see [low match rates](../features/addressable-audiences.md#low-match-rates) for your destinations.

## Date Ranges in Addressable Audiences and Destinations {#date-ranges}

Read the sections below for available date ranges and how data ages out of each interval in the reports for an [!UICONTROL Addressable Audience] or [!UICONTROL Destination].

## Available Date Ranges and Time Zones {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Reports for your [!UICONTROL Addressable Audiences] and [Destinations](../features/destinations/destinations.md) use the same date range intervals. Las opciones de intervalo de fechas incluyen:

* [!UICONTROL Last 1 Day] (Este intervalo se ejecuta desde Medianoche hasta Medianoche del período anterior de 24 horas. No es una métrica real o de tiempo actual.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

All dates and date ranges are set in the [!DNL UTC] time zone. See [Time Zones in Audience Manager](../reference/aam-time-zones.md).

## Data in Date Range Intervals {#date-range-intervals}

The [!UICONTROL Addressable Audience] and [!UICONTROL Destination] metrics return a count of unique users for the selected time interval. Por ejemplo, un visitante se cuenta solamente una vez, incluso si ingresan varias veces al sitio. La primera visita es la única visita y se registra. Las visitas subsiguientes son visitas recurrentes y no se cuentan porque no son únicas.

Los intervalos de fecha contienen datos para el intervalo de tiempo seleccionado o anterior. Y las edades de los datos de cada intervalo de informes con el transcurso del tiempo. For example, let's assume you see 2 visitors after choosing the [!UICONTROL Last 30 Days] option. En los informes, estos visitantes:

* *Se incluirá* en los resultados devueltos por intervalos de tiempo más largos (60 días, 90 días y Duración).
* *No* se incluirá en intervalos cortos que precedan a la [!UICONTROL Last 30 Day] opción (actual, 7 días y 14 días).

And, on day 31, these visitors only show up in the 60 day, 90 day, and [!UICONTROL Lifetime] results. Han superado el intervalo de 30 días. Visitors do not age out of the [!UICONTROL Lifetime] interval.

## Addressable Audience Metrics {#addressable-audience-metrics}

This section describes the types of metrics provided by [!UICONTROL Addressable Audiences].

### Customer-Level Metrics {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

These metrics return data for traits realized when visitors come to your site or when you send inbound data files to [!DNL Audience Manager]. Estas métricas proporcionan una vista completa del tamaño de la audiencia para su cuenta.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audiencia objetivo para clientes</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Recuento de superposición de dispositivos que han obtenido una característica basada en reglas o un rasgo onbotado durante la ventana de retroceso y los dispositivos que se sincronizan con el destino seleccionado independientemente del tiempo de sincronización. </p> 
    </draft-comment> <p>Esta métrica representa los dispositivos que: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Tenga una sincronización de ID con el destino elegido independientemente del tiempo de sincronización. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audiencia total del cliente</b> </p> </td> 
   <td colname="col2"> <p>Recuento de dispositivos que han obtenido una característica basada en reglas de sus propiedades o un rasgo integrado de sus archivos sin conexión durante la ventana de retroceso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasa de coincidencia de clientes</b> </p> </td> 
   <td colname="col2"> <p>Audiencia a la que puede dirigirse el cliente ÷ Audiencia total del cliente expresada como %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Segment-Level Match Metrics {#segment-level-metrics}

Estas métricas devuelven datos sobre la pertenencia a segmentos. Ayudan a obtener una vista más precisa y precisa del tamaño de la audiencia para cada uno de los segmentos.

>[!NOTE]
>
>La manera en la que se aplica la ventana de retroceso a nivel de segmento difiere de la del nivel de cliente. Los visitantes pueden ingresar al sitio y ver una característica hace 10 días, y pueden cumplir los requisitos de un segmento desde entonces y salir del segmento 2 días atrás. Cuando se aplique el retroceso de 7 días, estos visitantes se contabilizarán en el nivel de segmento pero no en el nivel de cliente.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audiencia objetivo para segmentos</b> </p> </td> 
   <td colname="col2"> <p>El número de usuarios que pertenecen al segmento durante el período de retroceso del informe y tienen una sincronización de ID activa en el sitio. Segments can include your own first-party data and second party and third party data, via traits acquired in the <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Sugerencia: Cuando se utiliza con el período de retroceso de 1 día, esta métrica puede ayudarle a comprender el estado actual de los segmentos. This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Población total de segmentos</b> </p> </td> 
   <td colname="col2"> <p>Recuento de todos los dispositivos que eran miembros del segmento durante el período de retroceso del informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasa de coincidencia de segmentos</b> </p> </td> 
   <td colname="col2"> <p>Audiencia objetivo para segmentos ÷ Población total del segmento expresada como un %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Platform-Level Metrics {#platform-level-metrics}

Esta métrica devuelve datos sobre actividades recopiladas en todos los clientes de Audience Manager. Pueden proporcionar una vista más amplia de la audiencia del cliente en comparación con los clientes agregados de Audience Manager.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audiencia objetivo de Audience Manager</b> </p> </td> 
   <td colname="col2"> <p>Recuento de todos los dispositivos que interactuaron con todos los clientes de Audience Manager en el nivel de plataforma durante el período de retroceso del informe y que podrían coincidir con el destino elegido. </p> <p>Esta métrica es útil porque muestra: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> The size of the total addressable audience that <span class="keyword"> Audience Manager</span> can reach on a particular targeting destination. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">How big the <span class="keyword"> Audience Manager</span> profile pool is for a targeting platform and the size of their audiences. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comparing Customer and Segment Addressable Audiences{#comparing-metrics}

You shouldn't compare the [!UICONTROL Customer Addressable Audience] and [!UICONTROL Segment Addressable Audience] metrics to determine if one is more significant than the other. Son métricas independientes, diferentes e independientes. Como se describe en las definiciones anteriores, cada una de ellas proviene de conjuntos de datos diferentes. En este caso, debe evitar derivar conclusiones si una métrica es más grande que la otra. Lo único que puede decirse al comparar es que:

* [!UICONTROL Customer Addressable Audiences] se basa en características de características *para sus propios datos de origen*. Esta métrica proporciona una vista amplia y exhaustiva de la integración con un socio de datos.

* [!UICONTROL Segment Addressable Audiences] se basa en los requisitos de segmentos *para sus propios datos de origen, además de datos de segundo y tercero*. Esta métrica proporciona una vista granular y precisa de las audiencias direccionables en una plataforma de segmentación.

## Causes of Low Match Rates for Addressable Audiences {#low-match-rates}

Common elements responsible for low [!UICONTROL Addressable Audience] match rates or discrepancies in reported numbers.

<!-- addressable-audiences.xml -->

<table id="table_895D536F69134330A4F13887ECAFD4F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Causa </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Tráfico móvil</b> </p> </td> 
   <td colname="col2"> <p>La mayoría de las integraciones de servidor a servidor dependen de procesos de sincronización facilitados por cookies de terceros. Sin embargo, los entornos móviles no utilizan cookies de terceros. Como resultado, los números de audiencia direccionable pueden parecer bajos en comparación con el tamaño del segmento. </p> <p>Desde enero de 2018, puede activar audiencias móviles en los mismos destinos de Google y Adobe Advertising Cloud configurados para audiencias basadas en cookies. Aunque esto significa que puede enviar segmentos con un ID de cookie móvil y cookie combinado a los destinos de Google y Marketing Cloud, tenga en cuenta que las audiencias objetivo solo muestran la superposición entre ID de cookies y destinos. Audience Manager envía el 100% de audiencias móviles a destinos, pero las audiencias móviles no se miden con la métrica Audiencia direccionable. </p> <p> <p><b>Nota</b>: Por ejemplo, tome un segmento con una población de 1000.000. Si asigna este segmento a un destino de Google o Adobe Advertising Cloud, puede ver una Audiencia direccionable de 700 000 dispositivos y una tasa de coincidencia del 70%. La pertenencia a 700.000 consiste en ID de cookies que tienen una sincronización de ID con el destino. Su audiencia direccionable puede ser, de hecho, mucho más alta, ya que los ID móviles direccionables no aparecen en esta métrica. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tráfico Safari</b> </p> </td> 
   <td colname="col2"> <p>Safari bloquea las cookies de terceros. Esto evita que Audience Manager sincronice los ID con el destino. With the introduction of <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, you can expect your addressable audiences not to include Safari users. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Impresiones de medios rastreados</b> </p> </td> 
   <td colname="col2"> <p>Debido a las optimizaciones del servidor de publicidad, las sincronizaciones de ID no se realizan dentro de las etiquetas de publicidad. Los clientes que realizan una gran cantidad de publicidad fuera del sitio no sincronizarán a los usuarios con integraciones de terceros en esos entornos. Además, una gran cantidad de datos de impresión de medios recopilados podría reducir los números de audiencia direccionables. </p> </td>
  </tr> 
 </tbody> 
</table>

## Troubleshooting with Addressable Audiences {#troubleshooting}

In addition to surfacing match rates, you can also use [!UICONTROL Addressable Audiences] as a troubleshooting tool.

<!-- addressable-audiences-troubleshooting.xml -->

Por ejemplo, supongamos que envía un segmento a un destino y que el destino muestra los números bajos de los informes. Checking the [!UICONTROL Addressable Audience] results will show you if this is a technical problem or just a case of low match rates. Una tasa de coincidencia baja muestra que el destino no es tan maravilloso para los segmentos seleccionados. Sin embargo, una diferencia en los números de audiencia direccionables totales entre Audience Manager y el destino indica una integración, sincronización u otro problema técnico. En estos casos, póngase en contacto con el administrador de cuentas.