---
description: Crea una instancia de DIL específica del socio.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL crear
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 4%

---

# método de creación del DIL{#dil-create}

>[!WARNING]
>
>A partir de julio de 2023, el Adobe ha interrumpido el desarrollo de la extensión [!DNL Data Integration Library (DIL)] y [!DNL DIL].
>
>Los clientes existentes pueden seguir usando su implementación de [!DNL DIL]. Sin embargo, el Adobe no se desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes que evalúen [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) para su estrategia de recopilación de datos a largo plazo.
>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos a partir de julio de 2023 deben utilizar [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) en su lugar.

## DIL crear {#dil-create-new}

Crea una instancia [!UICONTROL DIL] específica del socio.

**Firma de función:** `DIL.create: function (initConfig) {}`

**Elementos initConfig**

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
   <td colname="col3"> <p>Esta propiedad establece el identificador de contenedor que usa el Audience Manager </span> de <span class="keyword"> para las sincronizaciones de ID. Establecería <code> containerNSID </code> si tiene <span class="wintitle"> DIL </span> implementado en varios sitios. Cada uno de estos sitios tendrá su propio ID de contenedor y sincronizaciones de ID. Cuando solo tiene 1 sitio, el ID de contenedor es 0 de forma predeterminada y no necesita configurarlo correctamente. Póngase en contacto con su consultor de para obtener una lista de sus sitios y sus ID de contenedor. </p> <p>En el servicio de identidad de Adobe Experience Platform <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es" format="https" scope="external"> </a>, la propiedad <code> idSyncContainerID </code> corresponde a <code> containerNSID </code> en el DIL <span class="wintitle"> </span>. Tenga en cuenta lo siguiente si utiliza el DIL <span class="wintitle"> </span> <i>y</i> el servicio de ID en varios sitios: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Para cada sitio, establezca los mismos ID de contenedor en <code> containerNSID </code> y <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Tanto el DIL <span class="wintitle"> </span> como el servicio de ID intentarán enviar sincronizaciones de ID a nuestro iFrame de recopilación de datos. Sin embargo, el iFrame garantiza que el DIL <span class="wintitle"> </span> no activará una sincronización de ID. Esto evita la duplicación. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Solo el DIL <span class="wintitle"> </span> envía datos a un destino de URL <a href="../../features/destinations/destinations.md"> </a>. </li> 
     </ul> </p> <p>Ver también <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html?lang=es" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> se usa para pasar el: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID del socio de datos asignado a usted por el Audience Manager <span class="keyword"> </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: su ID único de usuario. </li> 
    </ul> <p> <p>Importante: Utilice únicamente valores no codificados para sus ID. La codificación creará identificadores con codificación doble. </p> </p> <p> <p>Nota: Si usa el servicio de identidad de Adobe Experience Platform <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es" format="https" scope="external"> </a>, establezca los identificadores de cliente con el método <code> setCustomerIDs </code> en lugar del DIL <span class="wintitle"> </span>. Ver <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=es" format="https" scope="external"> ID de cliente y estados de autenticación </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Si el valor es True, retrasa la ejecución de todas las solicitudes (IFRAME, llamadas de evento, sincronización de ID y destino) hasta que se desencadene el evento <code> Page Load </code>. El valor predeterminado es <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> False de manera predeterminada, lo que significa que el Audience Manager <span class="keyword"> </span> establece una cookie en el dominio del socio (establece una cookie de origen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Este elemento ha quedado obsoleto con el DIL <span class="wintitle"> </span> versión 8.0 (lanzado en agosto de 2018). En su lugar, use la función <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=es" format="https" scope="external"> </a> en el servicio de identidad de Adobe Experience Platform. </p> </p> <p> Si <code> true </code>, no adjuntará el IFRAME de publicación de destino al DOM o a los destinos de activación. El valor predeterminado es <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Este elemento ha quedado obsoleto con el DIL <span class="wintitle"> </span> versión 8.0 (lanzado en agosto de 2018). En su lugar, use la función <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=es" format="https" scope="external"> </a> en el servicio de identidad de Adobe Experience Platform. </p> </p> <p>Deshabilita la sincronización de ID. Debe deshabilitar las sincronizaciones de ID al usar DIL v6.2 o posterior y el servicio de ID de visitante. La función <code> visitorService </code> (consulte el código de ejemplo siguiente) se encarga de esta operación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Se establece en <code> true </code> para habilitar los informes de errores para todas las instancias de DIL </span> de <span class="wintitle"> en la página. Solo funciona con Boolean <code> true </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Este elemento ha quedado obsoleto con el DIL <span class="wintitle"> </span> versión 8.0 (lanzado en agosto de 2018). En su lugar, use la función <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html?lang=es" format="https" scope="external"> </a> en el servicio de identidad de Adobe Experience Platform. </p> </p> <p> Especifica si la plantilla de publicación de destino debe utilizar Akamai para conexiones HTTPS. Habilitado por socio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Asocia el valor de un par clave-valor a otro. Consulte <a href="../../dil/dil-use-cases.md#map-key-values"> Asignar valores de clave a otras claves </a>. Publicado con la versión 2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Requerido. </p> <p>El par clave-valor <code> namespace </code> contiene el identificador de organización del Experience Cloud </span> <span class="keyword">. Si no tiene este identificador, puede encontrarlo en la sección <span class="wintitle"> Administration </span> del panel <span class="keyword"> Experience Cloud </span>. Necesita permisos de administrador para ver este tablero. Consulte las Preguntas frecuentes sobre las funciones y características del producto <a href="../../faq/faq-features.md"> y Administración de </a> y <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html?lang=es" format="https" scope="external">: administración de usuarios y preguntas frecuentes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Requerido. </p> <p> Nombre de socio proporcionado por el Audience Manager </span> de <span class="keyword">. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Quita los scripts y las llamadas de retorno. El valor predeterminado es <code> False </code>. Solo se aplica a la instancia actual <span class="wintitle"> del DIL </span>. Publicado con la versión 3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Establece una cookie con el identificador de usuario único devuelto por el Audience Manager <span class="keyword"> </span>. Ver <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> propiedades uuidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Requerido con el DIL <span class="wintitle"> </span> 6.2 o superior. </p> <p> El DIL se basa en la función <code> setCustomerIDs </code> del servicio de identidad de Adobe Experience Platform <span class="wintitle"> </span> para pasar los identificadores declarados al Audience Manager <span class="keyword"> </span>. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=es" format="https" scope="external"> ID de cliente y estados de autenticación </a> para obtener más información. </p> </td> 
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

Una respuesta correcta devuelve la instancia [!UICONTROL DIL]. Un intento fallido devuelve un objeto de error (no arrojado) si el código está configurado incorrectamente o siempre que se encuentre un error.

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
| `path` | Ruta de la cookie, p. ej., `'/test'` ( `/` es el valor predeterminado). |
| `domain` | Dominio en el que se establece la cookie, por ejemplo: `'adobe.com'` ( `'.'+document.domain` es el predeterminado). |
| `secure` | Establece un indicador para enviar datos únicamente a través de una conexión HTTPS. |

## Propiedades de visitorService {#visitor-service-props}

Define las propiedades utilizadas por la variable `visitorService`. Esta variable forma parte del método `DIL.create`.

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
