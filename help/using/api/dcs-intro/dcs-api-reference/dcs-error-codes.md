---
description: Códigos de error y mensajes generados por los servidores de recopilación de datos (DCS) enumerados en orden numérico por ID de código.
title: Códigos de error DCS, mensajes y ejemplos
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: f8ba09b674b71045e08f6d171471cdcdd0efb265
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 3%

---

# Códigos de error DCS, mensajes y ejemplos {#dcs-error-codes-messages-and-examples}

Códigos de error y mensajes generados por [!UICONTROL Data Collection Servers] ([!DNL DCS]) enumerados en orden numérico por identificador de código.

En las tablas siguientes, *cursiva* representa un marcador de posición de variable.

## Códigos de error del sistema {#system-error-codes}

| Código de error | Mensaje de error | Descripción |
|---|---|---|
| 0 | Error no especificado | Este es un error de captador global que controla eventos que no están cubiertos por los otros controladores de errores. Solucionar este error es difícil. Puede deberse a una variedad de acciones o eventos desconocidos. Si recibe este error, intente de nuevo la solicitud [!DNL DCS]. Póngase en contacto con su representante de [!DNL Adobe] si el problema persiste. |
| 1 | No se encontró la configuración del nombre de host: `hostname` | El equipo de aprovisionamiento de socios no ha configurado el nombre de host enviado en la solicitud. Póngase en contacto con su representante de [!DNL Adobe] si ve este mensaje de error. |
| 2 | Valor `d_orgid` no válido (no se pudo encontrar una configuración para este identificador de organización): `ID` | El ID de organización es incorrecto. Compruebe su ID e inténtelo de nuevo. Si no conoce o no tiene su identificador de organización, consulte la sección &quot;Página de administración&quot; [Organizaciones y vinculación de cuentas](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) para obtener información sobre cómo encontrarlo. |
| 10 | No se pueden evaluar los rasgos | Los rasgos de la solicitud se evaluaron parcialmente o no se evaluaron en absoluto. Póngase en contacto con su representante de [!DNL Adobe] si el problema persiste. |

## Códigos de error de integración {#integration-error-codes}

| Código de error | Mensaje de error | Descripción |
|---|---|---|
| 100 | No se pudo recuperar el nombre de host para la solicitud | Una llamada de [!DNL API] no envió el encabezado de host [!DNL HTTP] en la solicitud. Añada el encabezado host a la llamada e inténtelo de nuevo. La mayoría de los exploradores y [!DNL API] clientes hacen esto automáticamente. |
| 101 | ID [!DNL Experience Cloud] no válido pasado en `ID` | La llamada [!DNL DCS] contiene un identificador [!DNL Experience Cloud] no válido. Compruebe el par clave-valor `d_mid=` en la cadena de encabezado. Asegúrese de pasar el ID [!DNL Experience Cloud] correcto e intente la solicitud de nuevo. |
| 102 | [!DNL AAM ID] no válido pasado en la solicitud `ID` | La llamada [!DNL DCS] contiene un identificador [!DNL Audience Manager] no válido. Compruebe el par clave-valor `d_uuid=` en la cadena de encabezado. Asegúrese de pasar el ID [!DNL Audience Manager] correcto e intente la solicitud de nuevo. |
| 104 | Todos los ID de cliente no son válidos | Todos los ID de cliente de la llamada no son válidos. Compruebe sus ID e inténtelo de nuevo. |
| 109 | El referente `HTTP referer` no está permitido para el socio `Partner ID` | El encabezado `HTTP referer` de la llamada no está permitido para el identificador de socio en la llamada. Compruebe que el encabezado `HTTP referer` sea correcto. |
| 111 | Token recibido `IMS` no válido | Devuelto para integraciones de [!DNL Audience Manager] - [!DNL Adobe Target]. Se produce el error cuando se realiza una llamada a [!DNL DCS], que contiene un token [!DNL IMS] no válido. El token puede estar mal formado, haber caducado o puede que el usuario no tenga autorización para acceder al recurso requerido. |

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
   <td colname="col2"> <p>Se encontró una etiqueta de exclusión para el ID <code><i>ID</i></code> </p> </td> 
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
   <td colname="col2"> <p>El socio ha bloqueado las solicitudes de este país </p> </td> 
   <td colname="col3"> <p>En función de la dirección IP, el DCS<span class="wintitle"> de </span> bloquea las solicitudes de países donde el socio ha limitado deliberadamente el tráfico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>No se permiten solicitudes de este país </p> </td> 
   <td colname="col3"> <p>En función de la dirección IP, el DCS <span class="wintitle"> </span> bloquea las solicitudes de los siguientes países: </p> <p> 
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
   <td colname="col2"> <p> No se pueden leer los rasgos de la caché de perfiles para el identificador: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando un perfil de usuario no se puede leer desde nuestro almacenamiento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> No se pueden leer los identificadores de dispositivo de la caché de perfiles para el id. de cliente: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Devuelto cuando el identificador de dispositivo <a href="../../../reference/ids-in-aam.md"> </a> no se puede recuperar para una regla de combinación de vínculos de perfil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>No se puede leer el cliente relacionado para el id. de dispositivo: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Se devuelve cuando el ID de cliente (UUID) <a href="../../../reference/ids-in-aam.md"> de </a> asociado a un ID de dispositivo no se puede recuperar para una regla de combinación de Last Authenticated de nuestro almacenamiento interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> No se puede leer el clúster de dispositivos para el identificador: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Los ID de dispositivo vinculados del mismo clúster de gráficos de dispositivos no se pueden devolver para este ID de dispositivo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>No se ha podido realizar la migración porque se ha producido un error en la lectura del perfil del dispositivo principal </p> </td> 
   <td colname="col3"> <p>Si recibe este error, es posible que estemos experimentando problemas de escalabilidad con nuestro almacén de datos (<span class="wintitle"> PCS</span>). Póngase en contacto con su representante de Adobe si el problema persiste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>No se pudo realizar la migración de <code><i>ID</i></code> a <code><i>ID</i></code> porque se produjo un error en la lectura del perfil de <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Si recibe este error, es posible que estemos experimentando problemas de escalabilidad con nuestro almacén de datos (<span class="wintitle"> PCS</span>). Póngase en contacto con su representante de Adobe si el problema persiste. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Códigos de advertencia de integración {#integration-warning-codes}

| ID de código | Mensaje | Descripción |
| --- | --- | --- |
| 300 | ID de cliente `_ID_` no válido | El ID de cliente no es válido (faltan valores para la fuente de datos, faltan códigos de integración, formato no válido para las fuentes de datos, ID de cliente bloqueado, ID de cliente en blanco, intento de acceso no autorizado a una fuente de datos que no pertenece al socio). |
| 301 | Se ha superado el número máximo de ID de cliente. El máximo permitido es `_maximum allowed_`. Se encontró `_maximum found_`. | El número de ID de cliente asociados a una fuente de datos entre dispositivos supera el número permitido de ID entre dispositivos por solicitud. Estos ID incluyen ID de cookies, móviles o entre dispositivos. El límite actual es de 10. |
| 302 | Id. de cliente no autorizado `_ID_` | Se devuelve cuando el origen de datos del ID de cliente no es propiedad del ID de organización actual. Si no conoce o no tiene su identificador de organización, consulte la sección &quot;Buscar su identificador de organización&quot; en [Organizaciones y vinculación de cuentas](https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html) para obtener información sobre cómo encontrarlo. |
| 303 | ID de cliente bloqueado `_ID_` | Se devuelve cuando el ID de cliente se ha identificado como malintencionado y se ha agregado a una lista de bloqueados de la lista de distribución de datos de la lista de distribución de. |
| 304 | ID de origen de datos bloqueado `_ID_` | Se devuelve cuando el ID de la fuente de datos se ha identificado como malintencionado y se ha agregado a una lista de bloqueados de la fuente de datos de la que se ha hecho clic en el nombre de usuario. |
| 306 | Identificador de dispositivo declarado bloqueado `_ID_` | El ID del dispositivo se ha identificado como malintencionado y se ha agregado a una lista de bloqueados de. Esto puede ocurrir cuando recibimos una cantidad extrema de solicitudes de DCS que contienen este ID del dispositivo en un corto período de tiempo. |
| 307 | Operación de perfil bloqueada para `_ID_` | Se ha bloqueado una acción de lectura y escritura porque se ha identificado un ID como malintencionado y se ha agregado a una lista de bloqueados de error. Consulte el código de error 306. |
| 309 | El id. de cliente `_ID_` se descartó porque superó el límite de id de cliente declarados por solicitud | Relacionado con el error 301. Este error especifica qué ID de cliente se descartó porque se superó el límite.<br><br>Por ejemplo, si hay 12 ID de cliente declarados en la llamada del DCS, se descartarán dos de ellos. Para retransmitir cuáles se descartaron, este error aparecerá dos veces en la respuesta (una vez por cada ID de cliente descartado ). |
| 310 | El ID de cliente se descartó porque superaba el límite de un área de nombres determinada. El identificador del área de nombres es `_ID_`, el identificador de cliente es `_ID_`. | Este código de error se devuelve si hay más de 3 ID de cliente declarados para el mismo espacio de nombres ( `DPID`) en una llamada del DCS.<br><br>`https://partner.demdex.net/event?d_rtbd=json&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one`<br><br>En esta solicitud de DCS de ejemplo, hay 4 ID declarados para el mismo área de nombres (con el código de integración uno). Se descarta uno de los ID y se devuelve el error 310. |
| 311 | La solicitud contiene parámetros no válidos | El DCS devuelve este código de error cuando al menos un parámetro de URL no está codificado correctamente. En este caso, el DCS ignora toda la solicitud.<br><br>`http(s)://partner.demdex.net/event?d_event=imp&d_rtbd=json&d_src=38454&d_site=%esid!&d_creative=%ecid!&d_adgroup=%eaid!&d_placement=%epid!&d_campaign=%ebuy!&d_adsrc=48123`<br><br>En la solicitud de ejemplo anterior, la secuencia `%` está codificada incorrectamente. En consecuencia, el DCS no lo tendrá en cuenta.<br><br>La muestra codificada correctamente debería tener este aspecto:<br><br>`http(s)://partner.demdex.net/event?d_event=imp&d_rtbd=json&d_src=38454&d_site=%25esid!&d_creative=%25ecid!&d_adgroup=%25eaid!&d_placement=%25epid!&d_campaign=%25ebuy!&d_adsrc=48123` |
| 312 | La solicitud contiene un ID de dispositivo global no válido | El DCS devuelve este código de error cuando la solicitud contiene un ID de dispositivo global no válido. DCS ignora el ID no válido y genera un error 312 junto con los errores específicos del ID no válido. Consulte [Fuentes de datos globales](../../../features/global-data-sources.md) e [Índice de ID en Audience Manager](../../../reference/ids-in-aam.md) para obtener información detallada sobre los formatos de ID de publicidad de dispositivo correctos y las fuentes de datos globales correspondientes.<br><br>Ejemplo de llamada incorrecta: `"http://partner.demdex.net/event?d_rtbd=json&d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"`<br><br>Explicación: un IDFA (20915 DPID) debe ser un ID en mayúsculas. El ID proporcionado en la solicitud está en minúsculas. |
| 313 | El ID de CMP no está presente en GCL | Cuando `gdpr=1` y la cadena IAB TC se generan mediante un ID de CMP que no está presente en la versión en caché de Audience Manager de la Lista global de CMP en el momento de la evaluación, el complemento de Audience Manager para el TCF de IAB descarta la cadena IAB TC y procesa la solicitud como de costumbre. La macro TCF de IAB v2.2 ${GDPR} se establece en 0 y la macro ${GDPR\_CONSENT\_XXX} está vacía. |
| 314 | El ID de CMP se marca como eliminado en GCL | Cuando `gdpr=1` y la cadena IAB TC se generan mediante una CMP marcada como eliminada en la versión en caché de la lista CMP global, el complemento Audience Manager para TCF de IAB descarta la cadena TC y procesa la solicitud como de costumbre si el tiempo de evaluación ha pasado el tiempo de eliminación de la lista CMP global. La macro TCF de IAB v2.2 ${GDPR} se establece en 0 y la macro ${GDPR\_CONSENT\_XXX} está vacía. |
| 315 | La cadena de consentimiento indica que no hay consentimiento | Cuando no se proporciona ningún consentimiento, el complemento de Audience Manager para el TCF de IAB excluye al usuario de una recopilación de datos adicional o anula la llamada completamente si no se detecta ningún contexto de socio. |

## Ejemplos de mensajes de código de error {#sample-error-codes}

[!DNL DCS] devuelve códigos de error y mensajes en un objeto [!DNL JSON] o en un encabezado X de la cadena de respuesta HTTP.

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
