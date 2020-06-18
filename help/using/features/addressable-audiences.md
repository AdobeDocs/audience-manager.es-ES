---
description: Información general sobre la función de Audiencia direccionable y los casos de uso.
keywords: DIL
seo-description: Información general sobre la función de Audiencia direccionable y los casos de uso.
seo-title: Audiencias a las que se puede dirigir
solution: Audience Manager
title: Audiencias a las que se puede dirigir
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '2059'
ht-degree: 0%

---


# Audiencia direccionable {#addressable-audiences}

Información general sobre la función y los casos de uso [!UICONTROL Addressable Audience] .

## ¿Qué es una Audiencia direccionable? {#addressable-audience-description}

La [!UICONTROL Addressable Audiences] función muestra la superposición entre las audiencias que ve en todas las propiedades donde [!DNL Audience Manager] recopila datos y el destino seleccionado. Para ayudarle a comprender este concepto, eche un vistazo a la siguiente ilustración. La superposición entre cada círculo representa los diferentes tipos de audiencias direccionables.

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
   <td colname="col2"> <p>Recuento de todos los dispositivos que han interactuado con todos los clientes Audience Manager a nivel de plataforma durante el período de retrospectiva del informe y que se pueden comparar con el destino elegido. </p> <p>Esta métrica es útil porque muestra: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> El tamaño de la audiencia direccionable total a la que puede llegar el <span class="keyword"> Audience Manager</span> en un destino determinado. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Qué tamaño tiene el grupo de perfiles <span class="keyword"> Audience Manager</span> para una plataforma de objetivo y el tamaño de sus audiencias. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audiencia total del cliente</b> </p> </td> 
   <td colname="col2"> <p>Recuento de dispositivos que han realizado una característica basada en reglas en sus propiedades o una característica integrada de los archivos sin conexión durante la ventana retroactiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasa de coincidencia de Audiencias direccionables</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Recuento de superposición de dispositivos que han adquirido una característica basada en reglas o una característica incorporada durante la ventana retroactiva y dispositivos que tienen una sincronización de ID con el destino elegido independientemente del tiempo de sincronización. </p> 
    </draft-comment> <p>Esta métrica representa los dispositivos que: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Se han realizado características basadas en reglas o integradas durante la ventana retroactiva <b>Y</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Haga una sincronización de ID con el destino elegido independientemente del tiempo de sincronización. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasa de coincidencia del cliente</b> </p> </td> 
   <td colname="col2"> <p>Audiencia direccionable al cliente ÷ Audiencia total del cliente expresada como porcentaje. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>Población total del segmento</b> </p> </td> 
   <td colname="col2"> <p>Recuento de todos los dispositivos que eran miembros del segmento durante el período de retroceso del informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audiencia direccionable del segmento</b> </p> </td> 
   <td colname="col2"> <p>El número de usuarios que han pertenecido al segmento durante el período de retroactividad del informe y que tienen una sincronización de ID activa en el sitio. Los segmentos pueden incluir sus propios datos de origen y datos de terceros y de terceros, a través de las características adquiridas en el <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Sugerencia: Cuando se utiliza con el período retrospectivo de 1 día, esta métrica puede ayudarle a comprender el estado actual de los segmentos. Esto se debe a que la métrica de Audiencia <span class="wintitle"></span> Segmento direccionable representa a los usuarios que permanecieron en un segmento durante el día anterior. Combinar esto con el hecho de que el <span class="keyword"> Audience Manager</span> actualiza diariamente las Audiencias <span class="wintitle"> direccionables</span> , la combinación de esta métrica y el período retrospectivo proporciona la instantánea más actualizada de los segmentos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasa de coincidencia de segmentos</b> </p> </td> 
   <td colname="col2"> <p>Audiencia direccionable del segmento ÷ Población total del segmento expresada como porcentaje. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Interfaz de Audiencia direccionable {#addressable-audience-interface}

La [!UICONTROL Addressable Audience] característica convierte este concepto abstracto en datos cuantificables. En [!DNL Audience Manager], esta función muestra solapamiento de audiencia con visualizaciones de datos que proporcionan información de un vistazo junto con datos numéricos en forma de tabla.

[!UICONTROL Addressable Audiences] en **[!UICONTROL Audience Data > Destinations]**. Seleccione **[!UICONTROL Integrated Platforms > Device-Based]** para ver las métricas de audiencias direccionables.

![](assets/addressable-audiences-landing.png)

Las tres métricas que puede ver en la [!UICONTROL Addressable Audiences] página de aterrizaje representan:

| Métrica | Descripción |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Esta métrica representa la [!UICONTROL Customer Addressable Audience] (descrita en la tabla anterior) *de los últimos 30 días.* |
| **[!UICONTROL Match Rate]** | Esta métrica representa la [!UICONTROL Addressable Audience Match Rate] (descrita en la tabla anterior) *de los últimos 30 días*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Recuento de todos los dispositivos que han interactuado con todos [!DNL Audience Manager] los clientes a nivel de plataforma durante el período de retrospectiva del informe y que podrían coincidir con este destino. Consulte Métricas [de nivel de](/help/using/features/addressable-audiences.md#platform-level-metrics) Platform para obtener más información. |

Haga clic en el nombre de un destino de servidor a servidor para vista de los datos de audiencia direccionables. Tenga en cuenta que esta función devuelve datos solo para destinos de servidor a servidor y el acceso requiere permisos de administrador.

![](assets/addressableAudiences.png)

La revisión de estos datos puede ayudarle con:

* **Previsión y planificación:** [!UICONTROL Segment Addressable Audience] los datos le proporcionan más granularidad en los segmentos que está planeando enviar a un destino para la segmentación de audiencias y la activación.

* **Reseñas del rendimiento:** La [!UICONTROL Addressable Audiences] función también es una herramienta de resolución de problemas. Le permite revisar el rendimiento de la campaña, comprender el alcance de la campaña y realizar comprobaciones cruzadas con socios de objetivo/activación si no ve los resultados esperados.

### Prospecting con datos de terceros e implicaciones para tasas de coincidencia

Antes de comprar datos de terceros para la adquisición de audiencias, los clientes pueden validar la superposición con otros proveedores de datos. Esto puede ayudarle a tomar una decisión informada antes de comprar nuevos datos. La sincronización de ID para los datos de terceros adquiridos no solo depende de la superposición de los datos, sino también de las huellas de los proveedores de terceros con el resto de los [!DNL Audience Manager] clientes. El [!DNL Adobe] consultor puede ayudarle a identificar fuentes de datos relevantes adicionales para optimizar las campañas de prospección.

### Usuarios móviles y tasas de coincidencia

Hay huecos al intentar conectar [!DNL Safari] o a los usuarios de aplicaciones móviles en los que no hay cookies de terceros presentes. Esto dificulta la sincronización de los usuarios con algunos socios, ya que en los registros de envío de medios solo se proporcionan [!DNL Adobe] los ID de cookies de terceros sincronizadas. Por este motivo, es posible que vea tasas [de coincidencia](../features/addressable-audiences.md#low-match-rates) bajas para los destinos.

## Intervalos de fechas en Audiencias y destinos abordables {#date-ranges}

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

## Métricas de Audiencia direccionables {#addressable-audience-metrics}

Esta sección describe los tipos de métricas que proporciona [!UICONTROL Addressable Audiences].

### Métricas de nivel de cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Estas métricas devuelven datos de características realizadas cuando los visitantes llegan a su sitio o cuando envía archivos de datos de entrada a [!DNL Audience Manager]. Estas métricas proporcionan una vista completa del tamaño de audiencia de su cuenta.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audiencia direccionable al cliente</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Recuento de superposición de dispositivos que han adquirido una característica basada en reglas o una característica incorporada durante la ventana retroactiva y dispositivos que tienen una sincronización de ID con el destino elegido independientemente del tiempo de sincronización. </p> 
    </draft-comment> <p>Esta métrica representa los dispositivos que: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Se han realizado características basadas en reglas o integradas durante la ventana retroactiva <b>Y</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Haga una sincronización de ID con el destino elegido independientemente del tiempo de sincronización. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audiencia total del cliente</b> </p> </td> 
   <td colname="col2"> <p>Recuento de dispositivos que han realizado una característica basada en reglas en sus propiedades o una característica integrada de los archivos sin conexión durante la ventana retroactiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasa de coincidencia del cliente</b> </p> </td> 
   <td colname="col2"> <p>Audiencia direccionable al cliente ÷ Audiencia total del cliente expresada como porcentaje. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Métricas de coincidencia de nivel de segmento {#segment-level-metrics}

Estas métricas devuelven datos sobre la pertenencia a segmentos. Ayudan a proporcionar una vista más granular y precisa del tamaño de la audiencia para cada uno de los segmentos.

>[!NOTE]
>
>La forma en que se aplica la ventana retroactiva en el nivel de segmento es diferente a la del cliente. Los Visitantes pueden llegar al sitio y darse cuenta de una característica hace 10 días, y desde entonces pueden calificar para un segmento y retirarse del segmento hace 2 días. Cuando se aplica la retrospectiva de 7 días, estos visitantes se contabilizarán en el nivel de segmento pero no en el nivel de cliente.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audiencia direccionable del segmento</b> </p> </td> 
   <td colname="col2"> <p>El número de usuarios que han pertenecido al segmento durante el período de retroactividad del informe y que tienen una sincronización de ID activa en el sitio. Los segmentos pueden incluir sus propios datos de origen y datos de terceros y de terceros, a través de las características adquiridas en el <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Sugerencia: Cuando se utiliza con el período retrospectivo de 1 día, esta métrica puede ayudarle a comprender el estado actual de los segmentos. Esto se debe a que la métrica de Audiencia <span class="wintitle"></span> Segmento direccionable representa a los usuarios que permanecieron en un segmento durante el día anterior. Combinar esto con el hecho de que el <span class="keyword"> Audience Manager</span> actualiza diariamente las Audiencias <span class="wintitle"> direccionables</span> , la combinación de esta métrica y el período retrospectivo proporciona la instantánea más actualizada de los segmentos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Población total del segmento</b> </p> </td> 
   <td colname="col2"> <p>Recuento de todos los dispositivos que eran miembros del segmento durante el período de retroceso del informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasa de coincidencia de segmentos</b> </p> </td> 
   <td colname="col2"> <p>Audiencia direccionable del segmento ÷ Población total del segmento expresada como porcentaje. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Métricas de nivel Platform {#platform-level-metrics}

Esta métrica devuelve datos sobre actividades recopiladas en todos los [!DNL Audience Manager] clientes. Pueden proporcionar una vista más amplia de la audiencia del cliente en comparación con los [!DNL Audience Manager] clientes agregados.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audiencia direccionable de Audience Manager</b> </p> </td> 
   <td colname="col2"> <p>Recuento de todos los dispositivos que han interactuado con todos los clientes Audience Manager a nivel de plataforma durante el período de retrospectiva del informe y que se pueden comparar con el destino elegido. </p> <p>Esta métrica es útil porque muestra: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> El tamaño de la audiencia direccionable total a la que puede llegar el <span class="keyword"> Audience Manager</span> en un destino determinado. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Qué tamaño tiene el grupo de perfiles <span class="keyword"> Audience Manager</span> para una plataforma de objetivo y el tamaño de sus audiencias. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comparación de Audiencias a las que puede dirigirse el cliente y el segmento{#comparing-metrics}

No debe comparar las métricas [!UICONTROL Customer Addressable Audience] y [!UICONTROL Segment Addressable Audience] para determinar si una es más significativa que la otra. Son métricas independientes, diferentes e independientes. Como se describe en las definiciones anteriores, cada una de ellas se deriva de diferentes conjuntos de datos. Dado esto, debe evitar extraer conclusiones si una métrica es más grande que la otra. Todo lo que se puede decir al comparar esto es que:

* [!UICONTROL Customer Addressable Audiences] se basa en la realización *de características de sus propios datos* de origen. Esta métrica proporciona una vista amplia y completa de la integración con un socio de datos.

* [!UICONTROL Segment Addressable Audiences] se basa en las cualificaciones de los segmentos *para sus propios datos de origen, además de los datos* de terceros y de segundo nivel. Esta métrica proporciona una vista granular y más precisa de sus audiencias direccionables en una plataforma de segmentación.

## Causas de bajas tasas de coincidencia para Audiencias direccionables {#low-match-rates}

Elementos comunes responsables de bajas tasas de [!UICONTROL Addressable Audience] coincidencia o discrepancias en los números notificados.

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
   <td colname="col2"> <p>La mayoría de las integraciones de servidor a servidor dependen de procesos de sincronización facilitados por cookies de terceros. Sin embargo, los entornos móviles no utilizan cookies de terceros. Como resultado, los números de Audiencia objetivo pueden parecer bajos en comparación con el tamaño del segmento. </p> <p>A partir de enero de 2018, puede activar audiencias móviles en los mismos destinos de Google y Adobe Advertising Cloud configurados para audiencias basadas en cookies. Aunque esto significa que puede enviar segmentos con una pertenencia combinada a cookies e ID de móvil a los destinos de Google y Advertising Cloud, tenga en cuenta que las Audiencias direccionables solo muestran la superposición entre ID de cookies y destinos. Audience Manager envía el 100 % de las audiencias móviles a los destinos, pero las audiencias móviles no se miden mediante la métrica Audiencia direccionable. </p> <p> <p><b>Nota</b>:  Por ejemplo, tomemos un segmento con una población de 1.000.000 habitantes. Si asigna este segmento a un destino de Google o Adobe Advertising Cloud, es posible que vea una Audiencia direccionable de 700.000 dispositivos y una tasa de coincidencia del 70%. La membresía de 700.000 consiste en ID de cookies que tienen una sincronización de ID con el destino. La Audiencia a la que se puede dirigir puede ser, de hecho, mucho mayor, porque los ID de dispositivos móviles direccionables no aparecen en esta métrica. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tráfico de Safari</b> </p> </td> 
   <td colname="col2"> <p>Safari bloquea las cookies de terceros. Esto evita que el Audience Manager sincronice los ID con el destino. Con la introducción de <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, puede esperar que sus audiencias direccionables no incluyan usuarios de Safari. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Impresiones de medios rastreados</b> </p> </td> 
   <td colname="col2"> <p>Debido a las optimizaciones del servidor de publicidad, las sincronizaciones de ID no se realizan dentro de las etiquetas de publicidad. Los clientes que realizan una gran cantidad de publicidad fuera del sitio no sincronizarán a los usuarios con integraciones de terceros en esos entornos. Además, una gran cantidad de datos de impresión de medios recopilados podría reducir los números de audiencia direccionables. </p> </td>
  </tr> 
 </tbody> 
</table>

## Resolución de problemas con Audiencias direccionables {#troubleshooting}

Además de las tasas de coincidencia de superficie, también puede utilizar [!UICONTROL Addressable Audiences] como herramienta de resolución de problemas.

<!-- addressable-audiences-troubleshooting.xml -->

Por ejemplo, supongamos que envía un segmento a un destino y que ese destino muestra números de sistema de informes bajos. Si se seleccionan los [!UICONTROL Addressable Audience] resultados, se le mostrará si se trata de un problema técnico o sólo de un caso de tasas de coincidencia bajas. Una tasa de coincidencia baja muestra que el destino no es tan bueno para los segmentos seleccionados. Sin embargo, una diferencia en los números de audiencia direccionables totales entre [!DNL Audience Manager] y el destino indica un problema de integración, sincronización u otro problema técnico. En estos casos, póngase en contacto con su administrador de cuentas.