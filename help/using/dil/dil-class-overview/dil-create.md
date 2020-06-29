---
description: Crea una instancia DIL específica del socio.
seo-description: Crea una instancia DIL específica del socio.
seo-title: DIL crear
solution: Audience Manager
title: DIL crear
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 9%

---


# Método de creación DIL{#dil-create}

## DIL crear {#dil-create-new}

Crea una [!UICONTROL DIL] instancia específica del socio.

**Firma de función:** `DIL.create: function (initConfig) {}`

**elementos initConfig**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>La `visitorService` propiedad *siempre* es necesaria. Otras propiedades enumeradas aquí son opcionales, a menos que se indique lo contrario.

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
   <td colname="col3"> <p>Esta propiedad define el ID de contenedor que utiliza <span class="keyword">Audience Manager</span> para sincronizar los ID. Se configuraría <code> containerNSID </code> si se ha implementado <span class="wintitle"> DIL </span> en varios sitios. Cada uno de estos sitios tendrá su propio ID de contenedor y sincronizaciones de ID. Cuando solo tiene 1 sitio, el ID de contenedor es 0 de forma predeterminada y no necesita configurarlo correctamente. Póngase en contacto con el consultor para obtener una lista de los sitios y sus ID de contenedor. </p> <p>En el servicio de identidad de <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform </a>, la propiedad <code> idSyncContainerID </code> corresponde a <code> containerNSID </code> en <span class="wintitle"> DIL </span>. Tenga en cuenta lo siguiente si utiliza <span class="wintitle"> DIL </span> y el servicio de ID en varios <i></i> sitios: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Para cada sitio, establezca los mismos ID de contenedor en <code> containerNSID </code> y <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Tanto <span class="wintitle"> DIL </span> como el servicio de ID intentarán enviar sincronizaciones de ID a nuestro iFrame de recopilación de datos. Sin embargo, el iFrame garantiza que <span class="wintitle"> DIL </span> no active una sincronización de ID. Esto evita la duplicación. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Solo <span class="wintitle"> DIL </span> envía datos a un destino <a href="../../features/destinations/destinations.md"> URL </a>. </li> 
     </ul> </p> <p>Consulte también <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> 
    <draft-comment> 
     <p>Envía las variables de ID declaradas <a href="../../features/declared-ids.md"> </a> en cada llamada de evento al <span class="keyword"> Audience Manager </span>. </p> 
    </draft-comment> <p> <code> delcaredId </code> se utiliza para pasar el: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>:: ID del socio de datos que le ha asignado el <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>:: Su ID única para un usuario. </li> 
    </ul> <p> <p>Importante:  Utilice únicamente valores no codificados para sus ID. La codificación creará identificadores con codificación de doble. </p> </p> <p> <p>Nota:  Si utiliza el servicio de identidad de <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform </a>, configure los ID de cliente con el <code> setCustomerIDs </code> método en lugar de <span class="wintitle"> DIL </span>. See <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Si es true, se retrasa la ejecución de todas las solicitudes (IFRAME, llamadas de evento, sincronización de ID y destino) hasta que se activa el <code> Page Load </code> evento. El valor predeterminado es <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Falso de forma predeterminada, lo que significa que el <span class="keyword"> Audience Manager </span> establece una cookie en el dominio del socio (establece una cookie de origen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento está en desuso con <span class="wintitle"> DIL </span> versión 8.0 (lanzado en agosto de 2018). En su lugar, utilice la <code> visitor.disableIdSyncs </code> función <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> </a> del servicio de identidad de Adobe Experience Platform. </p> </p> <p> Si <code> true </code>, no adjuntará el IFRAME de publicación de destino a los destinos DOM o fire. El valor predeterminado es <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento está en desuso con <span class="wintitle"> DIL </span> versión 8.0 (lanzado en agosto de 2018). En su lugar, utilice la <code> visitor.disableIdSyncs </code> función <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> </a> del servicio de identidad de Adobe Experience Platform. </p> </p> <p>Deshabilita la sincronización de ID. Debe deshabilitar las sincronizaciones de ID al utilizar DIL v6.2+ y el servicio de ID de Visitante. La <code> visitorService </code> función (consulte el código de muestra a continuación) se encarga de esta operación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Establezca en <code> true </code> para habilitar el sistema de informes de errores para todas las <span class="wintitle"> instancias de DIL </span> en la página. Funciona <code> true </code> solo con booleano. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento está en desuso con <span class="wintitle"> DIL </span> versión 8.0 (lanzado en agosto de 2018). En su lugar, utilice la <code> visitor.idSyncSSLUseAkamai </code> función <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> </a> del servicio de identidad de Adobe Experience Platform. </p> </p> <p> Especifica si la plantilla de publicación de destino debería utilizar Akamai para conexiones HTTPS. Habilitado por socio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Asocia el valor de un par clave-valor a otro. Consulte <a href="../../dil/dil-use-cases.md#map-key-values"> Asignación de valores clave a otras claves </a>. Publicado con v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Requerido. </p> <p>El par <code> namespace </code> clave-valor contiene el identificador de organización <span class="keyword"> Experience Cloud </span> . Si no tiene este ID, puede encontrarlo en la sección <span class="wintitle"> Administración </span> del <span class="keyword"> panel del Experience Cloud </span> . Necesita permisos de administrador para vista de este panel. Consulte las preguntas más frecuentes sobre las funciones y características del <a href="../../faq/faq-features.md"> producto </a> y <a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> Administración - Administración de usuarios y preguntas más frecuentes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Requerido. </p> <p> Nombre del socio proporcionado por el <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Elimina las secuencias de comandos y las rellamadas. El valor predeterminado es <code> False </code>. Solo se aplica a la instancia <span class="wintitle"> DIL actual </span> . Publicado con v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Establece una cookie con el ID de usuario único que devuelve el <span class="keyword"> Audience Manager </span>. Consulte <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> Propiedades de uuidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Necesario con <span class="wintitle"> DIL </span> 6.2 o bueno. </p> <p> DIL se basa en la <code> setCustomerIDs </code> función del servicio de identidad de <span class="wintitle"> Adobe Experience Platform </span> para pasar los ID declarados al <span class="keyword"> Audience Manager </span>. Consulte <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external">ID de cliente y estados de autenticación</a> para obtener más información. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Código de ejemplo**

Una llamada de ejemplo [!UICONTROL DIL] podría tener un aspecto similar al siguiente:

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

Una respuesta correcta devuelve la [!UICONTROL DIL] instancia. Un intento fallido devuelve un objeto de error (no generado) si el código está configurado incorrectamente o si se encuentra un error.

## Propiedades de uuidCookie {#uuidcookie-props}

Define las propiedades utilizadas por la `uuidCookie` variable. Esta variable forma parte del `DIL.create` método.

`uuidCookie` tiene las siguientes propiedades:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nombre | Descripción |
|---|---|
| `name` | The cookie name ( `aam_did` is default). |
| `days` | Duración de la cookie (100 días es el valor predeterminado). |
| `path` | Ruta de la cookie, por ejemplo: `'/test'` ( `/` es predeterminada). |
| `domain` | Dominio en el que se establece la cookie, por ejemplo `'adobe.com'` ( `'.'+document.domain` es el valor predeterminado). |
| `secure` | Establece un indicador para enviar datos solo a través de una conexión HTTPS. |

## Propiedades de visitorService {#visitor-service-props}

Define las propiedades utilizadas por la `visitorService` variable. Esta variable forma parte del `DIL.create` método.

`visitorService` tiene las siguientes propiedades:

| Nombre | Tipo | Descripción |
|---|---|---|
| `namespace` | Cadena | Requerido. Representa El Id. De La Organización Experience Cloud. Esto es necesario para la funcionalidad del servicio principal de Experience Cloud. El mismo parámetro utilizado para crear instancias de la funcionalidad de ID de Visitante. |

**Ejemplo de código:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
