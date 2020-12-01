---
description: Los archivos de registro procesables le permiten capturar señales de medios de archivos de registro del servidor de publicidad para crear características en el Audience Manager. Capture impresiones, clics y conversiones de servidores de publicidad como características sin tener que anexar píxeles.
keywords: actionable logs, alf, ALF
seo-description: Los archivos de registro procesables le permiten capturar señales de medios de archivos de registro del servidor de publicidad para crear características en el Audience Manager. Capture impresiones, clics y conversiones de servidores de publicidad como características sin tener que anexar píxeles.
seo-title: Archivos de registro procesables
solution: Audience Manager
title: Archivos de registro procesables
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
translation-type: tm+mt
source-git-commit: a4d86fb0324a03002123f8713eb9786b5b74c38e
workflow-type: tm+mt
source-wordcount: '1605'
ht-degree: 3%

---


# Archivos de registro procesables {#actionable-log-files}

[!UICONTROL Actionable Log Files] permite capturar datos de medios de archivos de registro del servidor de publicidad y utilizar los datos para crear características en Audience Manager. Capture impresiones, clics y conversiones de servidores de publicidad como características sin tener que anexar [píxeles](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *cursiva*, paréntesis `[ ]` `( )`, etc.) en este documento, indique los elementos y las opciones del código. Consulte [Convenciones de estilo para elementos de código y texto](../../reference/code-style-elements.md) para obtener más información.

## Finalidad {#purpose}

[!UICONTROL Actionable Log Files] optimice la forma de capturar impresiones, clics y conversiones desde servidores de publicidad. Utilice esta información para la segmentación de usuarios sin tener que utilizar medios de píxeles manualmente para enviar atributos de campaña a [!DNL Audience Manager].

## Introducción {#getting-started}

Para comenzar con [!UICONTROL Actionable Log Files], debe importar datos de registro en [!DNL Audience Manager]. Los siguientes vínculos le ayudarán a iniciarse:

* Para obtener [!UICONTROL Google Campaign Manager] registros, consulte [Importar archivos de datos del Administrador de Campañas de Google en Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *y* comunicarse con su [!DNL Audience Manager] asesor.
* Para obtener los registros [!UICONTROL Google Ad Manager] (anteriormente Google DFP), consulte [Importar archivos de datos del administrador de publicidad de Google en Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *y* comunicarse con su [!DNL Audience Manager] asesor.
* Para ver otros registros de servidores de publicidad, consulte [Archivos de datos y metadatos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *y* póngase en contacto con su [!DNL Audience Manager] consultor.

Si ya está importando datos de registro en [!DNL Audience Manager], pregunte a su [!DNL Audience Manager] asesor o [Servicio de atención al cliente](https://helpx.adobe.com/es/contact/enterprise-support.ec.html) para habilitarlo [!UICONTROL Actionable Log Files] por usted.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## Uso de archivos de registro procesables {#working-with-actionable-log-files}

Con [!UICONTROL Actionable Log Files], la información de los registros del servidor de publicidad se captura en [!DNL Audience Manager] de la misma manera que se capturan los datos de las interacciones del sitio Web en tiempo real. [!DNL Audience Manager] se conecta al almacenamiento de registro del servidor de publicidad, analiza la información de los registros y envía los datos del registro como señales procesables a nuestros servidores [ de recopilación de ](../../reference/system-components/components-data-collection.md#dcs-pcs)datos.

Todavía necesita configurar características basadas en reglas para capturar las señales procesables. Consulte cómo configurar características basadas en reglas en la [interfaz de usuario del Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) o mediante las [Herramientas de administración masiva](../../reference/bulk-management-tools/bulk-create.md). Desplácese hacia abajo hasta la sección [Señales procesables](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) para obtener una lista de todas las claves que puede utilizar en características basadas en reglas.

>[!IMPORTANT]
>
>Se recomienda implementar [!UICONTROL Actionable Log Files] *en lugar de* [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). Desalentamos el uso de ambas opciones, ya que esto lleva a un aumento en los recuentos de frecuencias de las características.

## Señales procesables {#actionable-signals}

Las señales son las [unidades de datos más pequeñas](../../reference/signal-trait-segment.md) en [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] permite capturar los valores de anunciante, unidad de negocio, elemento creativo y campaña en eventos de impresión, eventos de clic y eventos de conversión como señales de los registros de servidores de publicidad.

Recuerde que, para utilizar esta información para la creación y segmentación de audiencias, debe configurar usted mismo las características basadas en reglas.

### Señales procesables de los registros de Google Campaña Manager {#dcm-logs-signals}

La tabla lista las señales procesables de los archivos de registro [!DNL Google Campaign Manager]:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre de encabezado en el archivo de registro </th> 
   <th colname="col2" class="entry"> Señal </th> 
   <th colname="col3" class="entry"> Descripción </th> 
   <th colname="col4" class="entry"> Valor de ejemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>Disponible solo para eventos de conversión. </p> <p>Representa el ID numérico de la actividad de conversión en el Administrador de Campañas de Google. Este campo se asigna al ID de Actividad desde el Administrador de Campañas de Google. </p> <p> <p>Sugerencia: Puede capturar actividades de conversión múltiples o específicas desde el Administrador de Campañas de Google. Cree características mediante <code> d_conversion = activity ID</code> para cada actividad de conversión desde el Administrador de Campañas de Google. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Disponible solo para eventos de conversión. </p> <p>Este campo se asigna al ID de conversión en el Administrador de Campañas de Google. Indica la actividad que precede a la conversión del usuario desde el Administrador de Campañas de Google. </p> <p>Los valores aceptados son: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> para conversiones posteriores al clic. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> para conversiones posteriores a la impresión. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> para conversiones no coincidentes. La conversión no puede coincidir con una actividad anterior. </li> 
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
   <td colname="col3"><p>Código de integración de la fuente de datos del anunciante. Tenga en cuenta que esto no está relacionado con las fuentes de datos de Audience Manager.</p> <p>Este campo se asigna al ID del grupo de anunciantes desde el Administrador de Campañas de Google. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>ID de unidad de negocio. Este campo se asigna al ID del anunciante desde el Administrador de Campañas de Google. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>ID de Campaña proporcionado por el Administrador de Campañas de Google.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>El ID creativo proporcionado por el Administrador de Campañas de Google. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> El importe de ventas en USD, a la potencia de -6. Multiplicar por 1.000.000 para ver como una cantidad en dólares.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indica el tipo de evento. El Audience Manager lee el tipo de evento del nombre del archivo de registro del Administrador de Campañas de Google y lo transforma en una señal procesable. </p> <p>Los valores aceptados son: </p> <p> 
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
   <td colname="col3"> <p>ID del origen de datos que se utiliza para capturar datos del Administrador de Campañas de Google. Consulte <a href="../../features/manage-datasources.md#create-data-source"> Cómo crear una fuente de datos</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Las señales descritas en la tabla se capturan en [!DNL Audience Manager] como una llamada `HTTP` en tiempo real. La llamada de ejemplo siguiente contiene información sobre un evento de conversión de [!DNL Google Campaign Manager]. Las llamadas no necesariamente deben incluir *all* las señales en la llamada de ejemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Para un archivo de registro [!DNL Google Campaign Manager] de tamaño promedio de 2 millones de líneas, cualquier característica creada a partir de señales procesables se realiza en aproximadamente una hora después de procesar los registros.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>La marca de tiempo de evento proporcionada en los registros [!DNL Google Campaign Manager] se respetará y pasará a [!UICONTROL Data Collection Servers].
>
>* Si no hay una marca de hora disponible para una fila de datos en el archivo de registro [!DNL Google Campaign Manager], usamos la hora de la llamada `HTTP` como marca de hora de evento.
>* Si la fila de datos del archivo de registro [!DNL Google Campaign Manager] contiene una marca de tiempo con formato incorrecto, se ignora toda la fila.


<br> 

### Señales procesables de [!DNL Google Ad Manager] registros {#ad-manager-logs-signals}

La tabla lista las señales procesables de los archivos de registro [!DNL Google Ad Manager]:


| Nombre de encabezado en el archivo de registro | Señal | Descripción |
---------|----------|---------
| `LineItemId` | `d_lineitem` | El ID numérico del elemento de línea del Administrador de publicidad enviado |
| `OrderId` | `d_orderid` | ID numérico del orden del Administrador de publicidad que contenía el elemento de línea y el elemento creativo entregados. |
| `CreativeId` | `d_creative` | ID numérico del elemento creativo del administrador de publicidad enviado. |
| `-` | `d_event` | Indica el tipo de evento. El Audience Manager lee el tipo de evento del nombre del archivo de registro del Administrador de publicidad y lo transforma en una señal procesable. Los valores aceptados son: <br> <ul><li>d_evento = imp para impresiones.</li><li>d_evento = clic para clics.</li><li>d_evento = conv para conversiones y actividades.</li></ul> |
| `-` | `d_src` | ID del origen de datos que se utiliza para capturar datos del Administrador de publicidad. Consulte [Cómo crear una fuente de datos](/help/using/features/manage-datasources.md). |

Las señales que se describen en la tabla se capturan en Audience Manager como una llamada HTTP en tiempo real. La llamada de ejemplo siguiente contiene información sobre un evento de conversión del Administrador de publicidad de Google. Las llamadas no necesariamente tienen que incluir todas las señales en la llamada de ejemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>La marca de tiempo de evento proporcionada en los registros [!DNL Google Ad Manager] se respetará y pasará a [!UICONTROL Data Collection Servers].
>
>* Si no hay una marca de hora disponible para una fila de datos en el archivo de registro [!DNL Google Ad Manager], usamos la hora de la llamada `HTTP` como marca de hora de evento.
>* Si la fila de datos del archivo de registro [!DNL Google Ad Manager] contiene una marca de tiempo con formato incorrecto, se ignora toda la fila.


<br> 

### Señales procesables de los registros genéricos del servidor de publicidad {#generic-logs-signals}

En primer lugar, debe depositar los registros de su servidor de publicidad en nuestros cubos Amazon S3. Para ello, lea [Archivos de datos para informes de Audience Optimization y archivos de registro procesables](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *y* póngase en contacto con su [!DNL Audience Manager] consultor. La tabla lista las señales procesables de los archivos de registro genéricos:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre de encabezado en el archivo de registro </th> 
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
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> No atribuido o desconocido </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> Una fecha y hora UTC para el evento de impresión, clic o conversión. Utilice el formato <code>yyyy-MM-dd HH:mm:ss</code>. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Código de integración de la fuente de datos del anunciante. Tenga en cuenta que este campo no está relacionado con <a href="../../features/datasources-list-and-settings.md">orígenes de datos de Audience Manager.</a></p></td> 
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
   <td colname="col3"> <p>ID de Campaña del archivo de registro.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>El ID creativo del archivo de registro. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Compra u otra cantidad de conversión. Tipo de datos: Flotante. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indica el tipo de evento. El Audience Manager lee el tipo de evento del nombre del archivo de registro y lo transforma en una señal procesable. Consulte <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">convenciones de nombres de archivos de registro</a>. </p> <p>Los valores aceptados son: </p> <p> 
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
   <td colname="col3"> <p>ID del origen de datos que se utiliza para capturar los datos del registro. Consulte <a href="../../features/manage-datasources.md#create-data-source"> Cómo crear una fuente de datos</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Las señales descritas en la tabla se capturan en [!DNL Audience Manager] como una llamada `HTTP` en tiempo real. Las llamadas no necesariamente deben incluir *all* las señales en la llamada de ejemplo.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Uso de señales procesables en la interfaz de usuario del Audience Manager {#actionable-signals-in-ui}

Puede vista las señales accionables entrantes en la interfaz [Búsqueda de señales](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md).

Vaya a **Datos de Audiencia** (1) > **Señales** (2) > **Buscar** (3) y seleccione el filtro **Archivos de registro procesables** (4).

![Señales procesables en la interfaz de usuario](/help/using/integration/assets/alf-in-signals.png)

Para crear características basadas en reglas con sus señales procesables, seleccione **Archivos de registro procesables** (1), seleccione las señales procesables que desee utilizar como reglas de características (2) y presione **Crear rasgo a partir de señales seleccionadas** (3).

![Crear características a partir de señales](/help/using/integration/assets/alf-create-trait.png)


## Casos de uso {#use-cases}

Una ventaja de implementar [!UICONTROL Actionable Log Files] es la opción de aplicar controles [de actualización y frecuencia](../../features/segments/recency-and-frequency.md) a cualquier [característica basada en reglas](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) que contenga señales procesables. Esto le permite, por ejemplo, limitar la frecuencia del número de veces que se muestra a un usuario un elemento creativo determinado, dentro de una campaña de medios. Lea [Supresión instantánea entre dispositivos](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) para obtener información sobre cómo hacerlo. Otros casos de uso incluyen:

### Usuarios de reasignaciones

Vuelva a segmentar usuarios que hayan visto el elemento creativo 123 pero que no hayan hecho clic o convertido y muéstreles el elemento creativo 456. Haga esto:

1. Cree una característica para capturar a los usuarios que vieron el elemento creativo. Supongamos que usted nombra la característica [!DNL Creative Trait 123]. Utilice la regla de características:

   `d_creative == 123 AND d_event == imp`

2. Cree una característica para capturar a los usuarios que hacen clic o convierten. Supongamos que le pone un nombre [!DNL Click and Converter]. Utilice la regla de características:

   `d_event == click OR d_event=conv`

3. Cree un segmento para rellenarlo con los usuarios que vieron el elemento creativo 123 pero no hicieron clic ni convirtieron. Asigne un nombre a [!DNL Retarget Users] y utilice la regla de segmento:

   `Creative Trait 123 AND NOT Click and Converter`

4. Asigne el segmento [!DNL Retarget Users] a un destino y a los usuarios de destinatario del destino con el elemento creativo 456.

### Utilizar la Actividad de Floodlight del Administrador de Campañas de Google en los informes de Audience Optimization o en el laboratorio de Audiencias

[Los anunciantes ](https://support.google.com/dcm/partner/answer/4293719?hl=en) etiquetables de Floodlight rastrean las conversiones de los usuarios. Con [!UICONTROL Actionable Log Files], puede rastrear las conversiones [!DNL Google Campaign Manager] en los [Informes de Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md) o en [Laboratorio de Audiencia](../../features/audience-lab/audience-lab.md):

1. Cree una característica y utilice la siguiente regla de características para capturar una conversión de los registros del servidor de publicidad:

   `d_event == conv AND d_conversion == 123`

   Al crear la característica en el Audience Manager [!UICONTROL UI], seleccione [!UICONTROL Conversion] como [!UICONTROL Event Type].

2. Una vez que haya creado la característica, la conversión comenzará a generarse en los informes [!UICONTROL Audience Optimization Reports] y en [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importar archivos de datos de Google Campaña Manager en Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Informes de optimización de Audiencia](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

