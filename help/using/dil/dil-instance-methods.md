---
description: Las API DIL de nivel instancia permiten crear y trabajar con objetos Audience Manager mediante programación. Los métodos de nivel instancia mejoran los funcionalidad de API establecidos por los métodos de nivel de clase.
keywords: crear rasgos; Crear rasgo
seo-description: The instance-level DIL APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.
seo-title: Instance-level DIL Methods
solution: Audience Manager
title: Métodos DIL de nivel de instancia
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL Implementation
exl-id: 0342439d-708e-461c-b155-a3ee423f5437
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 13%

---

# Métodos DIL de nivel de instancia{#instance-level-dil-methods}

>[!WARNING]
>
>A partir de julio de 2023, Adobe Systems ha interrumpido el desarrollo de la [!DNL Data Integration Library (DIL)] y la [!DNL DIL] extensión.
>
>Los clientes existentes pueden seguir usando sus [!DNL DIL] implementación. Sin embargo, Adobe Systems no se desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes que evalúen [Experience Platform SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) web según su estrategia de recopilación de datos a largo plazo.
>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos después de julio de 2023 deberían usar [Experience Platform SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) web.

Las API de nivel [!UICONTROL DIL] instancia permiten crear y trabajar con objetos Audience Manager mediante programación. Los métodos de nivel instancia mejoran los funcionalidad de API establecidos por los métodos de nivel de clase.

## Introducción a los métodos DIL de nivel de instancia {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Al trabajar con las API de nivel [!UICONTROL DIL] instancia:

* Access requiere un nombre socio y contenedor ID de espacio de nombres (NSID). Póngase en contacto con su Administrador de cuentas de Audience Manager para obtener esta información.
* Reemplazar cualquier texto en cursiva *de muestra* en la documentación de API con valor, ID u otras variable según lo requiera el método con el que esté trabajando.

<!-- 

c_instance_start.xml

 -->

## señales {#signals}

Agrega asignaciones de cliente y de nivel de plataforma al cadena de consulta de un solicitud pendiente.

<!-- 

r_dil_signals.xml

 -->

**Firma de función:** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Puede encadenar otras llamadas de API a este método.
>* Si el Adobe Experience Cloud JavaScript biblioteca está en el Página, `submit()` espera a que Cloud establezca un cookie antes de enviar un solicitud.

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
| `obj` | Objeto | Un objeto que representa los pares clave-valor para las asignaciones de nivel de plataforma. El parámetro acepta cadenas y matrices como valores Propiedad en el objeto. |
| `prefix` | Cadena | Opcional. El valor de cadena prefijado a cada clave de objeto (reemplaza la clave original). |
| `return` | DIL.api | Devuelve el objeto API del instancia DIL actual. |

**Respuesta**

Devuelve el objeto API del instancia actual [!UICONTROL DIL] .

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
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

Agrega SID al cadena de consulta de un solicitud pendiente.

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
| `sids` | Matriz | Los ID de segmento de características de una matriz. |

**Respuesta**

Devuelve el objeto API del instancia actual [!UICONTROL DIL] .

**Código de ejemplo**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## trozas {#logs}

añadir datos a los archivos de registro en el solicitud pendiente.

<!-- 

r_dil_logs.xml

 -->

**Firma de función:** `logs: function {key1:value1, key2:value2}`

**Respuesta**

Devuelve el objeto API del instancia actual [!UICONTROL DIL] .

**Código de ejemplo**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;);
</code></pre>

## submit {#submit}

Envía todos los datos pendientes a Audience Manager para la [!UICONTROL DIL] instancia.

<!-- 

r_dil_submit.xml

 -->

**Firma de función:** `submit: function () {}`

>[!NOTE]
>
>Puede encadenar otras llamadas de API a este método. Además, [!UICONTROL DIL] escribe datos codificados en un cookie de destino. Por ejemplo, los espacios se codifican como `%20` y los puntos y comas como `%3B`.

**Respuesta**

Devuelve el objeto API del instancia actual [!UICONTROL DIL] .

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits(&lbrack; 
<i>123,456, 789</i>&rbrack;).logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;).signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;).submit();
</code></pre>

## afterResult {#afterresult}

Función que se ejecuta después de la llamada de retorno de publicación de destino predeterminada.

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
| `fn` | Función | La función que desea ejecutar después de JSON es procesada por la llamada de retorno predeterminada que gestiona la publicación de destino. |

**Respuesta**

Devuelve un objeto API del instancia actual [!UICONTROL DIL] .

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.signals(&lbrace; 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
&rbrace;).afterResult(function(json)&lbrace; 
     //Do something with the JSON data returned from the server. 
&rbrace;).submit();
</code></pre>

## clearData {#cleardata}

Borra todos los datos de un solicitud pendiente.

<!-- 

r_dil_clear_data.xml

 -->

**Firma de función:** `clearData: function () {}`

>[!NOTE]
>
>Puede encadenar otras llamadas de API a este método.

**Respuesta**

Devuelve el objeto API del instancia actual [!UICONTROL DIL] .

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs(&lbrace; 
     file: 'dil.js' 
     message: 'This is the first request' 
&rbrace;).signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Agrega parámetros de consulta personalizados que el servidor recopilación de datos no define explícitamente a un solicitud pendiente.

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

Devuelve el objeto API del instancia DIL actual.

**Código de ejemplo**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.customQueryParams(&lbrace; 
     nid: 54231, 
     ntype: 'default' 
&rbrace;); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Devuelve el valor del NSID de contenedor para el [!UICONTROL DIL] instancia. Útil para la depuración y la solución de problemas.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Firma de función:** `dil.api.getContainerNSID: function () {}`

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

Devuelve datos de registro de evento ordenados cronológicamente como una matriz de cadenas. Útil para la depuración y la solución de problemas.

<!-- 

r_dil_get_event_log.xml

 -->

**Firma de función:** `dil.api.getEventLog: function () {}`

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;);.signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;);.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) &lbrace; 
     alert(log.join('\n')); 
&rbrace;else&lbrace; 
     alert('No log messages'); 
&rbrace;
</code></pre>

## getPartner {#getpartner}

Devuelve el nombre socio de un [!UICONTROL DIL] instancia. Útil para la depuración y la solución de problemas.

<!-- 

r_dil_get_partner.xml

 -->

**Firma de función:** `dil.api.getPartner: function () {}`

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Devuelve el estado del instancia actual [!UICONTROL DIL] . Útil para la depuración y la solución de problemas.

<!-- 

r_dil_get_state.xml

 -->

**Firma de función:** `dil.api.getState: function () {}`

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs(&lbrace; 
     file: 'dil.js', 
     message:'This is the first request' 
&rbrace;);.signals(&lbrace; 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;);.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = &lbrace; 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:&lbrace; 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: &lbrace; 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          &rbrace;, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     &rbrace;, 
     destinationPublishingInfo: &lbrace; 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          &#x200B;+ containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     &rbrace; 
&rbrace; 
*/
</code></pre>

## idSync {#idsync}

Consta de dos funciones que permiten a los socios de datos intercambiar y sincronizar ID de usuario entre ellos y Audience Manager.

<!-- 

r_dil_idsync.xml

 -->

**Firma de función:**

Funciona con [!UICONTROL DIL] las versiones 2.10 y 3.1 o superior.

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
   <td colname="col2"> <p>Entre diferentes socios de datos y Audience Manager. Por ejemplo: socio x usaría esto para sincronizar un ID de usuario con socio y luego lo enviaría a Audience Manager. </p> <p> <p><b>Importante:</b>  Este método está en desuso. Utilice el método del <code> idSyncByURL </code> Servicio de identidad de Adobe Experience Platform instancia. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Cuando ya conoce el ID de usuario y desea enviárselo a Audience Manager. </p> <p> <p><b>Importante:</b>  Este método está en desuso. Utilice el método del <code> idSyncByDataSource </code> Servicio de identidad de Adobe Experience Platform instancia. </p> </p> </td> 
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
   <td colname="col3"> <p>El ID único de proveedor de datos para el usuario. </p> </td> 
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
* **`%HTTP_PROTO%`:** define el protocolo Página ( `http` o `https`).

**Respuesta**

Ambas funciones se devuelven si se realiza `Successfully queued` correctamente. Si no, devuelven una cadena con un mensaje de error.

**Código de ejemplo**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync(&lbrace; 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
&rbrace;);
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync(&lbrace; 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
&rbrace;);
</code></pre>

## resultado {#result}

Agrega una devolución de llamada (que recibe JSON) al solicitud pendiente.

<!-- 

r_dil_result.xml

 -->

**Firma de función:** `result: function (callback) {}`

Esta devolución de llamada reemplaza a la devolución de llamada predeterminada que gestiona la publicación en destino.

>[!NOTE]
>
>Puede encadenar otras llamadas de API a este método.

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `callback` | Función | JavaScript función ejecutada por la llamada de retorno JSONP. |

**Respuesta**

Devuelve el objeto API del instancia actual [!UICONTROL DIL] .

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json)&lbrace; 
     //Do something, possibly with the JSON data returned from the server. 
&rbrace;);.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` es un parámetro booleano que controla cómo [!UICONTROL DIL] realiza llamadas a [!UICONTROL Data Collection Servers (DCS)] Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* Cuando `secureDataCollection= true` (predeterminado), [!UICONTROL DIL] siempre realiza llamadas HTTPS seguras.

* Cuando `secureDataCollection= false`, [!UICONTROL DIL] realiza llamadas HTTP o HTTPS siguiendo el protocolo de seguridad establecido por el Página.

>[!IMPORTANT]
>
>Establezca `secureDataCollection= false` si utiliza visitorAPI.js y [!UICONTROL DIL] en el mismo Página. Consulte el ejemplo de código que aparece a continuación.

<pre><code class="js">
var dilInstance = DIL.create(&lbrace; 
     ... 
     secureDataCollection: false 
&rbrace;);
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` es un parámetro booleano true/false que controla la forma en que el explorador solicita recursos de otros dominios.

<!-- 

dil-use-cors-only.xml

 -->

**Información general**

`useCORSOnly` es false de forma predeterminada. &quot;False&quot; significa que el explorador puede realizar comprobaciones de recursos con CORS o JSONP. Sin embargo, [!UICONTROL DIL] siempre intenta solicitud recursos con CORS primero. Vuelve a JSONP en navegadores anteriores que no son compatibles con CORS. Si necesita forzar la explorador a utilizar solo CORS, como en el caso de los sitios que tienen requisitos de alta seguridad, establezca `useCORSOnly:true`.

**Ejemplo de código**

<pre><code class="js">
var dilInstance = DIL.create(&lbrace; 
     ... 
     useCORSOnly: true 
&rbrace;);
</code></pre>

>[!IMPORTANT]
>
>* Le recomendamos que `useCORSOnly: true` configure solo cuando esté seguro de que los visitantes de su sitio tienen navegadores compatibles con esta función.
>* Cuando `useCORSOnly: true`, [!UICONTROL DIL] no realizará llamadas de ID desde Internet Explorer versión 9 o posterior.
>

## useImageRequest {#useimagerequest}

Cambia el tipo de solicitud a imagen `<img>` desde la secuencia de comandos `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Firma de función:** `useImageRequest: function () {}`

>[!NOTE]
>
>Puede encadenar otras llamadas de API a este método.

**Respuesta**

Devuelve un objeto API del instancia actual [!UICONTROL DIL] .

**Código de ejemplo**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [Requisitos de nombre para variables clave](../features/traits/trait-key-name-requirements.md)
>* [Requisitos de prefijo para variables clave](../features/traits/trait-variable-prefixes.md)
>* [Funciones de sincronización en el servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/idsync.html)
>* [DIL crear](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Servicio de identidad Adobe Experience Platform: UseCORSOnly](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [Compatibilidad con CORS en el servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/reference/cors.html)
