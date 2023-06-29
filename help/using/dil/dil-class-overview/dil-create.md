---
description: Crea una instancia de DIL específica del socio.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL crear
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 9%

---

# método de creación del DIL{#dil-create}

>[!WARNING]
>
>A partir de julio de 2023, el Adobe ha interrumpido el desarrollo del [!DNL Data Integration Library (DIL)] y el [!DNL DIL] extensión.
><br>
>Los clientes existentes pueden seguir utilizando su [!DNL DIL] implementación. Sin embargo, el Adobe no se desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes que evalúen [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para su estrategia de recopilación de datos a largo plazo.
><br>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos a partir de julio de 2023 deben utilizar [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) en su lugar.

## DIL crear {#dil-create-new}

Crea un socio específico [!UICONTROL DIL] ejemplo.

**Firma de función:** `DIL.create: function (initConfig) {}`

**initConfig Elements**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>El `visitorService` la propiedad es *siempre* requerido. Otras propiedades enumeradas aquí son opcionales, a menos que se indique lo contrario.

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
   <td colname="col3"> <p>Esta propiedad define el ID de contenedor que utiliza <span class="keyword">Audience Manager</span> para sincronizar los ID. Que usted fijara <code> containerNSID </code> si tiene <span class="wintitle"> DIL </span> implementado en varios sitios. Cada uno de estos sitios tendrá su propio ID de contenedor y sincronizaciones de ID. Cuando solo tiene 1 sitio, el ID de contenedor es 0 de forma predeterminada y no necesita configurarlo correctamente. Póngase en contacto con su consultor de para obtener una lista de sus sitios y sus ID de contenedor. </p> <p>En el <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Servicio de identidad de Adobe Experience Platform </a>, la propiedad <code> idSyncContainerID </code> corresponde a <code> containerNSID </code> in <span class="wintitle"> DIL </span>. Tenga en cuenta lo siguiente si está utilizando <span class="wintitle"> DIL </span> <i>y</i> el servicio de ID en varios sitios: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Para cada sitio, establezca los mismos ID de contenedor en <code> containerNSID </code> y <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Ambos <span class="wintitle"> DIL </span> y el servicio de ID intentará enviar sincronizaciones de ID a nuestro iFrame de recopilación de datos. Sin embargo, el iFrame garantiza que <span class="wintitle"> DIL </span> no activa una sincronización de ID. Esto evita la duplicación. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Solo <span class="wintitle"> DIL </span> envía datos a un <a href="../../features/destinations/destinations.md"> URL de destino </a>. </li> 
     </ul> </p> <p>Consulte también. <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> se utiliza para pasar el: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID del socio de datos asignado a usted por <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: su ID único de usuario. </li> 
    </ul> <p> <p>Importante: Utilice únicamente valores no codificados para sus ID. La codificación creará identificadores con codificación doble. </p> </p> <p> <p>Nota: Si utiliza la variable <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Servicio de identidad de Adobe Experience Platform </a>, establezca los ID de cliente con <code> setCustomerIDs </code> en lugar de <span class="wintitle"> DIL </span>. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> ID de cliente y estados de autenticación </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Si el valor es True, retrasa todas las solicitudes (IFRAME, llamadas de evento, sincronización de ID y destino) de la ejecución hasta el <code> Page Load </code> se activa el evento. El valor predeterminado es <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Falso de forma predeterminada, lo que significa que <span class="keyword"> Audience Manager </span> establece una cookie en el dominio del socio (establece una cookie de origen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Este elemento ha quedado obsoleto con <span class="wintitle"> DIL </span> versión 8.0 (lanzada en agosto de 2018). Utilice el <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> función </a> en el servicio de identidad de Adobe Experience Platform. </p> </p> <p> If <code> true </code>, no adjuntará el IFRAME de publicación de destino al DOM o a los destinos de activación. El valor predeterminado es <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Este elemento ha quedado obsoleto con <span class="wintitle"> DIL </span> versión 8.0 (lanzada en agosto de 2018). Utilice el <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> función </a> en el servicio de identidad de Adobe Experience Platform. </p> </p> <p>Deshabilita la sincronización de ID. Debe deshabilitar las sincronizaciones de ID al usar DIL v6.2 o posterior y el servicio de ID de visitante. El <code> visitorService </code> (consulte el código de ejemplo que aparece a continuación) se encarga de esta operación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Configure como. <code> true </code> para habilitar los informes de errores para todos <span class="wintitle"> DIL </span> instancias en la página. Funciona con Boolean <code> true </code> solo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Este elemento ha quedado obsoleto con <span class="wintitle"> DIL </span> versión 8.0 (lanzada en agosto de 2018). Utilice el <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> función </a> en el servicio de identidad de Adobe Experience Platform. </p> </p> <p> Especifica si la plantilla de publicación de destino debería utilizar Akamai para conexiones HTTPS. Habilitado por socio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Asocia el valor de un par clave-valor a otro. Consulte <a href="../../dil/dil-use-cases.md#map-key-values"> Asignar valores de clave a otras claves </a>. Publicado con la versión 2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Requerido. </p> <p>El <code> namespace </code> el par clave-valor contiene su <span class="keyword"> Experience Cloud </span> ID de organización. Si no dispone de este ID, puede encontrarlo en la <span class="wintitle"> Administration </span> de la sección <span class="keyword"> Experience Cloud </span> panel. Necesita permisos de administrador para ver este tablero. Consulte la <a href="../../faq/faq-features.md"> Preguntas frecuentes sobre funciones y características del producto </a> y <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> Administración: administración de usuarios y preguntas frecuentes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Requerido. </p> <p> Nombre del socio proporcionado por <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Quita los scripts y las llamadas de retorno. El valor predeterminado es <code> False </code>. Se aplica al actual <span class="wintitle"> DIL </span> solo instancia de. Publicado con la versión 3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Establece una cookie con el ID único de usuario devuelto desde <span class="keyword"> Audience Manager </span>. Consulte <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> Propiedades de uuidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Requerido con <span class="wintitle"> DIL </span> 6,2 o bueno. </p> <p> El DIL se basa en <code> setCustomerIDs </code> función en la <span class="wintitle"> Servicio de identidad de Adobe Experience Platform </span> para pasar los ID declarados a <span class="keyword"> Audience Manager </span>. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external">ID de cliente y estados de autenticación</a> para obtener más información. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Código de ejemplo**

Una muestra [!UICONTROL DIL] La llamada de podría tener un aspecto similar al siguiente:

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

Una respuesta correcta devuelve el valor [!UICONTROL DIL] ejemplo. Un intento fallido devuelve un objeto de error (no arrojado) si el código está configurado incorrectamente o siempre que se encuentre un error.

## Propiedades de uuidCookie {#uuidcookie-props}

Define las propiedades utilizadas por `uuidCookie` variable. Esta variable forma parte de la variable `DIL.create` método.

`uuidCookie` tiene las siguientes propiedades:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nombre | Descripción |
|---|---|
| `name` | El nombre de la cookie ( `aam_did` es el valor predeterminado). |
| `days` | Duración de la cookie (100 días es el valor predeterminado). |
| `path` | Ruta de la cookie, por ejemplo, `'/test'` ( `/` es el valor predeterminado). |
| `domain` | El dominio en el que se establece la cookie, por ejemplo, `'adobe.com'` ( `'.'+document.domain` es el valor predeterminado). |
| `secure` | Establece un indicador para enviar datos únicamente a través de una conexión HTTPS. |

## Propiedades de visitorService {#visitor-service-props}

Define las propiedades utilizadas por `visitorService` variable. Esta variable forma parte de la variable `DIL.create` método.

`visitorService` tiene las siguientes propiedades:

| Nombre | Tipo | Descripción |
|---|---|---|
| `namespace` | Cadena | Requerido. Representa El Id. De Organización Del Experience Cloud. Esto es necesario para la funcionalidad del servicio principal de Experience Cloud. El mismo parámetro se utiliza para crear una instancia de la funcionalidad de ID de visitante. |

**Ejemplo de código:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
