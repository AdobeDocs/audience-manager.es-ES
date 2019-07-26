---
description: Un método para enviar datos de medios a Audience Manager usa macros de servidor de publicidad para enviar atributos de campaña a Audience Manager.
seo-description: Un método para enviar datos de medios a Audience Manager usa macros de servidor de publicidad para enviar atributos de campaña a Audience Manager.
seo-title: Capturación de los datos de impresión de campaña a través de Pixel Calls
solution: Audience Manager
title: Capturación de los datos de impresión de campaña a través de Pixel Calls
uuid: 6 ac 44100-4 c 55-4992-8835-0 d 578 bb 4 e 5 c 2
translation-type: tm+mt
source-git-commit: c79c2311c3ea76ce2450dc1b84a7a22b60a6edb7

---


# Capturación de los datos de impresión de campaña a través de Pixel Calls{#capturing-campaign-impression-data-via-pixel-calls}

Un método para enviar datos de medios a Audience Manager usa macros de servidor de publicidad para enviar atributos de campaña a Audience Manager.

Esta metodología suele conocerse como "pixelación del elemento creativo". Those data points are dynamically inserted into the [!DNL Audience Manager] pixel code by the third-party ad server macros, which are used to map and report all impressions and clicks based on the key reporting attributes of the campaign. Los datos agregados proporcionan una vista unificada del rendimiento de la campaña, ayudan a identificar las rutas de conversión personalizadas y ayudan a los clientes a mejorar la secuencia de eventos de servidor de publicidad que llevan a las conversiones.

## Sintaxis de llamada de evento

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *cursiva*, paréntesis `[ ]` `( )`, etc.) indicar elementos y opciones de código. Consulte [Convenciones de estilo para elementos de código y texto](../../reference/code-style-elements.md) para obtener más información.

La llamada de evento recopila datos de impresión y conversión y los envía a los [!DNL Audience Manager] [servidores de recopilación de datos](/help/using/reference/system-components/components-data-collection.md) ([!UICONTROL DCS]. Este proceso se basa en servidores de publicidad de terceros que permiten al creativo decidir qué contenido se inserta en el código. Los servidores de publicidad de terceros (por ejemplo, [!DNL DFA]) pueden colocar este código dentro de cada impresión de publicidad. Además, una llamada de publicidad no utiliza [!DNL JavaScript] ni emplea técnicas de eliminación de fotogramas para acceder a los datos del editor fuera de la etiqueta de publicidad.

Las llamadas de evento consisten en pares clave-valor que utilizan la siguiente sintaxis:

<pre>
http://clientname.demdex.net/event?d_event=imp&amp;d_src=datasource_id&amp;d_site=siteID&amp;
d_creative=<i>creative_id</i>&amp;d_adgroup=<i>adgroup_id</i>&amp;d_placement=<i>placement_id</i>
&amp;d_campaign=<i>campaign_id</i>[&amp;d_cid=(GAID|IDFA)%01 DPUUID]&amp;d_bust=cache buster value
</pre>

En el par clave-valor, la variable value es un ID o macro insertado por el servidor de publicidad. When the ad tag loads, that `%macro%` gets replaced with the required, corresponding values. Esta llamada no devuelve una respuesta.

## Supported Key-Value Pairs {#supported-key-value-pairs}

Las llamadas de evento de impresión aceptan datos formados en pares de valor clave. La siguiente tabla enumera y describe las claves utilizadas para albergar estas variables. Many of these are required if you want to capture and analyze data in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Clave </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_ adgroup </code> </td> 
   <td colname="col2"> <p>ID de grupo de publicidad numérico del servidor de publicidad. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ adsrc </code> </td> 
   <td colname="col2"> <p>ID de fuente de datos o código de integración para el anunciante. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ bu </code> </td> 
   <td colname="col2"> <p>ID de fuente de datos o código de integración para su unidad comercial. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bust </code> </p> </td> 
   <td colname="col2"> <p>Valor de eliminación de caché. <span class="keyword"> Audience Manager envía </span> automáticamente encabezados de control de caché que son aceptados por la mayoría de los exploradores y proxies. Si desea realizar una llamada adicional de caché, incluya este parámetro en una llamada de evento, seguido de una cadena aleatoria. </p> <p> Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ campaign </code> </td> 
   <td colname="col2"> <p>ID de campaña numérica del servidor de publicidad. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In this context, <code> d_cid </code> instantiates a key-value pair that lets you associate a mobile device type to a unique user ID (DPUUID). Un ID fijo determina el tipo de dispositivo móvil. El valor, que es el ID de usuario, puede variar. Separate the key-value pair with <code> %01 </code>, which is a non-printing control character. Este parámetro acepta las claves siguientes: </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914: Identifica un dispositivo Android (GAID). For example, <code> d_cid = 20914 %01 1234 </code> says that user 1234 is associated with an Android device. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915: Identifica un dispositivo de iOS (IDFA). For example, <code> d_cid = 20915 %01 5678 </code> says that user 5678 is associated with an iOS device. </li> 
    </ul> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ creative </code> </td> 
   <td colname="col2"> <p>ID creativos numéricos del servidor de publicidad. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ event = imp </code> </td> 
   <td colname="col2"> <p>Identifica una llamada de evento como un evento de impresión. </p> <p>Requerido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ placement </code> </td> 
   <td colname="col2"> <p>ID de ubicación numérica del servidor de publicidad. </p> <p> Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ site </code> </td> 
   <td colname="col2"> <p>ID numérico del sitio del servidor de publicidad. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ src </code> </td> 
   <td colname="col2"> <p>ID de fuente de datos o código de integración de la plataforma que proporciona los metadatos (por ejemplo, DFA, Atlas, GBM, Media Math, etc.). </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code><i>gdpr</i></code>  </td> 
   <td colname="col2"> <p>Relacionado con el <a href="../../overview/aam-gdpr/aam-iab-plugin.md">complemento de Audience Manager para IAB TCF.</a></p> <p><code>rdpr</code> puede ser 0 (el RGPD no se aplica) o 1 (se aplica RGPD).</p> <p>El valor predeterminado es 0.</p><p>Opcional.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_ permission</code> </td> 
   <td colname="col2"> <p>Relacionado con el <a href="../../overview/aam-gdpr/aam-iab-plugin.md">complemento de Audience Manager para IAB TCF.</a></p><p> Si <code>gdpr=1</code>, entonces <code>%gdpr_consent%</code> se sustituye por la cadena <code>gdpr_consent</code> (consulte la especificación <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">IAB</a>).</p> <p>El valor predeterminado es 0.</p><p>Opcional.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Comuníquese con el consultor de Adobe Audience Manager o con el lead lead de la URL exacta específica del dominio de cliente.

>[!MORE_ LIKE_ THIS]
>
>* [Archivos de metadatos y datos para informes de optimización de audiencias](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

