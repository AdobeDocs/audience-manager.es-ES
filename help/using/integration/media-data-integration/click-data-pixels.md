---
description: 'null'
seo-description: 'null'
seo-title: Captura de datos de clic de campaña mediante llamadas de píxel
solution: Audience Manager
title: Captura de datos de clic de campaña mediante llamadas de píxel
uuid: 7 c 3797 f 7-9674-493 d -972 b -38 be 0584 fede
translation-type: tm+mt
source-git-commit: c79c2311c3ea76ce2450dc1b84a7a22b60a6edb7

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

El rastreo de clics permite medir el compromiso de los visitantes en toda la campaña, ya que registra la actividad basada en clics para creativos de terceros. Similar to impressions collection, an event call is sent to the Audience Manager data collection servers ([!UICONTROL DCS]) for processing. A continuación, se redirige al visitante a la dirección Web prevista.

## Requisitos

Las llamadas de rastreo de clics requieren los parámetros siguientes:

* `d_event=click`: Par clave-valor que identifica una llamada de evento como evento de clic.
* `d_rd=redirect URL`: Par clave-valor que contiene una redirección [!DNL URL]codificada.

Además, la llamada puede contener pares de clave-valor que se pueden utilizar para la cualificación de características o para proporcionar datos y metadatos para otros informes.

## Muestra de solicitud

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Respuesta

The response redirects the browser to the [!DNL URL] specified in the `d_rd` parameter. La cadena de respuesta puede incluir valores generados por cualquiera de las macros admitidas a continuación.

Based on the above example, the browser is redirected to the following [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=123`]

## Macros admitidas

Los eventos de clic admiten las macros enumeradas en la siguiente tabla. Una macro es una pequeña unidad de código independiente que se activa cuando se carga la etiqueta de publicidad para la campaña y el seguimiento de usuarios. The macros will be passed along with the destination [!DNL URL], as long as they are marked with the following format: `%macro%`. Algunas claves no tienen macros y aceptan un valor de ID prefijado. Keys that accept hard coded values are required if you want to analyze data in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Clave </th> 
   <th colname="col02" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ grupo de publicidad % d</code> </p> </td> 
   <td colname="col2"> <p>ID de grupo de publicidad numérico del servidor de publicidad. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsrc</code> </p> </td> 
   <td colname="col02"> <p>Sin macro. </p> <p>Acepta un valor de ID codificado. </p> </td> 
   <td colname="col2"> <p> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> ID de fuente</a> de datos o código de integración para el anunciante. </p> <p> Required for <span class="wintitle"> Audience Optimization</span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ bu %</code> </p> </td> 
   <td colname="col2"> <p>ID numérico para la unidad comercial. </p> <p> Required for <span class="wintitle"> Audience Optimization</span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ campaign %</code> </p> </td> 
   <td colname="col2"> <p>ID de campaña numérica del servidor de publicidad. </p> <p> Required for <span class="wintitle"> Audience Optimization</span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ creative %</code> </p> </td> 
   <td colname="col2"> <p>ID creativos numéricos del servidor de publicidad. </p> <p>Requerido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ id %</code> </p> </td> 
   <td colname="col2"> <p>ID del proveedor de datos. </p> <p>Often used with <code> d_dpuuid</code> to link a data provider ID to a user ID. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ dpuuid %</code> </p> </td> 
   <td colname="col2"> <p>ID de usuario único proporcionado por el proveedor de datos. </p> <p>Often used with <code> d_dpid</code> to link a user ID to a data provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID (ECID). </span> For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ placement</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ placement %</code> </p> </td> 
   <td colname="col2"> <p>ID de ubicación numérica del servidor de publicidad. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ region</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ region %</code> </p> </td> 
   <td colname="col2"> <p>ID de región numérica para el clúster del DCS que servicios una solicitud. For more information about the DCS, see <a href="../../reference/system-components/components-data-collection.md"> Data Collection Components</a>. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_ rand</code> </p> </td> 
   <td colname="col02"> <p> <code> % r_ rand %</code> </p> </td> 
   <td colname="col2"> <p>Número aleatorio utilizado para la eliminación de caché. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ site</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ site %</code> </p> </td> 
   <td colname="col2"> <p>ID numérico del sitio del servidor de publicidad. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ src %</code> </p> </td> 
   <td colname="col2"> <p>DPID del origen desde el que Audience Manager extrae los metadatos. </p> <p>Requerido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ uuid %</code> </p> </td> 
   <td colname="col2"> <p>Especifique el ID del visitante directamente en la URL en lugar de depender de la cookie Demdex. </p> <p>Opcional. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>% gdpr_ aplica %</code> </p> </td> 
   <td colname="col2"> <p>Relacionado con el <a href="../../overview/aam-gdpr/aam-iab-plugin.md">complemento de Audience Manager para IAB TCF.</a> </p><p><code>rdpr</code> puede ser 0 (el RGPD no se aplica) o 1 (se aplica RGPD).</p> <p>El valor predeterminado es 0.</p><p>Opcional.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_ permission</code> </p> </td> 
   <td colname="col02"> <p> <code>% gdpr_ permission %</code> </p> </td> 
   <td colname="col2"> <p>Relacionado con el <a href="../../overview/aam-gdpr/aam-iab-plugin.md">complemento de Audience Manager para IAB TCF.</a></p><p> Si <code>gdpr=1</code>, entonces <code>%gdpr_consent%</code> se sustituye por la cadena <code>gdpr_consent</code> (consulte la especificación <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">IAB</a>).</p> <p>El valor predeterminado es 0.</p><p>Opcional.</p></td> 
  </tr> 
 </tbody> 
</table>

## Ejemplo de macros

En este ejemplo se muestra el paso de las macros de elementos creativos, de grupo de publicidad y de colocación. Asume que los valores de cada parámetro se pasan en la porción no redireccionada de la llamada de rastreo de clics.

<ul class="simplelist"> 
 <li> <code> creative = 1235 </code> </li> 
 <li> <code> campaign = 4709 </code> </li> 
 <li> <code> grupo de publicidad = 3408 </code> </li> 
 <li> <code> placement = 1001 </code> </li> 
 <li> <code> src = 203 </code> </li> 
</ul>

## Solicitud

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25%26campaign%3D%25d_campaign%25%26adgroup%3D%25
d_adgroup%25%26d_placement%3D%25placement%25%26src%3D%25d_src%25
```

## Respuesta

Based on the above example, the browser is redirected to the following [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORE_ LIKE_ THIS]
>
>* [Archivos de metadatos y datos para informes de optimización de audiencias](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

