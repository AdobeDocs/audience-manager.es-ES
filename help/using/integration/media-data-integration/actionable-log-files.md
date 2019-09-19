---
description: Los archivos de registro procesables le permiten capturar datos de medios de los archivos de registro DCM de Google y utilizar los datos para crear características en Audience Manager. Capture impresiones, clics y conversiones de servidores de publicidad como características sin tener que usar llamadas de píxeles.
keywords: registros procesables
seo-description: Los archivos de registro procesables le permiten capturar datos de medios de los archivos de registro DCM de Google y utilizar los datos para crear características en Audience Manager. Capture impresiones, clics y conversiones de servidores de publicidad como características sin tener que usar llamadas de píxeles.
seo-title: Archivos de registro procesables
solution: Audience Manager
title: Archivos de registro procesables
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# Archivos de registro procesables {#actionable-log-files}

[!UICONTROL Actionable Log Files] permite capturar datos de medios de archivos de [!DNL Google DCM] registro y utilizar los datos para crear características en Audience Manager. Capture impresiones, clics y conversiones de servidores de publicidad como características sin tener que usar llamadas de píxeles.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *cursiva*, paréntesis `[ ]` `( )`, etc.) en este documento, indique los elementos y las opciones del código. Consulte [Convenciones de estilo para elementos de código y texto](../../reference/code-style-elements.md) para obtener más información.

## Finalidad {#purpose}

[!UICONTROL Actionable Log Files] optimice la forma de capturar impresiones, clics y conversiones desde servidores de publicidad. Utilice esta información para la segmentación de usuarios sin tener que utilizar medios de píxeles manuales para enviar atributos de campaña a [!DNL Audience Manager].

## Introducción {#getting-started}

Para empezar con [!UICONTROL Actionable Log Files]y utilizar nuestros informes [de optimización de](../../reporting/audience-optimization-reports/audience-optimization-reports.md)público, debe importar datos de registro de DCM en [!DNL Audience Manager]. Consulte [Importación de archivos de datos de DCM en Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *y póngase* en contacto con su [!DNL Audience Manager] asesor.

Si ya está importando datos de [!UICONTROL DCM] registro en [!DNL Audience Manager], pregunte a su [!DNL Audience Manager] consultor o al Servicio de atención al [cliente](https://helpx.adobe.com/contact/enterprise-support.ec.html) para que [!UICONTROL Actionable Log Files] los habilite.

>[!NOTE] {important="high"}
>
>[!UICONTROL Actionable Log Files] solo funciona con archivos [!DNL Google DCM] de registro.

## Uso de archivos de registro procesables {#working-with-actionable-log-files}

Con [!UICONTROL Actionable Log Files], la información de los [!DNL DCM] registros se captura de [!DNL Audience Manager] la misma manera que se capturan los datos de las interacciones del sitio web en tiempo real. [!DNL Audience Manager] se conecta a su [!DNL Google Cloud] almacenamiento, analiza la información de los [!DNL DCM] registros y envía los datos de registro como señales procesables a nuestros servidores [de recopilación](../../reference/system-components/components-data-collection.md#dcs-pcs)de datos.

Todavía necesita configurar características basadas en reglas para capturar las señales procesables. Consulte cómo configurar características basadas en reglas en la interfaz de usuario [de](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) Audience Manager o mediante nuestras herramientas [de administración](../../reference/bulk-management-tools/bulk-create.md)masiva. Desplácese hacia abajo hasta la sección Señales [](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) procesables para obtener una lista de todas las claves que puede utilizar en las características basadas en reglas.

Para un archivo [!DNL DCM] de registro de tamaño medio de 2 millones de líneas, cualquier característica creada a partir de señales procesables se realiza en aproximadamente una hora después de procesar los registros.

>[!IMPORTANT] {important="high"}
>
>Recomendamos implementar [!UICONTROL Actionable Log Files] en *lugar* de [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). Desalentamos el uso de ambas opciones, ya que esto lleva a un aumento en los recuentos de frecuencias de las características.

## Señales procesables {#actionable-signals}

Las señales son las unidades [de datos](../../reference/signal-trait-segment.md) más pequeñas de [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] permite capturar los valores de anunciante, unidad de negocio, elemento creativo y campaña en eventos de impresión, eventos de clic y eventos de conversión como señales de [!DNL DCM] registros.

Recuerde que, para utilizar esta información para la creación y segmentación de audiencias, debe configurar usted mismo las características basadas en reglas. La tabla muestra las señales procesables de los archivos de [!DNL DCM] registro:

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
   <td colname="col1"> <p> <code> d_event</code> </p> </td> 
   <td colname="col2"> <p>Indica el tipo de evento de DCM. </p> <p>Los valores aceptados son: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> para impresiones. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = clic</code> para clics. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> para conversiones. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col2"> <p>Disponible solo para eventos de conversión. </p> <p>Representa el ID numérico de la actividad de conversión en DCM. Este campo se asigna al ID de actividad de DCM. </p> <p> <p>Sugerencia: Puede capturar varias actividades de conversión específicas desde DCM. Cree características con <code> d_conversion = ID</code> de actividad para cada actividad de conversión de DCM. </p> </p> </td> 
   <td colname="col3"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_conversionType</code> </p> </td> 
   <td colname="col2"> <p>Disponible solo para eventos de conversión. </p> <p>Este campo se asigna al ID de conversión en DCM. Indica la actividad que precede a la conversión del usuario desde DCM. </p> <p>Los valores aceptados son: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> para conversiones posteriores al clic. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> para conversiones posteriores a la impresión. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> para conversiones no coincidentes. La conversión no puede coincidir con una actividad anterior. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> 0,1,2</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col2"> <p>ID del anunciante.</p> <p>Código de integración de la fuente de datos del anunciante. Tenga en cuenta que esto no está relacionado con las fuentes de datos de Audience Manager.</p> <p>Este campo se asigna al ID de grupo de anunciantes de DCM. </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col2"> <p>ID de unidad de negocio. Este campo se asigna al ID del anunciante de DCM. </p> </td> 
   <td colname="col3"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col2"> <p>ID de campaña proporcionada por DCM. </p> </td> 
   <td colname="col3"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col2"> <p>ID creativo proporcionado por DCM. </p> </td> 
   <td colname="col3"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col2"> <p>ID del origen de datos que se utiliza para capturar datos de DCM. Consulte <a href="../../features/manage-datasources.md#create-data-source"> Cómo crear una fuente</a>de datos. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Las señales descritas en la tabla se capturan en [!DNL Audience Manager] forma de `HTTP` llamada en tiempo real. La llamada de ejemplo siguiente contiene información sobre un evento de conversión de [!DNL DCM]. Las llamadas no necesariamente deben incluir *todas* las señales en la llamada de ejemplo.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {important="high"}
>
>La marca de tiempo del evento proporcionada en los [!DNL DCM] registros se respetará y pasará al [!UICONTROL Data Collection Servers].
>
>* Si no hay una marca de hora disponible para una fila de datos en el archivo de [!DNL DCM] registro, se utiliza la hora de la llamada como la marca de hora del `HTTP` evento.
>* Si la fila de datos del archivo de [!DNL DCM] registro contiene una marca de tiempo con formato incorrecto, se ignora toda la fila.


## Casos de uso {#use-cases}

Una de las ventajas de la implementación [!UICONTROL Actionable Log Files] es la opción de aplicar controles de [actualización y frecuencia](../../features/segments/recency-and-frequency.md) a cualquier característica basada en [reglas](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) que contenga señales procesables. Esto le permite, por ejemplo, limitar la frecuencia del número de veces que un usuario recibe un elemento creativo determinado en una campaña de medios. Otros casos de uso incluyen:

### Usuarios de reasignaciones

Vuelva a segmentar usuarios que hayan visto el elemento creativo 123 pero que no hayan hecho clic o convertido y muéstreles el elemento creativo 456. Haga esto:

1. Cree una característica para capturar a los usuarios que vieron el elemento creativo. Supongamos que se llama la característica [!DNL Creative Trait 123]. Utilice la regla de características:

   `d_creative == 123 AND d_event == imp`

1. Cree una característica para capturar a los usuarios que hacen clic o convierten. Supongamos que le llamas a éste [!DNL Click and Converter]. Utilice la regla de características:

   `d_event == click OR d_event=conv`

1. Cree un segmento para rellenarlo con los usuarios que vieron el elemento creativo 123 pero no hicieron clic ni convirtieron. Asígnele un nombre [!DNL Retarget Users] y utilice la regla de segmento:

   `Creative Trait 123 AND NOT Click and Converter`

1. Asigne el segmento [!DNL Retarget Users] a un destino y dirija la acción a los usuarios del destino con el elemento creativo 456.

### Utilizar la actividad de Floodlight de DCM en los informes de optimización de audiencia o en el Audience Lab

[Las etiquetas](https://support.google.com/dcm/partner/answer/4293719?hl=en) de Floodlight permiten a los anunciantes rastrear las conversiones de los usuarios. Con [!UICONTROL Actionable Log Files], puede realizar el seguimiento de las [!DNL DCM] conversiones en los informes [de optimización de](../../reporting/audience-optimization-reports/audience-optimization-reports.md) audiencias o en el [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Cree una característica y utilice la siguiente regla de características para capturar una conversión de los registros del servidor de publicidad:

   `d_event == conv AND d_conversion == 123`

   Al crear la característica en Audience Manager [!UICONTROL UI], seleccione [!UICONTROL Conversion] como [!UICONTROL Event Type].

2. Una vez que haya creado la característica, la conversión comenzará a registrarse en el informe [!UICONTROL Audience Optimization Reports] y en [!UICONTROL Audience Lab].

>[!MORE_LIKE_THIS]
>
>* [Importar archivos de datos de DCM en Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Informes de optimización de audiencia](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

