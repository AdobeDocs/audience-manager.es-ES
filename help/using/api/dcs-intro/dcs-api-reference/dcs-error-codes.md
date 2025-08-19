---
description: Error códigos y mensajes generados por los servidores de recopilación de datos (DCS) enumerados en numérica orden por ID de código.
title: Códigos Error DCS, mensajes y ejemplos
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 5044a38c751abace922008f00b9ff463ea9c7e57
workflow-type: tm+mt
source-wordcount: '1517'
ht-degree: 3%

---

# Códigos Error DCS, mensajes y ejemplos {#dcs-error-codes-messages-and-examples}

Error códigos y mensajes generados por () enumerados en numérica orden por ID de [!UICONTROL Data Collection Servers][!DNL DCS]código.

En las tablas siguientes, *la cursiva representa un marcador de* posición variable.

## Códigos de Error del sistema {#system-error-codes}

| Error Code | Mensaje de error | Descripción |
|---|---|---|
| 0 | Error no especificado | Se trata de un error general que gestiona eventos que no están cubiertos por los demás gestores de errores. Solucionar este error es difícil. Puede ser causada por una variedad de acciones o eventos desconocidos. Si recibe este error, pruebe su [!DNL DCS] solicitud nuevamente. Si el problema continúa, póngase en contacto con su [!DNL Adobe] representante. |
| 1 | No se pudo encontrar la configuración para el nombre de host: `hostname` | El nombre host enviado en el solicitud no ha sido configurado por nuestra equipo de aprovisionamiento de socio. Póngase en contacto con su [!DNL Adobe] representante si ve este mensaje de error. |
| 2 | Valor no válido `d_orgid` (no se pudo encontrar una configuración para este identificador de organización): `ID` | El ID de organización es incorrecto. Compruebe su ID y vuelva a probar la solicitud. Si no conoce o no tiene su identificador de organización, consulte la sección [&quot;Administración Página&quot; Organizaciones y enlaces de cuenta](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) para obtener información sobre cómo encontrarlo. |
| 10 | No se pueden evaluar los rasgos | Los rasgos en el solicitud fueron evaluados parcialmente o no han sido evaluados en absoluto. Si el problema continúa, póngase en contacto con su [!DNL Adobe] representante. |

## Códigos de Error de integración {#integration-error-codes}

| Error Code | Mensaje de error | Descripción |
|---|---|---|
| 100 | No se pudo recuperar host nombre del solicitud | Una [!DNL API] llamada no envió el encabezado host [!DNL HTTP] en el solicitud. añadir el encabezado host a la llamada e inténtelo de nuevo. La mayoría de los exploradores y [!DNL API] clientes lo hacen automáticamente. |
| 101 | ID no [!DNL Experience Cloud] válido transferido `ID` | La [!DNL DCS] llamada contiene un ID de no válido [!DNL Experience Cloud] . Compruebe el `d_mid=` par clave-valor en la cadena de encabezado. Asegúrese de pasar el ID correcto [!DNL Experience Cloud] y vuelva a probar la solicitud. |
| 102 | Invalid [!DNL AAM ID] passed in solicitud `ID` | La [!DNL DCS] llamada contiene un ID de no válido [!DNL Audience Manager] . Compruebe el `d_uuid=` par clave-valor en la cadena de encabezado. Asegúrese de pasar el ID correcto [!DNL Audience Manager] y vuelva a probar la solicitud. |
| 104 | Todos los ID de cliente están no válido | Todos los ID de cliente de la llamada están no válido. Compruebe sus ID e inténtelo de nuevo. |
| 109 | No se permite el remitente `HTTP referer` para socio `Partner ID` | El `HTTP referer` encabezado de la llamada no está permitido para el ID socio de la llamada. Compruebe que el `HTTP referer` encabezado sea correcto. |
| 111 | Se ha recibido un token no válido `IMS` | Devuelto para [!DNL Audience Manager] - [!DNL Adobe Target] integraciones. El error se lanza cuando se realiza una llamada al [!DNL DCS], que contiene un token no válido [!DNL IMS] . Es posible que el token tenga un formato incorrecto, que haya caducado o que el usuario no esté autorizado para acceder al recurso necesario. |

## Códigos de Error de exclusión {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code ID </th> 
   <th colname="col2" class="entry"> Mensaje </th> 
   <th colname="col3" class="entry"> Descripción </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>Se ha encontrado exclusión etiqueta para la identificación <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un cliente ha optado por no recibir publicidad basada en interés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Cookies bloqueadas </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el explorador del usuario bloquea terceros cookies.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Relación de confianza encontrada a través de <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>El usuario ha iniciado un proceso de exclusión a través de la NAI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Las solicitudes procedentes de este país están bloqueadas por socio </p> </td> 
   <td colname="col3"> <p>Basándose en la dirección IP, el DCS bloquea<span class="wintitle"> las </span> solicitudes de países donde el socio ha limitado deliberadamente el tráfico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>No se permiten solicitudes desde este país </p> </td> 
   <td colname="col3"> <p>Según la dirección IP, el DCS<span class="wintitle"> bloquea las </span> solicitudes de los países siguientes: </p> <p> 
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

## Códigos de Error de recuperación de perfiles {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code ID </th> 
   <th colname="col2" class="entry"> Mensaje </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> No se pueden leer características de perfil caché para la identificación: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando un perfil de usuario no se puede leer desde nuestro almacenamiento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> No se pueden leer los ID de dispositivos de perfil caché para el ID de cliente: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando no se puede recuperar el ID<a href="../../../reference/ids-in-aam.md"> de </a> dispositivos para una regla de combinación de vínculos de perfil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>No se puede leer el cliente relacionado para dispositivos ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el <a href="../../../reference/ids-in-aam.md"> ID de cliente (UUID)</a> asociado a un ID de dispositivos no se puede recuperar para un regla de combinación último autenticado desde nuestro almacenamiento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> No se puede leer dispositivos clúster para su id: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Los ID de dispositivos vinculados del mismo clúster de gráficos de dispositivos no se pueden devolver para este ID de dispositivos. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>No se pudo realizar la migración porque falló perfil lectura para la dispositivos principal </p> </td> 
   <td colname="col3"> <p>Si recibe este error, es posible que tengamos problemas escalabilidad con nuestro tienda de datos (<span class="wintitle"> PCS</span>). Póngase en contacto con su representante de Adobe si el problema persiste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>No se pudo realizar la migración de a <code><i>ID</i></code>, porque perfil error de <code><i>ID</i></code> lectura para<code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Si recibe este error, es posible que tengamos problemas escalabilidad con nuestro tienda de datos (<span class="wintitle"> PCS</span>). Póngase en contacto con su representante de Adobe si el problema persiste. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Códigos de Advertencia de integración {#integration-warning-codes}

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code ID </th> 
   <th colname="col2" class="entry"> Mensaje </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>300 </p> </td> 
   <td colname="col2"> <p>ID de cliente no válido <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>El ID de cliente es no válido (faltan valores para fuente de datos, faltan códigos de integración no válido formato para las fuentes de datos, ID de cliente bloqueado, ID de cliente en blanco, intento de acceso no autorizado a una fuente de datos que no pertenece al socio). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Se ha superado el número máximo de ID de cliente. El máximo permitido es <code><i>maximum allowed</i></code>. Encontrado es <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>El número de ID de cliente asociados a un dispositivos cruzado fuente de datos superar el número permitido de ID dispositivos cruzados por solicitud. Estos ID incluyen ID dispositivos cruzados, móviles o cookie. El límite está establecido actualmente en 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>ID de cliente no autorizado <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el ID de cliente fuente de datos no pertenece al ID de organización actual. Si no conoce o no tiene su identificador de organización, consulte la sección "Buscar el identificador de organización" en <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organizaciones y vinculación</a> de cuentas para obtener información sobre cómo encontrarlo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>ID de cliente bloqueado <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el ID de cliente se ha identificado como malicioso y se ha agregado a una lista de denegación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>ID de fuente de datos bloqueada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el ID del fuente de datos ha sido identificado como malicioso y se ha agregado a una lista de denegación </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>ID de dispositivos declarada bloqueada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>El ID de dispositivos se ha identificado como malicioso y se ha agregado a una lista de denegación Esto puede ocurrir cuando recibimos una cantidad extrema de solicitudes DCS<span class="wintitle"> que contienen este ID de </span> dispositivos en un corto período de tiempo. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Operación de perfil bloqueada durante <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se ha bloqueado una acción de lectura/escritura porque se ha identificado un ID como malicioso y se ha agregado a una lista de denegación Consulte el código de error 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>Se descartó el ID <code><i>ID</i></code> de cliente porque superaba el límite de ID de cliente declarados por solicitud </p> </td> 
   <td colname="col3"> <p>Relacionado con el error 301. Este error especifica qué ID de cliente se descartó porque se superó el límite. </p> <p>Por ejemplo, si se declaran 12 ID de cliente en la <span class="wintitle"> llamada DCS</span> , dos de ellos se descartarán. Para retransmitir cuáles se descartaron, este error aparecerá dos veces en la respuesta (una para cada ID de cliente descartado). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>Se descartó el ID de cliente porque superaba el límite de un espacio de nombres determinado. El ID de espacio de nombres es <code><i>ID</i></code>, el ID de cliente es <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Se devuelve este código de error si hay más de 3 ID de cliente declarados para el mismo espacio de nombres (<code> DPID</code>) en una <span class="wintitle"> llamada DCS</span> . </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one </code> </p> <p>En este solicitud DCS<span class="wintitle"> de ejemplo</span>, hay 4 ID declarados para el mismo espacio de nombres (con el código de integración). Uno de los ID se descarta y se devuelve el error 310. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>La solicitud contiene parámetros no válido </p> </td> 
   <td colname="col3"> <p>El <span class="wintitle"> DCS devuelve este código de</span> error cuando al menos un parámetro URL no está codificado correctamente. En este caso, el <span class="wintitle"> DCS</span> ignora todo el solicitud. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>En el ejemplo solicitud anterior, la <code> %</code> Secuencia está codificada incorrectamente. En consecuencia, el <span class="wintitle"> DCS</span> lo ignorará. </p> <p>La muestra codificada correctamente debería tener gustar siguiente aspecto: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>La solicitud contiene un no válido ID de dispositivo global </p> </td> 
   <td colname="col3"> <p>El <span class="wintitle">DCS devuelve este código de</span> error cuando el solicitud contiene un ID de dispositivo global no válido. DCS ignora el ID de no válido y arroja un error 312 junto con los errores específicos del ID de no válido. Consulte <a href="../../../features/global-data-sources.md" format="dita" scope="local">Fuentes</a> de datos globales y <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Index de ID en Audience Manager</a> para obtener información detallada sobre los formatos de ID de publicidad dispositivos correctos y las fuentes de datos globales correspondientes.</p>
   <p>Ejemplo de llamada incorrecta: <code>"http://partner.demdex.net/event?d_rtbd=json&d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Explicación: Un <span class="keyword">IDFA (DPID 20915)</span> debe ser un ID en mayúsculas. El ID proporcionado en la solicitud está en minúsculas.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>El ID de CMP no está presente en GCL</p> </td> 
   <td colname="col3"> <p>Cuando <code>gdpr=1</code> la cadena IAB TC es generada por un ID de CMP que no está presente en la versión en caché de Audience Manager de la lista global de CMP en el momento de la evaluación, el complemento de Audience Manager para IAB TCF descarta la cadena IAB TC y procesa el solicitud de la forma habitual. La macro IAB TCF v2.2 ${GDPR} se establece en 0 y la macro ${GDPR_CONSENT_XXX} está vacía.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>El ID de CMP se marca como eliminado en GCL</p> </td> 
   <td colname="col3"> <p>Cuando <code>gdpr=1</code> y la cadena IAB TC es generada por una CMP que está marcada como eliminada en nuestro versión en caché de la Lista CMP global, el complemento Audience Manager para IAB TCF descarta la cadena TC y procesa la solicitud como de costumbre, si el tiempo de evaluación ha pasado el tiempo de eliminación de la Lista CMP global. La macro IAB TCF v2.2 ${GDPR} se establece en 0 y la macro ${GDPR_CONSENT_XXX} está vacía.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>La cadena de consentimiento indica que no hay consentimiento</p> </td> 
   <td colname="col3"> <p>Cuando no se proporciona consentimiento, el complemento Audience Manager para IAB TCF excluye el usuario de más recopilación de datos o interrumpe la llamada por completo si no se detecta ningún contexto socio.</p>
   </td>
  </tr>

</tbody>
</table>

## Ejemplo Error mensajes Code {#sample-error-codes}

El [!DNL DCS] devuelve códigos y mensajes de error en un [!DNL JSON] objeto o en un encabezado X de la cadena de respuesta HTTP.

### DCS de muestra Error Code y Enviar mensaje

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

Error códigos capturados por el encabezado X- aparecen en la cadena URL gustar este, `X-Error: 101,102`.

[Condiciones de carrera y manejo Error](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
