---
description: Crea una instancia de DIL específica del socio.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL create
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
TQID: https://experienceleague.adobe.com/aXgfaEO2ICrekZMD2JsRqeZOcm4kQYazZCru2wkmPtM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
  - id: d7e573ad-4eda-46ec-90c4-239e75362af9
  - id: f8c1669e-86ba-49c4-b622-9dfa07854df8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 820
ht-degree: 4%

---

# método create de DIL{#dil-create}

>[!WARNING]
>
>Desde julio de 2023, Adobe ha interrumpido el desarrollo de la extensión [!DNL Data Integration Library (DIL)] y [!DNL DIL].
>
>Los clientes existentes pueden seguir usando su implementación de [!DNL DIL]. Sin embargo, Adobe no desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes evaluar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) para su estrategia de recopilación de datos a largo plazo.
>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos a partir de julio de 2023 deben utilizar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) en su lugar.

## DIL create {#dil-create-new}

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
   <td colname="col3"> <p>Esta propiedad establece el id. de contenedor que usa <span class="keyword"> Audience Manager </span> para las sincronizaciones de id. Establecería <code> containerNSID </code> si tiene <span class="wintitle"> DIL </span> implementado en varios sitios. Cada uno de estos sitios tendrá su propio ID de contenedor y sincronizaciones de ID. Cuando solo tiene 1 sitio, el ID de contenedor es 0 de forma predeterminada y no necesita configurarlo correctamente. Póngase en contacto con su consultor de para obtener una lista de sus sitios y sus ID de contenedor. </p> <p>En el servicio de identidad de Adobe Experience Platform <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es" format="https" scope="external"> </a>, la propiedad <code> idSyncContainerID </code> corresponde a <code> containerNSID </code> en <span class="wintitle"> DIL </span>. Tenga en cuenta lo siguiente si utiliza <span class="wintitle"> DIL </span> <i>y</i> el servicio de ID en varios sitios: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Para cada sitio, establezca los mismos ID de contenedor en <code> containerNSID </code> y <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Tanto <span class="wintitle"> DIL </span> como el servicio de ID intentarán enviar sincronizaciones de ID a nuestro iFrame de recopilación de datos. Sin embargo, el iFrame garantiza que <span class="wintitle"> DIL </span> no activará una sincronización de ID. Esto evita la duplicación. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Solo <span class="wintitle"> DIL </span> envía datos a un <a href="../../features/destinations/destinations.md"> destino de URL </a>. </li> 
     </ul> </p> <p>Ver también <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html?lang=es" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> se usa para pasar el: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID del socio de datos asignado a usted por <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: su ID único de usuario. </li> 
    </ul> <p> <p>Importante: Utilice únicamente valores no codificados para sus ID. La codificación creará identificadores con codificación doble. </p> </p> <p> <p>Nota: Si usa el servicio de identidad de Adobe Experience Platform <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es" format="https" scope="external"> </a>, establezca los identificadores de cliente con el método <code> setCustomerIDs </code> en lugar de con <span class="wintitle"> DIL </span>. Ver <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=es" format="https" scope="external"> ID de cliente y estados de autenticación </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Si el valor es True, retrasa la ejecución de todas las solicitudes (IFRAME, llamadas de evento, sincronización de ID y destino) hasta que se desencadene el evento <code> Page Load </code>. El valor predeterminado es <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> False de manera predeterminada, lo que significa que <span class="keyword"> Audience Manager </span> establece una cookie en el dominio del socio (establece una cookie de origen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Este elemento ha quedado obsoleto con <span class="wintitle"> DIL </span> versión 8.0 (lanzado en agosto de 2018). En su lugar, use la función <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=es" format="https" scope="external"> </a> en el servicio de identidad de Adobe Experience Platform. </p> </p> <p> Si <code> true </code>, no adjuntará el IFRAME de publicación de destino al DOM o a los destinos de activación. El valor predeterminado es <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Este elemento ha quedado obsoleto con <span class="wintitle"> DIL </span> versión 8.0 (lanzado en agosto de 2018). En su lugar, use la función <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=es" format="https" scope="external"> </a> en el servicio de identidad de Adobe Experience Platform. </p> </p> <p>Deshabilita la sincronización de ID. Debe deshabilitar las sincronizaciones de ID al usar DIL v6.2 o posterior y el servicio de ID de visitante. La función <code> visitorService </code> (consulte el código de ejemplo siguiente) se encarga de esta operación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Se establece en <code> true </code> para habilitar los informes de errores para todas las instancias de DIL <span class="wintitle"> de </span> en la página. Solo funciona con Boolean <code> true </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Este elemento ha quedado obsoleto con <span class="wintitle"> DIL </span> versión 8.0 (lanzado en agosto de 2018). En su lugar, use la función <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html?lang=es" format="https" scope="external"> </a> en el servicio de identidad de Adobe Experience Platform. </p> </p> <p> Especifica si la plantilla de publicación de destino debe utilizar Akamai para conexiones HTTPS. Habilitado por socio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Asocia el valor de un par clave-valor a otro. Consulte <a href="../../dil/dil-use-cases.md#map-key-values"> Asignar valores de clave a otras claves </a>. Publicado con la versión 2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Requerido. </p> <p>El par clave-valor <code> namespace </code> contiene el identificador de organización <span class="keyword"> de Experience Cloud </span>. Si no tiene este identificador, puede encontrarlo en la sección <span class="wintitle"> Administration </span> del panel <span class="keyword"> Experience Cloud </span>. Necesita permisos de administrador para ver este tablero. Consulte las Preguntas frecuentes sobre las funciones y características del producto <a href="../../faq/faq-features.md"> y Administración de </a> y <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html?lang=es" format="https" scope="external">: administración de usuarios y preguntas frecuentes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Requerido. </p> <p> Nombre de socio proporcionado por <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Quita los scripts y las llamadas de retorno. El valor predeterminado es <code> False </code>. Solo se aplica a la instancia actual <span class="wintitle"> de DIL </span>. Publicado con la versión 3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Establece una cookie con el identificador de usuario único devuelto desde <span class="keyword"> Audience Manager </span>. Ver <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> propiedades uuidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objeto </p> </td> 
   <td colname="col3"> <p>Requerido con <span class="wintitle"> DIL </span> 6.2 o superior. </p> <p> DIL se basa en la función <code> setCustomerIDs </code> del servicio de identidad de Adobe Experience Platform <span class="wintitle"> </span> para pasar los identificadores declarados a <span class="keyword"> Audience Manager </span>. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=es" format="https" scope="external"> ID de cliente y estados de autenticación </a> para obtener más información. </p> </td> 
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
| `namespace` | Cadena | Requerido. Representa El Id. De Organización De Experience Cloud. Esto es necesario para la funcionalidad del servicio principal de Experience Cloud. El mismo parámetro se utiliza para crear una instancia de la funcionalidad de ID de visitante. |

**Ejemplo de código:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
