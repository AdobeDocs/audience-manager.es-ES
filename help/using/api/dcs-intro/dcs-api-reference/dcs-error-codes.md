---
description: Códigos de error y mensajes generados por los servidores de recopilación de datos (DCS) enumerados en orden numérico por ID de código.
seo-description: Códigos de error y mensajes generados por los servidores de recopilación de datos (DCS) enumerados en orden numérico por ID de código.
seo-title: Códigos de error DCS, mensajes y ejemplos
solution: Audience Manager
title: Códigos de error DCS, mensajes y ejemplos
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 1be86de9322df6b764ee3870fa82ddb2bb8b06ec
workflow-type: tm+mt
source-wordcount: '1540'
ht-degree: 4%

---

# Códigos de error DCS, mensajes y ejemplos {#dcs-error-codes-messages-and-examples}

Códigos de error y mensajes generados por el [!UICONTROL Data Collection Servers] ([!DNL DCS]) enumerados en orden numérico por ID de código.

En las tablas siguientes, *cursiva* representa un marcador de posición de variable.

## Códigos de error del sistema {#system-error-codes}

| Código de error | Mensaje de error | Descripción |
|---|---|---|
| 0 | Error no especificado | Se trata de un error de captador global que gestiona eventos que no están cubiertos por los otros controladores de errores. Solucionar este error es difícil. Puede ser causado por una variedad de acciones o eventos desconocidos. Si recibe este error, vuelva a intentar la solicitud [!DNL DCS]. Póngase en contacto con su representante de [!DNL Adobe] si el problema persiste. |
| 1 | No se encontró la configuración para el nombre de host: `hostname` | El nombre de host enviado en la solicitud no ha sido configurado por nuestro equipo de aprovisionamiento de socios. Póngase en contacto con su representante de [!DNL Adobe] si ve este mensaje de error. |
| 2 | Valor `d_orgid` no válido (no se pudo encontrar una configuración para este id de organización): `ID` | El ID de organización es incorrecto. Compruebe su ID e intente la solicitud de nuevo. Si no conoce o no tiene su ID de organización, consulte la sección &quot;Página de administración&quot; [Organizaciones y vinculación de cuentas](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html) para obtener información sobre cómo encontrarla. |
| 10 | No se pueden evaluar los rasgos | Los rasgos de la solicitud se evaluaron parcialmente o no se evaluaron en absoluto. |

## Códigos de error de integración {#integration-error-codes}

| Código de error | Mensaje de error | Descripción |
|---|---|---|
| 100 | No se pudo recuperar el nombre de host para la solicitud | Una llamada [!DNL API] no envió el encabezado [!DNL HTTP] del host en la solicitud. Agregue el encabezado host a la llamada e inténtelo de nuevo. La mayoría de los exploradores y clientes [!DNL API] lo hacen automáticamente. |
| 101 | Id. [!DNL Experience Cloud] no válido pasado en `ID` | La llamada [!DNL DCS] contiene un ID [!DNL Experience Cloud] no válido. Compruebe el par clave-valor `d_mid=` en la cadena de encabezado. Asegúrese de que está pasando el ID [!DNL Experience Cloud] correcto e intente la solicitud de nuevo. |
| 102 | [!DNL AAM ID] no válido pasado en la solicitud `ID` | La llamada [!DNL DCS] contiene un ID [!DNL Audience Manager] no válido. Compruebe el par clave-valor `d_uuid=` en la cadena de encabezado. Asegúrese de que está pasando el ID [!DNL Audience Manager] correcto e intente la solicitud de nuevo. |
| 104 | Todos los ID de cliente no son válidos | Todos los ID de cliente de la llamada de no son válidos. Compruebe sus ID e inténtelo de nuevo. |
| 109 | No se permite el referente `HTTP referer` para el socio `Partner ID` | El encabezado `HTTP referer` de la llamada no está permitido para el ID de socio en la llamada. Compruebe que el encabezado `HTTP referer` sea correcto. |
| 111 | Se recibió un token `IMS` no válido | Se devuelve para integraciones [!DNL Audience Manager] - [!DNL Adobe Target]. El error se produce cuando se realiza una llamada a [!DNL DCS], que contiene un token [!DNL IMS] no válido. Es posible que el token esté mal formado, que haya caducado o que el usuario no esté autorizado a acceder al recurso requerido. |

## Códigos de error de exclusión {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de código </th> 
   <th colname="col2" class="entry"> Mensaje </th> 
   <th colname="col3" class="entry"> Descripción </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>Se ha encontrado la etiqueta de exclusión para el id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un cliente ha optado por no recibir publicidad basada en intereses. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Cookies bloqueadas </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el explorador del usuario bloquea las cookies de terceros.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Se encontró una relación de confianza a través de <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>El usuario ha iniciado un proceso de exclusión a través de NAI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Las solicitudes de este país están bloqueadas por un socio </p> </td> 
   <td colname="col3"> <p>En función de la dirección IP, el <span class="wintitle"> DCS</span> bloquea las solicitudes de los países en los que el socio ha limitado deliberadamente el tráfico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>No se permiten solicitudes de este país </p> </td> 
   <td colname="col3"> <p>En función de la dirección IP, el <span class="wintitle"> DCS</span> bloquea las solicitudes de los siguientes países: </p> <p> 
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

## Códigos de error de recuperación de perfil {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de código </th> 
   <th colname="col2" class="entry"> Mensaje </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> No se pueden leer los rasgos de la caché de perfiles para el id: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando un perfil de usuario no se puede leer desde nuestro almacenamiento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> No se pueden leer los id de dispositivo de la caché de perfiles para el id de cliente: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el <a href="../../../reference/ids-in-aam.md"> ID de dispositivo</a> no se puede recuperar para una regla de combinación de vínculos de perfil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>No se puede leer el cliente relacionado para el id de dispositivo: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el <a href="../../../reference/ids-in-aam.md"> ID de cliente (UUID)</a> asociado a un ID de dispositivo no se puede recuperar para una última regla de combinación autenticada de nuestro almacenamiento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> No se puede leer el clúster de dispositivos para el id: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>No se pueden devolver los ID de dispositivo vinculados del mismo clúster de gráficos de dispositivos para este ID de dispositivo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>No se pudo realizar la migración porque no se pudo leer el perfil en el dispositivo principal </p> </td> 
   <td colname="col3"> <p>Si recibe este error, es posible que tengamos problemas de escalabilidad con nuestro almacén de datos (<span class="wintitle"> PCS</span>). Si el problema persiste, póngase en contacto con el representante del Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>No se pudo realizar la migración de <code><i>ID</i></code> a <code><i>ID</i></code> porque la lectura del perfil falló para <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Si recibe este error, es posible que tengamos problemas de escalabilidad con nuestro almacén de datos (<span class="wintitle"> PCS</span>). Si el problema persiste, póngase en contacto con el representante del Adobe. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Códigos de advertencia de integración {#integration-warning-codes}

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de código </th> 
   <th colname="col2" class="entry"> Mensaje </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>300 </p> </td> 
   <td colname="col2"> <p>Id. de cliente no válido <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>El ID de cliente no es válido (faltan valores para la fuente de datos, faltan códigos de integración, formato no válido para las fuentes de datos, ID de cliente bloqueado, ID de cliente en blanco, intento de acceso no autorizado a una fuente de datos que no pertenece al socio). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Se ha superado el número máximo de id de cliente. El máximo permitido es <code><i>maximum allowed</i></code>. Encontrado es <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>El número de ID de cliente asociados a una fuente de datos entre dispositivos supera el número permitido de ID entre dispositivos por solicitud. Estos ID incluyen entre dispositivos, móviles o ID de cookies. El límite está establecido actualmente en 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>ID de cliente no autorizado <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el ID de cliente no es propiedad del ID de organización actual. Si no conoce o no tiene su ID de organización, consulte la sección "Buscar su ID de organización" en <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organizaciones y vinculación de cuentas</a> para obtener información sobre cómo encontrarlo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>ID de cliente bloqueado <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el ID de cliente se ha identificado como malicioso y se ha añadido a una  de lista de bloqueados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>Id. de fuente de datos bloqueada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el ID de la fuente de datos se ha identificado como malicioso y se ha añadido a una  de lista de bloqueados </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>Id de dispositivo declarado bloqueado <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>El ID del dispositivo se ha identificado como malintencionado y se ha agregado a una  de lista de bloqueados Esto puede suceder cuando recibimos una cantidad extrema de solicitudes <span class="wintitle"> DCS</span> que contienen este ID del dispositivo en un corto periodo de tiempo. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Operación de perfil bloqueada para <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se ha bloqueado una acción de lectura y escritura porque se ha identificado un ID como malintencionado y se ha añadido a un  de lista de bloqueados Véase código de error 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>El ID de cliente <code><i>ID</i></code> se descartó porque superaba el límite de ID de cliente declarados por solicitud </p> </td> 
   <td colname="col3"> <p>Relacionado con el error 301. Este error especifica qué ID de cliente se descartó porque se superó el límite. </p> <p>Por ejemplo, si hay 12 ID de cliente declarados en la llamada <span class="wintitle"> DCS</span>, dos de ellos se descartarán. Para retransmitir los que se descartaron, este error aparecerá dos veces en la respuesta (una para cada ID de cliente descartado ). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>Se descartó el ID de cliente porque superaba el límite de un área de nombres determinada. El id de área de nombres es <code><i>ID</i></code>, el id de cliente es <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Este código de error se devuelve si hay más de 3 ID de cliente declarados para el mismo espacio de nombres (<code> DPID</code>) en una llamada <span class="wintitle"> DCS</span>. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>En esta solicitud <span class="wintitle"> DCS</span> de ejemplo, hay 4 ID declarados para el mismo espacio de nombres (con el código de integración uno). Se descarta uno de los ID y se devuelve el error 310. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>La solicitud contiene parámetros no válidos </p> </td> 
   <td colname="col3"> <p>El <span class="wintitle"> DCS</span> devuelve este código de error cuando al menos un parámetro de URL no está codificado correctamente. En este caso, el <span class="wintitle"> DCS</span> ignora toda la solicitud. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>En la solicitud de ejemplo anterior, la secuencia <code> %</code> se codifica incorrectamente. En consecuencia, el <span class="wintitle"> DCS</span> no lo tendrá en cuenta. </p> <p>La muestra codificada correctamente debe tener este aspecto: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>La solicitud contiene un ID de dispositivo global no válido </p> </td> 
   <td colname="col3"> <p>El <span class="wintitle">DCS</span> devuelve este código de error cuando la solicitud contiene un ID de dispositivo global no válido. El DCS ignora el ID no válido y genera un error 312 junto con los errores específicos del ID no válido. Consulte <a href="../../../features/global-data-sources.md" format="dita" scope="local">Fuentes de datos globales</a> e <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Índice de ID en Audience Manager</a> para obtener información detallada sobre los formatos de ID publicitarios de dispositivo correctos y las fuentes de datos globales correspondientes.</p>
   <p>Ejemplo de llamada incorrecta: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Explicación: Un <span class="keyword">IDFA (DPID 20915)</span> debe ser un ID en mayúsculas. El ID proporcionado en la solicitud se escribe en minúscula.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>El ID de CMP no está presente en GCL</p> </td> 
   <td colname="col3"> <p>Cuando <code>gdpr=1</code> y la cadena de TC de IAB se genera mediante un ID de CMP que no está presente en la versión en caché del Audience Manager de la lista de CMP global en el momento de la evaluación, el complemento Audience Manager para el TCF de IAB descarta la cadena de TC de IAB y procesa la solicitud como de costumbre. La macro TCF v2.0 ${GDPR} de IAB está establecida en 0 y la macro ${GDPR_CONSENT_XXX} está vacía.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>El ID de CMP está marcado como eliminado en GCL</p> </td> 
   <td colname="col3"> <p>Cuando <code>gdpr=1</code> y la cadena TC de IAB la genera una CMP que está marcada como eliminada en nuestra versión en caché de la lista CMP global, el complemento Audience Manager para el TCF de IAB descarta la cadena TC y procesa la solicitud como de costumbre, si el tiempo de evaluación supera el tiempo de eliminación de la lista CMP global. La macro TCF v2.0 ${GDPR} de IAB está establecida en 0 y la macro ${GDPR_CONSENT_XXX} está vacía.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>La cadena de consentimiento indica que no hay consentimiento</p> </td> 
   <td colname="col3"> <p>Cuando no se proporciona consentimiento, el complemento Audience Manager para IAB TCF excluye al usuario de una recopilación de datos adicional o la descarta completamente si no se detecta ningún contexto de socio.</p>
   </td>
  </tr>

</tbody>
</table>

## Ejemplo de mensajes de código de error {#sample-error-codes}

El [!DNL DCS] devuelve códigos y mensajes de error en un objeto [!DNL JSON] o en un encabezado X de la cadena de respuesta HTTP.

### Ejemplo de código de error y mensaje de DCS

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

Los códigos de error capturados por el encabezado X aparecen en la cadena URL de esta manera, `X-Error: 101,102`.

[Condiciones de carrera y gestión de errores](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
