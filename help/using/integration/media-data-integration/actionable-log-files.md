---
description: Los archivos de registro procesables permiten capturar datos de medios de archivos de registro de Google DCM y utilizar los datos para crear características en Audience Manager. Capture impresiones, clics y conversiones de servidores de publicidad como características sin tener que usar llamadas de píxeles.
keywords: registros procesables
seo-description: Los archivos de registro procesables permiten capturar datos de medios de archivos de registro de Google DCM y utilizar los datos para crear características en Audience Manager. Capture impresiones, clics y conversiones de servidores de publicidad como características sin tener que usar llamadas de píxeles.
seo-title: Archivos de registro procesables
solution: Audience Manager
title: Archivos de registro procesables
uuid: 4 c 47615 f-ed 47-41 ba -8694-1 d 7 de 4 f 55 d 62 d
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# Archivos de registro procesables {#actionable-log-files}

[!UICONTROL Actionable Log Files] permite capturar datos de medios de archivos [!DNL Google DCM] de registro y utilizar los datos para crear características en Audience Manager. Capture impresiones, clics y conversiones de servidores de publicidad como características sin tener que usar llamadas de píxeles.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *cursiva*, paréntesis `[ ]` `( )`, etc.) en este documento indican elementos y opciones de código. Consulte [Convenciones de estilo para elementos de código y texto](../../reference/code-style-elements.md) para obtener más información.

## Finalidad {#purpose}

[!UICONTROL Actionable Log Files] racionalice la manera de capturar impresiones, clics y conversiones de servidores de publicidad. Utilice esta información para la segmentación de usuarios sin tener que tener que enviar los atributos de campaña manualmente a los medios [!DNL Audience Manager]de píxeles.

## Introducción {#getting-started}

Para comenzar [!UICONTROL Actionable Log Files], y para utilizar nuestros [informes](../../reporting/audience-optimization-reports/audience-optimization-reports.md)de Optimización de audiencia, debe importar datos de registro de DCM. [!DNL Audience Manager] Consulte [Importación de archivos de datos de DCM en Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *y* póngase en contacto con su [!DNL Audience Manager] asesor.

Si ya está importando datos [!UICONTROL DCM] de registro, [!DNL Audience Manager]pídale a su [!DNL Audience Manager] asesor o [al Servicio](https://helpx.adobe.com/contact/enterprise-support.ec.html) de atención al cliente que lo habiliten [!UICONTROL Actionable Log Files] .

>[!NOTE] {important = "high"}
>
>[!UICONTROL Actionable Log Files] solo funcionan con archivos [!DNL Google DCM] de registro.

## Uso de archivos de registro procesables {#working-with-actionable-log-files}

Con [!UICONTROL Actionable Log Files], la información de [!DNL DCM] los registros se captura de [!DNL Audience Manager] la misma manera que capturaría datos desde interacciones de sitios web en tiempo real. [!DNL Audience Manager] conecta con [!DNL Google Cloud] su almacenamiento, analiza la información de [!DNL DCM] registros y envía los datos de registro como señales procesables a nuestros [servidores de recopilación de datos](../../reference/system-components/components-data-collection.md#dcs-pcs).

Aún necesita configurar características basadas en reglas para capturar las señales procesables. Consulte cómo configurar características basadas en reglas en la interfaz de [usuario de Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) o mediante nuestras herramientas [de administración masiva](../../reference/bulk-management-tools/bulk-create.md). Desplácese hacia abajo hasta la [sección Señales](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) procesables para ver una lista de todas las claves que puede utilizar en características basadas en reglas.

Para un archivo [!DNL DCM] de registro de tamaño promedio de 2 millones de líneas, cualquier rasgo creado a partir de señales procesables se realiza dentro de aproximadamente una hora después de procesar los registros.

>[!IMPORTANT] {important = "high"}
>
>Se recomienda implementar [!UICONTROL Actionable Log Files]*en lugar de* [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). Desactivamos el uso de ambas opciones, ya que esto lleva a un aumento en recuentos de frecuencia para características.

## Señales procesables {#actionable-signals}

Las señales son las [unidades de datos más pequeñas](../../reference/signal-trait-segment.md) en [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] permite capturar los valores de los anunciantes, unidades empresariales, elementos creativos y campañas en eventos de impresión, eventos y eventos de conversión como señales desde [!DNL DCM] registros.

Recuerde, para utilizar esta información para la creación y segmentación de audiencias, debe configurar usted mismo las características basadas en reglas. La tabla enumera las señales procesables de los archivos [!DNL DCM] de registro:

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
   <td colname="col2"> <p>Disponible solamente para eventos de conversión. </p> <p>Representa el ID numérico de la actividad de conversión en DCM. Este campo se asigna al ID de actividad desde DCM. </p> <p> <p>Sugerencia: Puede capturar actividades de conversión múltiples o específicas desde DCM. Cree características utilizando <code> d_ conversion = activity ID</code> para cada actividad de conversión desde DCM. </p> </p> </td> 
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
   <td colname="col2"> <p>ID del anunciante.</p> <p>Código de integración para la fuente de datos del anunciante. Tenga en cuenta que esto no está relacionado con las fuentes de datos de Audience Manager.</p> <p>Este campo se asigna al ID de grupo anunciante desde DCM. </p> </td> 
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
   <td colname="col2"> <p>ID del origen de datos que utiliza para capturar datos de DCM. Consulte <a href="../../features/manage-datasources.md#create-data-source"> Cómo crear una fuente de datos</a>. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Las señales descritas en la tabla se capturan [!DNL Audience Manager] como `HTTP` una llamada en tiempo real. La llamada de ejemplo a continuación contiene información sobre un evento de conversión desde [!DNL DCM]. Las llamadas no tienen por qué incluir necesariamente *todas* las señales en la llamada de ejemplo.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {important = "high"}
>
>La marca de tiempo de evento proporcionada en [!DNL DCM] los registros se respetará y pasará a [!UICONTROL Data Collection Servers]la.
>
>* Si una marca de fecha y hora no está disponible para una fila de datos en el archivo [!DNL DCM] de registro, se usa el tiempo de `HTTP` la llamada como fecha de registro del evento.
>* Si la fila de datos del archivo [!DNL DCM] de registro contiene una marca de fecha y hora incorrecta, se ignora toda la fila.


## Casos de uso {#use-cases}

Una ventaja de implementar [!UICONTROL Actionable Log Files] es la opción de aplicar controles [de actualización y frecuencia](../../features/segments/recency-and-frequency.md) a cualquier característica [basada en reglas](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) que contenga señales procesables. Esto permite, por ejemplo, limitar la frecuencia de la cantidad de veces que un usuario se muestra como creativo particular, dentro de una campaña multimedia. Otros casos de uso son:

### Retarget Usuarios

Retarget a usuarios que vieron creative 123 pero no hicieron clic ni convertirlos ni mostrarles Creative 456. Haga esto:

1. Cree una característica para capturar a los usuarios que vieron el elemento creativo. Supongamos que usted asigna un nombre a la característica [!DNL Creative Trait 123]. Utilice la regla de características:

   `d_creative == 123 AND d_event == imp`

1. Cree una característica para capturar usuarios que hagan clic o conviertan. Supongamos que le pongamos un nombre [!DNL Click and Converter]. Utilice la regla de características:

   `d_event == click OR d_event=conv`

1. Cree un segmento para rellenar con usuarios que vieron creative 123 pero que no hayan hecho clic ni convertido. Póngale nombre [!DNL Retarget Users] y utilice la regla de segmento:

   `Creative Trait 123 AND NOT Click and Converter`

1. Asigne el segmento [!DNL Retarget Users] a un destino y dirija el segmento a los usuarios del destino con creative 456.

### Usar actividad de Floodlight DCM en los informes de Optimización de audiencias o en Audience Lab

[Las etiquetas Floodlight](https://support.google.com/dcm/partner/answer/4293719?hl=en) permiten a los anunciantes realizar un seguimiento de las conversiones de usuario. Con [!UICONTROL Actionable Log Files], puede rastrear [!DNL DCM] las conversiones en los informes [de Optimización de audiencias](../../reporting/audience-optimization-reports/audience-optimization-reports.md) o [en Audience Lab](../../features/audience-lab/audience-lab.md):

1. Cree una característica y utilice la regla de características siguiente para capturar una conversión desde los registros del servidor de publicidad:

   `d_event == conv AND d_conversion == 123`

   Al crear la característica en Audience Manager [!UICONTROL UI], seleccione [!UICONTROL Conversion] como [!UICONTROL Event Type].

2. Una vez que haya creado la característica, la conversión comenzará a informarse en la [!UICONTROL Audience Optimization Reports] y [!UICONTROL Audience Lab]en la.

>[!MORE_ LIKE_ THIS]
>
>* [Importación de archivos de datos de DCM en Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Informes de optimización de audiencias](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

