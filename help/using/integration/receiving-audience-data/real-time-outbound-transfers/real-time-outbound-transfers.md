---
description: El proceso de transferencia de datos saliente en tiempo real devuelve los datos del usuario como una serie de objetos JSON pasados con un método POST.
seo-description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-title: Real-Time Outbound Data Transfers
solution: Audience Manager
title: Transferencias de datos salientes en tiempo real
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
exl-id: 12aee831-1a44-4cd6-aeba-7738a584dfe7
source-git-commit: 0245dd11de31c3139c5df5dc78100f0d3935aa2e
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 2%

---

# Transferencias de datos salientes en tiempo real {#real-time-outbound-data-transfers}

El proceso saliente de transferencia de datos en tiempo real envía datos de usuario como una serie de [!DNL JSON] mensajes con formato a una plataforma de destino.

<!-- c_outbound_json.xml -->

## Las actividades de

Para utilizar este método, la plataforma de destino debe cumplir los siguientes requisitos:

* Debe proporcionar un extremo [!DNL URL] que se pueda escalar para recibir un gran volumen de mensajes de Audience Manager;
* Debe aceptar datos en formato [!DNL JSON] (`Content-type: application/json`);
* Debe aceptar transferencias de datos seguras de `HTTPS`. [!DNL Audience Manager] no enviará mensajes a través del protocolo no seguro `HTTP`.

## Frecuencia

Este método de transferencia de datos puede enviar datos en tiempo casi real a medida que los usuarios cumplen los requisitos para los segmentos. Los mensajes en tiempo real solo se entregan mientras el usuario está en línea y es visible de forma activa en la red Edge de Audience Manager. De forma opcional, este método también puede enviar lotes de datos sin conexión o incorporados con la misma frecuencia que cada 24 horas.

## Transferencias por lotes

Tanto las transferencias en tiempo real como las por lotes se envían al mismo punto de conexión y utilizan el mismo formato de mensaje. Cuando se habilitan las transferencias por lotes, la plataforma de destino ve un pico en el volumen de mensajes mientras se entregan los mensajes por lotes. Muchas de las clasificaciones de segmentos enviadas a través de mensajes en tiempo real se repetirán en los mensajes por lotes. Las transferencias por lotes solo incluirán las clasificaciones de segmentos (o las que anulen las clasificaciones) que hayan cambiado desde que se entregó el último lote.

## Límites de velocidad

No hay límites de velocidad establecidos en el rendimiento de los mensajes enviados. Establecer límites de velocidad podría provocar la pérdida de datos.

## Respuestas requeridas

De forma predeterminada, el servidor de destinatarios debe devolver el código `200 OK` para indicar que la confirmación se ha realizado correctamente. Otros códigos se interpretarán como errores. Esta respuesta se espera dentro de los 3000 milisegundos. En respuesta a un error, [!DNL Audience Manager] realizará un solo intento de reintento.

## Parámetros

En la tabla siguiente se definen los elementos del archivo de datos [!DNL JSON] que se envían al destino.

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
   <td colname="col3"> <p>Identificador que indica el tipo de identificadores de dispositivo contenidos en el mensaje, en la propiedad User.DataPartner_UUID. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">ID de iOS (IDFA): <code> 20915</code> </li>
     <li>ID de cookies/web: varía según la plataforma de destino</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Representa la cuenta de destino en la plataforma de destino. Este ID se origina desde la plataforma de destino.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>ID del objeto "destination" de Audience Manager. Este ID se origina desde Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>Número total de usuarios en la solicitud <code> POST</code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>Matriz </p> </td> 
   <td colname="col3"> <p>Matriz de objetos de usuario. De forma predeterminada, cada mensaje contiene entre 1 y 10 usuarios, para mantener un tamaño de mensaje óptimo. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>El UUID <span class="keyword"> de Audience Manager</span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>UUID de la plataforma de destino o ID del dispositivo global. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> Matriz </td> 
   <td colname="col3"> El ID de región Audience Manager<span class="keyword"> </span> donde hemos visto este dispositivo. Por ejemplo, si el dispositivo tuviera alguna actividad en París (Europa), el ID de región sería <code> 6</code>. Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> ID de región de DCS, ubicaciones y nombres de host</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Matriz </p> </td> 
   <td colname="col3"> <p>Matriz de objetos de segmento. Para los mensajes en tiempo real, la matriz contiene todos los segmentos a los que pertenece el usuario. Para los mensajes por lotes, la matriz solo contiene cambios de segmento desde el último lote.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>El identificador del segmento. En la mayoría de los casos, este es el ID del segmento generado por Audience Manager (un número entero). En algunos casos, si la plataforma de destino lo permite, los clientes pueden definir el identificador del segmento en la interfaz de usuario de Audience Manager (campo de texto abierto), que luego se reflejaría en esta propiedad. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Número entero </p> </td> 
   <td colname="col3"> <p>Define el estado de un usuario en el segmento. Acepta los siguientes valores: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Activo (predeterminado) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inactivo, excluido o no segmentado. </li> 
    </ul> <p>Los usuarios no están segmentados cuando: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Se ha eliminado de un segmento según la regla de segmento. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Se eliminó de un segmento en función del intervalo de duración <a href="../../../features/traits/segment-ttl-explained.md"> del segmento</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Se mueve a un estado inactivo si no se han visto en los últimos 120 días. </li>
     <li>Se eliminó debido a una solicitud de cambio de privacidad (es decir, <span class="keyword"> RGPD</span>)</li>
    </ul> <p>Todos los identificadores de socio sincronizados con un identificador Audience Manager<span class="keyword"> de </span> recibirán el marcador <code> "Status":"0"</code> cuando un usuario no esté segmentado. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Hora a la que se verificó la calificación del segmento de usuario por última vez.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Seguridad

Puede asegurar su proceso de transferencia de datos salientes en tiempo real [firmando solicitudes HTTP](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) con claves privadas o haciendo que [!DNL Audience Manager] se autentique a través del protocolo [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md).

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
