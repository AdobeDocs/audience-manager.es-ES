---
description: Funcionamiento de los ID declarados, configuración de procedimientos, ejemplos de código y variables.
keywords: id sync
seo-description: Funcionamiento de los ID declarados, configuración de procedimientos, ejemplos de código y variables.
seo-title: ID declarados
solution: Audience Manager
title: ID declarados
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: Sincronizaciones de ID
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 10%

---

# [!UICONTROL Declared IDs] {#declared-ids}

Funcionamiento de [!UICONTROL declared IDs], configuración de procedimientos, ejemplos de código y variables.

## [!UICONTROL Declared ID] Segmentación {#declared-id-targeting}

Intercambie y sincronice los ID de usuario con [!DNL Audience Manager] de dispositivos o navegadores que no utilicen ni acepten mecanismos de almacenamiento persistentes, como [!DNL cookies] de terceros.

## Objetivo de [!UICONTROL Declared ID] Segmentación {#declared-id-targeting-purpose}

Algunos exploradores y la mayoría de los dispositivos móviles no aceptan [!DNL cookies] de terceros. Esto dificulta la retención de información sobre los visitantes del sitio o la asignación de ID persistentes. Para resolver este problema, [!DNL Audience Manager] utiliza [!UICONTROL DIL] para permitirle pasar [!UICONTROL declared IDs] en una llamada de evento. Además, un [!UICONTROL declared ID] puede actuar como un ID universal que se aplica al mismo usuario en todas las soluciones del [!DNL Experience Cloud]. En la tabla siguiente se describe el proceso de establecimiento de objetivos/coincidencia con ID:

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
   <td colname="col2"> <p>Para funcionar, necesita <span class="wintitle"> DIL </span> y el código <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> del servicio de identidad de Adobe Experience Platform </a> en la página. <span class="wintitle"> El DIL  </span> obtiene los ID  <span class="wintitle"> declarados  </span> de la  <code> setVisitorID </code> función proporcionada por el servicio de identidad de  <span class="keyword"> Adobe Experience Platform  </span> y los pasa a  <span class="keyword"> Audience Manager  </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Coincidencia de ID</b> </td> 
   <td colname="col2"> <p>El Audience Manager intenta hacer coincidir el ID de cliente y de visitante con un ID correspondiente en nuestro sistema. Si no existe un ID coincidente, el Audience Manager crea un nuevo ID y lo asocia con el ID del cliente y del visitante. </p> <p> <p>Nota:  La asignación más reciente se utiliza si su ID se asigna a más de un ID de Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de retorno</b> </td> 
   <td colname="col2"> <p>El Audience Manager escribe su ID sincronizado en una cookie de origen (u otro espacio de almacenamiento accesible) en el dominio o la aplicación del cliente. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Llamadas de evento posteriores</b> </td>
   <td colname="col2"> <p>Las llamadas de evento adicionales leen el ID de Audience Manager del dominio del cliente y lo envían al Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Para comenzar, debe configurar el servicio de [!DNL Experience Cloud] ID y [!UICONTROL DIL] en las páginas del sitio que desee utilizar para la recopilación de datos. Consulte [Creación de DIL](../dil/dil-class-overview/dil-create.md#dil-create) y [Variables de ID declaradas](../features/declared-ids.md#declared-id-variables).

## Llamadas de exclusión {#opt-out-calls}

El proceso [!UICONTROL declared ID] respeta las preferencias de los visitantes del sitio de excluirse de la segmentación [!DNL Audience Manager] por parte del sitio web. Cuando [!DNL Audience Manager] recibe una solicitud de exclusión, el [!DNL JSON] devuelto por el [!DNL DCS] contiene el código de error 171, con el mensaje `Encountered opt out tag`, en lugar del [!DNL Audience Manager] ID de usuario.

* [!DNL Audience Manager] puede pasar una  [!UICONTROL declared ID] exclusión junto con una  [!DNL Audience Manager] [!UICONTROL UUID] en  [!DNL URL].
* La exclusión [!UICONTROL declared ID] se almacena en el [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) por socio. No hay exclusión a nivel de plataforma mediante [!UICONTROL declared IDs]. Además, [!DNL Audience Manager] excluye al usuario de esa región en particular en el borde (la exclusión no cruza [!DNL DCS] regiones).

Consulte [Privacidad de datos](../overview/data-security-and-privacy/data-privacy.md) para obtener más información sobre la exclusión de la recopilación de datos.

## [!UICONTROL Declared ID] Ejemplos de exclusión  {#opt-out-examples}

Puede realizar una [!UICONTROL declared ID] solicitud de exclusión con los pares de clave-valor `d_cid` y `d_cid_ic` . Los parámetros heredados como `d_dpid` y `d_dpuuid` siguen funcionando, pero se consideran obsoletos. Consulte [CID reemplaza DPID y DPUUID](../reference/cid.md). En los ejemplos, la *cursiva* indica un marcador de posición para una variable.

### Exclusiones con [!UICONTROL CID] y [!UICONTROL CID_IC]

Para obtener una descripción y sintaxis, consulte [variables de URL y Sintaxis para ID declarados](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción de exclusión mediante </th> 
   <th colname="col2" class="entry"> Ejemplo de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID de proveedor de datos e ID de usuario. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código de integración e ID de usuario. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Varios pares de clave-valor <code> d_cid </code> y <code> d_cid_ic </code>. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exclusiones con [!UICONTROL DPID], [!UICONTROL DPUUID] y [!UICONTROL UUID] (obsoleto)

Estos métodos siguen funcionando, pero se consideran obsoletos. Esta información se proporciona con fines y referencias heredados. Las exclusiones heredadas incluyen:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exclusión (obsoleto) </th> 
   <th colname="col2" class="entry"> Ejemplo de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> solamente </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exclusión a nivel de socio </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Se almacena una exclusión a nivel de socio para la asignación más reciente de este par <code> dpid </code> + <code> dpuuid </code> a un UUID AAM. Si no hay ninguna asignación existente anteriormente, el Audience Manager comprueba si la solicitud contiene un UUID de AAM en la cookie y, en caso afirmativo, lo utiliza para almacenar la exclusión. De lo contrario, Audience Manager genera un UUID de AAM nuevo y almacena la exclusión en él. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> +  <code> d_dpid </code> y explícito  <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> siempre tiene prioridad. Si la combinación <code> dpid </code> + <code> dpuuid </code> se asigna a otro UUID de AAM, la exclusión se almacena en el UUID de AAM pasado en la solicitud ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables y sintaxis para [!UICONTROL Declared IDs] {#variables-and-syntax}

En la tabla siguiente se enumeran los pares clave-valor que pasan el ID del proveedor de datos [!DNL Audience Manager] y los ID de usuario o los códigos de integración, si se utilizan. Tenga en cuenta que la *cursiva* indica un marcador de posición de variable. Se han agregado espacios para facilitar la lectura.

En cada par clave-valor:

* El símbolo `=` separa la clave de sus valores relacionados.
* El carácter [!DNL ASCII] no imprimible `%01` separa los valores.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid =<i>data provider ID</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contiene un ID de proveedor de datos y un ID de usuario único asociado en un único par clave-valor. <code> d_cid </code> reemplaza  <code> d_dpid </code> y  <code> d_dpuuid </code>, que se consideran obsoletos, pero que siguen siendo compatibles. Consulte <a href="../reference/cid.md">CID reemplaza DPID y DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contiene un código de integración y un ID de usuario único asociado en un único par clave-valor. <code> d_cid_ic </code> reemplaza  <code> d_dpid </code> y  <code> d_dpuuid </code>, que están en desuso, pero que siguen siendo compatibles. Consulte <a href="../reference/cid.md">CID reemplaza DPID y DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplo de llamadas de evento {#sample-event-calls}

Dados estos pares clave-valor y la sintaxis necesaria, debe realizar llamadas de evento como se muestra a continuación.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Inclusión de llamada de evento </th> 
   <th colname="col2" class="entry"> Ejemplo de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID de proveedor de datos e ID de usuario. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código de integración e ID de usuario. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Varios pares de clave-valor <code> d_cid </code> y <code> d_cid_ic </code>. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variables {#declared-id-variables}

Describe las variables de configuración utilizadas para pasar [!UICONTROL declared IDs] de [!UICONTROL DIL] a [!DNL Audience Manager.]

## [!UICONTROL DIL] utiliza el  [!DNL Adobe Experience Platform Identity Service] para pasar  [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Cuando se utiliza con el [Servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html), ya no es necesario pasar [!UICONTROL declared IDs] con las variables `dpid` y `dpuuid` obsoletas. En su lugar, las versiones actuales de [!UICONTROL DIL] dependen de la función `visitorService` para obtener la [!UICONTROL declared IDs] de la función `setCustomerIDs` en [!UICONTROL Adobe Experience Platform Identity Service]. Para obtener más información, consulte [ID de cliente y estados de autenticación](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). Llamaría a `visitorService` en `DIL.create` como se muestra a continuación.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

En el par `namespace` clave-valor, `MCORG` es su [!DNL Experience Cloud] ID de organización. Si no tiene este ID, puede encontrarlo en la sección [!UICONTROL Administration] del panel [!DNL Experience Cloud]. Necesita permisos de administrador para ver este tablero. Consulte [Administración: Servicios principales](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## Funciones obsoletas {#deprecated-functions}

Con las últimas versiones de [!UICONTROL DIL] (6.2+), no es necesario utilizar estos pares clave-valor para pasar [!UICONTROL declared IDs]. Esto se debe a que [!UICONTROL DIL] ahora se basa en la función `visitorService` que se muestra en el ejemplo de código anterior. Esta función obtiene [!UICONTROL declared IDs] del [!UICONTROL Adobe Experience Platform Identity Service]. Sin embargo, aquí hacemos referencia a estas variables con fines históricos y heredados. Consulte el código siguiente para ver un ejemplo de cómo configurar `DIL.create` para obtener un [!UICONTROL declared ID] desde el [!UICONTROL Visitor ID Service].
La tabla siguiente describe las variables heredadas que utiliza el objeto `declaredId`:

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
   <td colname="col3"> <p>ID del socio de datos asignado por el Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Cadena </td> 
   <td colname="col3"> <p>El ID único de proveedor de datos para el usuario. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] y [!UICONTROL DPUUID]

[!DNL Audience Manager] compara y coincide con el ID de usuario combinado  `DPID` y  `DPUUID` con el ID de usuario correspondiente en nuestro sistema. Si no existe un ID, [!DNL Audience Manager] crea un nuevo ID de usuario y lo sincroniza con la combinación `DPID/DPUUID`. Una vez que [!DNL Audience Manager] coincide o crea un ID de usuario (el `UUID`), devuelve ese ID en la respuesta [!DNL JSON] al [!DNL cookie] en el dominio del cliente ([!DNL cookie] de origen) u otro almacenamiento local.

Llame a esta función cuando esté utilizando [!UICONTROL DIL] v6.1 o una versión anterior. Sin embargo, esta función ha quedado obsoleta en favor de la nueva versión que obtiene [!UICONTROL declared IDs] de [!DNL Adobe Experience Platform Identity Service].

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
>Debe desarrollar mediante programación el código que proporciona los valores de ID para las claves `d_dpuuid` y `d_dpid` .

### Pasar ID después de [!UICONTROL DIL] instancias

>[!NOTE]
>
>Si realiza una llamada [!DNL API] con una combinación `declaredID` diferente, la nueva combinación solo se utilizará para esa llamada. Las llamadas de evento normales adicionales utilizarán la combinación original `DIL.create` `declaredID`.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Ejemplos de solicitud/respuesta {#request-response-examples}

La solicitud envía un proveedor de datos y un ID de usuario a [!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

La respuesta devuelve el ID de Audience Manager (por ejemplo, `UUID`) que se escribe en una cookie de origen en el dominio de la página.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## No dirigir ni excluir llamadas {#do-not-target}

El proceso [!UICONTROL declared ID] respeta las preferencias de los visitantes del sitio de excluirse de la segmentación [!DNL Audience Manager] por parte del sitio web. Cuando [!DNL Audience Manager] recibe una solicitud de exclusión, el [!DNL DCS] devuelve un objeto [!DNL JSON] vacío en lugar del ID de usuario [!DNL Audience Manager].

>[!MORELIKETHIS]
>
>* [CID sustituye DPID y DPUUID](../reference/cid.md)

