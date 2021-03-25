---
description: Las API de DIL de nivel de instancia permiten crear y trabajar mediante programación con objetos de Audience Manager. Los métodos de nivel de instancia mejoran la funcionalidad de la API establecida por los métodos de nivel de clase.
keywords: crear rasgos;crear rasgos
seo-description: Las API de DIL de nivel de instancia permiten crear y trabajar mediante programación con objetos de Audience Manager. Los métodos de nivel de instancia mejoran la funcionalidad de la API establecida por los métodos de nivel de clase.
seo-title: Métodos DIL de nivel de instancia
solution: Audience Manager
title: Métodos DIL de nivel de instancia
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: Implementación del DIL
translation-type: tm+mt
source-git-commit: e40233ace5cb74743db7d0f9f90707fa596a7e79
workflow-type: tm+mt
source-wordcount: '1111'
ht-degree: 15%

---


# Métodos DIL de nivel de instancia{#instance-level-dil-methods}

Las API [!UICONTROL DIL] de nivel de instancia permiten crear y trabajar programáticamente con objetos de Audience Manager. Los métodos de nivel de instancia mejoran la funcionalidad de la API establecida por los métodos de nivel de clase.

## Introducción a Métodos de DIL de nivel de instancia {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Al trabajar con las API [!UICONTROL DIL] de nivel de instancia:

* Access requiere un nombre de socio y un ID de área de nombres de contenedor (NSID). Póngase en contacto con el administrador de cuentas del Audience Manager para obtener esta información.
* Reemplace cualquier texto *cursiva* de muestra de la documentación de API por valor, ID u otra variable según lo requiera el método con el que esté trabajando.

<!-- 

c_instance_start.xml

 -->

## señales {#signals}

Agrega asignaciones de nivel de cliente y plataforma a la cadena de consulta de una solicitud pendiente.

<!-- 

r_dil_signals.xml

 -->

**Firma de función:** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Puede encadenar otras llamadas de API a este método.
>* Si la biblioteca JavaScript de Adobe Experience Cloud está en la página, `submit()` espera a que Cloud establezca una cookie antes de enviar una solicitud.


**Claves de solicitud reservadas**

Las siguientes claves de solicitud están reservadas y no se pueden sobrescribir con este método:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `obj` | Objeto | Un objeto que representa los pares clave-valor para las asignaciones a nivel de plataforma. El parámetro acepta cadenas y matrices como valores de propiedad en el objeto. |
| `prefix` | Cadena | Opcional. El valor de cadena con el prefijo de cada clave de objeto (reemplaza la clave original). |
| `return` | DIL.api | Devuelve el objeto API de la instancia de DIL actual. |

**Respuesta**

Devuelve el objeto API de la instancia [!UICONTROL DIL] actual.

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
// Method 1 
var obj = { key1 : 1, key2 : 2 }; 
dataLib.api.signals(obj, 'c_').submit(); 
 
// Method 2 
dataLib.api.signals({c_zdid: 54321}).submit(); 
 
// Method 3 
// Will send 'c_key=a&c_key=2&c_key=3' to Audience Manager 
var obj = { key : ['a', 'b', 'c'] }; 
dataLib.api.signals(obj, 'c_').submit(); 
</code></pre>

## traits {#traits}

Agrega SID a la cadena de consulta de una solicitud pendiente.

<!-- 

r_dil_traits.xml

 -->

**Firma de función:** `traits:function (sids){}`

>[!NOTE]
>
>Puede encadenar otras llamadas de API a este método.

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `sids` | Matriz | ID de segmentos de características en una matriz. |

**Respuesta**

Devuelve el objeto API de la instancia [!UICONTROL DIL] actual.

**Código de ejemplo**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

Agregue datos a los archivos de registro en la solicitud pendiente.

<!-- 

r_dil_logs.xml

 -->

**Firma de función:** `logs: function {key1:value1, key2:value2}`

**Respuesta**

Devuelve el objeto API de la instancia [!UICONTROL DIL] actual.

**Código de ejemplo**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});
</code></pre>

## submit {#submit}

Envía todos los datos pendientes al Audience Manager para la instancia [!UICONTROL DIL].

<!-- 

r_dil_submit.xml

 -->

**Firma de función:** `submit: function () {}`

>[!NOTE]
>
>Puede encadenar otras llamadas de API a este método. Además, [!UICONTROL DIL] escribe datos codificados en una cookie de destino. Por ejemplo, los espacios se codifican como `%20` y los punto y coma como `%3B`.

**Respuesta**

Devuelve el objeto API de la instancia [!UICONTROL DIL] actual.

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([ 
<i>123,456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}).submit();
</code></pre>

## afterResult {#afterresult}

Una función que se ejecuta después de la llamada de retorno de publicación de destino predeterminada.

<!-- 

r_dil_after_result.xml

 -->

**Firma de función:** `afterResult: function (fn) {}`

>[!NOTE]
>
>Puede encadenar otras llamadas de API a este método.

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `fn` | Función | La función que desea ejecutar después de JSON se procesa mediante la llamada de retorno predeterminada que gestiona la publicación de destino. |

**Respuesta**

Devuelve un objeto API de la instancia [!UICONTROL DIL] actual.

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.signals({ 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
}).afterResult(function(json){ 
     //Do something with the JSON data returned from the server. 
}).submit();
</code></pre>

## clearData {#cleardata}

Borra todos los datos de una solicitud pendiente.

<!-- 

r_dil_clear_data.xml

 -->

**Firma de función:** `clearData: function () {}`

>[!NOTE]
>
>Puede encadenar otras llamadas de API a este método.

**Respuesta**

Devuelve el objeto API de la instancia [!UICONTROL DIL] actual.

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ 
     file: 'dil.js' 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Agrega parámetros de consulta personalizados que no están definidos explícitamente por el servidor de recopilación de datos a una solicitud pendiente.

<!-- 

r_dil_custom_query_params.xml

 -->

**Firma de función:** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>Puede encadenar otras llamadas de API a este método.

**Claves de solicitud reservadas**

Las siguientes claves de solicitud están reservadas y no se pueden sobrescribir con este método:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Respuesta**

Devuelve el objeto API de la instancia de DIL actual.

**Código de ejemplo**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.customQueryParams({ 
     nid: 54231, 
     ntype: 'default' 
}); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Devuelve el valor del NSID de contenedor para la instancia [!UICONTROL DIL]. Útil para la depuración y la solución de problemas.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Firma de función:** `dil.api.getContainerNSID: function () {}`

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

Devuelve datos de registro de eventos ordenados cronológicamente como una matriz de cadenas. Útil para la depuración y la solución de problemas.

<!-- 

r_dil_get_event_log.xml

 -->

**Firma de función:** `dil.api.getEventLog: function () {}`

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});.signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) { 
     alert(log.join('\n')); 
}else{ 
     alert('No log messages'); 
}
</code></pre>

## getPartner {#getpartner}

Devuelve el nombre del socio para una instancia [!UICONTROL DIL]. Útil para la depuración y la solución de problemas.

<!-- 

r_dil_get_partner.xml

 -->

**Firma de función:** `dil.api.getPartner: function () {}`

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Devuelve el estado de la instancia [!UICONTROL DIL] actual. Útil para la depuración y la solución de problemas.

<!-- 

r_dil_get_state.xml

 -->

**Firma de función:** `dil.api.getState: function () {}`

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message:'This is the first request' 
});.signals({ 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = { 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:{ 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: { 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          }, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     }, 
     destinationPublishingInfo: { 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          + containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

Consiste en dos funciones que permiten a los socios de datos intercambiar y sincronizar ID de usuario entre ellos y el Audience Manager.

<!-- 

r_dil_idsync.xml

 -->

**Firma de función:**

Funciona con [!UICONTROL DIL] versiones 2.10 y 3.1 o superiores.

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Código </th> 
   <th colname="col2" class="entry"> Sincroniza los ID de los usuarios </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.idSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Entre diferentes socios de datos y Audience Manager. Por ejemplo, el socio x utilizaría esto para sincronizar un ID de usuario con el socio y luego enviarlo al Audience Manager. </p> <p> <p><b>Importante:</b>  Este método está obsoleto. Utilice el método <code> idSyncByURL </code> de la instancia del servicio de identidad de Adobe Experience Platform. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Cuando ya conoce el ID de usuario y desea enviarlo al Audience Manager. </p> <p> <p><b>Importante:</b>  Este método está obsoleto. Utilice el método <code> idSyncByDataSource </code> de la instancia del servicio de identidad de Adobe Experience Platform. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Elementos de idSync**

`idSync` puede constar de lo siguiente:

<table id="table_5343BE784E694C67B09A0A8878CF8001"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> Cadena </td> 
   <td colname="col3"> <p>ID de proveedor de datos asignado por Audience Manager. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Cadena </td> 
   <td colname="col3"> <p>El ID exclusivo de proveedor de datos para el usuario. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> minutesToLive </code> </td> 
   <td colname="col2"> Número </td> 
   <td colname="col3"> <p><i>(Opcional)</i> Establece el tiempo de caducidad de la cookie. Debe ser un número entero. El valor predeterminado es de 20160 minutos (14 días). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> url </code> </td> 
   <td colname="col2"> Cadena </td> 
   <td colname="col3"> <p>Dirección URL de destino. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Macros**

`idSync` acepta las siguientes macros:

* **`%TIMESTAMP%`:** genera una marca de hora (en milésimas de segundo). Se emplea para ignorar la caché.
* **`%DID%`:** inserta el ID de Audience Manager para el usuario.
* **`%HTTP_PROTO%`:** establece el protocolo de página (  `http` o  `https`).

**Respuesta**

Ambas funciones devuelven `Successfully queued` si se realiza correctamente. Si no, devuelven una cadena con un mensaje de error.

**Código de ejemplo**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync({ 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync({ 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

## resultado {#result}

Agrega una llamada de retorno (que recibe JSON) a la solicitud pendiente.

<!-- 

r_dil_result.xml

 -->

**Firma de función:** `result: function (callback) {}`

Esta rellamada reemplaza la rellamada predeterminada que gestiona la publicación de destino.

>[!NOTE]
>
>Puede encadenar otras llamadas de API a este método.

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `callback` | Función | Función JavaScript ejecutada por la llamada de retorno JSONP. |

**Respuesta**

Devuelve el objeto API de la instancia [!UICONTROL DIL] actual.

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json){ 
     //Do something, possibly with the JSON data returned from the server. 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` es un parámetro booleano que controla cómo se  [!UICONTROL DIL] realizan las llamadas a  [!UICONTROL Data Collection Servers (DCS)] y Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* Cuando `secureDataCollection= true` (predeterminado), [!UICONTROL DIL] siempre realiza llamadas HTTPS seguras.

* Cuando `secureDataCollection= false`, [!UICONTROL DIL] realiza llamadas HTTP o HTTPS siguiendo el protocolo de seguridad establecido por la página.

>[!IMPORTANT]
>
>Configure `secureDataCollection= false` si utiliza visitorAPI.js y [!UICONTROL DIL] en la misma página. Consulte el ejemplo de código que aparece a continuación.

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     secureDataCollection: false 
});
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` es un parámetro booleano true/false que controla el modo en que el explorador solicita recursos de otros dominios.

<!-- 

dil-use-cors-only.xml

 -->

**Información general**

`useCORSOnly` es false de forma predeterminada. False significa que el explorador puede realizar comprobaciones de recursos con CORS o JSONP. Sin embargo, [!UICONTROL DIL] siempre intenta solicitar recursos con CORS primero. Vuelve a JSONP en navegadores anteriores que no son compatibles con CORS. Si necesita forzar al explorador para que use solo CORS, como con sitios que tienen requisitos de alta seguridad, establezca `useCORSOnly:true`.

**Ejemplo de código**

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     useCORSOnly: true 
});
</code></pre>

>[!IMPORTANT]
>
>* Le recomendamos que configure `useCORSOnly: true` solo cuando esté seguro de que los visitantes del sitio tienen exploradores que admiten esta función.
>* Cuando `useCORSOnly: true`, [!UICONTROL DIL] no realizará llamadas de ID desde Internet Explorer versión 9 o anterior.

>



## useImageRequest {#useimagerequest}

Cambia el tipo de solicitud a la imagen `<img>` desde el script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Firma de función:** `useImageRequest: function () {}`

>[!NOTE]
>
>Puede encadenar otras llamadas de API a este método.

**Respuesta**

Devuelve un objeto API de la instancia [!UICONTROL DIL] actual.

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create({ 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [Requisitos de nombre para variables clave](../features/traits/trait-key-name-requirements.md)
>* [Requisitos de prefijo para variables clave](../features/traits/trait-variable-prefixes.md)
>* [Funciones de sincronización en el servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/idsync.html)
>* [DIL crear](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Servicio de identidad de Adobe Experience Platform: UseCORSOnly](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [Compatibilidad con CORS en el servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/reference/cors.html)

