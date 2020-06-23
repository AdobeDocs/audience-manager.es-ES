---
description: 'null'
seo-description: 'null'
seo-title: Captura de datos de clics en Campaña mediante llamadas de píxel
solution: Audience Manager
title: Captura de datos de clics en Campaña mediante llamadas de píxel
uuid: 7c3797f7-9674-493d-972b-38be0584fede
translation-type: tm+mt
source-git-commit: 620730ab1596d4777a768de4453b73538671279d
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 7%

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

El rastreo de clics permite medir el compromiso de visitantes en toda la campaña, ya que registra la actividad basada en clics para elementos creativos de terceros. De forma similar a la recopilación [de](/help/using/integration/media-data-integration/impression-data-pixels.md)impresiones, se envía una llamada de evento a los servidores [!DNL Audience Manager] de recopilación de datos ([!DNL DCS]) para su procesamiento. A continuación, el visitante se redirige a la dirección web deseada.

>[!NOTE]
>
>Póngase en contacto con su asesor [!DNL Audience Manager] o con el posible cliente de la cuenta para conocer el [!DNL URL] contenido específico del dominio cliente.

## Requisitos

Las llamadas de seguimiento de clics requieren los siguientes parámetros:

* `d_event=click`:: Un par clave-valor que identifica una llamada de evento como un evento de clics.
* `d_rd=redirect URL`:: Un par clave-valor que contiene una redirección codificada para dobles [!DNL URL]. Si utiliza una herramienta de codificación en línea, ejecute la cadena a través del codificador y, a continuación, vuelva a codificar el resultado para que la redirección funcione.

Además, la llamada puede contener pares de clave-valor que se pueden utilizar para la calificación de características o para proporcionar datos y metadatos para otros informes.

## Muestra de solicitud

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Respuesta

La respuesta redirige el explorador al [!DNL URL] especificado en el `d_rd` parámetro. La cadena de respuesta puede incluir valores generados por cualquiera de las macros admitidas que se enumeran a continuación.

Según el ejemplo anterior, el explorador se redirige a lo siguiente [!DNL URL]:

`https://adobe.com/callback?creative=123`

## Macros admitidos

Haga clic en eventos para admitir las macros enumeradas en la tabla siguiente. Una macro es una pequeña unidad de código independiente que se activa cuando se carga la etiqueta de publicidad para campaña y seguimiento de usuarios. Las macros se pasarán junto con el destino [!DNL URL], siempre que estén marcadas con el siguiente formato: `%macro%`. Algunas claves no tienen macros y aceptan un valor de ID incrustado. Se requieren claves que acepten valores codificados si desea analizar los datos en los informes [de optimización de](../../reporting/audience-optimization-reports/audience-optimization-reports.md)Audiencia.

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
   <td colname="col2"> <p>ID del grupo de publicidad numérica desde el servidor de publicidad. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>Sin macro. </p> <p>Acepta un valor de ID codificado. </p> </td> 
   <td colname="col2"> <p>ID del anunciante.</p> <p>Código de integración de la fuente de datos del anunciante. Tenga en cuenta que esto no está relacionado con las fuentes de datos de Audience Manager.</p> <p> Necesario para los informes de Optimización <span class="wintitle"> de</span> Audiencia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>ID numérico para la unidad de negocio. </p> <p> Necesario para los informes de Optimización <span class="wintitle"> de</span> Audiencia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>ID de campaña numérica del servidor de publicidad. </p> <p> Necesario para los informes de Optimización <span class="wintitle"> de</span> Audiencia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>ID creativa numérica del servidor de publicidad. </p> <p>Requerido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>ID del proveedor de datos. </p> <p>A menudo se utiliza con <code> d_dpuuid</code> para vincular un ID de proveedor de datos a un ID de usuario. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>ID de usuario único proporcionada por el proveedor de datos. </p> <p>A menudo se utiliza con <code> d_dpid</code> para vincular un ID de usuario a un ID de proveedor de datos. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID (ECID). </span> For more information about the ECID, see <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>ID de ubicación numérica desde el servidor de publicidad. </p> <p>Opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>ID de región numérica para el clúster de DCS que atiende una solicitud. Para obtener más información sobre el DCS, consulte <a href="../../reference/system-components/components-data-collection.md"> Componentes</a>de recopilación de datos. </p> <p>Opcional. </p> </td> 
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
   <td colname="col2"> <p>DPID del origen desde el que Audience Manager extrae los metadatos. </p> <p>Requerido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>Especifique el ID del visitante directamente en la URL en lugar de depender de la cookie Demdex. </p> <p>Opcional. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p>Relacionado con el <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">complemento de Audience Manager para IAB TCF.</a> </p><p><code>gdpr</code> puede ser 0 (no se aplica el RGPD) o 1 (se aplica el RGPD).</p> <p>El valor predeterminado es 0.</p><p>Opcional.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p>Relacionado con el <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">complemento de Audience Manager para IAB TCF.</a></p><p> Si <code>gdpr=1</code>, entonces <code>${gdpr_consent_XXXX}</code> se reemplaza por la <code>gdpr_consent</code> cadena y el ID del proveedor (consulte <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> la especificación</a>IAB).</p> <p>El valor predeterminado es 0.</p><p>Opcional.</p></td> 
  </tr> 
 </tbody> 
</table>

## Ejemplo de macros

En este ejemplo se muestra cómo pasar las macros de elementos creativos, grupos de publicidad y colocación. Supone que los valores de cada parámetro se pasan en la parte no redireccionada de la llamada de seguimiento de clics.

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

Según el ejemplo anterior, el explorador se redirige a lo siguiente [!DNL URL]:

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## Funcionalidad adicional: [!UICONTROL Audience Optimization Reports]

Puede utilizar llamadas en píxeles para activar los informes [de optimización de](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md)Audiencia. Consulte [Información general y asignaciones para archivos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) de metadatos si desea utilizar píxeles para activar los informes.


>[!MORELIKETHIS]
>
>* [Archivos de datos y metadatos para informes de optimización de Audiencia](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

