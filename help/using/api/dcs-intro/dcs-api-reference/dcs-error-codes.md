---
description: Códigos de error y mensajes generados por los servidores de recopilación de datos (DCS) enumerados en orden numérico por ID de código.
title: Códigos de error DCS, mensajes y ejemplos
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 5044a38c751abace922008f00b9ff463ea9c7e57
workflow-type: tm+mt
source-wordcount: '1520'
ht-degree: 4%

---

# Códigos de error DCS, mensajes y ejemplos {#dcs-error-codes-messages-and-examples}

Códigos de error y mensajes generados por [!UICONTROL Data Collection Servers] ([!DNL DCS]) enumerados en orden numérico por ID de código.

En los cuadros siguientes, *cursiva* representa un marcador de posición variable.

## Códigos de error del sistema {#system-error-codes}

| Código de error | Mensaje de error | Descripción |
|---|---|---|
| 0 | Error no especificado | Este es un error de captador global que controla eventos que no están cubiertos por los otros controladores de errores. Solucionar este error es difícil. Puede deberse a una variedad de acciones o eventos desconocidos. Si recibe este error, intente lo siguiente [!DNL DCS] volver a solicitar. Póngase en contacto con su [!DNL Adobe] representativo si el problema persiste. |
| 1 | No se pudo encontrar la configuración para el nombre de host: `hostname` | El equipo de aprovisionamiento de socios no ha configurado el nombre de host enviado en la solicitud. Póngase en contacto con su [!DNL Adobe] representante de si ve este mensaje de error. |
| 2 | No válido `d_orgid` valor (no se ha podido encontrar una configuración para este identificador de organización): `ID` | El ID de organización es incorrecto. Compruebe su ID e inténtelo de nuevo. Si no conoce o no tiene su ID de organización de, consulte la sección &quot;Página de administración&quot; [Organizaciones y vinculación de cuentas](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) para obtener información sobre cómo encontrarlo. |
| 10 | No se pueden evaluar los rasgos | Los rasgos de la solicitud se evaluaron parcialmente o no se evaluaron en absoluto. Póngase en contacto con su [!DNL Adobe] representativo si el problema persiste. |

## Códigos de error de integración {#integration-error-codes}

| Código de error | Mensaje de error | Descripción |
|---|---|---|
| 100 | No se pudo recuperar el nombre de host para la solicitud | Un [!DNL API] La llamada de no ha enviado el host [!DNL HTTP] encabezado en la solicitud. Añada el encabezado host a la llamada e inténtelo de nuevo. La mayoría de los navegadores y [!DNL API] los clientes lo hacen automáticamente. |
| 101 | No válido [!DNL Experience Cloud] id pasado `ID` | El [!DNL DCS] la llamada contiene un valor no válido [!DNL Experience Cloud] ID. Compruebe la `d_mid=` par clave-valor en la cadena de encabezado. Asegúrese de que está pasando el correcto [!DNL Experience Cloud] ID e intente la solicitud de nuevo. |
| 102 | No válido [!DNL AAM ID] pasado en la solicitud `ID` | El [!DNL DCS] la llamada contiene un valor no válido [!DNL Audience Manager] ID. Compruebe la `d_uuid=` par clave-valor en la cadena de encabezado. Asegúrese de que está pasando el correcto [!DNL Audience Manager] ID e intente la solicitud de nuevo. |
| 104 | Todos los ID de cliente no son válidos | Todos los ID de cliente de la llamada no son válidos. Compruebe sus ID e inténtelo de nuevo. |
| 109 | Referer `HTTP referer` no está permitido para el socio `Partner ID` | El `HTTP referer` no se permite el encabezado de la llamada para el ID de socio en la llamada. Compruebe que la variable `HTTP referer` el encabezado es correcto. |
| 111 | No válido `IMS` token recibido | Devuelto para [!DNL Audience Manager] - [!DNL Adobe Target] integraciones. El error se produce cuando se realiza una llamada a [!DNL DCS], que contiene un no válido [!DNL IMS] token. El token puede estar mal formado, haber caducado o puede que el usuario no tenga autorización para acceder al recurso requerido. |

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
   <td colname="col2"> <p>Etiqueta de exclusión para el ID encontrada <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un cliente ha optado por no recibir publicidad basada en intereses. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Cookies bloqueadas </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el explorador del usuario bloquea las cookies de terceros.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Relación de confianza encontrada mediante <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>El usuario ha iniciado un proceso de exclusión a través de NAI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>El socio ha bloqueado las solicitudes de este país </p> </td> 
   <td colname="col3"> <p>En función de la dirección IP, la variable <span class="wintitle"> DCS</span> bloquea las solicitudes de países en los que el socio ha limitado deliberadamente el tráfico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>No se permiten solicitudes de este país </p> </td> 
   <td colname="col3"> <p>En función de la dirección IP, la variable <span class="wintitle"> DCS</span> bloquea las solicitudes de los siguientes países: </p> <p> 
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
   <td colname="col2"> <p> No se pueden leer los rasgos de la caché de perfiles para el ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando un perfil de usuario no se puede leer desde nuestro almacenamiento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> No se pueden leer los ID de dispositivo de la caché de perfiles para el ID de cliente: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Devuelto cuando el <a href="../../../reference/ids-in-aam.md"> ID de dispositivo</a> no se puede recuperar para una regla de combinación de vínculos de perfil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>No se puede leer el cliente relacionado para el ID de dispositivo: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Devuelto cuando el <a href="../../../reference/ids-in-aam.md"> ID de cliente (UUID)</a> No se pueden recuperar del almacenamiento interno los ID asociados a un dispositivo para una regla de combinación Última autenticación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> No se puede leer el clúster de dispositivos para el ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Los ID de dispositivo vinculados del mismo clúster de gráficos de dispositivos no se pueden devolver para este ID de dispositivo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>No se ha podido realizar la migración porque se ha producido un error en la lectura del perfil del dispositivo principal </p> </td> 
   <td colname="col3"> <p>Si recibe este error, es posible que tengamos problemas de escalabilidad con nuestro almacén de datos (<span class="wintitle"> PCS</span>). Póngase en contacto con el representante del Adobe si el problema persiste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>No se ha podido realizar la migración desde <code><i>ID</i></code> hasta <code><i>ID</i></code>, porque error de lectura de perfil para <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Si recibe este error, es posible que tengamos problemas de escalabilidad con nuestro almacén de datos (<span class="wintitle"> PCS</span>). Póngase en contacto con el representante del Adobe si el problema persiste. </p> </td> 
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
   <td colname="col2"> <p>ID de cliente no válido <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>El ID de cliente no es válido (faltan valores para la fuente de datos, faltan códigos de integración, formato no válido para las fuentes de datos, ID de cliente bloqueado, ID de cliente en blanco, intento de acceso no autorizado a una fuente de datos que no pertenece al socio). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Se ha superado el número máximo de ID de cliente. El máximo permitido es <code><i>maximum allowed</i></code>. Se ha encontrado <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>El número de ID de cliente asociados a una fuente de datos entre dispositivos supera el número permitido de ID entre dispositivos por solicitud. Estos ID incluyen ID de cookies, móviles o entre dispositivos. El límite actual es de 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>ID de cliente no autorizado <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el origen de datos del ID de cliente no es propiedad del ID de organización actual. Si no conoce o no tiene su ID de organización, consulte la sección "Búsqueda del ID de organización" en <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organizaciones y vinculación de cuentas</a> para obtener información sobre cómo encontrarlo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>ID de cliente bloqueado <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el ID de cliente se ha identificado como malintencionado y se ha agregado a una lista de bloqueados de la lista de distribución de datos de la lista de distribución de. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>ID de origen de datos bloqueado <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el ID de la fuente de datos se ha identificado como malintencionado y se ha agregado a una lista de bloqueados de la fuente de datos de la que se ha hecho clic en el nombre de usuario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>ID de dispositivo declarado bloqueado <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>El ID del dispositivo se ha identificado como malintencionado y se ha agregado a una lista de bloqueados de. Esto puede ocurrir cuando recibimos una cantidad extrema de <span class="wintitle"> DCS</span> solicitudes que contengan este ID de dispositivo en un corto período de tiempo. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Operación de perfil bloqueada para <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se ha bloqueado una acción de lectura y escritura porque se ha identificado un ID como malintencionado y se ha agregado a una lista de bloqueados de error. Consulte el código de error 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>ID del cliente <code><i>ID</i></code> se descartó porque superó el límite de id de cliente declarados por solicitud </p> </td> 
   <td colname="col3"> <p>Relacionado con el error 301. Este error especifica qué ID de cliente se descartó porque se superó el límite. </p> <p>Por ejemplo, si hay 12 ID de cliente declarados en la variable <span class="wintitle"> DCS</span> Llamada de, dos de ellos serán descartados. Para retransmitir cuáles se descartaron, este error aparecerá dos veces en la respuesta (una vez por cada ID de cliente descartado ). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>El ID de cliente se descartó porque superaba el límite de un área de nombres determinada. El ID de área de nombres es <code><i>ID</i></code>, el id del cliente es <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Este código de error se devuelve si hay más de 3 ID de cliente declarados para la misma área de nombres (<code> DPID</code>) en un <span class="wintitle"> DCS</span> llamada. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>En esta muestra <span class="wintitle"> DCS</span> solicitud, hay 4 id declarados para el mismo área de nombres (con el código de integración uno). Se descarta uno de los ID y se devuelve el error 310. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>La solicitud contiene parámetros no válidos </p> </td> 
   <td colname="col3"> <p>El <span class="wintitle"> DCS</span> devuelve este código de error cuando al menos un parámetro de URL no está codificado correctamente. En este caso, la variable <span class="wintitle"> DCS</span> no tiene en cuenta la solicitud completa. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>En la solicitud de ejemplo anterior, la variable <code> %</code> la secuencia se ha codificado incorrectamente. En consecuencia, la <span class="wintitle"> DCS</span> lo ignoraré. </p> <p>La muestra codificada correctamente debería tener un aspecto similar al siguiente: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>La solicitud contiene un ID de dispositivo global no válido </p> </td> 
   <td colname="col3"> <p>El <span class="wintitle">DCS</span> devuelve este código de error cuando la solicitud contiene un ID de dispositivo global no válido. DCS ignora el ID no válido y genera un error 312 junto con los errores específicos del ID no válido. Consulte <a href="../../../features/global-data-sources.md" format="dita" scope="local">Fuentes de datos globales</a> y <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Índice de ID en el Audience Manager</a> para obtener información detallada sobre los formatos de ID publicitarios de dispositivo correctos y las fuentes de datos globales correspondientes.</p>
   <p>Ejemplo de llamada incorrecta: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Explicación: Una <span class="keyword">IDFA (DPID 20915)</span> debe ser un ID en mayúsculas. El ID proporcionado en la solicitud está en minúsculas.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>El ID de CMP no está presente en GCL</p> </td> 
   <td colname="col3"> <p>Cuándo <code>gdpr=1</code> y la cadena IAB TC la genera un ID de CMP que no está presente en la versión en caché de Audience Manager de la lista global CMP en el momento de la evaluación, el complemento de Audience Manager para el TCF de IAB descarta la cadena IAB TC y procesa la solicitud como de costumbre. El TCF de IAB v2.2 ${GDPR} La macro se establece en 0 y ${GDPR_CONSENT_XXX} la macro está vacía.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>El ID de CMP se marca como eliminado en GCL</p> </td> 
   <td colname="col3"> <p>Cuándo <code>gdpr=1</code> y la cadena TC de la IAB la genera una CMP marcada como eliminada en la versión en caché de la lista CMP global, el complemento Audience Manager para TCF de IAB descarta la cadena TC y procesa la solicitud como de costumbre si el tiempo de evaluación pasa el tiempo de eliminación de la lista CMP global. El TCF de IAB v2.2 ${GDPR} La macro se establece en 0 y ${GDPR_CONSENT_XXX} la macro está vacía.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>La cadena de consentimiento indica que no hay consentimiento</p> </td> 
   <td colname="col3"> <p>Cuando no se proporciona ningún consentimiento, el complemento de Audience Manager para el TCF de IAB excluye al usuario de una recopilación de datos adicional o anula la llamada completamente si no se detecta ningún contexto de socio.</p>
   </td>
  </tr>

</tbody>
</table>

## Ejemplos de mensajes de código de error {#sample-error-codes}

El [!DNL DCS] devuelve códigos de error y mensajes en un [!DNL JSON] o en un encabezado X de la cadena de respuesta HTTP.

### Ejemplo de código y mensaje de error de DCS

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

### Error X

Los códigos de error capturados por el encabezado X- aparecen en la cadena URL de esta manera, `X-Error: 101,102`.

[Condiciones de carrera y gestión de errores](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
