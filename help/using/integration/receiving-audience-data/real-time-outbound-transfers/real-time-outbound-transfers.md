---
description: El proceso de transferencia de datos en tiempo real saliente devuelve datos de usuario como una serie de objetos JSON pasados con un método POST.
seo-description: El proceso de transferencia de datos en tiempo real saliente devuelve datos de usuario como una serie de objetos JSON pasados con un método POST.
seo-title: Transferencias de datos salientes en tiempo real
solution: Audience Manager
title: Transferencias de datos salientes en tiempo real
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: 425315a0a6aa739a90e34deb270ac21df9b88d31

---


# Transferencias de datos salientes en tiempo real {#real-time-outbound-data-transfers}

El proceso de transferencia de datos en tiempo real saliente devuelve datos de usuario como una serie de [!DNL JSON] objetos pasados con un `POST` método.

<!-- c_outbound_json.xml -->

## Las actividades de

Para utilizar este método, recomendamos que el socio de datos:

* Acepta datos en [!DNL JSON] formato.
* Proporciona una dirección URL que puede utilizar la `POST` llamada para devolver datos.
* Acepta transferencias `HTTPS` de datos seguras. [!DNL Audience Manager] no enviará este archivo con el protocolo no seguro `HTTP` .

## Frecuencia

Este método de transferencia de datos puede enviar datos en tiempo casi real a medida que los usuarios cumplen los requisitos para los segmentos. Además, este método puede enviar lotes de datos sin conexión o incorporados con la misma frecuencia que cada 24 horas.

## Respuestas obligatorias

De forma predeterminada, el servidor destinatario debe devolver el `200 OK` código para indicar que se ha recibido correctamente. Otros códigos se interpretarán como errores. Esta respuesta se espera en 3000 milisegundos. En respuesta a un error, solo [!DNL Audience Manager] realizará 1 intento de reintento.

## Parámetros

La siguiente tabla define los elementos del archivo [!DNL JSON] de datos devuelto.

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
   <td colname="col3"> <p>ID que indica si el archivo contiene ID de Android o iOS. Utiliza los siguientes valores de ID: </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">ID de Android (GAID): <code> 2014</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">ID de iOS (IDFA): <code> 2015</code> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>ID de cliente que utiliza el sistema al que envía los datos. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>ID que le ha asignado su socio de destino. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>Número total de usuarios en la solicitud <code> POST</code> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Usuarios</i></code> </td> 
   <td colname="col2"> <p>Matriz </p> </td> 
   <td colname="col3"> <p>Matriz de objetos de usuario. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>UUID de <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>UUID del socio de datos. Déjelo en blanco si su socio de datos no tiene un UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Region</i></code> </td> 
   <td colname="col2"> Matriz </td> 
   <td colname="col3"> ID de región de <span class="keyword"> Audience Manager</span> donde hemos visto este dispositivo. Por ejemplo, si el dispositivo tuviera alguna actividad en París (Europa), el ID de región sería <code> 6</code>. Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS Region IDs, Locations, and Host Names</a> (ID de región de DCS, ubicaciones y nombres de host). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmentos</i></code> </td> 
   <td colname="col2"> <p>Matriz </p> </td> 
   <td colname="col3"> <p>Matriz de objetos de segmento. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>Asignación del destino de ID de segmento. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Estado</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>Define el estado de un usuario en el segmento. Acepta lo siguiente: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Activo (predeterminado) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inactivo, no elegido o no segmentado. </li> 
    </ul> <p>Los usuarios no están segmentados cuando: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Se ha eliminado de un segmento en función de la regla de segmento. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Se ha eliminado de un segmento en función del intervalo <a href="../../../features/traits/segment-ttl-explained.md"> de tiempo de vida</a>del segmento. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Se ha movido a un estado inactivo si no se han visto en los últimos 120 días. </li> 
    </ul> <p>Todos los ID de socio sincronizados con un ID de <span class="keyword"> Audience Manager</span> recibirán el indicador <code> "Estado":"0"</code> cuando un usuario no está segmentado. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>La hora de la clasificación de segmentos más reciente.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Seguridad

Puede asegurar el proceso de transferencia de datos saliente en tiempo real [firmando solicitudes](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) HTTP con claves privadas o haciendo que [!DNL Audience Manager] se autentique mediante el protocolo [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) .

## Ejemplo de código

Una respuesta de datos en tiempo real puede tener un aspecto similar al siguiente:

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
