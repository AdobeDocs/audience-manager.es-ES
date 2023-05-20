---
description: El rastreo de clics permite medir la participación de los visitantes a lo largo de la campaña, ya que registra la actividad basada en clics para creativos de terceros.
seo-description: Click tracking enables measurement of visitor engagement throughout your campaign, as it records click-based activity for third-party creatives.
seo-title: Capturing Campaign Click Data via Pixel Calls
solution: Audience Manager
title: Captura de los datos de campaña por clic a través de Pixel Calls
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Adobe Campaign Integration
exl-id: 41b169bf-3727-4ed7-b74f-fea75244d2cb
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 10%

---

# Captura de los datos de campaña por clic a través de Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

El rastreo de clics permite medir la participación de los visitantes a lo largo de la campaña, ya que registra la actividad basada en clics para creativos de terceros. Similar a [colección impressions](/help/using/integration/media-data-integration/impression-data-pixels.md), se envía una llamada de evento a [!DNL Audience Manager] servidores de recopilación de datos ([!DNL DCS]) para su procesamiento. A continuación, se redirige al visitante a la dirección web deseada.

>[!NOTE]
>
>Póngase en contacto con su [!DNL Audience Manager] consultor o responsable de cuenta para el [!DNL URL] específico del dominio del cliente.

## Requisitos

Las llamadas de rastreo de clics requieren los siguientes parámetros:

* `d_event=click`: Un par clave-valor que identifica una llamada de evento como un evento de clic.
* `d_rd=redirect URL`: Un par clave-valor que contiene una redirección con codificación doble [!DNL URL]. Si está utilizando una herramienta de codificación en línea, ejecute la cadena a través del codificador y, a continuación, codifique el resultado de nuevo para que funcione la redirección.

Además, la llamada puede contener pares de clave-valor que se pueden utilizar para la clasificación de características o para proporcionar datos y metadatos para otros informes.

## Solicitar muestra

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Respuesta

La respuesta redirige el explorador a [!DNL URL] especificado en el `d_rd` parámetro. La cadena de respuesta puede incluir valores generados por cualquiera de las macros admitidas enumeradas a continuación.

En función del ejemplo anterior, el explorador se redirige a lo siguiente [!DNL URL]:

`https://adobe.com/callback?creative=123`

## Macros compatibles

Los eventos de clic admiten las macros enumeradas en la tabla siguiente. Una macro es una pequeña unidad de código independiente que se activa cuando se carga la etiqueta de anuncio para el seguimiento de campañas y usuarios. Las macros se pasarán junto con el destino [!DNL URL], siempre que estén marcados con el siguiente formato: `%macro%`. Algunas claves no tienen macros y aceptan un valor de ID codificado de forma rígida. Las claves que aceptan valores codificados son necesarias si desea analizar los datos en la variable [Informes del Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

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
   <td colname="col1"> <p> <code> d_adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_adgroup%</code> </p> </td> 
   <td colname="col2"> <p>ID de grupo de publicidad numérica del servidor de publicidad. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>No hay macro. </p> <p>Acepta un valor de ID codificado de forma rígida. </p> </td> 
   <td colname="col2"> <p>ID del anunciante.</p> <p>Un código de integración para la fuente de datos del anunciante. Tenga en cuenta que esto no está relacionado con las fuentes de datos de Audience Manager.</p> <p> Necesario para <span class="wintitle"> Audience Optimization</span> informes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>ID numérica de la unidad de negocio. </p> <p> Necesario para <span class="wintitle"> Audience Optimization</span> informes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>ID de campaña numérico del servidor de publicidad. </p> <p> Necesario para <span class="wintitle"> Audience Optimization</span> informes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>ID de creatividad numérica del servidor de publicidad. </p> <p>Requerido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>ID del proveedor de datos. </p> <p>Utilizado a menudo con <code> d_dpuuid</code> para vincular un ID de proveedor de datos a un ID de usuario. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>ID único de usuario proporcionado por el proveedor de datos. </p> <p>Utilizado a menudo con <code> d_dpid</code> para vincular un ID de usuario a un ID de proveedor de datos. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"></span> Experience Cloud ID (ECID). Para obtener más información sobre el ECID, consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies y el ID de Experience Cloud</a>. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>ID de ubicación numérica del servidor de publicidad. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>ID de región numérica para el clúster de DCS que atiende una solicitud. Para obtener más información sobre el DCS, consulte <a href="../../reference/system-components/components-data-collection.md"> Componentes de recopilación de datos</a>. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>Número aleatorio utilizado para la eliminación de caché. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>ID de sitio numérico del servidor de publicidad. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>DPID del origen desde el que el Audience Manager extrae los metadatos. </p> <p>Requerido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>Especifique la ID del visitante directamente en la URL, en lugar de depender de la cookie Demdex. </p> <p>Opcional. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p>Relacionado con el <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">complemento de Audience Manager para IAB TCF.</a> </p><p><code>gdpr</code> puede ser 0 (no se aplica el RGPD) o 1 (se aplica el RGPD).</p> <p>El valor predeterminado es 0.</p><p>Opcional.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p>Relacionado con el <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">complemento de Audience Manager para IAB TCF.</a></p><p> If <code>gdpr=1</code>, entonces <code>${gdpr_consent_XXXX}</code> se sustituye por el <code>gdpr_consent</code> y el ID del proveedor (consulte <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> Especificación de IAB</a>).</p> <p>El valor predeterminado es 0.</p><p>Opcional.</p></td> 
  </tr> 
 </tbody> 
</table>

## Ejemplo de macros

En este ejemplo se muestra cómo pasar las macros creative, adgroup y placement. Supone que los valores de cada parámetro se pasan en la parte de no redirección de la llamada de seguimiento de clics.

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> placement=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## Solicitud

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd%3Dhttp%253A%252F%252Fadobe.com%252Fcallback%253Fcreative%253D%2525d_creative%2525%2526campaign%253D%2525d_campaign%2525%2526adgroup%253D%2525%0Ad_adgroup%2525%2526d_placement%253D%2525placement%2525%2526src%253D%2525d_src%2525
```

## Respuesta

En función del ejemplo anterior, el explorador se redirige a lo siguiente [!DNL URL]:

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## Funcionalidad adicional: [!UICONTROL Audience Optimization Reports]

Puede utilizar llamadas en píxeles para activar el [Informes del Audience Optimization](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). Consulte [Información general y asignaciones para archivos de metadatos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) si desea utilizar píxeles para activar los informes.


>[!MORELIKETHIS]
>
>* [Archivos de metadatos y datos para informes de Audience Optimization](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

