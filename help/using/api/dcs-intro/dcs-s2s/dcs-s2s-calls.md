---
seo-title: Realización de llamadas de API de DCS de servidor a servidor
solution: Audience Manager
title: Realización de llamadas de API de DCS de servidor a servidor
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 9%

---


# Realización de llamadas de API de DCS de servidor a servidor {#making-server-to-server-dcs-api-calls}

Las llamadas requieren el nombre de host del servidor DCS regional y el ID de usuario. Si no tiene los ID de usuario y región necesarios, consulte [Obtener ID de usuario y regiones de una respuesta de DCS](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) y/o [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Una vez que tenga ID de usuario y región, puede realizar llamadas de servidor a servidor al DCS. Consulte esta sección para ver ejemplos y sintaxis.

>[!NOTE]
>
>En el código y los ejemplos, *cursiva* representa un marcador de posición de variable. Sustituya el valor real del marcador de posición cuando realice llamadas de servidor a servidor a [!DNL DCS].

## Ejemplo y sintaxis de llamada {#call-syntax-example}

Una solicitud básica de servidor a servidor que envía datos a [!DNL DCS] utiliza la sintaxis que se muestra a continuación.

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

Una llamada de ejemplo es similar al siguiente ejemplo.

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## Parámetros de llamada {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> <i>domain alias</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Esta parte de la llamada contiene: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Su alias de dominio asignado por <span class="keyword"> Audience Manager</span> (por ejemplo: <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Dominio de destino, que siempre es <i><code> demdex.net</code></i>. Consulte <a href="../../../reference/demdex-calls.md">Explicación de las llamadas al dominio Demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>El parámetro de host de encabezado http que muestra el nombre del servidor <span class="wintitle"> DCS</span> regional. El nombre de host está vinculado a un ID de región, por lo que es necesario antes de realizar este tipo de llamadas. Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS Region IDs, Locations, and Host Names</a> (ID de región de DCS, ubicaciones y nombres de host). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Esta parte de la llamada: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifica la llamada como una llamada de evento. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Define el inicio de la cadena URL que contiene los datos que desea enviar al DCS. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Es la clave de ID de usuario única que contiene el valor de ID de usuario <span class="keyword"> Audience Manager</span> en un par clave-valor. </p> <p>Utilice <code><i>d_uuid</i></code> si está pasando el ID de usuario <span class="keyword"> Audience Manager</span>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Es la clave de ID de usuario única que contiene el valor de ID de usuario <span class="keyword"> Experience Cloud</span> en un par clave-valor. Consulte también <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Obtener el ID de usuario de la cookie de servicio de ID</a>. </p> <p>Utilice <i><code> d_mid</code></i> si está pasando un ID de <span class="keyword"> Experience Cloud</span> capturado desde el servicio de ID de <span class="keyword"> Experience Cloud</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Parámetros de respuesta opcionales. </p> <p> No se requiere ninguno de estos datos para enviar datos al <span class="wintitle"> DCS</span>. Sin embargo, si desea que el <span class="wintitle"> DCS</span> devuelva una respuesta, debe incluir <i><code> d_rtbd=json</code></i> en la solicitud. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Respuesta de ejemplo {#sample-response}

Consulte [Recibir datos del DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
