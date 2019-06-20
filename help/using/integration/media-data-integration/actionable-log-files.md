---
description: Los archivos de registro procesables permiten capturar datos de medios de archivos de registro de Google DCM y utilizar los datos para crear características en Audience Manager. Capture impresiones, clics y conversiones de servidores de publicidad como características sin tener que usar llamadas de píxeles.
keywords: registros procesables
seo-description: Los archivos de registro procesables permiten capturar datos de medios de archivos de registro de Google DCM y utilizar los datos para crear características en Audience Manager. Capture impresiones, clics y conversiones de servidores de publicidad como características sin tener que usar llamadas de píxeles.
seo-title: Archivos de registro procesables
solution: Audience Manager
title: Archivos de registro procesables
uuid: 4 c 47615 f-ed 47-41 ba -8694-1 d 7 de 4 f 55 d 62 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Archivos de registro procesables {#actionable-log-files}

[!UICONTROL Actionable Log Files] permite capturar datos de medios de archivos [!DNL Google DCM] de registro y utilizar los datos para crear características en Audience Manager. Capture impresiones, clics y conversiones de servidores de publicidad como características sin tener que usar llamadas de píxeles.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *cursiva*, paréntesis `[ ]` `( )`, etc.) en este documento indican elementos y opciones de código. Consulte [Convenciones de estilo para elementos de código y texto](../../reference/code-style-elements.md) para obtener más información.

## Finalidad {#purpose}

[!UICONTROL Actionable Log Files] racionalice la manera de capturar impresiones, clics y conversiones de servidores de publicidad. Use this information for user segmentation without having to manually pixel media to send campaign attributes to [!DNL Audience Manager].

## Introducción {#getting-started}

To get started with [!UICONTROL Actionable Log Files], and to use our [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md), you need to import DCM log data into [!DNL Audience Manager]. See [Import DCM Data Files Into Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *and* contact your [!DNL Audience Manager] consultant.

If you are already importing [!UICONTROL DCM] log data into [!DNL Audience Manager], ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to enable [!UICONTROL Actionable Log Files] for you.

>[!NOTE] {important = &quot;high&quot;}
>
>[!UICONTROL Actionable Log Files] solo funcionan con archivos [!DNL Google DCM] de registro.

## Working with Actionable Log Files {#working-with-actionable-log-files}

With [!UICONTROL Actionable Log Files], the information from [!DNL DCM] logs is captured in [!DNL Audience Manager] the same way that you would capture data from real-time website interactions. [!DNL Audience Manager] conecta con [!DNL Google Cloud] su almacenamiento, analiza la información de [!DNL DCM] registros y envía los datos de registro como señales procesables a nuestros [servidores de recopilación de datos](../../reference/system-components/components-data-collection.md#dcs-pcs).

Aún necesita configurar características basadas en reglas para capturar las señales procesables. See how to set up rule-based traits either in the [Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or using our [Bulk Management Tools](../../reference/bulk-management-tools/bulk-create.md). Scroll down to the [Actionable Signals](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) section for a list of all the keys you can use in rule-based traits.

For an average-sized [!DNL DCM] log file of 2 million lines, any traits created from actionable signals are realized within approximately one hour after we process the logs.

>[!IMPORTANT] {important = &quot;high&quot;}
>
>We recommend implementing [!UICONTROL Actionable Log Files] *instead of*  [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). Desactivamos el uso de ambas opciones, ya que esto lleva a un aumento en recuentos de frecuencia para características.

## Actionable Signals {#actionable-signals}

Signals are the [smallest data units](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] permite capturar los valores de los anunciantes, unidades empresariales, elementos creativos y campañas en eventos de impresión, eventos y eventos de conversión como señales desde [!DNL DCM] registros.

Recuerde, para utilizar esta información para la creación y segmentación de audiencias, debe configurar usted mismo las características basadas en reglas. The table lists the actionable signals from [!DNL DCM] log files:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Señal </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Valor de ejemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ event</code> </p> </td> 
   <td colname="col2"> <p>Indica el tipo de evento de DCM. </p> <p>Los valores aceptables son: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_ event = imp</code> for impresiones. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_ event = clic</code> para clics. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_ event = conv</code> para conversiones. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversion</code> </p> </td> 
   <td colname="col2"> <p>Disponible solamente para eventos de conversión. </p> <p>Representa el ID numérico de la actividad de conversión en DCM. Este campo se asigna al ID de actividad desde DCM. </p> <p> <p>Sugerencia: Puede capturar actividades de conversión múltiples o específicas desde DCM. Create traits using <code> d_conversion = activity ID</code> for each conversion activity from DCM. </p> </p> </td> 
   <td colname="col3"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversiontype</code> </p> </td> 
   <td colname="col2"> <p>Disponible solamente para eventos de conversión. </p> <p>Este campo se asigna al ID de conversión en DCM. Indica la actividad que precede a la conversión de usuario de DCM. </p> <p>Los valores aceptables son: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> para conversiones posteriores al clic. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> para conversiones posteriores a la impresión. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> para conversiones no coincidentes. La conversión no puede coincidir con una actividad anterior. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> 0,1,2</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsrc</code> </p> </td> 
   <td colname="col2"> <p>ID del anunciante. Este campo se asigna al ID de grupo anunciante desde DCM. </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col2"> <p>ID de unidad comercial. Este campo se asigna al ID del anunciante desde DCM. </p> </td> 
   <td colname="col3"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col2"> <p>El ID de campaña proporcionado por DCM. </p> </td> 
   <td colname="col3"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col2"> <p>El ID creativo proporcionado por DCM. </p> </td> 
   <td colname="col3"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col2"> <p>ID del origen de datos que utiliza para capturar datos de DCM. See <a href="../../features/manage-datasources.md#create-data-source"> How to Create a Data Source</a>. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

The signals described in the table are captured in [!DNL Audience Manager] like a real-time `HTTP` call. The example call below contains information on a conversion event from [!DNL DCM]. Calls do not necessarily have to include *all* the signals in the example call.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {important = &quot;high&quot;}
>
>The event timestamp provided in the [!DNL DCM] logs will be honored and passed to the [!UICONTROL Data Collection Servers].
>
>* If a timestamp isn&#39;t available for a data row in the [!DNL DCM] log file, we use the time of the `HTTP` call as the event timestamp.
>* If the data row in the [!DNL DCM] log file contains a malformed timestamp, we ignore the entire row.


## Casos de uso {#use-cases}

One benefit of implementing [!UICONTROL Actionable Log Files] is the option to apply [recency and frequency](../../features/segments/recency-and-frequency.md) controls to any [rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) that contain actionable signals. Esto permite, por ejemplo, limitar la frecuencia de la cantidad de veces que un usuario se muestra como creativo particular, dentro de una campaña multimedia. Otros casos de uso son:

### Retarget Usuarios

Retarget a usuarios que vieron creative 123 pero no hicieron clic ni convertirlos ni mostrarles Creative 456. Haga esto:

1. Cree una característica para capturar a los usuarios que vieron el elemento creativo. Let&#39;s say you name the trait [!DNL Creative Trait 123]. Utilice la regla de características:

   `d_creative == 123 AND d_event == imp`

1. Cree una característica para capturar usuarios que hagan clic o conviertan. Let&#39;s say you name this one [!DNL Click and Converter]. Utilice la regla de características:

   `d_event == click OR d_event=conv`

1. Cree un segmento para rellenar con usuarios que vieron creative 123 pero que no hayan hecho clic ni convertido. Name it [!DNL Retarget Users] and use the segment rule:

   `Creative Trait 123 AND NOT Click and Converter`

1. Map the segment [!DNL Retarget Users] to a destination and target users in the destination with creative 456.

### Usar actividad de Floodlight DCM en los informes de Optimización de audiencias o en Audience Lab

[Las etiquetas Floodlight](https://support.google.com/dcm/partner/answer/4293719?hl=en) permiten a los anunciantes realizar un seguimiento de las conversiones de usuario. With [!UICONTROL Actionable Log Files], you can track the [!DNL DCM] conversions in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md) or in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Cree una característica y utilice la regla de características siguiente para capturar una conversión desde los registros del servidor de publicidad:

   `d_event == conv AND d_conversion == 123`

   When creating the trait in the Audience Manager [!UICONTROL UI], select [!UICONTROL Conversion] as the [!UICONTROL Event Type].

2. Once you have created the trait, the conversion will begin to be reported against in the [!UICONTROL Audience Optimization Reports] and in [!UICONTROL Audience Lab].

>[!MORE_ LIKE_ THIS]
>
>* [Importación de archivos de datos de DCM en Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Informes de optimización de audiencias](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

