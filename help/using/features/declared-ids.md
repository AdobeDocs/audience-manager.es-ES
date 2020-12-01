---
description: Funcionamiento de los ID declarados, configuración de procedimientos, ejemplos de código y variables.
keywords: id sync
seo-description: Funcionamiento de los ID declarados, configuración de procedimientos, ejemplos de código y variables.
seo-title: ID declarados
solution: Audience Manager
title: ID declarados
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
translation-type: tm+mt
source-git-commit: 29708d5fc528ac9da08f4c5a7f2bcaa11b240d8b
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 10%

---


# [!UICONTROL Declared IDs] {#declared-ids}

Cómo [!UICONTROL declared IDs] funciona, configura procedimientos, ejemplos de código y variables.

## [!UICONTROL Declared ID] Segmentación {#declared-id-targeting}

Intercambie y sincronice los ID de usuario con [!DNL Audience Manager] desde dispositivos o exploradores que no utilicen ni acepten mecanismos de almacenamiento persistentes, como [!DNL cookies] de terceros.

## Objetivo de [!UICONTROL Declared ID] objetivo {#declared-id-targeting-purpose}

Algunos exploradores y la mayoría de los dispositivos móviles no aceptan [!DNL cookies] de terceros. Esto dificulta la retención de información sobre visitantes del sitio o la asignación de ID persistentes. Para resolver este problema, [!DNL Audience Manager] utiliza [!UICONTROL DIL] para permitirle pasar [!UICONTROL declared IDs] en una llamada de evento. Además, un [!UICONTROL declared ID] puede actuar como ID universal que se aplica al mismo usuario en todas las soluciones del [!DNL Experience Cloud]. En la tabla siguiente se describe el proceso de coincidencia/establecimiento de objetivos de ID:

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
   <td colname="col2"> <p>Para trabajar, necesita <span class="wintitle"> DIL </span> y el código <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> del servicio de identidad de Adobe Experience Platform </a> en la página. <span class="wintitle"> DIL  </span> obtiene los ID  <span class="wintitle"> declarados  </span> de la  <code> setVisitorID </code> función proporcionada por el servicio de identidad de  <span class="keyword"> Adobe Experience Platform  </span> y los pasa al  <span class="keyword"> Audience Manager  </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Id. de coincidencia</b> </td> 
   <td colname="col2"> <p>El Audience Manager intenta hacer coincidir el ID de cliente y de visitante con un ID correspondiente en nuestro sistema. Si no existe un ID coincidente, Audience Manager crea un nuevo ID y lo asocia con el ID de cliente y de visitante. </p> <p> <p>Nota:  La asignación más reciente se utiliza si su ID se asigna a más de un ID de Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de devolución</b> </td> 
   <td colname="col2"> <p>Audience Manager escribe su ID sincronizada en una cookie de origen (u otro espacio de almacenamiento direccionable) en el dominio o la aplicación cliente. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Llamadas de Evento subsiguientes</b> </td>
   <td colname="col2"> <p>Las llamadas de evento adicionales leen el ID de Audience Manager del dominio del cliente y lo envían al Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Para comenzar, debe configurar el [!DNL Experience Cloud] servicio de ID y [!UICONTROL DIL] en las páginas del sitio que desee utilizar para la recopilación de datos. Consulte [Creación de DIL](../dil/dil-class-overview/dil-create.md#dil-create) y [Variables de ID declaradas](../features/declared-ids.md#declared-id-variables).

## Llamadas de exclusión {#opt-out-calls}

El proceso [!UICONTROL declared ID] respeta las preferencias de visitante del sitio para la exclusión de la segmentación [!DNL Audience Manager] por parte del sitio Web. Cuando [!DNL Audience Manager] recibe una solicitud de exclusión, el [!DNL JSON] devuelto por el [!DNL DCS] contiene el código de error 171, con el mensaje `Encountered opt out tag`, en lugar del [!DNL Audience Manager] identificador de usuario.

* [!DNL Audience Manager] puede pasar una  [!UICONTROL declared ID] opción de exclusión junto con una  [!DNL Audience Manager] [!UICONTROL UUID] en la  [!DNL URL].
* La opción de exclusión [!UICONTROL declared ID] se almacena en [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) por socio. No existe ninguna exclusión a nivel de plataforma mediante [!UICONTROL declared IDs]. Además, [!DNL Audience Manager] excluye al usuario de esa región concreta del borde (la exclusión no cruza [!DNL DCS] regiones).

Consulte [Privacidad de datos](../overview/data-security-and-privacy/data-privacy.md) para obtener más información sobre la exclusión de la recopilación de datos.

## [!UICONTROL Declared ID] Ejemplos de exclusión  {#opt-out-examples}

Puede realizar una solicitud de exclusión [!UICONTROL declared ID] con los pares de valor clave `d_cid` y `d_cid_ic`. Los parámetros heredados como `d_dpid` y `d_dpuuid` siguen funcionando, pero se consideran obsoletos. Consulte [CID reemplaza DPID y DPUUID](../reference/cid.md). En los ejemplos, la *cursiva* indica un marcador de posición para una variable.

### Opciones de exclusión con [!UICONTROL CID] y [!UICONTROL CID_IC]

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
   <td colname="col1"> <p>Varios pares <code> d_cid </code> y <code> d_cid_ic </code> clave-valor. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opciones de exclusión con [!UICONTROL DPID], [!UICONTROL DPUUID] y [!UICONTROL UUID] (obsoleto)

Estos métodos siguen funcionando pero se consideran obsoletos. Esta información se proporciona con fines y referencias heredados. Las exclusiones heredadas incluyen:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción de exclusión (desaprobada) </th> 
   <th colname="col2" class="entry"> Ejemplo de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> solamente </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opción de exclusión a nivel de socio </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Se almacena una exclusión a nivel de socio para la última asignación de este par <code> dpid </code> + <code> dpuuid </code> a un UUID de AAM. Si no hay ninguna asignación anterior, el Audience Manager comprueba si la solicitud contiene un UUID de AAM en la cookie y, si lo hace, lo utiliza para almacenar la exclusión. De lo contrario, Audience Manager genera un UUID de AAM nuevo y almacena la exclusión en él. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> +  <code> d_dpid </code> y explícito  <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> siempre tiene prioridad. Si la combinación <code> dpid </code> + <code> dpuuid </code> se asigna a otro UUID de AAM, la exclusión se almacena bajo el UUID de AAM pasado en la solicitud ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables y sintaxis para [!UICONTROL Declared IDs] {#variables-and-syntax}

La siguiente tabla lista los pares de clave-valor que pasan el ID de proveedor de datos [!DNL Audience Manager] y los ID de usuario o los códigos de integración, si se utilizan. Nota: *cursiva* indica un marcador de posición de variable. Se han agregado espacios para facilitar su lectura.

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
   <td colname="col2"> <p>Contiene un ID de proveedor de datos y un ID de usuario único asociado en un solo par clave-valor. <code> d_cid </code> reemplaza  <code> d_dpid </code> y  <code> d_dpuuid </code>, que se consideran obsoletos, pero que siguen siendo compatibles. Consulte <a href="../reference/cid.md">CID reemplaza DPID y DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contiene un código de integración y un ID de usuario único asociado en un solo par clave-valor. <code> d_cid_ic </code> reemplaza  <code> d_dpid </code> y  <code> d_dpuuid </code>, que están en desuso, pero que aún son compatibles. Consulte <a href="../reference/cid.md">CID reemplaza DPID y DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Llamadas de Evento de muestra {#sample-event-calls}

Dados estos pares de clave-valor y su sintaxis requerida, haría llamadas de evento como se muestra a continuación.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> La llamada de evento incluye </th> 
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
   <td colname="col1"> <p>Varios pares <code> d_cid </code> y <code> d_cid_ic </code> clave-valor. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variables {#declared-id-variables}

Describe las variables de configuración utilizadas para pasar [!UICONTROL declared IDs] a [!UICONTROL DIL] a [!DNL Audience Manager.]

## [!UICONTROL DIL] utiliza la opción  [!DNL Adobe Experience Platform Identity Service] para pasar  [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Cuando se utiliza con el [servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html), ya no es necesario pasar [!UICONTROL declared IDs] con las variables `dpid` y `dpuuid` obsoletas. En su lugar, las versiones actuales de [!UICONTROL DIL] dependen de la función `visitorService` para obtener [!UICONTROL declared IDs] de la función `setCustomerIDs` en [!UICONTROL Adobe Experience Platform Identity Service]. Para obtener más información, consulte [ID de cliente y estados de autenticación](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). Debe llamar a `visitorService` en `DIL.create` como se muestra a continuación.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

En el par `namespace` clave-valor, `MCORG` es su identificador de organización [!DNL Experience Cloud]. Si no tiene este ID, puede encontrarlo en la sección [!UICONTROL Administration] del panel [!DNL Experience Cloud]. Necesita permisos de administrador para vista de este panel. Consulte [Administración: Servicios principales](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## Funciones obsoletas {#deprecated-functions}

Con las últimas versiones de [!UICONTROL DIL] (6.2+), no necesita utilizar estos pares clave-valor para pasar [!UICONTROL declared IDs]. Esto se debe a que [!UICONTROL DIL] ahora depende de la función `visitorService` que se muestra en el ejemplo de código anterior. Esta función obtiene [!UICONTROL declared IDs] del [!UICONTROL Adobe Experience Platform Identity Service]. Sin embargo, aquí estamos haciendo referencia a estas variables con fines históricos y heredados. Consulte el código siguiente para ver un ejemplo de cómo configurar `DIL.create` para obtener un [!UICONTROL declared ID] de [!UICONTROL Visitor ID Service].
La siguiente tabla describe las variables heredadas utilizadas por el objeto `declaredId`:

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
   <td colname="col3"> <p>El ID exclusivo de proveedor de datos para el usuario. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] y [!UICONTROL DPUUID]

[!DNL Audience Manager] compara y hace coincidir el ID de usuario combinado  `DPID` y  `DPUUID` con el ID de usuario correspondiente de nuestro sistema. Si no existe un ID, [!DNL Audience Manager] crea un nuevo ID de usuario y lo sincroniza con la combinación `DPID/DPUUID`. Una vez que [!DNL Audience Manager] coincide o crea un ID de usuario (el `UUID`), devuelve ese ID en la respuesta [!DNL JSON] al [!DNL cookie] en el dominio del cliente (origen [!DNL cookie]) u otro almacenamiento local.

Llame a esta función cuando esté utilizando [!UICONTROL DIL] v6.1 o anterior. Sin embargo, esta función se ha desaprobado en favor de la nueva versión que obtiene [!UICONTROL declared IDs] de [!DNL Adobe Experience Platform Identity Service].

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
>Debe desarrollar mediante programación el código que proporciona los valores de ID para las claves `d_dpuuid` y `d_dpid`.

### Pasar ID después de [!UICONTROL DIL] instancias

>[!NOTE]
>
>Si realiza una llamada [!DNL API] con una combinación `declaredID` diferente, la nueva combinación se utilizará sólo para esa llamada. Otras llamadas de evento regulares utilizarán la combinación `DIL.create` `declaredID` original.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Ejemplos de solicitud/respuesta {#request-response-examples}

La solicitud envía un proveedor de datos y un identificador de usuario a [!DNL Audience Manager]:

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

## No Destinatario ni llamadas de exclusión {#do-not-target}

El proceso [!UICONTROL declared ID] respeta las preferencias de visitante del sitio para la exclusión de la segmentación [!DNL Audience Manager] por parte del sitio Web. Cuando [!DNL Audience Manager] recibe una solicitud de exclusión, el [!DNL DCS] devuelve un objeto [!DNL JSON] vacío en lugar del identificador de usuario [!DNL Audience Manager].

>[!MORELIKETHIS]
>
>* [CID sustituye DPID y DPUUID](../reference/cid.md)

