---
description: Los archivos de registro procesables le permiten capturar señales de medios de archivos de registro del servidor de publicidad para crear características en Audience Manager. Capture impresiones, clics y conversiones de servidores de publicidad como rasgos sin tener que anexar píxeles.
keywords: registros procesables, alf, ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: Archivos de registro procesables
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: b3f97cfbbd5167f03a6951fcc571368e4a0d15a4
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 3%

---

# Archivos de registro procesables {#actionable-log-files}

[!UICONTROL Actionable Log Files] permite capturar datos de medios de archivos de registro del servidor de publicidad y utilizar los datos para crear características en Audience Manager. Capturar impresiones, clics y conversiones de servidores de publicidad como rasgos sin tener que anexar [píxeles](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *cursiva*, paréntesis `[ ]` `( )`, etc.) en este documento, indique los elementos y las opciones de código. Consulte [Convenciones de estilo para elementos de código y texto](../../reference/code-style-elements.md) para obtener más información.

## Finalidad {#purpose}

[!UICONTROL Actionable Log Files] agiliza la forma de capturar impresiones, clics y conversiones desde los servidores de publicidad. Utilice esta información para la segmentación de usuarios sin tener que pixelar manualmente los medios para enviar atributos de campaña a [!DNL Audience Manager].

## Primeros pasos {#getting-started}

Para empezar con [!UICONTROL Actionable Log Files], debe importar los datos de registro en [!DNL Audience Manager]. Los siguientes vínculos le ayudarán a empezar:

* Para [!UICONTROL Google Campaign Manager] registros, consulte [Importación De Archivos De Datos Del Administrador De Google Campaign En Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *y* póngase en contacto con su [!DNL Audience Manager] consultor.
* Para [!UICONTROL Google Ad Manager] (anteriormente DFP de Google), consulte [Importar Archivos De Datos De Google Ad Manager En Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *y* póngase en contacto con su [!DNL Audience Manager] consultor.
* Para ver otros registros del servidor de publicidad, consulte [Archivos de datos y metadatos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *y* póngase en contacto con su [!DNL Audience Manager] consultor.

Si ya está importando datos de registro en [!DNL Audience Manager], pregunte a su [!DNL Audience Manager] consultor o [Atención al cliente](https://helpx.adobe.com/es/contact/enterprise-support.ec.html) para habilitar [!UICONTROL Actionable Log Files] para usted.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## Trabajar con archivos de registro procesables {#working-with-actionable-log-files}

Con [!UICONTROL Actionable Log Files], la información de los registros del servidor de publicidad se captura en [!DNL Audience Manager] del mismo modo que capturaría datos de interacciones del sitio web en tiempo real. [!DNL Audience Manager] se conecta al almacenamiento de registros del servidor de publicidad, analiza la información de los registros y envía los datos de registro como señales procesables a nuestro [Servidores de recopilación de datos](../../reference/system-components/components-data-collection.md#dcs-pcs).

Aún debe configurar rasgos basados en reglas para capturar las señales procesables. Consulte cómo configurar rasgos basados en reglas en la [Interfaz de usuario del Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) o utilizando nuestro [Herramientas de administración masiva](../../reference/bulk-management-tools/bulk-create.md). Desplácese hacia abajo hasta el [Señales procesables](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) para obtener una lista de todas las claves que se pueden utilizar en rasgos basados en reglas.

>[!IMPORTANT]
>
>Recomendamos implementar [!UICONTROL Actionable Log Files] *en lugar de*  [Llamadas en píxeles](../../integration/media-data-integration/impression-data-pixels.md). Desaconsejamos el uso de ambas opciones, ya que esto conduce a un aumento en los recuentos de frecuencia para los rasgos.

## Señales procesables {#actionable-signals}

Las señales son [unidades de datos más pequeñas](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] permite capturar los valores de anunciante, unidad empresarial, creativo y de campaña en eventos de impresión, eventos de clic y eventos de conversión como señales de los registros del servidor de publicidad.

>[!IMPORTANT]
>
>[!UICONTROL Actionable Log Files] son compatibles con los siguientes servidores de publicidad:
> <br>
>
> * [Administrador de Google Campaign](#dcm-logs-signals)
> * [Google Ad Manager](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud, Flashtalk y Sizmek](#generic-logs-signals)


Recuerde que, para utilizar esta información para la creación y segmentación de audiencias, debe configurar usted mismo los rasgos basados en reglas.

### Señales procesables desde los registros de Google Campaign Manager {#dcm-logs-signals}

La tabla enumera las señales procesables de [!DNL Google Campaign Manager] archivos de registro:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre del encabezado en el archivo de registro </th> 
   <th colname="col2" class="entry"> Señal </th> 
   <th colname="col3" class="entry"> Descripción </th> 
   <th colname="col4" class="entry"> Valor de ejemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>Disponible solo para eventos de conversión. </p> <p>Representa el ID numérico para la actividad de conversión en el Administrador de campañas de Google. Este campo se asigna al ID de actividad desde el Administrador de Google Campaign. </p> <p> <p>Sugerencia: puede capturar varias actividades de conversión o actividades específicas desde el Administrador de campañas de Google. Creación de rasgos mediante <code> d_conversion = activity ID</code> para cada actividad de conversión desde el Administrador de Google Campaign. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Disponible solo para eventos de conversión. </p> <p>Este campo se asigna al ID de conversión en el Administrador de Google Campaign. Indica la actividad anterior a la conversión del usuario desde el Administrador de Google Campaign. </p> <p>Los valores aceptados son: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> para conversiones posteriores al clic. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> para conversiones posteriores a la impresión. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> para conversiones que no coinciden. La conversión no puede coincidir con una actividad anterior. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Una fecha y hora UTC para el evento de impresión, clic o conversión. Representado en microsegundos desde 1970-01-01 00:00:00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Un código de integración para la fuente de datos del anunciante. Tenga en cuenta que esto no está relacionado con las fuentes de datos de Audience Manager.</p> <p>Este campo se asigna al ID del grupo de anunciantes desde el administrador de Google Campaign. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>ID de unidad de negocio. Este campo se asigna al ID del anunciante desde el administrador de Google Campaign. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>El ID de campaña proporcionado por el administrador de Google Campaign.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>El ID creativo proporcionado por el administrador de Google Campaign. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> El importe de ventas en USD, a la potencia de -6. Multiplicar por 1.000.000 para ver como una cantidad de dólar.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indica el tipo de evento. El Audience Manager lee el tipo de evento del nombre del archivo de registro de Google Campaign Manager y lo transforma en una señal procesable. </p> <p>Los valores aceptados son: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> para impresiones. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> para clics. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> para conversiones. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>El ID de la fuente de datos que utiliza para capturar los datos de Google Campaign Manager. Consulte <a href="../../features/manage-datasources.md#create-data-source"> Cómo crear una fuente de datos</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Las señales descritas en la tabla se capturan en [!DNL Audience Manager] como en tiempo real `HTTP` llamada. La llamada de ejemplo siguiente contiene información sobre un evento de conversión de [!DNL Google Campaign Manager]. Las llamadas no tienen que incluir necesariamente *todo* las señales de la llamada de ejemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Para un tamaño medio [!DNL Google Campaign Manager] archivo de registro de 2 millones de líneas, cualquier rasgo creado a partir de señales procesables se realiza en aproximadamente una hora después de procesar los registros.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>La marca de tiempo del evento proporcionada en la variable [!DNL Google Campaign Manager] Los registros se respetarán y pasarán al [!UICONTROL Data Collection Servers].
>
>* Si una marca de tiempo no está disponible para una fila de datos en la [!DNL Google Campaign Manager] archivo de registro, utilizamos la hora del `HTTP` llame a como marca de tiempo del evento.
>* Si la fila de datos de [!DNL Google Campaign Manager] Si el archivo de registro contiene una marca de tiempo mal formada, se ignora toda la fila.


<br> 

### Señales procesables de [!DNL Google Ad Manager] registros {#ad-manager-logs-signals}

La tabla enumera las señales procesables de [!DNL Google Ad Manager] archivos de registro:


| Nombre del encabezado en el archivo de registro | Señal | Descripción |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | El ID numérico para el elemento de línea del administrador de publicidad entregado |
| `OrderId` | `d_orderid` | El ID numérico del pedido del Administrador de publicidad que contenía el elemento de línea entregado y el creativo. |
| `CreativeId` | `d_creative` | ID numérico para el creativo del administrador de publicidad enviado. |
| `-` | `d_event` | Indica el tipo de evento. El Audience Manager lee el tipo de evento del nombre del archivo de registro del Administrador de publicidad y lo transforma en una señal procesable. Los valores aceptados son: <br> <ul><li>d_event = imp para impresiones.</li><li>d_event = clic para clics.</li><li>d_event = conv para conversiones y actividades.</li></ul> |
| `-` | `d_src` | El ID de la fuente de datos que utiliza para capturar los datos del Administrador de publicidad. Consulte [Cómo crear una fuente de datos](/help/using/features/manage-datasources.md). |

Las señales que se describen en la tabla se capturan en Audience Manager como una llamada HTTP en tiempo real. La llamada de ejemplo siguiente contiene información sobre un evento de conversión de Google Ad Manager. Las llamadas de no tienen que incluir necesariamente todas las señales de la llamada de ejemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>La marca de tiempo del evento proporcionada en la variable [!DNL Google Ad Manager] Los registros se respetarán y pasarán al [!UICONTROL Data Collection Servers].
>
>
>* Si una marca de tiempo no está disponible para una fila de datos en la [!DNL Google Ad Manager] archivo de registro, utilizamos la hora del `HTTP` llame a como marca de tiempo del evento.
>* Si la fila de datos de [!DNL Google Ad Manager] Si el archivo de registro contiene una marca de tiempo mal formada, se ignora toda la fila.


<br> 

### Señales procesables de los registros de Adobe Advertising Cloud, Flashtalk y Sizmek ad server {#generic-logs-signals}

En primer lugar, debe depositar los registros de su servidor de publicidad en nuestros bloques de Amazon S3. Para lograr esto, lea [Archivos de datos para informes de Audience Optimization y archivos de registro procesables](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *y* póngase en contacto con su [!DNL Audience Manager] consultor. En la tabla se enumeran las señales procesables de los archivos de registro del servidor de publicidad:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre del encabezado en el archivo de registro </th> 
   <th colname="col2" class="entry"> Señal </th> 
   <th colname="col3" class="entry"> Descripción </th> 
   <th colname="col4" class="entry"> Valor de ejemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Indica si una conversión coincide o no. Las opciones incluyen: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> Impresión </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> Haga clic </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> Sin atribuir o desconocido </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> Una fecha y hora UTC para el evento de impresión, clic o conversión. Utilice el <code>yyyy-MM-dd HH:mm:ss</code> formato. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Un código de integración para la fuente de datos del anunciante. Observe que este campo no está relacionado con <a href="../../features/datasources-list-and-settings.md">Fuentes de datos del Audience Manager.</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>ID de unidad de negocio.  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>ID de campaña del archivo de registro.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>El ID del creativo del archivo de registro. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Importe de compra u otro importe de conversión. Tipo de datos: Flotante. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indica el tipo de evento. El Audience Manager lee el tipo de evento del nombre del archivo de registro y lo transforma en una señal procesable. Consulte <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">Convenciones de nomenclatura de archivos de registro</a>. </p> <p>Los valores aceptados son: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> para impresiones. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> para clics. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> para conversiones. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>El ID de la fuente de datos utilizada para capturar los datos de registro. Consulte <a href="../../features/manage-datasources.md#create-data-source"> Cómo crear una fuente de datos</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Las señales descritas en la tabla se capturan en [!DNL Audience Manager] como en tiempo real `HTTP` llamada. Las llamadas no tienen que incluir necesariamente *todo* las señales de la llamada de ejemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Uso de señales procesables en la interfaz de usuario del Audience Manager {#actionable-signals-in-ui}

Puede ver las señales procesables entrantes en el [Búsqueda de señales](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) interfaz.

Ir a **Datos de audiencia** (1) > **Señales** (2) > **Buscar** (3) y seleccione la **Archivos de registro procesables** (4) filtro.

![Señales procesables en la IU](/help/using/integration/assets/alf-in-signals.png)

Para crear rasgos basados en reglas utilizando las señales procesables, seleccione **Archivos de registro procesables** (1), seleccione las señales procesables que desee utilizar como reglas de rasgos (2) y pulse **Crear característica a partir de señales seleccionadas** (3).

![Creación de rasgos a partir de señales](/help/using/integration/assets/alf-create-trait.png)


## Casos de uso {#use-cases}

Una ventaja de la implementación [!UICONTROL Actionable Log Files] es la opción que se debe aplicar [actualización y frecuencia](../../features/segments/recency-and-frequency.md) controles a cualquier [rasgos basados en reglas](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) que contienen señales procesables. Esto le permite, por ejemplo, limitar la frecuencia del número de veces que se muestra a un usuario un creativo en particular, dentro de una campaña de medios. Leer [Eliminación instantánea entre dispositivos](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) para aprender a hacer esto. Otros casos de uso incluyen:

### Redestinar usuarios

Reasigne a los usuarios que vieron Creative 123 pero no hicieron clic ni convirtieron y muéstreles Creative 456. Haga esto:

1. Cree un rasgo para capturar a los usuarios que vieron al creativo. Digamos que nombras el rasgo [!DNL Creative Trait 123]. Utilice la regla de rasgos:

   `d_creative == 123 AND d_event == imp`

2. Cree una característica para capturar a los usuarios que hacen clic o convierten. Digamos que le das nombre a este [!DNL Click and Converter]. Utilice la regla de rasgos:

   `d_event == click OR d_event=conv`

3. Cree un segmento para rellenar con usuarios que vieron el elemento creativo 123, pero que no hicieron clic ni convirtieron. Asígnele un nombre [!DNL Retarget Users] y utilice la regla de segmento:

   `Creative Trait 123 AND NOT Click and Converter`

4. Asignación del segmento [!DNL Retarget Users] a un destino y dirija a los usuarios en el destino con creative 456.

### Uso de la actividad de Floodlight de Google Campaign Manager en los informes de Audience Optimization o en Audience Lab

[Etiquetas de Floodlight](https://support.google.com/dcm/partner/answer/4293719?hl=en) permitir que los anunciantes realicen un seguimiento de las conversiones de usuarios. Con [!UICONTROL Actionable Log Files], puede realizar el seguimiento de [!DNL Google Campaign Manager] conversiones en el [Informes del Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md) o en [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Cree un rasgo y utilice la siguiente regla de rasgos para capturar una conversión de los registros del servidor de publicidad:

   `d_event == conv AND d_conversion == 123`

   Al crear la característica en el Audience Manager [!UICONTROL UI], seleccione [!UICONTROL Conversion] como el [!UICONTROL Event Type].

2. Una vez creado el rasgo, se empezará a informar de la conversión en el [!UICONTROL Audience Optimization Reports] y en [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importación De Archivos De Datos Del Administrador De Google Campaign En Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Informes de optimización de Audiencia](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

