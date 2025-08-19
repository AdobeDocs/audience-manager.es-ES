---
description: Crea un instancia DIL específico para socio.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: Creación de DIL
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 4%

---

# Método de creación DIL{#dil-create}

>[!WARNING]
>
>A partir de julio de 2023, Adobe Systems ha interrumpido el desarrollo de la [!DNL Data Integration Library (DIL)] y la [!DNL DIL] extensión.
>
>Los clientes existentes pueden seguir usando sus [!DNL DIL] implementación. Sin embargo, Adobe Systems no se desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes que evalúen [Experience Platform SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) web según su estrategia de recopilación de datos a largo plazo.
>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos después de julio de 2023 deberían usar [Experience Platform SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) web.

## Creación de DIL {#dil-create-new}

Crea un instancia específico [!UICONTROL DIL] para socio.

**Firma de función:** `DIL.create: function (initConfig) {}`

**Elementos initConfig**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>Siempre se `visitorService`*requiere la* Propiedad. Otras propiedades enumeradas aquí son opcionales, a menos que se indique lo contrario.

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
   <td colname="col3"> <p>Este Propiedad establece el ID de contenedor que utiliza <span class="keyword"> el Audience Manager </span> para las sincronizaciones de ID. Usted establecería <code> containerNSID </code> si tiene <span class="wintitle"> DIL </span> implementado en varios sitios. Cada uno de estos sitios tendrá su propio ID de contenedor y sincronizaciones de ID. Cuando solo tiene 1 sitio, el ID de contenedor es 0 de forma predeterminada y no es necesario configurarlo correctamente. Póngase en contacto con el consultor para obtener una lista de sus sitios y sus contenedor ID. </p> <p>En el servicio de <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> identidad de Adobe Experience Platform, la Propiedad </a> corresponde a <code> idSyncContainerID </code> en <code> containerNSID </code> DIL<span class="wintitle">.</span> Tenga en cuenta lo siguiente si utiliza <span class="wintitle"> DIL </span> <i>y</i> el servicio de ID en varios sitios: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Para cada sitio, establezca los mismos ID de contenedor en <code> containerNSID </code> y <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Tanto DIL <span class="wintitle"> como </span> el servicio de ID intentarán enviar sincronizaciones de ID a nuestro recopilación de datos iFrame. Sin embargo, el iFrame garantiza que <span class="wintitle"> DIL </span> no active un sincronizar de ID. Esto evita la duplicación. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Solo <span class="wintitle"> DIL </span> envía datos a un <a href="../../features/destinations/destinations.md"> destino </a>URL. </li> 
     </ul> </p> <p>Consulte también idSyncContainerID<a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external">. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> se utiliza para pasar cualquiera de las: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID del socio de datos asignado por <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: su ID único para una usuario. </li> 
    </ul> <p> <p>Importante: Utilice únicamente valores descodificados para sus ID. La codificación creará identificadores codificados doble. </p> </p> <p> <p>Nota: Si utiliza el servicio de identidad de <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform, establezca los ID de cliente con el </a> método en lugar de <code> setCustomerIDs </code> DIL<span class="wintitle">.</span> Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> ID de cliente y Estados </a>Authentication. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Si es true, aplaza la ejecución de todas las solicitudes (IFRAME, llamadas evento, sincronizar de ID y destino) hasta que se active el <code> Page Load </code> evento. El valor predeterminado es <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Falso de forma predeterminada, lo que significa <span class="keyword"> que Audience Manager </span> establece un cookie en el dominio del socio (establece un cookie propio). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Este elemento se ha quedado obsoleto con <span class="wintitle"> la versión 8.0 de DIL </span> (publicada en agosto de 2018). En su lugar, utilice la <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> función </a> del servicio de identidad de Adobe Experience Platform. </p> </p> <p> Si <code> true </code>, no adjuntará el IFRAME de publicación de destino al DOM ni activará destinos. El valor predeterminado es <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Este elemento se ha quedado obsoleto con <span class="wintitle"> la versión 8.0 de DIL </span> (publicada en agosto de 2018). En su lugar, utilice la <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> función </a> del servicio de identidad de Adobe Experience Platform. </p> </p> <p>Deshabilita la sincronización de ID. Debe deshabilitar las sincronizaciones de ID al usar DIL v6.2+ y el servicio de ID de visitante. La <code> visitorService </code> función (consulte el código de ejemplo más abajo) se encarga de esta operación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Configúrelo para <code> true </code> activar los sistema de informes de error en todas las <span class="wintitle"> instancias DIL </span> del Página. Solo funciona con booleano <code> true </code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Este elemento se ha quedado obsoleto con <span class="wintitle"> la versión 8.0 de DIL </span> (publicada en agosto de 2018). En su lugar, utilice la <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> función </a> del servicio de identidad de Adobe Experience Platform. </p> </p> <p> Especifica si los plantilla de publicación de destino deben utilizar Akamai para conexiones HTTPS. Habilitado por socio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Asocia el valor de un par clave-valor a otro. Consulte <a href="../../dil/dil-use-cases.md#map-key-values"> Asignar valores de clave a otras claves </a>. Lanzado con v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Obligatorio. </p> <p>El <code> namespace </code> par clave-valor contiene su <span class="keyword"> Experience Cloud </span> identificador de organización. Si no dispone de este ID, puede encontrarlo en la <span class="wintitle"> sección Administración </span> del <span class="keyword"> panel de Experience Cloud </span> . Se necesitan permisos de administrador para vista este panel. Consulte las características y funciones del producto, <a href="../../faq/faq-features.md"> preguntas frecuentes </a> y <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> administración: User Management y preguntas más frecuentes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Obligatorio. </p> <p> Nombre del socio proporcionado por <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Elimina scripts y devoluciones de llamada. El valor predeterminado es <code> False </code>. Solo se aplica a la instancia DIL <span class="wintitle"> actual</span>. Lanzado con v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Establece un cookie con el ID de usuario único devuelto por <span class="keyword"> Audience Manager </span>. Consulte <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie Propiedades </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Requerido con <span class="wintitle"> DIL </span> 6.2 o superior. </p> <p> DIL se basa en la función del <code> setCustomerIDs </code> servicio <span class="wintitle"> de identidad de </span> Adobe Experience Platform para pasar los ID declarados a Audience Manager.<span class="keyword"></span> Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> ID de cliente y Estados </a> Authentication para obtener más información. </p> </td> 
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

Una respuesta correcta devuelve el [!UICONTROL DIL] instancia. Un intento fallido devuelve un objeto de error (no lanzado) si el código está configurado incorrectamente o cada vez que se encuentra un error.

## Propiedades uuidCookie {#uuidcookie-props}

Define las propiedades utilizadas por el `uuidCookie` variable. Esta variable forma parte del `DIL.create` método.

`uuidCookie` tiene las siguientes propiedades:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nombre | Descripción |
|---|---|
| `name` | El nombre cookie ( `aam_did` el predeterminado es el predeterminado). |
| `days` | Cookie vida útil (el valor predeterminado es 100 días). |
| `path` | Ruta de la cookie, p. ej., `'/test'` ( `/` es predeterminada). |
| `domain` | El dominio en el que se establece la cookie, p. ej., `'adobe.com'` ( `'.'+document.domain` es el predeterminado). |
| `secure` | Establece una indicador para enviar datos únicamente a través de una conexión HTTPS. |

## Propiedades de visitorService {#visitor-service-props}

Define las propiedades utilizadas por el `visitorService` variable. Esta variable forma parte del `DIL.create` método.

`visitorService` tiene las siguientes propiedades:

| Nombre | Tipo | Descripción |
|---|---|---|
| `namespace` | Cadena | Requerido. Representa el ID de organización Experience Cloud. Esto es necesario para Experience Cloud funcionalidad de servicios principales. El mismo parámetro utilizado para crear instancias del funcionalidad de ID de visitante. |

**Ejemplo de código:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
