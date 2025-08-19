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
source-wordcount: '1601'
ht-degree: 2%

---

# Archivos de registro procesables {#actionable-log-files}

[!UICONTROL Actionable Log Files] le permite capturar datos de medios de archivos de registro del servidor de publicidad y utilizar los datos para crear características en Audience Manager. Capturar impresiones, clics y conversiones de servidores de publicidad como rasgos sin tener que anexar [píxeles](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Los estilos de texto (`monospaced text`, *cursiva*, corchetes `[ ]` `( )`, etc.) de este documento indican elementos y opciones de código. Consulte [Convenciones de estilo para elementos de código y texto](../../reference/code-style-elements.md) para obtener más información.

## Finalidad {#purpose}

[!UICONTROL Actionable Log Files] Optimice la forma en que captura impresiones, clics y conversiones de los servidores de anuncios. Utilice esta información para usuario segmentación sin tener que pixelar manualmente las medios para enviar campaña atributos a [!DNL Audience Manager].

## Primeros pasos {#getting-started}

Para empezar con [!UICONTROL Actionable Log Files], debe importar los datos de registro en [!DNL Audience Manager]. Los siguientes vínculos le ayudarán a empezar:

* Para obtener [!UICONTROL Google Campaign Manager] registros, consulte [Importar Archivos de datos de Google Campaign Manager en Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *y* póngase en contacto con su [!DNL Audience Manager] consultor.
* Para los registros de [!UICONTROL Google Ad Manager] (anteriormente DFP de Google), consulte [Importar archivos de datos de Google Ad Manager en Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *y* póngase en contacto con su consultor de [!DNL Audience Manager].
* Para ver otros registros del servidor de publicidad, consulta [Archivos de metadatos y datos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *y*, ponte en contacto con tu consultor de [!DNL Audience Manager].

Si ya está importando datos de registro en [!DNL Audience Manager], pídale al asesor de [!DNL Audience Manager] o al [Servicio de atención al cliente](https://helpx.adobe.com/es/contact/enterprise-support.ec.html) que habiliten [!UICONTROL Actionable Log Files].

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/es/contact/enterprise-support.ec.html) to get started.

-->

## Trabajar con archivos de registro procesables {#working-with-actionable-log-files}

Con [!UICONTROL Actionable Log Files], la información de los registros de servidor de anuncios se captura de [!DNL Audience Manager] la misma manera que capturaría los datos de las interacciones del sitio web en tiempo real. [!DNL Audience Manager] se conecta a su almacenamiento de registro de servidor de anuncios, analiza la información de los registros y envía los datos de registro como señales procesables a nuestros [servidores](../../reference/system-components/components-data-collection.md#dcs-pcs) de recopilación de datos.

Aún debe configurar rasgos basados en reglas para capturar las señales procesables. Consulte cómo configurar rasgos basados en reglas en la [interfaz de usuario de Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) o con nuestras [herramientas de administración en lotes](../../reference/bulk-management-tools/bulk-create.md). Desplácese hacia abajo hasta la sección [Señales procesables](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) para obtener una lista de todas las claves que puede usar en características basadas en reglas.

>[!IMPORTANT]
>
>Se recomienda implementar [!UICONTROL Actionable Log Files] *en lugar de* [llamadas de píxel](../../integration/media-data-integration/impression-data-pixels.md). Desaconsejamos el uso de ambas opciones, ya que esto conduce a un aumento en los recuentos de frecuencia para los rasgos.

## Señales procesables {#actionable-signals}

Las señales son las [unidades de datos más pequeñas](../../reference/signal-trait-segment.md) en [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] le permite capturar los valores de anunciante, unidad de negocio, creatividad y campaña en eventos de impresión, eventos de clic y eventos de conversión como señales de los registros del servidor de publicidad.

>[!IMPORTANT]
>
>[!UICONTROL Actionable Log Files] son compatibles con los siguientes servidores de publicidad:
>&#x200B;> <br>
>
> * [Administrador de Google Campaign](#dcm-logs-signals)
> * [Administrador de anuncios de Google](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud, FlashTalk y Sizmek](#generic-logs-signals)

Recuerde que, para utilizar esta información para la creación y segmentación de audiencias, debe configurar usted mismo los rasgos basados en reglas.

### Señales procesables desde los registros de Google Campaign Manager {#dcm-logs-signals}

En la tabla se enumeran las señales procesables de [!DNL Google Campaign Manager] archivos de registro:

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
   <td colname="col3"> <p>Disponible solo para eventos de conversión. </p> <p>Representa el ID numérico para la actividad de conversión en el Administrador de campañas de Google. Este campo se asigna al ID de actividad desde el Administrador de Google Campaign. </p> <p> <p>Sugerencia: puede capturar varias actividades de conversión o actividades específicas desde el Administrador de campañas de Google. Cree características con <code> d_conversion = activity ID</code> para cada actividad de conversión desde el Administrador de campañas de Google. </p> </p> </td> 
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
   <td colname="col3"> <p>El Creative ID proporcionado por el administrador de Google Campaign. </p> </td> 
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
   <td colname="col3"> <p>Indica el tipo de evento. Audience Manager lee el tipo de evento del nombre del archivo de registro de Google Campaign Manager y lo transforma en una señal procesable. </p> <p>Los valores aceptados son: </p> <p> 
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
   <td colname="col3"> <p>El ID de la fuente de datos que utiliza para capturar los datos de Google Campaign Manager. Ver <a href="../../features/manage-datasources.md#create-data-source"> Cómo crear un Source de datos</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Las señales descritas en la tabla se capturan en [!DNL Audience Manager] como una llamada a `HTTP` en tiempo real. La llamada de ejemplo siguiente contiene información sobre un evento de conversión de [!DNL Google Campaign Manager]. Las llamadas no tienen que incluir necesariamente *all* las señales en la llamada de ejemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Para un archivo de registro [!DNL Google Campaign Manager] de tamaño promedio de 2 millones de líneas, cualquier rasgo creado a partir de señales procesables se realiza en un plazo aproximado de una hora después de que procesemos los registros.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>La marca de tiempo del evento proporcionada en los registros de [!DNL Google Campaign Manager] se respetará y pasará a [!UICONTROL Data Collection Servers].
>
>* Si no hay una marca de tiempo disponible para una fila de datos en el archivo de registro [!DNL Google Campaign Manager], se usa la hora de la llamada a `HTTP` como marca de tiempo del evento.
>* Si la fila de datos del archivo de registro [!DNL Google Campaign Manager] contiene una marca de tiempo incorrecta, se omitirá toda la fila.

<br> 

### Señales procesables de [!DNL Google Ad Manager] los registros {#ad-manager-logs-signals}

La tabla enumera las señales procesables de los archivos de [!DNL Google Ad Manager] registro:


| Nombre del encabezado en el Archivo de registro | Señal | Descripción |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | El ID numérico para el elemento de línea del administrador de publicidad entregado |
| `OrderId` | `d_orderid` | El ID numérico del pedido del Administrador de publicidad que contenía el elemento de línea entregado y el creativo. |
| `CreativeId` | `d_creative` | ID numérico para el creativo del administrador de publicidad enviado. |
| `-` | `d_event` | Indica el tipo de evento. Audience Manager lee el tipo de evento del nombre del archivo de registro administrador de publicidad y lo transforma en una señal procesable. Los valores aceptados son: <br> <ul><li>d_event = imp para impresiones.</li><li>d_event = clic para clics.</li><li>d_event = conv para conversiones y actividades.</li></ul> |
| `-` | `d_src` | El ID de la fuente de datos que utiliza para capturar los datos del Administrador de publicidad. Ver [Cómo crear un Source de datos](/help/using/features/manage-datasources.md). |

Las señales descritas en la tabla se capturan en Audience Manager como una llamada HTTP en tiempo real. La llamada de ejemplo siguiente contiene información sobre un evento de conversión de Google Ad Manager. Las llamadas de no tienen que incluir necesariamente todas las señales de la llamada de ejemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>La marca de tiempo del evento proporcionada en los registros de [!DNL Google Ad Manager] se respetará y pasará a [!UICONTROL Data Collection Servers].
>
>
>* Si no hay una marca de tiempo disponible para una fila de datos en el archivo de registro [!DNL Google Ad Manager], se usa la hora de la llamada a `HTTP` como marca de tiempo del evento.
>* Si la fila de datos del archivo de registro [!DNL Google Ad Manager] contiene una marca de tiempo incorrecta, se omitirá toda la fila.

<br> 

### Señales procesables desde los registros del servidor de publicidad de Adobe Advertising Cloud, FlashTalk y Sizmek {#generic-logs-signals}

En primer lugar, debe depositar los registros de su servidor de publicidad en nuestros bloques de Amazon S3. Para ello, lea [Archivos de datos para informes de Audience Optimization y archivos de registro procesables](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *y* y póngase en contacto con su consultor de [!DNL Audience Manager]. En la tabla se enumeran las señales procesables de los archivos de registro del servidor de publicidad:

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
      <li id="li_29D3FF8919B7404297E80BACA913117A"> Impresión <code> 0</code> </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> clic </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> sin atribuir o desconocido </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> Una fecha y hora UTC para el evento de impresión, clic o conversión. Usar el formato <code>yyyy-MM-dd HH:mm:ss</code>. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Un código de integración para la fuente de datos del anunciante. Tenga en cuenta que este campo no está relacionado con <a href="../../features/datasources-list-and-settings.md">orígenes de datos de Audience Manager.</a></p></td> 
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
   <td colname="col3"> <p>El ID de Creative del archivo de registro. </p> </td> 
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
   <td colname="col3"> <p>Indica el tipo de evento. Audience Manager lee el tipo de evento del nombre del archivo de registro y lo transforma en una señal procesable. Consulte <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">convenciones de nomenclatura de archivos de registro</a>. </p> <p>Los valores aceptados son: </p> <p> 
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
   <td colname="col3"> <p>El ID de la fuente de datos utilizada para capturar los datos de registro. Ver <a href="../../features/manage-datasources.md#create-data-source"> Cómo crear un Source de datos</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Las señales descritas en la tabla se capturan en [!DNL Audience Manager] como una llamada a `HTTP` en tiempo real. Las llamadas no tienen que incluir necesariamente *all* las señales en la llamada de ejemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Uso de señales procesables en la interfaz de usuario de Audience Manager {#actionable-signals-in-ui}

Puede ver las señales procesables entrantes en la interfaz [Búsqueda de señales](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md).

Vaya a **Datos de audiencia** (1) > **Señales** (2) > **Buscar** (3) y seleccione el filtro **Archivos de registro procesables** (4).

![Señales procesables en la interfaz de usuario](/help/using/integration/assets/alf-in-signals.png)

Para crear rasgos basados en reglas usando sus señales procesables, seleccione **Archivos de registro procesables** (1), seleccione las señales procesables que desee usar como reglas de rasgos (2) y presione **Crear rasgo a partir de señales seleccionadas** (3).

![Crear rasgos a partir de señales](/help/using/integration/assets/alf-create-trait.png)


## Casos de uso {#use-cases}

Una ventaja de implementar [!UICONTROL Actionable Log Files] es la opción de aplicar los controles de [actualización y frecuencia](../../features/segments/recency-and-frequency.md) a cualquier [característica basada en reglas](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) que contenga señales procesables. Esto le permite, por ejemplo, limitar la frecuencia del número de veces que se muestra a un usuario un creativo en particular, dentro de una campaña de medios. Lea [Eliminación instantánea entre dispositivos](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) para saber cómo hacerlo. Otros casos de uso incluyen:

### Redestinar usuarios

Vuelva a dirigirse a los usuarios que vieron el creativa 123 pero no hicieron clic ni convertir y muéstreles creativa 456. Haga lo siguiente:

1. Crear una característica para capturar a los usuarios que vieron el creativa. Supongamos que nombras el rasgo [!DNL Creative Trait 123]. Utilice el rasgo regla:

   `d_creative == 123 AND d_event == imp`

2. Crear una característica para capturar a los usuarios que hacen clic o convertir. Digamos que nombras este [!DNL Click and Converter]. Utilice el rasgo regla:

   `d_event == click OR d_event=conv`

3. Cree un segmento para rellenar con usuarios que vieron el elemento creativo 123, pero que no hicieron clic ni convirtieron. Asígnele el nombre [!DNL Retarget Users] y utilice la regla de segmento:

   `Creative Trait 123 AND NOT Click and Converter`

4. Asigne el segmento [!DNL Retarget Users] a un destino y dirija a los usuarios en el destino con Creative 456.

### Utilice la actividad de Floodlight de Google Campaign Manager en los informes de Audience Optimization o en Audience Lab

[Las etiquetas](https://support.google.com/dcm/partner/answer/4293719?hl=en) de Floodlight permiten a los anunciantes rastrear conversiones usuario. Con [!UICONTROL Actionable Log Files], puede realizar un seguimiento de las [!DNL Google Campaign Manager] conversiones en los [informes](../../reporting/audience-optimization-reports/audience-optimization-reports.md) Audience Optimization o en [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Crear un rasgo y use los siguientes regla para capturar un Conversión de los registros de servidor de anuncios:

   `d_event == conv AND d_conversion == 123`

   Al crear la característica en Audience Manager [!UICONTROL UI], seleccione [!UICONTROL Conversion] como [!UICONTROL Event Type].

2. Una vez que haya creado el rasgo, se comenzará a informar de la conversión en el [!UICONTROL Audience Optimization Reports] y en el [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importar Archivos De Datos Del Administrador De Google Campaign En Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Informes de optimización de Audiencia](../../reporting/audience-optimization-reports/audience-optimization-reports.md)
