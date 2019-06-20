---
description: Crea una instancia DIL específica del socio.
seo-description: Crea una instancia DIL específica del socio.
seo-title: DIL Create
solution: Audience Manager
title: DIL Create
uuid: 6 e 054600-703 c -4 a 97-af 2 a -8207 c 50013 db
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL create method{#dil-create}

## DIL create {#dil-create-new}

Creates a partner-specific [!UICONTROL DIL] instance.

**Firma de función:**`DIL.create: function (initConfig) {}`

**Initconfig Elements**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>The `visitorService` property is *always* required. Otras propiedades enumeradas aquí son opcionales, a menos que se indique lo contrario.

`initConfig` acepta los siguientes elementos:

<table id="table_1334973505F54B238127FED9845B16C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> containerNSID </code> </p> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>Esta propiedad define el ID de contenedor que utiliza <span class="keyword">Audience Manager</span> para sincronizar los ID. You would set <code> containerNSID </code> if you have <span class="wintitle"> DIL </span> deployed across multiple sites. Cada uno de estos sitios tendrá su propio ID de contenedor y sincronizaciones de ID. Cuando solo tiene 1 sitio, el ID de contenedor es 0 de forma predeterminada y no es necesario establecerlo correctamente. Póngase en contacto con su asesor para obtener una lista de sus sitios y sus ID de contenedor. </p> <p>In the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID service </a>, the property <code> idSyncContainerID </code> corresponds to <code> containerNSID </code> in <span class="wintitle"> DIL </span>. Note the following if you're using <span class="wintitle"> DIL </span> <i>and</i> the ID service across multiple sites: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">For each site, set the same container IDs on <code> containerNSID </code> and <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF"><span class="wintitle"> Tanto DIL </span> como el servicio de ID intentarán enviar sincronizaciones de ID a nuestra iframe de recopilación de datos. However, the iFrame ensures that <span class="wintitle"> DIL </span> won't fire an ID sync. Esto evita la duplicación. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F"><span class="wintitle"> Solo DIL </span> envía datos a un destino <a href="../../features/destinations/destinations.md"></a>URL. </li> 
     </ul> </p> <p>See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Declaredid </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> 
    <draft-comment> 
     <p>Sends the <a href="../../features/declared-ids.md"> Declared ID variables </a> on every event call to <span class="keyword"> Audience Manager </span>. </p> 
    </draft-comment> <p> <code> Delcaredid </code> se utiliza para pasar: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID de socio de datos asignado por <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Su ID exclusivo para un usuario. </li> 
    </ul> <p> <p>Importante: Utilice únicamente valores no codificados para sus ID. La codificación creará identificadores con doble codificación. </p> </p> <p> <p>Note:  If you use the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID Service </a>, set customer IDs with the <code> setCustomerIDs </code> method instead of <span class="wintitle"> DIL </span>. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Delayalluntilwindowload </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> If true, defers all requests (IFRAME, event calls, ID sync, and destinationing) from executing until the <code> Page Load </code> event fires. Default is <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Disabledeclareduuidcookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Falso by default, which means <span class="keyword"> Audience Manager </span> sets a cookie in the partner's domain (sets a first party cookie). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <code> visitor.disableIdSyncs </code> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> function </a> in the Experience Cloud ID Service instead. </p> </p> <p> If <code> true </code>, will not attach the destination publishing IFRAME to the DOM or fire destinations. Default is <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <code> visitor.disableIdSyncs </code> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> function </a> in the Experience Cloud ID Service instead. </p> </p> <p>Deshabilita la sincronización de ID. Debe deshabilitar las sincronizaciones de ID al utilizar DIL v 6.2 + y el servicio de ID de visitante. The <code> visitorService </code> function (see sample code below) takes care of this operation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Enableerrorreporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Set to <code> true </code> to enable error reporting for all <span class="wintitle"> DIL </span> instances on the page. Works with Boolean <code> true </code> only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <code> visitor.idSyncSSLUseAkamai </code> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idSyncSSLUseAkamai.html" format="https" scope="external"> function </a> in the Experience Cloud ID Service instead. </p> </p> <p> Especifica si la plantilla de publicación de destino debería utilizar Akamai para conexiones HTTPS. Habilitado por socio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> asignaciones </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Asocia el valor de un par clave-valor a otro. See <a href="../../dil/dil-use-cases.md#map-key-values"> Map Key Values to Other Keys </a>. Publicado con v 2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Requerido. </p> <p>The <code> namespace </code> key-value pair contains your <span class="keyword"> Experience Cloud </span> Organization ID. If you don't have this ID, you can find it in the <span class="wintitle"> Administration </span> section of the <span class="keyword"> Experience Cloud </span> dashboard. Necesita permisos de administrador para ver este tablero. See the <a href="../../faq/faq-features.md"> Product Features and Functions FAQ </a> and <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> Administration - User Management and FAQ </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> socio </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Requerido. </p> <p> Partner name as provided by <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Removefinishedscriptsandcallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Elimina las secuencias de comandos y las rellamadas. Default is <code> False </code>. Applies to the current <span class="wintitle"> DIL </span> instance only. Publicado con v 3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Uuidcookie </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Sets a cookie with the unique user ID returned from <span class="keyword"> Audience Manager </span>. See <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie Properties </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Visitorservice </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Required with <span class="wintitle"> DIL </span> 6.2 or greater. </p> <p> DIL relies on the <code> setCustomerIDs </code> function in the <span class="wintitle"> Experience Cloud ID Service </span> to pass declared IDs into <span class="keyword"> Audience Manager </span>. Consulte <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external">ID de cliente y estados de autenticación</a> para obtener más información. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Código de ejemplo**

A sample [!UICONTROL DIL] call could look similar to the following:

```js
var partnerObject1 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-ORGANIZATION-ID-HERE" 
  }, 
  containerNSID: 3, 
  uuidCookie:{ 
    name:'ad_uuid', 
    days:200, 
    path:'/test', 
    domain:'adobe.com', 
    secure:true 
  } 
}); 
 
var partnerObject2 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-MCORG-ID-HERE" 
  }, 
  containerNSID: 3 
}); 
```

A successful response returns the [!UICONTROL DIL] instance. Un intento fallido devuelve un objeto de error (no se genera) si el código está configurado incorrectamente o siempre que se encuentra un error.

## uuidCookie Properties {#uuidcookie-props}

Defines the properties used by the `uuidCookie` variable. This variable is part of the `DIL.create` method.

`uuidCookie` tiene las siguientes propiedades:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nombre | Descripción |
|---|---|
| `name` | The cookie name ( `aam_did` is default). |
| `days` | Duración de la cookie (100 días es predeterminada). |
| `path` | Cookie path, e.g., `'/test'` ( `/` is default). |
| `domain` | The domain the cookie is set in, e.g., `'adobe.com'` ( `'.'+document.domain` is default). |
| `secure` | Define un indicador para enviar datos únicamente a través de una conexión HTTPS. |

## visitorService Properties {#visitor-service-props}

Defines the properties used by the `visitorService` variable. This variable is part of the `DIL.create` method.

`visitorService` tiene las siguientes propiedades:

| Nombre | Tipo | Descripción |
|---|---|---|
| `namespace` | Cadena | Requerido. Representa el ID de organización de Experience Cloud. Esto es necesario para la funcionalidad de servicio principal de Experience Cloud. El mismo parámetro utilizado para crear una instancia de la funcionalidad de ID de visitante. |

**Ejemplo de código:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
