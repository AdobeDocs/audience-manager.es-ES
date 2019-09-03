---
description: El proceso de transferencia de datos en tiempo real saliente devuelve datos de usuario como una serie de objetos JSON pasados con un método POST.
seo-description: El proceso de transferencia de datos en tiempo real saliente devuelve datos de usuario como una serie de objetos JSON pasados con un método POST.
seo-title: Transferencias de datos salientes en tiempo real
solution: Audience Manager
title: Transferencias de datos salientes en tiempo real
uuid: 1895 e 818-7 ab 8-4569-a 920-4 b 0 a 4 c 8 b 83 d 2
translation-type: tm+mt
source-git-commit: 425315a0a6aa739a90e34deb270ac21df9b88d31

---


# Transferencias de datos salientes en tiempo real {#real-time-outbound-data-transfers}

El proceso de transferencia de datos en tiempo real saliente devuelve datos de usuario como una serie de [!DNL JSON] objetos pasados con `POST` un método.

<!-- c_outbound_json.xml -->

## Las actividades de

Para utilizar este método, recomendamos que el socio de datos:

* Acepta datos en [!DNL JSON] formato.
* Proporciona una URL que puede utilizar `POST` la llamada para devolver datos.
* Acepta transferencias de `HTTPS` datos seguras. [!DNL Audience Manager] no enviará este archivo con `HTTP` el protocolo no seguro.

## Frecuencia

Este método de transferencia de datos puede enviar datos casi en tiempo real a medida que los usuarios cumplen los segmentos. Además, este método puede enviar lotes de datos sin conexión o onbotados con tanta frecuencia como cada 24 horas.

## Respuestas requeridas

De forma predeterminada, el servidor destinatario debe devolver `200 OK` el código para indicar que se ha recibido correctamente. Otros códigos se interpretarán como errores. Se espera que esta respuesta sea de 3000 milisegundos. Como respuesta a un error, [!DNL Audience Manager] realizará 1 intento de reintento solamente.

## Parámetros

La tabla siguiente define los elementos del archivo [!DNL JSON] de datos devuelto.

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
   <td colname="col1"> <code><i>Processtime</i></code> </td> 
   <td colname="col2"> <p>Datetime </p> </td> 
   <td colname="col3"> <p>Hora en la que se ejecutó la solicitud. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_ DPID</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>ID que indica si el archivo contiene ID de Android o iOS. Utiliza los siguientes valores de ID: </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">ID de Android (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">ID de iOS (IDFA): <code> 20915</code> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ ID</i></code> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>ID de cliente utilizado por el sistema al que está enviando datos. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ Destination_ ID</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>El ID asignado por su socio de destino. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_ count</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>Número total de usuarios en la solicitud <code> POST</code> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Usuarios</i></code> </td> 
   <td colname="col2"> <p>Matriz </p> </td> 
   <td colname="col3"> <p>Matriz de objetos de usuario. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ UUID</i></code> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>El UUID <span class="keyword"> de Audience Manager</span> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Datapartner_ UUID</i></code> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>UUID de socio de datos. Deje en blanco si el socio de datos no tiene un UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ Regions</i></code> </td> 
   <td colname="col2"> Matriz </td> 
   <td colname="col3"> ID de región <span class="keyword"> de Audience Manager</span> en el que hemos visto este dispositivo. Por ejemplo, si el dispositivo tenía alguna actividad en París (Europa), el ID de región sería <code> 6</code>. Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS Region IDs, Locations, and Host Names</a> (ID de región de DCS, ubicaciones y nombres de host). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmentos</i></code> </td> 
   <td colname="col2"> <p>Matriz </p> </td> 
   <td colname="col3"> <p>Matriz de objetos de segmento. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment_ ID</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>Asignación de destino de ID de segmento. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Estado</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>Define el estado de un usuario en el segmento. Acepta lo siguiente: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Activo (predeterminado) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inactivo, excluido o sin segmentar. </li> 
    </ul> <p>Los usuarios no están segmentados cuando son: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Se eliminó de un segmento basado en la regla de segmento. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Se eliminó de un segmento basado en el intervalo <a href="../../../features/traits/segment-ttl-explained.md"> de tiempo de vida del segmento</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Se ha trasladado a estado inactivo si no se han visto durante los últimos 120 días. </li> 
    </ul> <p>Todos los ID de socio sincronizados con un ID <span class="keyword"> de Audience Manager</span> recibirán el <code> estado "Estado": indicador "0"</code> cuando un usuario no está segmentado. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Datetime</i></code> </td> 
   <td colname="col2"> <p>Datetime </p> </td> 
   <td colname="col3"> <p>La hora de la calificación de segmentos más reciente.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Seguridad

Puede asegurar el proceso de transferencia de datos saliente en tiempo real [mediante la firma de solicitudes](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) HTTP mediante claves privadas o [!DNL Audience Manager] la autenticación mediante el protocolo [oauth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) .

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
