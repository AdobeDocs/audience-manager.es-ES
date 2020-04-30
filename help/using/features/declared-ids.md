---
description: Funcionamiento de los ID declarados, configuración de procedimientos, ejemplos de código y variables.
keywords: id sync
seo-description: Funcionamiento de los ID declarados, configuración de procedimientos, ejemplos de código y variables.
seo-title: ID declarados
solution: Audience Manager
title: ID declarados
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# ID declarados {#declared-ids}

Funcionamiento de los ID declarados, configuración de procedimientos, ejemplos de código y variables.

## Orientación a ID declarado {#declared-id-targeting}

Intercambie y sincronice los ID de usuario con el Administrador de Audiencias desde dispositivos o navegadores que no utilicen ni acepten mecanismos de almacenamiento persistentes, como cookies de terceros.

<!-- declared_id_about.xml -->

## Objetivo del objetivo de ID declarado {#declared-id-targeting-purpose}

Algunos exploradores y la mayoría de los dispositivos móviles no aceptan cookies de terceros. Esto dificulta la retención de información sobre visitantes del sitio o la asignación de ID persistentes. Para resolver este problema, el Administrador de Audiencias utiliza [!UICONTROL DIL] para permitirle pasar [!UICONTROL declared IDs] una llamada de evento. Además, un [!UICONTROL declared ID] puede actuar como ID universal que se aplica al mismo usuario en todas las soluciones del [!DNL Experience Cloud]. En la tabla siguiente se describe el proceso de coincidencia/establecimiento de objetivos de ID:

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Proceso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Llamada de Evento</b> </td> 
   <td colname="col2"> <p>Para trabajar, necesita <span class="wintitle"> DIL </span> y el código del servicio de identidad de la plataforma de <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> experiencia de Adobe </a> en la página. <span class="wintitle"> DIL </span> obtiene los ID <span class="wintitle"> declarados </span> de la <code> setVisitorID </code> función proporcionada por el servicio de identidad de la plataforma de experiencia de <span class="keyword"> Adobe </span> y los pasa al administrador <span class="keyword"> de Audiencias </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Id. de coincidencia</b> </td> 
   <td colname="col2"> <p>El Administrador de Audiencias intenta hacer coincidir el ID de cliente y de visitante con un ID correspondiente en nuestro sistema. Si no existe un ID coincidente, el Administrador de Audiencias crea un nuevo ID y lo asocia al ID de cliente y de visitante. </p> <p> <p>Nota:  La asignación más reciente se utiliza si su ID se asigna a más de un ID del Administrador de Audiencias. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de devolución</b> </td> 
   <td colname="col2"> <p>El Administrador de Audiencias escribe su ID sincronizada en una cookie de origen (u otro espacio de almacenamiento direccionable) en el dominio o la aplicación cliente. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Llamadas de Evento subsiguientes</b> </td>
   <td colname="col2"> <p>Las llamadas de evento adicionales leen el ID del Administrador de Audiencias del dominio del cliente y lo envían al Administrador de Audiencias. </p> </td>
  </tr> 
 </tbody>
</table>

Para comenzar, debe configurar el servicio de [!DNL Experience Cloud] ID y [!UICONTROL DIL] las páginas del sitio que desee utilizar para la recopilación de datos. Consulte [DIL crear](../dil/dil-class-overview/dil-create.md#dil-create) y [declarar variables](../features/declared-ids.md#declared-id-variables)de ID.

## Llamadas de exclusión {#opt-out-calls}

El [!UICONTROL declared ID] proceso respeta las preferencias de visitante del sitio para la exclusión de la segmentación del Administrador de Audiencias por parte del sitio web. Cuando el Administrador de Audiencias recibe una solicitud de exclusión, el [!DNL JSON] que devuelve el [!UICONTROL DCS] contiene el código de error 171, con el mensaje &quot;Se encontró la etiqueta exclusión&quot;, en lugar del ID de usuario del Administrador de Audiencias.

* El Administrador de Audiencias puede pasar una [!UICONTROL declared ID] exclusión junto con un Administrador de Audiencias [!UICONTROL UUID] en la [!DNL URL].
* La [!UICONTROL declared ID] exclusión se almacena en el servidor de caché de Perfil de [!UICONTROL ([!UICONTROL PCS]) por socio. No hay ninguna opción de exclusión a nivel de plataforma que utilice [!UICONTROL declared IDs]. Además, el Administrador de Audiencias excluye al usuario de esa región concreta del borde (la exclusión no cruza [!UICONTROL DCS] las regiones).

Consulte Privacidad [de](../overview/data-security-and-privacy/data-privacy.md) datos para obtener más información sobre la exclusión de la recopilación de datos.

## Ejemplos de exclusión de ID declarados {#opt-out-examples}

Puede realizar solicitudes de [!UICONTROL declared ID] exclusión con los pares `d_cid` y `d_cid_ic` clave-valor. Los parámetros heredados como `d_dpid` y `d_dpuuid` siguen funcionando, pero se consideran obsoletos. Consulte [CID sustituye DPID y DPUUID](../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

### Opciones de exclusión con CID y CID_IC

Para obtener una descripción y sintaxis, consulte Variables [URL y Sintaxis de ID declarados](../features/declared-ids.md#variables-and-syntax).

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

### Opciones de exclusión con DPID, DPUUID y UUID (obsoleto)

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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Se almacena una exclusión a nivel de socio para la asignación más reciente de este <code> dpid </code> + <code> dpuuid </code> par a un UUID de AAM. Si no hay ninguna asignación anterior, el Administrador de Audiencias comprueba si la solicitud contiene un UUID de AAM en la cookie y, si lo hace, lo utiliza para almacenar la exclusión. De lo contrario, el Administrador de Audiencias genera un nuevo UUID de AAM y almacena la exclusión en él. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> y explícito <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> siempre tiene prioridad. Si la combinación <code> dpid </code> + <code> dpuuid </code> se asigna a otro UUID de AAM, la exclusión se almacena bajo el UUID de AAM pasado en la solicitud ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables y sintaxis para ID declarados {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

La siguiente tabla lista los pares de clave-valor que pasan el ID del proveedor de datos y los ID de usuario o los códigos de integración, si se utilizan. [!DNL Audience Manager] Note, *italics* indicates a variable placeholder. Se han agregado espacios para facilitar su lectura.

En cada par clave-valor:

* El `=` símbolo separa la clave de sus valores relacionados.
* El carácter no imprimible [!DNL ASCII] `%01` separa los valores.

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
   <td colname="col2"> <p>Contiene un ID de proveedor de datos y un ID de usuario único asociado en un solo par clave-valor. <code> d_cid </code> reemplaza <code> d_dpid </code> y <code> d_dpuuid </code>, que se consideran obsoletos, pero que siguen siendo compatibles. Consulte <a href="../reference/cid.md">CID sustituye DPID y DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contiene un código de integración y un ID de usuario único asociado en un solo par clave-valor. <code> d_cid_ic </code> reemplaza <code> d_dpid </code> y <code> d_dpuuid </code>, que están en desuso, pero que aún son compatibles. Consulte <a href="../reference/cid.md">CID sustituye DPID y DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplo de llamadas de Evento {#sample-event-calls}

Dados estos pares de clave-valor y su sintaxis requerida, haría llamadas de evento como se muestra a continuación.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> La llamada de Evento incluye </th> 
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

## Variables de ID declaradas {#declared-id-variables}

Describe las variables de configuración utilizadas para pasar ID declarados [!UICONTROL DIL] a [!DNL Audience Manager.]

## DIL utiliza el servicio de identidad de Adobe Experience Platform para pasar ID declarados {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

Cuando se utiliza con [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), ya no es necesario pasar [!UICONTROL declared IDs] con las variables `dpid` y `dpuuid` obsoletas. En su lugar, las versiones actuales de [!UICONTROL DIL] confían en la `visitorService` función para obtener el [!UICONTROL declared IDs] resultado de la `setCustomerIDs` función en la [!UICONTROL Adobe Experience Platform Identity Service]. Para obtener más información, consulte ID [de cliente y estados](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)de autenticación. Llamaría `visitorService` a `DIL.create` como se muestra a continuación.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

En el par `namespace` clave-valor, `MCORG` es su identificador [!DNL Experience Cloud] de organización. Si no tiene este ID, puede encontrarlo en la [!UICONTROL Administration] sección del [!DNL Experience Cloud] panel. Necesita permisos de administrador para vista de este panel. See [Administration: Core Services](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## Funciones obsoletas {#deprecated-functions}

Con las últimas versiones de [!UICONTROL DIL] (6.2 o posterior), no es necesario utilizar estos pares de clave-valor para pasar [!UICONTROL declared IDs]. Esto se debe a que [!UICONTROL DIL] ahora depende de la `visitorService` función mostrada en el ejemplo de código anterior. Esta función se obtiene [!UICONTROL declared IDs] de la [!UICONTROL Adobe Experience Platform Identity Service]. Sin embargo, aquí estamos haciendo referencia a estas variables con fines históricos y heredados. Consulte el código siguiente para ver un ejemplo de cómo configurar `DIL.create` para obtener un [!UICONTROL declared ID] de [!UICONTROL Visitor ID Service].
En la tabla siguiente se describen las variables heredadas utilizadas por el `declaredId` objeto:

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
   <td colname="col3"> <p>ID del socio de datos asignado por el Administrador de Audiencias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Cadena </td> 
   <td colname="col3"> <p>El ID exclusivo de proveedor de datos para el usuario. </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPID` y `DPUUID`

El Administrador de Audiencias compara y hace coincidir el ID de usuario combinado `DPID` y `DPUUID` con el ID de usuario correspondiente de nuestro sistema. Si no existe un ID, el Administrador de Audiencias crea un nuevo ID de usuario y lo sincroniza con la `DPID/DPUUID` combinación. Una vez que el Administrador de Audiencias coincide o crea un ID de usuario (el `UUID`), devuelve ese ID en la [!DNL JSON] respuesta a la cookie en el dominio del cliente (cookie de origen) u otro almacenamiento local.

Llame a esta función cuando esté utilizando [!UICONTROL DIL] v6.1 o una versión anterior. Sin embargo, esta función se ha desaprobado en favor de la nueva versión que se obtiene [!UICONTROL declared IDs] de la [!UICONTROL Adobe Experience Platform Identity Service].

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
>Tenga en cuenta que debe desarrollar mediante programación el código que proporciona los valores de ID para las `d_dpuuid` claves y `d_dpid` .

### Pasar ID después de crear instancias de DIL

>[!NOTE]
>
>Si realiza una [!DNL API] llamada con una `declaredID` combinación diferente, la nueva combinación se utilizará solamente para esa llamada. Las llamadas de evento regulares adicionales utilizarán la `DIL.create` combinación original `declaredID` .

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Ejemplos de solicitud/respuesta {#request-response-examples}

La solicitud envía un proveedor de datos y un ID de usuario al Administrador de Audiencias:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

La respuesta devuelve la ID del Administrador de Audiencias (por ejemplo, `UUID`) que se escribe en una cookie de origen en el dominio de la página.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## No realizar Destinatarios ni llamadas de exclusión {#do-not-target}

El [!UICONTROL declared ID] proceso respeta las preferencias de visitante del sitio para la exclusión de la segmentación del Administrador de Audiencias por parte del sitio web. Cuando el Administrador de Audiencias recibe una solicitud de exclusión, el [!UICONTROL DCS] devuelve un [!DNL JSON] objeto vacío en lugar del ID de usuario del Administrador de Audiencias.

>[!MORELIKETHIS]
>
>* [CID sustituye DPID y DPUUID](../reference/cid.md)

