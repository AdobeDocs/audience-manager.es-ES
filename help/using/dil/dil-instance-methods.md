---
description: Las API DIL de nivel de instancia permiten crear y trabajar mediante programación con objetos de Audience Manager. Los métodos a nivel de instancia mejoran la funcionalidad de API establecida por los métodos de nivel de clase.
keywords: crear características; crear rasgo
seo-description: Las API DIL de nivel de instancia permiten crear y trabajar mediante programación con objetos de Audience Manager. Los métodos a nivel de instancia mejoran la funcionalidad de API establecida por los métodos de nivel de clase.
seo-title: Métodos DIL de nivel de instancia
solution: Audience Manager
title: Métodos DIL de nivel de instancia
uuid: aa 5147 bb -51 d 5-41 d 4-a 78 a-e 550 f 7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Instance-level DIL Methods{#instance-level-dil-methods}

[!UICONTROL DIL] Las API de nivel de instancia permiten crear y trabajar mediante programación con objetos de Audience Manager. Los métodos a nivel de instancia mejoran la funcionalidad de API establecida por los métodos de nivel de clase.

## Getting started with Instance-level DIL Methods {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

When working with the instance-level [!UICONTROL DIL] APIs:

* Access requiere un nombre de socio y un ID de espacio de nombres de contenedor (NSID). Póngase en contacto con el administrador de cuentas de Audience Manager para obtener esta información.
* Replace any sample *italicized* text in the API documentation with value, ID, or other variable as required by the method you&#39;re working with.

<!-- 

c_instance_start.xml

 -->

## signals {#signals}

Agrega asignaciones de cliente y de plataforma a la cadena de consulta de una solicitud pendiente.

<!-- 

r_dil_signals.xml

 -->

**Firma de función:**`signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Puede segmentar otras llamadas de API a este método.
>* If the Adobe Experience Cloud JavaScript library is on the page, `submit()` waits for the Cloud to set a cookie before sending a request.


**Claves de solicitud reservadas**

Las claves de solicitud siguientes están reservadas y no pueden sobrescribirse con este método:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `obj` | Objeto | Un objeto que representa los pares de clave-valor para asignaciones a nivel de plataforma. El parámetro acepta cadenas y matrices como valores de propiedad en el objeto. |
| `prefix` | Cadena | Opcional. El valor de cadena con el prefijo de cada clave de objeto (reemplaza la clave original). |
| `return` | DIL. api | Devuelve el objeto API de la instancia DIL actual. |

**Respuesta**

Returns the API object of the current [!UICONTROL DIL] instance.

**Código de ejemplo**

<pre><code>var datalib = DIL. create ({ 
 socio: '<i>Partnername</i>' 
 Containernsid: <i>Containernsid</i> }); 
 
// Method 1 
var obj = {key 1: 1, key 2: 2}; 
Datalib. api. señales (obj,' c_'). submit (); 
 
// Método 2 
datalib. api. señales ({c_ zdid: 54321}). submit (); 
 
// Method 3 
// enviará'c_ key = a &amp; c_ key = 2 &amp; c_ key = 3 ' a Audience Manager 
var obj = {key: [' a ',' b ',' c ']}; 
Datalib. api. señales (obj,' c_'). submit ();</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Requisitos de nombre para variables clave](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

Agrega los SID a la cadena de consulta de una solicitud pendiente.

<!-- 

r_dil_traits.xml

 -->

**Firma de función:**`traits:function (sids){}`

>[!NOTE]
>
>Puede segmentar otras llamadas de API a este método.

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `sids` | Matriz | ID de segmentos de características en una matriz. |

**Respuesta**

Returns the API object of the current [!UICONTROL DIL] instance.

**Código de ejemplo**

<pre><code>var partnerobject = DIL. create ({ 
 socio: '<i>nombre del socio</i>', 
 Containernsid: <i>NSID</i> }); 
Partnerobject. api. traits (<i>[123, 456, 789]</i>);</code>
</pre>

## logs {#logs}

Agregue datos a los archivos de registro en la solicitud pendiente.

<!-- 

r_dil_logs.xml

 -->

**Firma de función:**`logs: function {key1:value1, key2:value2}`

**Respuesta**

Returns the API object of the current [!UICONTROL DIL] instance.

**Código de ejemplo**

<pre><code>var partnerobject = DIL. create ({ 
 socio: '<i>partner</i>', 
 Containernsid: <i>NSID</i> }); 
Partnerobject. api. logs ({ 
 archivo: ' dil. js ', 
 message: ' Ésta es la primera solicitud '});</code>
</pre>

## submit {#submit}

Submits all pending data to Audience Manager for the [!UICONTROL DIL] instance.

<!-- 

r_dil_submit.xml

 -->

**Firma de función:**`submit: function () {}`

>[!NOTE]
>
>Puede segmentar otras llamadas de API a este método. [!UICONTROL DIL] Asimismo, escribe datos codificados en una cookie de destino. For example, spaces are encoded as `%20` and semicolons as `%3B`.

**Respuesta**

Returns the API object of the current [!UICONTROL DIL] instance.

**Código de ejemplo**

<pre><code>var datalib = DIL. create ({ 
 socio: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. traits ([<i>123.456, 
789</i>]). logs ({ 
 archivo: ' dil. js ', 
 message: ' Ésta es la primera solicitud '}). 
señales ({ 
 c_ zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}). 
submit ();</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Requisitos de prefijo para variables clave](../features/traits/trait-variable-prefixes.md)


## afterResult {#afterresult}

Una función que se ejecuta después de la rellamada de publicación de destino predeterminada.

<!-- 

r_dil_after_result.xml

 -->

**Firma de función:**`afterResult: function (fn) {}`

>[!NOTE]
>
>Puede segmentar otras llamadas de API a este método.

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `fn` | Función | La función que desea ejecutar después de JSON se procesa mediante la llamada de retorno predeterminada que gestiona la publicación de destino. |

**Respuesta**

Returns an API object of the current [!UICONTROL DIL] instance.

**Código de ejemplo**

<pre><code>var datalib = DIL. create ({ 
 socio: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. señales ({ 
 c_ zdid: <i>54321</i> 
 d_ dma: '<i>default</i>'}). 
afterresult (function (json) { 
 //Do algo con los datos JSON devueltos por el servidor. 
}).submit();
</code></pre>

## clearData {#cleardata}

Borra todos los datos en una solicitud pendiente.

<!-- 

r_dil_clear_data.xml

 -->

**Firma de función:**`clearData: function () {}`

>[!NOTE]
>
>Puede segmentar otras llamadas de API a este método.

**Respuesta**

Returns the API object of the current [!UICONTROL DIL] instance.

**Código de ejemplo**

<pre><code>var datalib = DIL. create ({ 
 socio: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. traits ([<i>123.456, 789</i>]). logs ({ 
 archivo: ' dil. js ' 
 message: ' Ésta es la primera solicitud '}). 
señales ({ 
 c_ zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}); 
 
//Reset los datos 
pendientes datalib. cleardata ();</code>
</pre>

## customQueryParams {#customqueryparams}

Agrega parámetros de consulta personalizados que el servidor de recopilación de datos no define explícitamente a una solicitud pendiente.

<!-- 

r_dil_custom_query_params.xml

 -->

**Firma de función:**`customQueryParams: function (obj) {}`

>[!NOTE]
>
>Puede segmentar otras llamadas de API a este método.

**Claves de solicitud reservadas**

Las claves de solicitud siguientes están reservadas y no pueden sobrescribirse con este método:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Respuesta**

Devuelve el objeto API de la instancia DIL actual.

**Código de ejemplo**

<pre><code>var partnerobject = DIL. create ({ 
 socio: '<i>partner</i>', 
 Containernsid: <i>NSID</i> }); 
Partnerobject. api. customqueryparams ({ 
 nid: 54231, 
 ntype: ' default '});</code>
</pre>

## getContainerNSID {#getcontainernsid}

Returns the value of the container NSID for the [!UICONTROL DIL] instance. Es útil para depurar y solucionar problemas.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Firma de función:**`dil.api.getContainerNSID: function () {}`

**Código de ejemplo**

<pre><code>var datalib = DIL. create ({ 
 socio: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
//Verify the container NSID 
var nsid = datalib. api. getcontainernsid ();</code>
</pre>

## getEventLog {#geteventlog}

Devuelve datos de registro de eventos ordenados cronológicamente como una matriz de cadenas. Es útil para depurar y solucionar problemas.

<!-- 

r_dil_get_event_log.xml

 -->

**Firma de función:**`dil.api.getEventLog: function () {}`

**Código de ejemplo**

<pre><code>var datalib = DIL. create ({ 
 socio: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. traits ([<i>123, 456, 789</i>]). logs ({ 
 archivo: ' dil. js ', 
 message: ' Ésta es la primera solicitud '}); . señales ({ 
 c_ zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}); . submit (); 
 
//Check log for messages 
var log = datalib. api. geteventlog (); 
if (log &amp; &amp; log. length) { 
 alert (log. join ('\ n ')); 
} else { 
 alert (' Sin mensajes de registro '); 
}</code>
</pre>

## getPartner {#getpartner}

Returns the partner name for a [!UICONTROL DIL] instance. Es útil para depurar y solucionar problemas.

<!-- 

r_dil_get_partner.xml

 -->

**Firma de función:**`dil.api.getPartner: function () {}`

**Código de ejemplo**

<pre><code>var datalib = DIL. create ({ 
 socio: '<i>Partnername</i>' 
 Containernsid: <i>Containernsid</i> }); 
 
//Verify the partner name 
var partner = datalib. api. getpartner ();</code>
</pre>

## getState {#getstate}

Returns the state of the current [!UICONTROL DIL] instance. Es útil para depurar y solucionar problemas.

<!-- 

r_dil_get_state.xml

 -->

**Firma de función:**`dil.api.getState: function () {}`

**Código de ejemplo**

<pre><code>var datalib = DIL. create ({ 
 socio: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. traits ([<i>123, 456, 789</i>]). logs ({ 
 archivo: ' dil. js ', 
 message: ' Ésta es la primera solicitud '}); . señales ({ 
 c. zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}); . submit (); 
 
var state = datalib. api. getstate (); 
 
/* Contorno de objeto del estado state 
= { 
 Pendingrequest: {<i>datos pendientes para llamar al servidor</i>}, 
 Otherrequestinfo: {{{{{{{{{{ 
 Firingqueue: [], 
 activado: [], 
 activación: false, 
 errored: [], 
 Reservaciones: {{{{{{{{{{ 
 sids: true, 
 pdata: true, 
 logdata: true, 
 rellamada: true, 
 Postcallbackfn: true, 
 Useimagerequest: true, 
 }, 
 Firstrequesthasactiv: false, 
 num_ of_ jsonp_ responses: 0, 
 num_ of_ jsonp_ errors: 0, 
 num_ of_ img_ responses: 0, 
 num_ of_ img_ errors: 0 
 }, 
 Destinationpublishinginfo: {{{{{{{{{{ 
 THROTTLE_ START: 3000, 
 Throttletimerset: false, 
 id: " destination_ publishing_ iframe_' + partner +'_' + containernsid, 
 url: (constantes. ishttps? ' https://': ' https://fast.') + partner +' .demdex.net/dest3.html?d_nsid=' 
 + Containernsid +' #' + encodeuricomponent (document. location. href), 
 iframe: null, 
 Iframehasloaded: false, 
 Sendingmessages: false, 
 mensajes: [], 
 Messagesendinginterval: constantes. POST_ MESSAGE_ MESSAGE_ ENABLED 15: 100, 
               //Recommend 100ms for IE 6 &amp; 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

Consiste en dos funciones que permiten a los socios de datos intercambiar y sincronizar ID de usuario entre ellos y Audience Manager.

<!-- 

r_dil_idsync.xml

 -->

**Firma de función:**

Works with [!UICONTROL DIL] versions 2.10 and 3.1 or higher.

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Código </th> 
   <th colname="col2" class="entry"> Sincroniza los ID de los usuarios </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil. Instance. api. idsync (initconfig) </code> </td> 
   <td colname="col2"> <p>Entre los diferentes socios de datos y Audience Manager. Por ejemplo, el socio x utilizaría esto para sincronizar un ID de usuario con un socio y enviarlo a Audience Manager. </p> <p> <p><b>Importante:</b> Este método está obsoleto. Please use the <code> idSyncByURL </code> method of the Experience Cloud ID Service instance. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil. Instance. api. aamidsync (initconfig) </code> </td> 
   <td colname="col2"> <p>Cuando ya conoce el ID de usuario y desea enviarlo a Audience Manager. </p> <p> <p><b>Importante:</b> Este método está obsoleto. Please use the <code> idSyncByDataSource </code> method of the Experience Cloud ID Service instance. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Idsync Elements**

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
* **`%HTTP_PROTO%`:** Define el protocolo de página ( `http` o `https`).

**Respuesta**

Both functions return `Successfully queued` if successful. Si no, devuelven una cadena con un mensaje de error.

**Código de ejemplo**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">// Fire url with macros sustituido 
dilinstance. api. idsync ({ 
 dpid: ' 23 ', // debe ser una cadena 
 url: '//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
% 2 Fibs % 3 Adpid % 3 D 420% 26 dpuuid % 3 D % 7 B % 7 Buid % 7 D % 7 D ', 
 Minutestolive: 20160 // opcional, defaults to 20160 minutes (14 days)});</code>
</pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">// Fire ' https:/https:' +'//dpm.demdex.net/ibs:dpid= &lt; dpid &gt; &amp; dpuuid = &lt; dpuuid &gt;' 
dilinstance. api. aamidsync ({ 
 dpid: ' 23 ', // debe ser una cadena 
 dpuuid: ' 98765 ', // debe ser una cadena 
 Minutestolive: 20160 // opcional, defaults to 20160 minutes (14 days)});</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Funciones de sincronización en el servicio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## result {#result}

Agrega una llamada de retorno (que recibe JSON) a la solicitud pendiente.

<!-- 

r_dil_result.xml

 -->

**Firma de función:**`result: function (callback) {}`

Esta llamada de retorno reemplaza la rellamada predeterminada que gestiona la publicación de destino.

>[!NOTE]
>
>Puede segmentar otras llamadas de API a este método.

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `callback` | Función | Función JavaScript ejecutada por la rellamada JSONP. |

**Respuesta**

Returns the API object of the current [!UICONTROL DIL] instance.

**Código de ejemplo**

<pre><code>var datalib = DIL. create ({ 
 socio: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. traits ([<i>123, 456, 789</i>]). result (function (json) { 
 //Do algo, posiblemente con los datos JSON devueltos del servidor. 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` es un parámetro booleano que controla cómo [!UICONTROL DIL] realiza llamadas a [!UICONTROL Data Collection Servers (DCS)] y Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* When `secureDataCollection= true` (default), [!UICONTROL DIL] always makes secure, HTTPS calls.

* When `secureDataCollection= false`, [!UICONTROL DIL] makes either HTTP or HTTPS calls by following the security protocol set by the page.

>[!IMPORTANT]
>
>Set `secureDataCollection= false` if you use visitorAPI.js and [!UICONTROL DIL] on the same page. Consulte la muestra de código siguiente.

<pre><code class="js">var dilinstance = DIL. create ({ 
 … 
 Securedatacollection: false});</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [DIL Create](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` es un parámetro booleano true/false que controla cómo el explorador solicita recursos desde otros dominios.

<!-- 

dil-use-cors-only.xml

 -->

**Información general**

`useCORSOnly` es false de forma predeterminada. False significa que el navegador puede realizar comprobaciones de recursos con CORS o JSONP. However, [!UICONTROL DIL] always tries to request resources with CORS first. Vuelve a JSONP en navegadores anteriores que no son compatibles con CORS. If you need to force the browser to use CORS only, such as with sites that have high-security requirements, set `useCORSOnly:true`.

**Ejemplo de código**

<pre><code class="js">var dilinstance = DIL. create ({ 
 … 
 Usecorsonly: true});</code>
</pre>

>[!IMPORTANT]
>
>* We recommend that you set `useCORSOnly: true` only when you&#39;re sure that your site visitors have browsers that support this feature.
>* When `useCORSOnly: true`, [!UICONTROL DIL] will not make ID calls from Internet Explorer version 9 or older.
>



>[!MORE_ LIKE_ THIS]
>
>* [DIL Create](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Servicio Experience Cloud ID: Usecorsonly](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [Compatibilidad con CORS en el servicio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## useImageRequest {#useimagerequest}

Changes the request type to image `<img>` from script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Firma de función:**`useImageRequest: function () {}`

>[!NOTE]
>
>Puede segmentar otras llamadas de API a este método.

**Respuesta**

Returns an API object of the current [!UICONTROL DIL] instance.

**Código de ejemplo**

<pre><code>var datalib = DIL. create ({ 
 socio: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. traits ([<i>123, 456, 789</i>]). useimagerequest (). submit ();</code>
</pre>

