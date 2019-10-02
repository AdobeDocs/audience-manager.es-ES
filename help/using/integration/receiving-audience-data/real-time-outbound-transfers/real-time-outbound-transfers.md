---
description: El proceso de transferencia de datos en tiempo real saliente devuelve datos de usuario como una serie de objetos JSON pasados con un método POST.
seo-description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-title: Real-Time Outbound Data Transfers
solution: Audience Manager
title: Transferencias de datos salientes en tiempo real
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: 4e84682dea46f5b6c76464c66199f7a468bec334

---


# Transferencias de datos salientes en tiempo real {#real-time-outbound-data-transfers}

El proceso de transferencia de datos en tiempo real saliente ofrece datos de usuario como una serie de mensajes con [!DNL JSON] formato a una plataforma de destino.

<!-- c_outbound_json.xml -->

## Las actividades de

Para utilizar este método, la plataforma de destino debe cumplir los siguientes requisitos:

* Debe proporcionar un punto final [!DNL URL] que pueda escalarse para recibir un gran volumen de mensajes de Audience Manager;
* Deberá aceptar datos en [!DNL JSON] formato (`Content-type: application/json`);
* Debe aceptar transferencias `HTTPS` de datos seguras. [!DNL Audience Manager] no enviará mensajes a través del protocolo no seguro `HTTP` .

## Frecuencia

This data transfer method can send data in near real-time as users qualify for segments. Real-time messages are only delivered while the user is online and actively visible to the Audience Manager Edge network. Opcionalmente, este método también puede enviar lotes de datos sin conexión o incorporados con la misma frecuencia que cada 24 horas.

## Transferencias por lotes

Both real-time and batch transfers are sent to the same endpoint and use the same message format. Cuando se habilitan las transferencias por lotes, la plataforma de destino verá un pico en el volumen de mensajes mientras se entregan los mensajes por lotes. Muchas de las cualificaciones de los segmentos enviadas a través de mensajes en tiempo real se repetirán en los mensajes por lotes. Las transferencias por lotes incluyen únicamente las cualificaciones de los segmentos (o anulaciones de cualificaciones) que han cambiado desde que se entregó el último lote.

## Rate Limits

No hay límites de velocidad establecidos en el rendimiento de los mensajes entregados. Setting rate limits could lead to data loss.

## Required Responses

By default, the recipient server must return the  code to indicate successful receipt. `200 OK` Otros códigos se interpretarán como errores. This response is expected within 3000 milliseconds. En respuesta a un error, solo [!DNL Audience Manager] realizará un intento de reintento.

## Parámetros

La siguiente tabla define los elementos del archivo de datos que se envían al destino [!DNL JSON] .

<table id="table_68475F9D01ED4A44B5909234114AEDE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Tipo de datos </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>ProcessTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Hora a la que se ejecutó la solicitud. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>ID que indica el tipo de ID de dispositivo contenido en el mensaje, en la propiedad User.DataPartner_UUID. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">ID de Android (GAID): <code> 2014</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">ID de iOS (IDFA): <code> 2015</code> </li>
     <li>ID de web/cookie: varía según la plataforma de destino</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Representa la cuenta de destino en la plataforma de destino. Este ID se origina en la plataforma de destino.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>ID del objeto "destino" de Audience Manager. Este ID se origina en Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>Total number of users in the  POST request.<code></code> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Usuarios</i></code> </td> 
   <td colname="col2"> <p>Matriz </p> </td> 
   <td colname="col3"> <p>Matriz de objetos de usuario. By default, each message will contain between 1 and 10 users, to keep the message size optimal. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>The  Audience Manager UUID.<span class="keyword"></span> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>UUID de plataforma de destino o ID de dispositivo global. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Region</i></code> </td> 
   <td colname="col2"> Matriz </td> 
   <td colname="col3"> ID de región de <span class="keyword"> Audience Manager</span> donde hemos visto este dispositivo. Por ejemplo, si el dispositivo tuviera alguna actividad en París (Europa), el ID de región sería <code> 6</code>. Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS Region IDs, Locations, and Host Names</a> (ID de región de DCS, ubicaciones y nombres de host). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmentos</i></code> </td> 
   <td colname="col2"> <p>Matriz </p> </td> 
   <td colname="col3"> <p>Matriz de objetos de segmento. Para los mensajes en tiempo real, la matriz contiene todos los segmentos a los que pertenece el usuario. For batch messages, the array contains only segment changes since the last batch.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmnent.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>The identifier for the segment. En la mayoría de los casos, es el ID de segmento generado por Audience Manager (un entero). En algunos casos, si la plataforma de destino lo permite, los clientes pueden definir el identificador de segmento en la interfaz de usuario de Audience Manager (campo de texto abierto), que luego se reflejaría en esta propiedad. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>Defines the status of a user in the segment. Accepts the following values: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Activo (predeterminado) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inactivo, no elegido o no segmentado. </li> 
    </ul> <p>Los usuarios no están segmentados cuando: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Se ha eliminado de un segmento en función de la regla de segmento. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Se ha eliminado de un segmento en función del intervalo <a href="../../../features/traits/segment-ttl-explained.md"> de tiempo de vida</a>del segmento. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Moved to an inactive state if they have not been seen for the last 120-days. </li>
     <li>Removed due to a privacy change request (i.e. [!DNL GDPR])</li>
    </ul> <p>All partner IDs that are synced to an  Audience Manager ID will receive the  "Status":"0" flag when a user is unsegmented.<span class="keyword"></span><code></code> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Hora en la que se verificó más recientemente la cualificación de segmento de usuario.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Seguridad

Puede asegurar el proceso de transferencia de datos saliente en tiempo real [firmando solicitudes](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) HTTP con claves privadas o haciendo que [!DNL Audience Manager] se autentique mediante el protocolo [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) .

## Solicitud

Una solicitud en tiempo real puede tener un aspecto similar al siguiente:

```js
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{  
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         },
         {
            "Segment_ID": "12176",
            "Status": "0",  
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   },
   {
   "AAM_UUID": "0578240750487542456854736923319946899715232",
   "DataPartner_UUID": "848457757347734",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "10329",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
         },
         {
            "Segment_ID": "23954",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
        }]
    }]
}
```
