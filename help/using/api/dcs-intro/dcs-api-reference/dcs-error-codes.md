---
description: Códigos de error y mensajes generados por los Servidores de recopilación de datos (DCS) enumerados en orden numérico por ID de código.
seo-description: Códigos de error y mensajes generados por los Servidores de recopilación de datos (DCS) enumerados en orden numérico por ID de código.
seo-title: Códigos de error DCS, mensajes y ejemplos
solution: Audience Manager
title: Códigos de error DCS, mensajes y ejemplos
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
translation-type: tm+mt
source-git-commit: 07fb9269f285a8662a9ce5e03d8be8b8d51df553
workflow-type: tm+mt
source-wordcount: '1533'
ht-degree: 4%

---


# Códigos de error DCS, mensajes y ejemplos {#dcs-error-codes-messages-and-examples}

Códigos de error y mensajes generados por los [!UICONTROL Data Collection Servers] ([!UICONTROL DCS]) enumerados en orden numérico por ID de código.

In the tables below, *italics* represents a variable placeholder.

## Códigos de error del sistema {#system-error-codes}

<table id="table_43F4321BEA6A4D1BBDFE2E9FB4402914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Id. de código </th> 
   <th colname="col2" class="entry"> Mensaje de error </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>0 </p> </td> 
   <td colname="col2"> <p>Error no especificado </p> </td> 
   <td colname="col3"> <p>Se trata de un error de captación global que gestiona eventos que no están cubiertos por los otros controladores de error. Solucionar este error es difícil. Puede ser causado por una variedad de acciones o eventos desconocidos. </p> <p>Si recibe este error, vuelva a intentar la solicitud <span class="wintitle"> de DCS</span> . Póngase en contacto con su representante de Adobe si el problema persiste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>No se pudo encontrar la configuración para nombredehost: <code><i>hostname</i></code> </p> </td> 
   <td colname="col3"> <p>El equipo de aprovisionamiento de socios no ha configurado el nombre de host enviado en la solicitud. Póngase en contacto con su representante de Adobe si aparece este mensaje de error. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Valor no válido <code> d_orgid</code> (no se pudo encontrar una configuración para esta identificación de organización): <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>El identificador de organización es incorrecto. </p> <p>Compruebe su ID e intente la solicitud de nuevo. Si no conoce o no tiene su identificador de organización, consulte la sección "Página de administración" en Organizaciones y vinculación <a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html" format="https" scope="external"></a> de cuentas para obtener información sobre cómo encontrarlo. </p> </td> 
  </tr>
 </tbody>
</table>

## Códigos de error de integración {#integration-error-codes}

<table id="table_EFF06FB3D045459BA7802872AF22DF79"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Id. de código </th> 
   <th colname="col2" class="entry"> Mensaje </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>100 </p> </td> 
   <td colname="col2"> <p>No se pudo recuperar el nombre de host para la solicitud </p> </td> 
   <td colname="col3"> <p>Una llamada de API no envió el encabezado HTTP del host en la solicitud. </p> <p>Añada el encabezado de host a la llamada e inténtelo de nuevo. Tenga en cuenta que la mayoría de los exploradores y clientes API lo hacen automáticamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>101 </p> </td> 
   <td colname="col2"> <p>Se pasó un identificador de Experience Cloud no válido <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>La <span class="wintitle"> llamada de DCS</span> contiene un ID de <span class="keyword"> Experience Cloud</span> no válido. </p> <p>Compruebe el par <code> d_mid=</code> clave-valor en la cadena de encabezado. Asegúrese de pasar el ID de <span class="keyword"> Experience Cloud</span> correcto e intente la solicitud de nuevo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>102 </p> </td> 
   <td colname="col2"> <p>Se pasó un identificador de aam no válido en la solicitud <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>La <span class="wintitle"> llamada de DCS</span> contiene un ID <span class="keyword"> del administrador</span> de Audiencias no válido. </p> <p>Compruebe el par <code> d_uuid=</code> clave-valor en la cadena de encabezado. Asegúrese de que está pasando el ID del administrador <span class="keyword"> de</span> Audiencias correcto e intente la solicitud de nuevo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>104 </p> </td> 
   <td colname="col2"> <p>Todas las ID de cliente no son válidas </p> </td> 
   <td colname="col3"> <p>Todos los ID de cliente de la llamada no son válidos. Compruebe sus ID e inténtelo de nuevo. </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p>109</p> </td> 
   <td colname="col2"> <p>El referente no <code>HTTP referer</code> está permitido para el socio <code>Partner ID</code> </p> </td> 
   <td colname="col3"> <p>No se permite el <code>HTTP referer</code> encabezado de la llamada para el ID del socio en la llamada. Compruebe que el <code>HTTP referer</code> encabezado es correcto.</p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>111 </p> </td> 
   <td colname="col2"> <p>Se recibió un token <span class="wintitle"> IMS</span> no válido </p> </td> 
   <td colname="col3"> <p>Se devuelve para el Administrador de Audiencias: integraciones de Adobe Destinatario. El error se produce cuando se realiza una llamada al DCS, que contiene un token IMS no válido. Es posible que el token esté mal formado, caduque o que el usuario no esté autorizado para acceder al recurso requerido. </p> </td>
  </tr>
 </tbody>
</table>

## Códigos de error de exclusión {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Id. de código </th> 
   <th colname="col2" class="entry"> Mensaje </th> 
   <th colname="col3" class="entry"> Descripción </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>Se encontró la etiqueta exclusión para id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un cliente ha optado por no recibir publicidad basada en intereses. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Cookies bloqueadas </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el explorador del usuario bloquea las cookies de terceros.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Se encontró una relación de confianza mediante <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>El usuario ha iniciado un proceso de exclusión a través de NAI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Las solicitudes de este país están bloqueadas por el socio </p> </td> 
   <td colname="col3"> <p>En función de la dirección IP, el <span class="wintitle"> DCS</span> bloquea las solicitudes de países en los que el socio ha limitado deliberadamente el tráfico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>No se permiten solicitudes de este país </p> </td> 
   <td colname="col3"> <p>Según la dirección IP, el <span class="wintitle"> DCS</span> bloquea las solicitudes de los siguientes países: </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">Cuba (CU) </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">Irán (IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">Corea del Norte (KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">Sudán (SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">Siria (SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Códigos de error de recuperación de Perfiles {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Id. de código </th> 
   <th colname="col2" class="entry"> Mensaje </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> No se pueden leer las características de la caché de perfil para la identificación: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando un perfil de usuario no se puede leer desde nuestro almacenamiento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> No se pueden leer los identificadores de dispositivo de la caché de perfil para el id. de cliente: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando no se puede recuperar el ID <a href="../../../reference/ids-in-aam.md"></a> del dispositivo para una regla de combinación de vínculos de Perfil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>No se puede leer el cliente relacionado para la identificación del dispositivo: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el ID del <a href="../../../reference/ids-in-aam.md"> cliente (UUID)</a> asociado a un ID de dispositivo no se puede recuperar para una regla de combinación autenticada por última vez desde nuestro almacenamiento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> No se puede leer el clúster de dispositivos para el identificador: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>No se pueden devolver los ID de dispositivo vinculados del mismo clúster de gráficos de dispositivos para este ID de dispositivo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>No se pudo realizar la migración porque no se pudo leer el perfil en el dispositivo principal </p> </td> 
   <td colname="col3"> <p>Si recibe este error, es posible que estemos experimentando problemas de escalabilidad con nuestro almacén de datos (<span class="wintitle"> PCS</span>). Póngase en contacto con su representante de Adobe si el problema persiste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>No se pudo realizar la migración de <code><i>ID</i></code> a <code><i>ID</i></code>, debido a un error de lectura de perfil para <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Si recibe este error, es posible que estemos experimentando problemas de escalabilidad con nuestro almacén de datos (<span class="wintitle"> PCS</span>). Póngase en contacto con su representante de Adobe si el problema persiste. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Códigos de advertencia de integración {#integration-warning-codes}

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Id. de código </th> 
   <th colname="col2" class="entry"> Mensaje </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>300 </p> </td> 
   <td colname="col2"> <p>ID de cliente no válida <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>El ID de cliente no es válido (faltan valores para el origen de datos, faltan códigos de integración, formato no válido para las fuentes de datos, ID de cliente bloqueado, ID de cliente en blanco, intento de acceso no autorizado a un origen de datos que no pertenece al socio). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Se ha superado el número máximo de ID de cliente. El máximo permitido es <code><i>maximum allowed</i></code>. Encontrado es <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>El número de ID de cliente asociados a una fuente de datos entre dispositivos supera el número permitido de ID entre dispositivos por solicitud. Estos ID incluyen ID entre dispositivos, móviles o cookies. El límite está establecido actualmente en 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>Id. de cliente no autorizado <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el origen de datos de ID de cliente no es propiedad del identificador de organización actual. Si no conoce o no tiene su identificador de organización, consulte la sección "Buscar su identificador de organización" en <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organizaciones y vinculación</a> de cuentas para obtener información sobre cómo encontrarlo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>Identificación de cliente bloqueada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el ID de cliente se ha identificado como malicioso y se ha en la lista negra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>Id. de fuente de datos bloqueada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el ID de fuente de datos se ha identificado como malicioso y se ha en la lista negra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>Id. de dispositivo declarado bloqueado <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>El ID del dispositivo se ha identificado como malintencionado y se ha en la lista negra. Esto puede ocurrir cuando recibimos una cantidad extrema de solicitudes <span class="wintitle"> DCS</span> que contienen este ID de dispositivo en un corto período de tiempo. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Operación de perfil bloqueada para <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se ha bloqueado una acción de lectura y escritura porque se ha identificado un ID como malicioso y se ha en la lista negra. Consulte el código de error 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>Se descartó la identificación del cliente <code><i>ID</i></code> porque superaba el límite de ID de cliente declaradas por solicitud </p> </td> 
   <td colname="col3"> <p>Relacionado con el error 301. Este error especifica qué ID de cliente se descartó porque se superó el límite. </p> <p>Por ejemplo: si hay 12 ID de cliente declarados en la llamada de <span class="wintitle"> DCS</span> , dos de ellos se descartarán. Para transmitir cuáles se descartaron, este error aparecerá dos veces en la respuesta (una para cada ID de cliente descartado). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>Se descartó la identificación del cliente porque superaba el límite de una Área de nombres determinada. ID de Área de nombres es <code><i>ID</i></code>, ID de cliente es <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Este código de error se devuelve si hay más de 3 ID de cliente declarados para la misma Área de nombres (<code> DPID</code>) en una llamada de <span class="wintitle"> DCS</span> . </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>En esta solicitud de DCS <span class="wintitle"></span> de ejemplo, hay 4 ID declarados para la misma Área de nombres (con el código de integración uno). Se descarta uno de los ID y se devuelve el error 310. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>La solicitud contiene parámetros no válidos </p> </td> 
   <td colname="col3"> <p>El <span class="wintitle"> DCS</span> devuelve este código de error cuando al menos un parámetro de URL no está codificado correctamente. En este caso, el <span class="wintitle"> DCS</span> ignora toda la solicitud. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>En la solicitud de ejemplo anterior, la <code> %</code> secuencia se codifica incorrectamente. En consecuencia, el <span class="wintitle"> DCS</span> no lo tendrá en cuenta. </p> <p>La muestra codificada correctamente debe tener este aspecto: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>La solicitud contiene un ID de dispositivo global no válido </p> </td> 
   <td colname="col3"> <p>El <span class="wintitle">DCS</span> devuelve este código de error cuando la solicitud contiene un ID de dispositivo global no válido. DCS ignora el ID no válido y genera un error 312 junto con los errores específicos del ID no válido. Consulte Fuentes <a href="../../../features/global-data-sources.md" format="dita" scope="local">de datos</a> globales e <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">índice de ID en el Administrador</a> de Audiencias para obtener información detallada sobre los formatos de ID de publicidad de dispositivos correctos y las fuentes de datos globales correspondientes.</p>
   <p>Ejemplo de una llamada incorrecta: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Explicación: Un <span class="keyword">IDFA (DPID 20915)</span> debe ser un ID en mayúsculas. El ID proporcionado en la solicitud se escribe en minúsculas.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>El Id. de CMP no está presente en GCL</p> </td> 
   <td colname="col3"> <p>Cuando <code>gdpr=1</code> y la cadena TC de IAB se genera mediante un ID de CMP que no está presente en la versión en caché del Administrador de Audiencias de la Lista de CMP global en el momento de la evaluación, el complemento Administrador de Audiencias para TCF de IAB descarta la cadena TC de IAB y procesa la solicitud como de costumbre. La macro TCF v2.0 ${GDPR} de IAB está establecida en 0 y la macro ${GDPR_CONSENT_XXX} está vacía.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>El ID de CMP está marcado como eliminado en GCL</p> </td> 
   <td colname="col3"> <p>Cuando <code>gdpr=1</code> y la cadena TC de IAB es generada por un CMP marcado como eliminado en nuestra versión en caché de la Lista de CMP global, el complemento Administrador de Audiencias para TCF de IAB descarta la cadena TC y procesa la solicitud como de costumbre, si el tiempo de evaluación ha pasado el tiempo de eliminación de la Lista de CMP global. La macro TCF v2.0 ${GDPR} de IAB está establecida en 0 y la macro ${GDPR_CONSENT_XXX} está vacía.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>La cadena de consentimiento indica que no hay consentimiento</p> </td> 
   <td colname="col3"> <p>Cuando no se proporciona el consentimiento, el complemento Administrador de Audiencias para IAB TCF excluye al usuario de la recopilación de datos adicionales o descarta la llamada por completo si no se detecta ningún contexto de socio.</p>
   </td>
  </tr>

</tbody>
</table>

## Ejemplo de mensajes de código de error {#sample-error-codes}

El [!UICONTROL DCS] devuelve códigos de error y mensajes en un [!DNL JSON] objeto o en un encabezado X de la cadena de respuesta HTTP.

### Ejemplo de código de error DCS y mensaje

```
{ 
   "errors":[ 
      { 
         "code":101,
         "msg":"Invalid Experience Cloud id passed in"
      },
      { 
         "code":102,
         "msg":"Invalid aam id passed in request"
      }
   ]
}
```

### X-Error

Los códigos de error capturados por el encabezado X aparecen en la cadena URL como este, `X-Error: 101,102`.

[Condiciones de carrera y gestión de errores](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)