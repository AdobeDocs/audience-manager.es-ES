---
description: Cómo funcionan los ID declarados, configurar procedimientos, ejemplos de código y variables.
keywords: sincronización de id
seo-description: How declared IDs work, set up procedures, code examples, and variables.
seo-title: Declared IDs
solution: Audience Manager
title: ID declarados
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 9%

---

# [!UICONTROL Declared IDs] {#declared-ids}

Cómo [!UICONTROL declared IDs] trabajar, configurar procedimientos, ejemplos de código y variables.

## [!UICONTROL Declared ID] Objetivo {#declared-id-targeting}

Intercambio y sincronización de ID de usuario con [!DNL Audience Manager] desde dispositivos o exploradores que no utilizan o aceptan mecanismos de almacenamiento persistentes, como los de terceros [!DNL cookies].

## Finalidad de [!UICONTROL Declared ID] Segmentación {#declared-id-targeting-purpose}

Algunos exploradores, y la mayoría de los dispositivos móviles, no aceptan cookies de terceros [!DNL cookies]. Esto dificulta la retención de información sobre los visitantes del sitio o la asignación de ID persistentes. Para resolver este problema, [!DNL Audience Manager] utiliza [!UICONTROL DIL] para permitirle pasar [!UICONTROL declared IDs] en una llamada de evento. Además, una [!UICONTROL declared ID] puede actuar como un ID universal que se aplique al mismo usuario en todas las soluciones de [!DNL Experience Cloud]. En la tabla siguiente se describe el proceso de segmentación/coincidencia de ID:

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
   <td colname="col2"> <p>Para trabajar, necesita <span class="wintitle"> DIL </span> y el <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Servicio de identidad de Adobe Experience Platform </a> código de la página. <span class="wintitle"> DIL </span> obtiene <span class="wintitle"> ID declarados </span> desde el <code> setVisitorID </code> función proporcionada por el <span class="keyword"> Servicio de identidad de Adobe Experience Platform </span> y se lo pasa a <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de coincidencia</b> </td> 
   <td colname="col2"> <p>El Audience Manager intenta hacer coincidir el ID de cliente y el ID de visitante con un ID correspondiente en nuestro sistema. Si no existe ningún ID coincidente, Audience Manager crea un nuevo ID y lo asocia al ID de cliente y al ID de visitante. </p> <p> <p>Nota: Se utilizará la asignación más reciente si el ID se asigna a más de un ID de Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Identificador de devolución</b> </td> 
   <td colname="col2"> <p>El Audience Manager escribe su ID sincronizado en una cookie de origen (u otro espacio de almacenamiento direccionable) en el dominio o la aplicación del cliente. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Llamadas de evento posteriores</b> </td>
   <td colname="col2"> <p>Las llamadas de evento adicionales leen el ID de Audience Manager del dominio del cliente y lo envían al Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Para empezar, debe configurar la variable [!DNL Experience Cloud] Servicio de ID y [!UICONTROL DIL] en las páginas del sitio que desee utilizar para la recopilación de datos. Consulte [DIL crear](../dil/dil-class-overview/dil-create.md#dil-create) y [Variables de ID declaradas](../features/declared-ids.md#declared-id-variables).

## Llamadas de exclusión {#opt-out-calls}

El [!UICONTROL declared ID] el proceso respeta las preferencias de los visitantes del sitio para desactivar [!DNL Audience Manager] segmentación por su sitio web. Cuándo [!DNL Audience Manager] recibe una solicitud de exclusión, la variable [!DNL JSON] devuelto por el [!DNL DCS] contiene el código de error 171, con el mensaje `Encountered opt out tag`, en lugar del [!DNL Audience Manager] ID de usuario.

* [!DNL Audience Manager] puede pasar un [!UICONTROL declared ID] exclusión junto con un [!DNL Audience Manager] [!UICONTROL UUID] en el [!DNL URL].
* El [!UICONTROL declared ID] la exclusión se almacena en el [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) en función de cada socio. No hay exclusión a nivel de plataforma mediante [!UICONTROL declared IDs]. Además, [!DNL Audience Manager] excluye al usuario de esa región en particular del perímetro de (la exclusión no se cruza con [!DNL DCS] regiones).

Consulte [Privacidad de datos](../overview/data-security-and-privacy/data-privacy.md) para obtener más información sobre la exclusión de la recopilación de datos.

## [!UICONTROL Declared ID] Ejemplos de exclusión {#opt-out-examples}

Puede hacer una [!UICONTROL declared ID] solicitudes de exclusión con el `d_cid` y `d_cid_ic` pares clave-valor. Los parámetros heredados como `d_dpid` y `d_dpuuid` siguen funcionando, pero se consideran obsoletos. Consulte [CID reemplaza DPID y DPUUID](../reference/cid.md). En los ejemplos, la *cursiva* indica un marcador de posición para una variable.

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
   <td colname="col1"> <p>Múltiple <code> d_cid </code> y <code> d_cid_ic </code> pares clave-valor. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exclusiones con [!UICONTROL DPID], [!UICONTROL DPUUID], y [!UICONTROL UUID] (Obsoleto)

Estos métodos siguen funcionando, pero se consideran obsoletos. Esta información se proporciona con fines heredados y de referencia. Las exclusiones heredadas incluyen:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción de exclusión (obsoleta) </th> 
   <th colname="col2" class="entry"> Ejemplo de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> solamente </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opción de exclusión de nivel de socio </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Se almacena una exclusión a nivel de socio para la última asignación de esto <code> dpid </code> + <code> dpuuid </code> AAM emparejar con un UUID de. Si no hay ninguna asignación existente anteriormente, el Audience Manager AAM comprueba si la solicitud contiene un UUID de en la cookie y, si lo tiene, la utiliza para almacenar la exclusión. De lo contrario, Audience Manager AAM genera un nuevo UUID de UUID y almacena la exclusión en él. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> y explícito <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> siempre tiene prioridad. Si la variable <code> dpid </code> + <code> dpuuid </code> AAM AAM Si la combinación se asigna a otro UUID de, la exclusión se almacena bajo el UUID de que se pasa en la solicitud ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables y sintaxis para [!UICONTROL Declared IDs] {#variables-and-syntax}

En la tabla siguiente se enumeran los pares clave-valor que pasan su [!DNL Audience Manager] ID del proveedor de datos, ID de usuario o códigos de integración, si se utilizan. Nota, *cursiva* indica un marcador de posición variable. Se han agregado espacios para facilitar la lectura.

En cada par clave-valor:

* El `=` separa la clave de sus valores relacionados.
* La no impresión [!DNL ASCII] carácter `%01` separa los valores.

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
   <td colname="col2"> <p>Contiene un ID de proveedor de datos y un ID de usuario único asociado en un único par clave-valor. <code> d_cid </code> reemplaza <code> d_dpid </code> y <code> d_dpuuid </code>, que se consideran obsoletas, pero siguen siendo compatibles. Consulte <a href="../reference/cid.md">CID reemplaza DPID y DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contiene un código de integración y un ID de usuario único asociado en un único par clave-valor. <code> d_cid_ic </code> reemplaza <code> d_dpid </code> y <code> d_dpuuid </code>, que están en desuso, pero que siguen siendo compatibles. Consulte <a href="../reference/cid.md">CID reemplaza DPID y DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Llamadas de evento de muestra {#sample-event-calls}

Dados estos pares clave-valor y su sintaxis requerida, realizaría llamadas de evento como se muestra a continuación.

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
   <td colname="col1"> <p>Múltiple <code> d_cid </code> y <code> d_cid_ic </code> pares clave-valor. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variables {#declared-id-variables}

Describe las variables de configuración utilizadas para pasar [!UICONTROL declared IDs] mediante [!UICONTROL DIL] hasta [!DNL Audience Manager.]

## [!UICONTROL DIL] utiliza el [!DNL Adobe Experience Platform Identity Service] para aprobar [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Cuando se utiliza con [Servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html), ya no es necesario que pase [!UICONTROL declared IDs] con el obsoleto `dpid` y `dpuuid` variables. En su lugar, las versiones actuales de [!UICONTROL DIL] confíe en el `visitorService` para obtener la función [!UICONTROL declared IDs] desde el `setCustomerIDs` función en la [!UICONTROL Adobe Experience Platform Identity Service]. Para obtener más información, consulte [ID de cliente y estados de autenticación](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). Usted llamaría a `visitorService` in `DIL.create` como se muestra a continuación.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

En el `namespace` par clave-valor, `MCORG` es su [!DNL Experience Cloud] ID de organización. Si no dispone de este ID, puede encontrarlo en la [!UICONTROL Administration] de la sección [!DNL Experience Cloud] panel. Necesita permisos de administrador para ver este tablero. Consulte [Administración: servicios principales](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html).

## Funciones obsoletas {#deprecated-functions}

Con las últimas versiones de [!UICONTROL DIL] (6.2+), no necesita utilizar estos pares clave-valor para pasar [!UICONTROL declared IDs]. Eso es porque [!UICONTROL DIL] ahora se basa en `visitorService` función que se muestra en el ejemplo de código anterior. Esta función obtiene [!UICONTROL declared IDs] desde el [!UICONTROL Adobe Experience Platform Identity Service]. Sin embargo, aquí hacemos referencia a estas variables con fines históricos y heredados. Consulte el siguiente código para ver un ejemplo de cómo configurar `DIL.create` para obtener una [!UICONTROL declared ID] desde el [!UICONTROL Visitor ID Service].
En la tabla siguiente se describen las variables heredadas que utiliza la variable `declaredId` objeto:

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

[!DNL Audience Manager] compara y hace coincidir el combinado de `DPID` y `DPUUID` a un ID de usuario correspondiente en nuestro sistema. Si no existe ningún ID, [!DNL Audience Manager] crea un nuevo ID de usuario y lo sincroniza con el `DPID/DPUUID` combinación. Una [!DNL Audience Manager] coincide o crea un ID de usuario (el `UUID`) devuelve ese ID en el [!DNL JSON] respuesta a la [!DNL cookie] en el dominio del cliente (de origen) [!DNL cookie]) u otro almacenamiento local.

Llame a esta función cuando esté utilizando [!UICONTROL DIL] v6.1 o anterior. Sin embargo, esta función ha quedado obsoleta en favor de la nueva versión que obtiene [!UICONTROL declared IDs] desde el [!DNL Adobe Experience Platform Identity Service].

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
>Debe desarrollar mediante programación el código que proporciona los valores de ID para `d_dpuuid` y `d_dpid` llaves.

### Pasar ID después de [!UICONTROL DIL] Instanciados

>[!NOTE]
>
>Si realiza una [!DNL API] llamar con un elemento diferente `declaredID` combinación, la nueva combinación se utilizará solo para esa llamada. Las llamadas de evento regulares adicionales utilizarán el original `DIL.create`  `declaredID` combinación.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Ejemplos de solicitudes/respuestas {#request-response-examples}

La solicitud envía un proveedor de datos y un ID de usuario a [!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

La respuesta devuelve el ID del Audience Manager (por ejemplo, `UUID`), que se escribe en una cookie de origen en el dominio de página.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Llamadas de no segmentación y de exclusión {#do-not-target}

El [!UICONTROL declared ID] el proceso respeta las preferencias de los visitantes del sitio para desactivar [!DNL Audience Manager] segmentación por su sitio web. Cuándo [!DNL Audience Manager] recibe una solicitud de exclusión, la variable [!DNL DCS] devuelve un valor empty [!DNL JSON] en lugar del objeto [!DNL Audience Manager] ID de usuario.

>[!MORELIKETHIS]
>
>* [CID sustituye DPID y DPUUID](../reference/cid.md)

