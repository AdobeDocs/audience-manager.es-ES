---
description: Cómo funcionan los ID declarados, configure procedimientos, ejemplos de código y variables.
keywords: sincronización de ID
seo-description: Cómo funcionan los ID declarados, configure procedimientos, ejemplos de código y variables.
seo-title: ID declarados
solution: Audience Manager
title: ID declarados
uuid: 49 bb 4 f 7 e-b 4 a 7-4 d 87-a 29 c-c 3 dca 036 d 2 a 3
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# ID declarados {#declared-ids}

Cómo funcionan los ID declarados, configure procedimientos, ejemplos de código y variables.

## Orientación a ID declarado {#declared-id-targeting}

Intercambie y sincronice los ID de usuario con Audience Manager desde dispositivos o navegadores que no utilicen o acepten mecanismos de almacenamiento persistentes, como cookies de terceros.

<!-- declared_id_about.xml -->

## Objetivo de targeting de ID declarado {#declared-id-targeting-purpose}

Algunos exploradores y la mayoría de los dispositivos móviles no aceptan cookies de terceros. Esto hace que sea difícil retener la información sobre los visitantes del sitio o asignar ID persistentes. Para resolver este problema, Audience Manager utiliza [!UICONTROL DIL] para permitir pasar [!UICONTROL declared IDs] en una llamada de evento. Además, puede [!UICONTROL declared ID] actuar como un ID universal que se aplique al mismo usuario en todas las soluciones de [!DNL Experience Cloud]la. En la tabla siguiente se describe el proceso de coincidencia/objetivo de ID:

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
   <td colname="col2"> <p>Para trabajar, necesita <span class="wintitle"> DIL </span> y <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> el código de servicio </a> Experience Cloud ID en la página. <span class="wintitle"> DIL </span> obtiene <span class="wintitle"> ID declarados </span> de <code> la </code> función setvisitorid que proporciona <span class="keyword"> el servicio Experience Cloud ID </span> y pasa esto a <span class="keyword"> Audience Manager </span>. </p> </td> 
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

Para comenzar, debe configurar el servicio [!DNL Experience Cloud] de ID y [!UICONTROL DIL] las páginas del sitio que desee utilizar para la recopilación de datos. Consulte [Creación](../dil/dil-class-overview/dil-create.md#dil-create) de DIL y variables de ID [declaradas](../features/declared-ids.md#declared-id-variables).

## Llamadas de exclusión {#opt-out-calls}

[!UICONTROL declared ID] El proceso respeta las preferencias de los visitantes del sitio a la exclusión de la segmentación de Audience Manager por su sitio web. Cuando Audience Manager recibe una solicitud de exclusión, la [!DNL JSON] devuelta por [!UICONTROL DCS] contiene el código de error 171, con el mensaje «La etiqueta de desactivación encontró», en lugar del ID de usuario de Audience Manager.

* Audience Manager puede pasar una [!UICONTROL declared ID] opción de exclusión junto con Audience Manager [!UICONTROL UUID] en [!DNL URL]la.
* La [!UICONTROL declared ID] opción de exclusión se almacena en el [! El servidor de caché de perfil UICONTROL ([!UICONTROL PCS]) depende de cada socio. No hay ninguna opción de exclusión a nivel de plataforma. [!UICONTROL declared IDs] Además, Audience Manager elige al usuario fuera de esa zona en particular del Edge (la opción de exclusión no se cruza [!UICONTROL DCS] con regiones).

Consulte [Privacidad de datos](../overview/data-security-and-privacy/data-privacy.md) para obtener más información sobre la exclusión de la recopilación de datos.

## Ejemplos de exclusión de ID declarados {#opt-out-examples}

Puede [!UICONTROL declared ID] realizar solicitudes de exclusión con `d_cid` pares `d_cid_ic` de clave-valor. Los parámetros heredados como `d_dpid` y `d_dpuuid` aún funcionan, pero se consideran obsoletos. Consulte [CID sustituye DPID y DPUUID](../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

### Opciones de exclusión con CID y CID_ IC

Para obtener una descripción y sintaxis, consulte [Variables de URL y Sintaxis para ID declarados](../features/declared-ids.md#variables-and-syntax).

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
   <td colname="col1"> <p>Pares de <code> clave-valor muld_ cid </code> y <code> d_ cid_ ic </code> . </p> </td> 
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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID &amp; d_ dpid = data provider ID </code> </p> <p>Se almacena una exclusión de nivel de socio para la asignación más reciente de este <code> par dpid </code> + <code> dpuuid </code> a un UUID de AAM. Si no hay ninguna asignación existente, Audience Manager comprueba si la solicitud contiene un UUID de AAM en la cookie y, si lo hace, sirve para almacenar la opción de desactivación. De lo contrario, Audience Manager genera un nuevo UUID de AAM y almacena la opción de exclusión debajo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid </code> + <code> d_ dpid </code> y explícito <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>user ID &amp; d_ dpuuid = ID de usuario del proveedor de datos &amp;<i>d_ dpid = data provider ID</i></code> </p> <p> <code> d_ uuid </code> siempre tiene prioridad. Si la <code> combinación dpid </code> + <code> dpuuid </code> se asigna a otro UUID de AAM, la opción de exclusión se almacena bajo el UUID de AAM que se pasa a la solicitud ( <code> d_ uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables y sintaxis para los ID declarados {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

La siguiente tabla enumera los pares de clave-valor que pasan el ID de proveedor [!DNL Audience Manager] de datos, los ID de usuario o los códigos de integración, si se utilizan. Note, *italics* indicates a variable placeholder. Se han agregado espacios para facilitar la lectura.

En cada par clave-valor:

* `=` El símbolo separa la clave de sus valores relacionados.
* El carácter no imprimible [!DNL ASCII]`%01` separa los valores.

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

## Ejemplo de llamadas de evento {#sample-event-calls}

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
   <td colname="col1"> <p>Pares de <code> clave-valor muld_ cid </code> y <code> d_ cid_ ic </code> . </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nombre</i>/evento? d_ cid = 123% 01987 &amp; d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [CID sustituye DPID y DPUUID](../reference/cid.md)


## Variables de ID declaradas {#declared-id-variables}

Describe las variables de configuración utilizadas para pasar los ID declarados [!UICONTROL DIL] a [!DNL Audience Manager.]

## DIL usa el servicio Experience Cloud ID para pasar ID declarados {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

Cuando se utiliza con [el servicio](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud ID, ya no tiene que pasar [!UICONTROL declared IDs] con las variables y las `dpid``dpuuid` variables obsoletas. En su lugar, las versiones actuales [!UICONTROL DIL] de dependen de `visitorService` la función para obtener la [!UICONTROL declared IDs] de `setCustomerIDs`[!UICONTROL Experience Cloud ID Service]la función. Para obtener más información, consulte [ID de cliente y estados de autenticación](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). Se llamaría `visitorService` como `DIL.create` se muestra a continuación.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

En el par `namespace` clave-valor, `MCORG` es [!DNL Experience Cloud] su identificador de organización. Si no tiene este ID, puede encontrarlo en la [!UICONTROL Administration] sección del [!DNL Experience Cloud] tablero. Necesita permisos de administrador para ver este tablero. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Funciones obsoletas {#deprecated-functions}

Con las últimas versiones de [!UICONTROL DIL] (6.2 +), no es necesario utilizar estos pares de clave-valor para pasar [!UICONTROL declared IDs]. Esto se debe [!UICONTROL DIL] a que ahora se basa en la `visitorService` función exhibida en el ejemplo de código anterior. Esta función obtiene [!UICONTROL declared IDs] de [!UICONTROL Experience Cloud ID Service]la. Sin embargo, aquí se hace referencia a estas variables con fines históricos y heredados. Consulte el código siguiente para ver un ejemplo de cómo configurar `DIL.create` a [!UICONTROL declared ID] partir [!UICONTROL Visitor ID Service]de la.
En la tabla siguiente se describen las variables heredadas utilizadas por `declaredId` el objeto:

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

Audience Manager compara y coincide con la ID combinada `DPID` y `DPUUID` con el ID de usuario correspondiente en nuestro sistema. Si un ID no existe, Audience Manager crea un nuevo ID de usuario y lo sincroniza con `DPID/DPUUID` la combinación. Una vez que Audience Manager coincide o crea un ID de usuario (el `UUID`) devuelve ese ID en [!DNL JSON] la respuesta a la cookie en el dominio del cliente (cookie de origen) u otro almacenamiento local.

Llame esta función cuando utilice [!UICONTROL DIL] la versión 6.1 o anterior. Sin embargo, esta función se ha desaprobado en favor de la nueva versión que obtiene [!UICONTROL declared IDs] del [!UICONTROL Experience Cloud ID Service].

```js
DIL.create({
    partner : "partner name",
    declaredId : {
       dpuuid : dpuuid,
       DPID : dpid
    }
 });
```

>[!NOTE]
>
>Tenga en cuenta que debe desarrollar programáticamente el código que proporciona los valores de ID para las claves `d_dpuuid` y `d_dpid` las claves.

### Pasar ID después de la creación de instancias DIL

>[!NOTE]
>
>Si realiza [!DNL API] una llamada con `declaredID` una combinación diferente, la nueva combinación se utilizará solo para esa llamada. Otras llamadas de evento normales utilizarán `DIL.create``declaredID` la combinación original.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Ejemplos de solicitud y respuesta {#request-response-examples}

La solicitud envía un proveedor de datos y un ID de usuario a Audience Manager:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

La respuesta devuelve el ID de Audience Manager (por ejemplo `UUID`,) que se escribe en una cookie de origen en el dominio de página.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## No segmentar y llamadas de exclusión {#do-not-target}

[!UICONTROL declared ID] El proceso respeta las preferencias de los visitantes del sitio a la exclusión de la segmentación de Audience Manager por su sitio web. Cuando Audience Manager recibe una solicitud de exclusión, [!UICONTROL DCS] la devuelve un objeto vacío [!DNL JSON] en lugar del ID de usuario de Audience Manager.
