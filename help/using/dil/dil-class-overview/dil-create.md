---
description: Crea una instancia de DIL específica del socio.
seo-description: Crea una instancia de DIL específica del socio.
seo-title: DIL crear
solution: Audience Manager
title: DIL crear
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 12%

---


# DIL create method{#dil-create}

## DIL crear {#dil-create-new}

Crea una instancia [!UICONTROL DIL] específica del socio.

**Firma de función:** `DIL.create: function (initConfig) {}`

**elementos initConfig**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>La propiedad `visitorService` es *siempre* necesaria. Otras propiedades enumeradas aquí son opcionales, a menos que se indique lo contrario.

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
   <td colname="col3"> <p>Esta propiedad define el ID de contenedor que utiliza <span class="keyword">Audience Manager</span> para sincronizar los ID. Establecería <code> containerNSID </code> si tiene <span class="wintitle"> DIL </span> implementado en varios sitios. Cada uno de estos sitios tendrá su propio ID de contenedor y sincronizaciones de ID. Cuando solo tiene 1 sitio, el ID de contenedor es 0 de forma predeterminada y no necesita configurarlo correctamente. Póngase en contacto con el consultor para obtener una lista de los sitios y sus ID de contenedor. </p> <p>En el <a href="https://docs.adobe.com/content/help/es-ES/id-service/using/home.html" format="https" scope="external"> servicio de identidad de Adobe Experience Platform </a>, la propiedad <code> idSyncContainerID </code> corresponde a <code> containerNSID </code> en el DIL <span class="wintitle"> </span>. Tenga en cuenta lo siguiente si está utilizando <span class="wintitle"> DIL </span> <i>y</i> el servicio de ID en varios sitios: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Para cada sitio, establezca los mismos ID de contenedor en <code> containerNSID </code> y <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Tanto el <span class="wintitle"> DIL </span> como el servicio de ID intentarán enviar sincronizaciones de ID a nuestro iFrame de recopilación de datos. Sin embargo, el iFrame garantiza que el <span class="wintitle"> DIL </span> no active una sincronización de ID. Esto evita la duplicación. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Sólo el <span class="wintitle"> DIL </span> envía datos a un <a href="../../features/destinations/destinations.md"> destino de dirección URL </a>. </li> 
     </ul> </p> <p>Consulte también, <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> se utiliza para pasar el: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>:: ID del socio de datos que le ha asignado el  <span class="keyword"> Audience Manager  </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>:: Su ID única para un usuario. </li> 
    </ul> <p> <p>Importante:  Utilice únicamente valores no codificados para sus ID. La codificación creará identificadores con codificación de doble. </p> </p> <p> <p>Nota:  Si utiliza el <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> servicio de identidad de Adobe Experience Platform </a>, configure los ID de cliente con el método <code> setCustomerIDs </code> en lugar del DIL <span class="wintitle"> </span>. Consulte <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external"> ID de cliente y estados de autenticación </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Si es true, se retrasa la ejecución de todas las solicitudes (IFRAME, llamadas de evento, sincronización de ID y destino) hasta que se activa el evento <code> Page Load </code>. El valor predeterminado es <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Falso de forma predeterminada, lo que significa que <span class="keyword"> Audience Manager </span> establece una cookie en el dominio del socio (establece una cookie de origen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento se ha desaprobado con la versión 8.0 del <span class="wintitle"> DIL </span> (publicada en agosto de 2018). En su lugar, utilice la función <code> visitor.disableIdSyncs </code> <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> en el servicio de identidad de Adobe Experience Platform.</a> </p> </p> <p> Si <code> true </code>, no adjuntará el IFRAME de publicación de destino a los destinos DOM o fire. El valor predeterminado es <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento se ha desaprobado con la versión 8.0 del <span class="wintitle"> DIL </span> (publicada en agosto de 2018). En su lugar, utilice la función <code> visitor.disableIdSyncs </code> <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> en el servicio de identidad de Adobe Experience Platform.</a> </p> </p> <p>Deshabilita la sincronización de ID. Debe desactivar las sincronizaciones de ID al utilizar DIL v6.2 o posterior y el servicio de ID de Visitante. La función <code> visitorService </code> (consulte el código de muestra a continuación) se encarga de esta operación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Establezca <code> true </code> para habilitar el sistema de informes de errores para todas las instancias <span class="wintitle"> del DIL </span> de la página. Funciona solo con booleano <code> true </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Este elemento se ha desaprobado con la versión 8.0 del <span class="wintitle"> DIL </span> (publicada en agosto de 2018). En su lugar, utilice la función <code> visitor.idSyncSSLUseAkamai </code> <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> en el servicio de identidad de Adobe Experience Platform.</a> </p> </p> <p> Especifica si la plantilla de publicación de destino debería utilizar Akamai para conexiones HTTPS. Habilitado por socio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Asocia el valor de un par clave-valor a otro. Consulte <a href="../../dil/dil-use-cases.md#map-key-values"> Asignar valores clave a otras claves </a>. Publicado con v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Requerido. </p> <p>El par <code> namespace </code> clave-valor contiene el identificador de organización <span class="keyword"> Experience Cloud </span>. Si no tiene este ID, puede encontrarlo en la sección <span class="wintitle"> Administración </span> del panel <span class="keyword"> Experience Cloud </span>. Necesita permisos de administrador para vista de este panel. Consulte las <a href="../../faq/faq-features.md"> preguntas frecuentes sobre funciones y características del producto </a> y <a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> administración: administración del usuario y preguntas más frecuentes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Requerido. </p> <p> Nombre del socio proporcionado por el Audience Manager <span class="keyword"> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Elimina las secuencias de comandos y las rellamadas. El valor predeterminado es <code> False </code>. Se aplica únicamente a la instancia <span class="wintitle"> del DIL </span> actual. Publicado con v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Establece una cookie con el identificador de usuario único devuelto por el Audience Manager <span class="keyword"> </span>. Consulte <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> Propiedades de uidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Necesario con <span class="wintitle"> DIL </span> 6.2 o bueno. </p> <p> El DIL confía en la función <code> setCustomerIDs </code> del <span class="wintitle"> Servicio de identidad de Adobe Experience Platform </span> para pasar los ID declarados al Audience Manager <span class="keyword"> </span>. Consulte <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external">ID de cliente y estados de autenticación</a> para obtener más información. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Código de ejemplo**

Una llamada [!UICONTROL DIL] de ejemplo podría tener un aspecto similar al siguiente:

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

Una respuesta correcta devuelve la instancia [!UICONTROL DIL]. Un intento fallido devuelve un objeto de error (no generado) si el código está configurado incorrectamente o si se encuentra un error.

## Propiedades de uuidCookie {#uuidcookie-props}

Define las propiedades utilizadas por la variable `uuidCookie`. Esta variable forma parte del método `DIL.create`.

`uuidCookie` tiene las siguientes propiedades:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nombre | Descripción |
|---|---|
| `name` | El nombre de la cookie ( `aam_did` es el predeterminado). |
| `days` | Duración de la cookie (100 días es el valor predeterminado). |
| `path` | Ruta de cookie, por ejemplo: `'/test'` ( `/` es el valor predeterminado). |
| `domain` | Dominio en el que se establece la cookie, por ejemplo: `'adobe.com'` ( `'.'+document.domain` es el valor predeterminado). |
| `secure` | Establece un indicador para enviar datos solo a través de una conexión HTTPS. |

## Propiedades de visitorService {#visitor-service-props}

Define las propiedades utilizadas por la variable `visitorService`. Esta variable forma parte del método `DIL.create`.

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
