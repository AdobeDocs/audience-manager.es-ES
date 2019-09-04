---
seo-title: Realización de llamadas de API de servidor a servidor
solution: Audience Manager
title: Realización de llamadas de API de servidor a servidor
uuid: bdfe 3430-e 27 f -4 a 5 c -88 d 9-ae 164 d 28 f 601
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Realización de llamadas de API de servidor a servidor {#making-server-to-server-dcs-api-calls}

Las llamadas requieren el nombre de host del servidor DCS regional y el ID de usuario. Si no tiene los ID de usuario y región requeridos, consulte [Obtención de ID de usuario y regiones desde una respuesta](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) de DCS o [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Una vez que tenga ID de usuarios y regiones, puede realizar llamadas de servidor a servidor al DCS. Consulte esta sección para obtener sintaxis y ejemplos.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Sustituya un valor real del marcador de posición cuando realice llamadas de servidor a servidor al [!UICONTROL DCS].

## Sintaxis y ejemplo de llamada {#call-syntax-example}

Una solicitud básica de servidor a servidor que envía datos a los [!UICONTROL DCS] usuarios usa la sintaxis que se muestra a continuación.

<pre><code>" Host:<i>domain alias</i>. demdex. net "" https://DCS<i>host name.demdex.net/event?d_rtbd=json&amp;d_jsonv=1&amp;d_uuid=user</i><i>ID</i>.</code></pre>

Un ejemplo de llamada de muestra es similar al siguiente ejemplo.

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
   <td colname="col1"> <p><code><i>domain alias</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>Esta parte de la llamada contiene: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">El alias de dominio asignado por <span class="keyword"> Audience Manager</span> (p. ej. <i><code> my_ domain. demdex. net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Dominio de destino, que siempre es <i><code> demdex. net</code></i>. Consulte <a href="../../../reference/demdex-calls.md">Explicación de las llamadas al dominio Demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>Nombre de host DCS</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>El parámetro host de encabezado http que muestra el nombre del servidor <span class="wintitle"> DCS</span> regional. El nombre de host está ligado a un ID de región, por eso es necesario antes de realizar estos tipos de llamadas. Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS Region IDs, Locations, and Host Names</a> (ID de región de DCS, ubicaciones y nombres de host). </p> </td> 
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
   <td colname="col2"> <p>Esta es la clave única de ID de usuario que contiene el valor de ID de usuario <span class="keyword"> de Audience Manager</span> en un par clave-valor. </p> <p>Utilice <code><i>d_ uuid</i></code> si va a pasar el ID de usuario <span class="keyword"> de Audience Manager</span> . </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ mid =<i>ID de usuario de Experience Cloud</i></code> </p> </td> 
   <td colname="col2"> <p>Esta es la clave única de ID de usuario que contiene el valor de ID de usuario <span class="keyword"> de Experience Cloud</span> en un par clave-valor. Consulte también <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Obtención del ID de usuario desde la cookie del servicio de ID</a>. </p> <p>Utilice <i><code> d_ mid</code></i> si va a pasar un ID <span class="keyword"> de Experience Cloud</span> capturado desde <span class="keyword"> el servicio Experience Cloud</span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_ cb =<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Parámetros opcionales de respuesta. </p> <p> No se requiere ninguna de ellas para enviar datos al <span class="wintitle"> DCS</span>. Sin embargo, si desea que <span class="wintitle"> el DCS</span> devuelva una respuesta, debe incluir <i><code> d_ rtbd = json</code></i> en su solicitud. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Respuesta de ejemplo {#sample-response}

Consulte [Recepción de datos del DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
