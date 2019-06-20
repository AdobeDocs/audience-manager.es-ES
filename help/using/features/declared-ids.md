---
description: Cómo funcionan los ID declarados, configure procedimientos, ejemplos de código y variables.
keywords: sincronización de ID
seo-description: Cómo funcionan los ID declarados, configure procedimientos, ejemplos de código y variables.
seo-title: ID declarados
solution: Audience Manager
title: ID declarados
uuid: 49 bb 4 f 7 e-b 4 a 7-4 d 87-a 29 c-c 3 dca 036 d 2 a 3
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Declared IDs {#declared-ids}

Cómo funcionan los ID declarados, configure procedimientos, ejemplos de código y variables.

## Orientación a ID declarado {#declared-id-targeting}

Intercambie y sincronice los ID de usuario con Audience Manager desde dispositivos o navegadores que no utilicen o acepten mecanismos de almacenamiento persistentes, como cookies de terceros.

<!-- declared_id_about.xml -->

## Purpose of Declared ID Targeting {#declared-id-targeting-purpose}

Algunos exploradores y la mayoría de los dispositivos móviles no aceptan cookies de terceros. Esto hace que sea difícil retener la información sobre los visitantes del sitio o asignar ID persistentes. To resolve this issue, Audience Manager uses [!UICONTROL DIL] to let you pass in [!UICONTROL declared IDs] on an event call. Also, a [!UICONTROL declared ID] can act as a universal ID that applies to the same user across all the solutions in the [!DNL Experience Cloud]. En la tabla siguiente se describe el proceso de coincidencia/objetivo de ID:

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Proceso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Llamada de evento</b> </td> 
   <td colname="col2"> <p>To work, you need <span class="wintitle"> DIL </span> and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID service </a> code on the page. <span class="wintitle"> DIL </span> obtiene <span class="wintitle"> ID declarados </span> de <code> la </code> función setvisitorid que proporciona <span class="keyword"> el servicio Experience Cloud ID </span> y pasa esto a <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de coincidencia</b> </td> 
   <td colname="col2"> <p>Audience Manager intenta coincidir con el ID del cliente y del visitante con un ID correspondiente en nuestro sistema. Si no existe un ID coincidente, Audience Manager crea un nuevo ID y lo asocia con el ID del cliente y del visitante. </p> <p> <p>Nota: La asignación más reciente se utiliza si el ID se asigna a más de un ID de Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de retorno</b> </td> 
   <td colname="col2"> <p>Audience Manager escribe su ID sincronizado en una cookie de origen (u otro espacio de almacenamiento direccionable) en el dominio o aplicación del cliente. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Llamadas de evento subsiguientes</b> </td>
   <td colname="col2"> <p>Las llamadas de evento adicionales leen el ID de Audience Manager del dominio del cliente y lo envían a Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

To get started, you need to configure the [!DNL Experience Cloud] ID service and [!UICONTROL DIL] across the pages on your site that you want to use for data collection. See [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) and [Declared ID Variables](../features/declared-ids.md#declared-id-variables).

## Opt-out Calls {#opt-out-calls}

[!UICONTROL declared ID] El proceso respeta las preferencias de los visitantes del sitio a la exclusión de la segmentación de Audience Manager por su sitio web. When Audience Manager receives an opt-out request, the [!DNL JSON] returned by the [!UICONTROL DCS] contains the error code 171, with the message &quot;Encountered opt out tag&quot;, instead of the Audience Manager user ID.

* Audience Manager can pass in a [!UICONTROL declared ID] opt-out alongside an Audience Manager [!UICONTROL UUID] in the [!DNL URL].
* The [!UICONTROL declared ID] opt-out is stored in the [!UICONTROL Profile Cache Serveîr ([!UICONTROL PCS]) on a per-partner basis. There is no platform-level opt-out using [!UICONTROL declared IDs]. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross [!UICONTROL DCS] regions).

See [Data Privacy](../overview/data-security-and-privacy/data-privacy.md) for more information about opting-out of data collection.

## Declared ID Opt-Out Examples {#opt-out-examples}

You can make a [!UICONTROL declared ID] opt-out requests with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. Consulte [CID sustituye DPID y DPUUID](../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

### Opciones de exclusión con CID y CID_ IC

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción de exclusión con </th> 
   <th colname="col2" class="entry"> Ejemplo de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID de proveedor de datos y ID de usuario. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>name</i>/demoptout.jpg? d_ cid = 123% 01987… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Un código de integración y un ID de usuario. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>name</i>/demoptout? d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>name</i>/demoptout? d_ cid = 123% 01987 &amp; d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opciones de exclusión con DPID, DPUUID y UUID (obsoleto)

Estos métodos siguen funcionando pero se consideran obsoletos. Esta información se proporciona con fines heredados y referencia. Las opciones de exclusión heredadas incluyen:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exclusión (obsoleto) </th> 
   <th colname="col2" class="entry"> Ejemplo de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid </code> solamente </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=AAM<i></i>ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desactivación de nivel de socio </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID &amp; d_ dpid = data provider ID </code> </p> <p>A partner level opt-out gets stored for the latest mapping of this <code> dpid </code> + <code> dpuuid </code> pair to an AAM UUID. Si no hay ninguna asignación existente, Audience Manager comprueba si la solicitud contiene un UUID de AAM en la cookie y, si lo hace, sirve para almacenar la opción de desactivación. De lo contrario, Audience Manager genera un nuevo UUID de AAM y almacena la opción de exclusión debajo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid </code> + <code> d_ dpid </code> y explícito <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>user ID &amp; d_ dpuuid = ID de usuario del proveedor de datos &amp;<i>d_ dpid = data provider ID</i></code> </p> <p> <code> d_ uuid </code> siempre tiene prioridad. If the <code> dpid </code> + <code> dpuuid </code> combination maps to another AAM UUID, the opt-out is stored under the AAM UUID passed in the request ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables and Syntax for Declared IDs {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

The following table lists the key-value pairs that pass in your [!DNL Audience Manager] data provider ID and user IDs or integration codes, if used. Note, *italics* indicates a variable placeholder. Se han agregado espacios para facilitar la lectura.

En cada par clave-valor:

* `=` El símbolo separa la clave de sus valores relacionados.
* The non-printing [!DNL ASCII] character `%01` separates the values.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid =<i>ID del proveedor de datos</i> % 01 ID<i>de usuario</i></code> </p> </td> 
   <td colname="col2"> <p>Contiene un ID de proveedor de datos y un ID de usuario único asociado en un solo par clave-valor. <code> d_ cid </code> reemplaza <code> d_ dpid </code> y <code> d_ dpuuid </code>, que se consideran obsoletos, pero aún se admiten. Consulte <a href="../reference/cid.md">CID sustituye DPID y DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid_ ic =<i>código de integración</i> % 01<i>ID de usuario</i></code> </p> </td> 
   <td colname="col2"> <p>Contiene un código de integración y un ID de usuario único asociado en un solo par clave-valor. <code> d_ cid_ ic </code> reemplaza <code> d_ dpid </code> y <code> d_ dpuuid </code>, que están obsoletos, pero aún se admiten. Consulte <a href="../reference/cid.md">CID sustituye DPID y DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sample Event Calls {#sample-event-calls}

Dados estos pares clave-valor y su sintaxis requerida, realizaría llamadas de eventos como se muestra a continuación.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> La llamada de evento incluye </th> 
   <th colname="col2" class="entry"> Ejemplo de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID de proveedor de datos y ID de usuario. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nombre</i>/evento? d_ cid = 123% 01987… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Un código de integración y un ID de usuario. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nombre</i>/evento? d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nombre</i>/evento? d_ cid = 123% 01987 &amp; d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [CID sustituye DPID y DPUUID](../reference/cid.md)


## Declared ID Variables {#declared-id-variables}

Describes the configuration variables used to pass declared IDs through [!UICONTROL DIL] to [!DNL Audience Manager.]

## DIL Uses the Experience Cloud ID Service to Pass Declared IDs {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

When used with the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), you no longer need to pass in [!UICONTROL declared IDs] with the deprecated `dpid` and `dpuuid` variables. Instead, the current versions of [!UICONTROL DIL] rely on the `visitorService` function to get the [!UICONTROL declared IDs] from the `setCustomerIDs` function in the [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). You would call `visitorService` in `DIL.create` as shown below.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

In the `namespace` key-value pair, `MCORG` is your [!DNL Experience Cloud] Organization ID. If you don&#39;t have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. Necesita permisos de administrador para ver este tablero. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Deprecated Functions {#deprecated-functions}

With the latest versions of [!UICONTROL DIL] (6.2+), you don&#39;t need to use these key-value pairs to pass in [!UICONTROL declared IDs]. That&#39;s because [!UICONTROL DIL] now relies on the `visitorService` function shown in the code sample above. This function gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service]. Sin embargo, aquí se hace referencia a estas variables con fines históricos y heredados. See the code below for an example of how to configure `DIL.create` to get a [!UICONTROL declared ID] from the [!UICONTROL Visitor ID Service].
The following table describes the legacy variables used by the `declaredId` object:

<table id="table_A1884B72950F4BBDA87F17DDFF173628"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> Cadena </td> 
   <td colname="col3"> <p>ID del socio de datos asignado por Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Cadena </td> 
   <td colname="col3"> <p>El ID exclusivo de proveedor de datos para el usuario. </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPID` y `DPUUID`

Audience Manager compares and matches the combined `DPID` and `DPUUID` to a corresponding user ID in our system. If an ID does not exist, Audience Manager creates a new user ID and synchronizes it to the `DPID/DPUUID` combination. Once Audience Manager matches or creates a user ID (the `UUID`) it returns that ID in the [!DNL JSON] response to the cookie in the client&#39;s domain (first-party cookie) or other local storage.

Call this function when you&#39;re using [!UICONTROL DIL] v6.1 or earlier. However, this function has been deprecated in favor of the new version that gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service].

<pre class="js"><code>DIL. create ({ 
 socio: " nombre del socio ", 
 Declaredid: {{{{{{{{{{ 
 dpuuid: <i>dpuuid</i>, 
 DPID: <i>dpid</i> 
 } 
 });</code>
</pre>

>[!NOTE]
>
>Note, you need to programmatically develop the code that supplies the ID values for the `d_dpuuid` and `d_dpid` keys.

### Pasar ID después de la creación de instancias DIL

>[!NOTE]
>
>If you make an [!DNL API] call with a different `declaredID` combination, the new combination will be used for that call only. Further regular event calls will use the original `DIL.create`  `declaredID` combination.

<pre class="js"><code>DIL. getdil (' partner name '). api. señales ({…}). targeedid ({ 
 dpuuid:<i>dpuuid</i> 
 dpid:<i>dpid</i> }). 
submit ();</code>
</pre>

## Request/Response Examples {#request-response-examples}

La solicitud envía un proveedor de datos y un ID de usuario a Audience Manager:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

The response returns the Audience Manager ID (e.g., `UUID`) which is written to a first-party cookie in the page domain.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Do Not Target and Opt-Out Calls {#do-not-target}

[!UICONTROL declared ID] El proceso respeta las preferencias de los visitantes del sitio a la exclusión de la segmentación de Audience Manager por su sitio web. When Audience Manager receives an opt-out request, the [!UICONTROL DCS] returns an empty [!DNL JSON] object instead of the Audience Manager user ID.