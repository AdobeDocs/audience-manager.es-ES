---
seo-title: Making Server-to-Server DCS API Calls
solution: Audience Manager
title: Realización de llamadas de API de DCS de servidor a servidor
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
feature: DCS
description: Sintaxis de llamada, ejemplo y parámetros al realizar llamadas de API de DCS de servidor a servidor
exl-id: 977f4dfe-0beb-43c8-b64e-df4042427474
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 8%

---

# Realización de llamadas de API de DCS de servidor a servidor {#making-server-to-server-dcs-api-calls}

Las llamadas requieren el nombre de host del servidor DCS regional y el ID de usuario. Si no tiene los ID de usuario y región requeridos, consulte [Obtención de ID y regiones de usuario a partir de una respuesta de DCS](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) y/o [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Una vez que tenga los ID de usuario y de región, puede realizar llamadas de servidor a servidor al DCS. Consulte esta sección para ver sintaxis y ejemplos.

>[!NOTE]
>
>En el código y los ejemplos, *cursiva* representa un marcador de posición variable. Sustituya el marcador de posición por un valor real cuando realice llamadas de servidor a servidor a [!DNL DCS].

## Sintaxis de llamada y ejemplo {#call-syntax-example}

Una solicitud básica de servidor a servidor que envía datos a [!DNL DCS] utiliza la sintaxis que se muestra a continuación.

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

Una llamada de ejemplo tiene un aspecto similar al siguiente ejemplo.

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
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Su alias de dominio asignado por <span class="keyword"> Audience Manager</span> (por ejemplo, <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">El dominio de destino, que siempre es <i><code> demdex.net</code></i>. Consulte <a href="../../../reference/demdex-calls.md">Explicación de las llamadas al dominio Demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>El parámetro de host de encabezado http que muestra el nombre del <span class="wintitle"> DCS</span> servidor. El nombre de host está vinculado a un ID de región, por lo que lo necesita antes de realizar estos tipos de llamadas. Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS Region IDs, Locations, and Host Names</a> (ID de región de DCS, ubicaciones y nombres de host). </p> </td> 
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
   <td colname="col2"> <p>Es la clave de ID único de usuario que contiene el <span class="keyword"> Audience Manager</span> valor de ID de usuario en un par clave-valor. </p> <p>Uso <code><i>d_uuid</i></code> si va a pasar el <span class="keyword"> Audience Manager</span> ID de usuario. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Es la clave de ID único de usuario que contiene el <span class="keyword"> Experience Cloud</span> valor de ID de usuario en un par clave-valor. Consulte también <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Obtención del ID de usuario desde la cookie del servicio de ID</a>. </p> <p>Uso <i><code> d_mid</code></i> si va a pasar un <span class="keyword"> Experience Cloud</span> ID capturado del <span class="keyword"> Experience Cloud</span> Servicio de ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Parámetros de respuesta opcionales. </p> <p> Ninguno de ellos es necesario para enviar datos a <span class="wintitle"> DCS</span>. Sin embargo, si desea la variable <span class="wintitle"> DCS</span> para devolver una respuesta, debe incluir <i><code> d_rtbd=json</code></i> en su solicitud. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Respuesta de ejemplo {#sample-response}

Consulte [Recibir datos del DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
