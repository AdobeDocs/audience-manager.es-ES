---
seo-title: Realización de llamadas de API de servidor a servidor
solution: Audience Manager
title: Realización de llamadas de API de servidor a servidor
uuid: bdfe 3430-e 27 f -4 a 5 c -88 d 9-ae 164 d 28 f 601
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Making Server-to-Server DCS API Calls {#making-server-to-server-dcs-api-calls}

Las llamadas requieren el nombre de host del servidor DCS regional y el ID de usuario. If you do not have the required user and region IDs, see [Get User IDs and Regions From a DCS Response](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) and/or [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Una vez que tenga ID de usuarios y regiones, puede realizar llamadas de servidor a servidor al DCS. Consulte esta sección para obtener sintaxis y ejemplos.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitute a real value for the placeholder when you server-to-server calls to the [!UICONTROL DCS].

## Call Syntax and Example {#call-syntax-example}

A basic server-to-server request that sends data to the [!UICONTROL DCS] uses the syntax shown below.

<pre><code>" Host:<i>domain alias</i>. demdex. net "" https://DCS<i>host name.demdex.net/event?d_rtbd=json&amp;d_jsonv=1&amp;d_uuid=user</i><i>ID</i>.</code>
</pre>

Un ejemplo de llamada de muestra es similar al siguiente ejemplo.

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## Call Parameters {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code><i>domain alias</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>Esta parte de la llamada contiene: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Your domain alias assigned by <span class="keyword"> Audience Manager</span> (e.g., <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">The destination domain, which is always <i><code> demdex.net</code></i>. Consulte <a href="../../../reference/demdex-calls.md">Explicación de las llamadas al dominio Demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>Nombre de host DCS</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>The http header host parameter which shows the name of the regional <span class="wintitle"> DCS</span> server. El nombre de host está ligado a un ID de región, por eso es necesario antes de realizar estos tipos de llamadas. Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS Region IDs, Locations, and Host Names</a> (ID de región de DCS, ubicaciones y nombres de host). </p> </td> 
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
   <td colname="col1"> <p><code>d_ uuid = <i>ID de usuario de Audience Manager</i></code> </p> </td> 
   <td colname="col2"> <p>This is the unique user ID key that holds the <span class="keyword"> Audience Manager</span> user ID value in a key-value pair. </p> <p>Use <code><i>d_uuid</i></code> if you're passing in the <span class="keyword"> Audience Manager</span> user ID. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ mid =<i>ID de usuario de Experience Cloud</i></code> </p> </td> 
   <td colname="col2"> <p>This is the unique user ID key that holds the <span class="keyword"> Experience Cloud</span> user ID value in a key-value pair. See also <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Get the User ID from the ID Service Cookie</a>. </p> <p>Use <i><code> d_mid</code></i> if you're passing in a <span class="keyword"> Experience Cloud</span> ID captured from the <span class="keyword"> Experience Cloud</span> ID service. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_ cb =<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Parámetros opcionales de respuesta. </p> <p> None of these are required to send data to the <span class="wintitle"> DCS</span>. However, if you want the <span class="wintitle"> DCS</span> to return a response, you must include <i><code> d_rtbd=json</code></i> in your request. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Respuesta de ejemplo {#sample-response}

See [Receive Data From the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
