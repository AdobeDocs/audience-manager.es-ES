---
description: Un método para enviar datos de medios a Audience Manager consiste en utilizar macros de servidor de anuncios para enviar atributos de campaña a Audience Manager.
seo-description: One approach for sending media data to Audience Manager uses ad server macros to send campaign attributes to Audience Manager.
seo-title: Capturing Campaign Impression Data via Pixel Calls
solution: Audience Manager
title: Captura de datos de impresión de campaña mediante llamadas de píxel
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
feature: Adobe Campaign Integration
exl-id: 04e6f1e5-5075-4221-a310-deb3717458ad
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 14%

---

# Captura de datos de impresión de campaña mediante llamadas de píxel{#capturing-campaign-impression-data-via-pixel-calls}

Un método para enviar datos de medios a Audience Manager consiste en utilizar macros de servidor de anuncios para enviar atributos de campaña a Audience Manager.

Esta metodología se conoce a menudo como &quot;pixelar al creativo&quot;. Estos puntos de datos se insertan dinámicamente en el código de píxeles [!DNL Audience Manager] mediante las macros de servidor de publicidad de terceros, que se utilizan para asignar y notificar todas las impresiones y clics según los atributos clave de sistema de informes de la campaña. Los datos agregados proporcionan una vista unificada del rendimiento de la campaña, ayudan a identificar rutas de conversión personalizadas y ayudan a los clientes a mejorar la secuencia de eventos del servidor de publicidad que generan conversiones.

## Sintaxis de llamada de evento

>[!NOTE]
>
>Los estilos de texto (`monospaced text`, *cursiva*, corchetes `[ ]` `( )`, etc.) indican elementos y opciones de código. Consulte [Convenciones de estilo para elementos de código y texto](../../reference/code-style-elements.md) para obtener más información.

La llamada de evento recopila datos de impresión y conversión y los envía a los [!DNL Audience Manager] [servidores de recopilación de datos](/help/using/reference/system-components/components-data-collection.md) ([!DNL DCS]). Este proceso se basa en servidores de publicidad de terceros que permiten al creativo decidir qué contenido se inserta en el código. Los servidores de publicidad de terceros (por ejemplo, [!DNL DFA]) pueden colocar este código dentro de cada impresión de publicidad. Además, una llamada de publicidad no utiliza [!DNL JavaScript] ni emplea técnicas de eliminación de fotogramas para acceder a los datos del editor fuera de la etiqueta de publicidad.

Las llamadas de evento constan de pares de clave-valor que utilizan la siguiente sintaxis:

```
https://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

En el par clave-valor, la variable de valor es una ID o macro insertada por el servidor de publicidad. Cuando se carga la etiqueta de anuncio, `%macro%` se reemplaza con los valores correspondientes requeridos. Esta llamada no devuelve una respuesta.

## Pares de clave-valor admitidos {#supported-key-value-pairs}

Las llamadas de evento de impresión aceptan datos formados en pares clave-valor. En la tabla siguiente se enumeran y describen las claves utilizadas para contener estas variables. Muchos de ellos son necesarios si desea capturar y analizar datos en [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Clave </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_adgroup </code> </td> 
   <td colname="col2"> <p>ID de grupo de publicidad numérica del servidor de publicidad. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>ID de fuente de datos o código de integración para el anunciante. </p> <p>Necesario para <span class="wintitle"> informes de Audience Optimization </span>. </p> <p>Opcional.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>ID de fuente de datos o código de integración para su unidad comercial. </p> <p>Necesario para <span class="wintitle"> informes de Audience Optimization </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Valor de eliminación de caché. <span class="keyword"> Audience Manager </span> envía automáticamente encabezados de control de caché que respetan la mayoría de los exploradores y proxies. Si desea realizar una eliminación de caché adicional, incluya este parámetro en una llamada de evento, seguido de una cadena aleatoria. </p> <p> Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>ID de campaña numérico del servidor de publicidad. </p> <p>Necesario para <span class="wintitle"> informes de Audience Optimization </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>En este contexto, <code> d_cid </code> crea una instancia de un par clave-valor que le permite asociar un tipo de dispositivo móvil a un ID de usuario único (DPUUID). Un ID fijo determina el tipo de dispositivo móvil. El valor, que es el ID de usuario, puede variar. Separe el par clave-valor con <code> %01 </code>, que es un carácter de control no imprimible. Este parámetro acepta las siguientes claves: </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914: Identifica un dispositivo Android (GAID). Por ejemplo, <code> d_cid = 20914 %01 1234 </code> indica que el usuario 1234 está asociado con un dispositivo Android. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915: Identifica un dispositivo iOS (IDFA). Por ejemplo, <code> d_cid = 20915 %01 5678 </code> indica que el usuario 5678 está asociado con un dispositivo iOS. </li> 
    </ul> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>ID de creatividad numérica del servidor de publicidad. </p> <p>Necesario para <span class="wintitle"> informes de Audience Optimization </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>Identifica una llamada de evento como un evento de impresión. </p> <p>Requerido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>ID de ubicación numérica del servidor de publicidad. </p> <p> Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>ID de sitio numérico del servidor de publicidad. </p> <p>Necesario para <span class="wintitle"> informes de Audience Optimization </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>ID de fuente de datos o código de integración de la plataforma que proporciona los metadatos (por ejemplo, DFA, Atlas, GBM, Media Math, etc.). </p> <p>Necesario para <span class="wintitle"> informes de Audience Optimization </span>. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p>Relacionado con el <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">complemento de Audience Manager para IAB TCF.</a></p> <p><code>gdpr</code> puede ser 0 (no se aplica el RGPD) o 1 (se aplica el RGPD).</p> <p>El valor predeterminado es 0.</p><p>Opcional.</p><p>Si es <code>gdpr=1</code>, el parámetro <code>gdpr_consent</code> debe contener el parámetro de consentimiento IAB TC para procesar los datos correctamente. De lo contrario, se perderán todos los datos.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p>Relacionado con el <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">complemento de Audience Manager para IAB TCF.</a></p><p> Si <code>gdpr=1</code>, entonces <code>${gdpr_consent_XXXX}</code> se reemplaza por la cadena <code>gdpr_consent</code> y el identificador de proveedor (consulte <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> especificación IAB</a>).</p> <p>El valor predeterminado es 0.</p><p>Opcional.</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Póngase en contacto con su asesor de Adobe Audience Manager o con el responsable de la cuenta para obtener la dirección URL exacta específica del dominio del cliente.

## Funcionalidad adicional: [!DNL Audience Optimization Reports] {#additional-functionality-aor}

Puede usar llamadas en píxeles para activar [Audience Optimization Reports](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). Consulte [Información general y asignaciones para archivos de metadatos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) si desea usar píxeles para alimentar los informes.

>[!MORELIKETHIS]
>
>* [Archivos de metadatos y datos para Audience Optimization Reports](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)
