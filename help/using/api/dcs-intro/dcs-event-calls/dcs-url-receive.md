---
description: Continúe aquí para obtener información sobre cómo solicitar una respuesta de DCS en una llamada /event. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.
seo-description: Continúe aquí para obtener información sobre cómo solicitar una respuesta de DCS en una llamada /event. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.
seo-title: Recibir datos del DCS
solution: Audience Manager
title: Recibir datos del DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 5%

---

# Recibir datos del DCS {#receive-data-from-the-dcs}

Continúe aquí para obtener información sobre cómo solicitar una respuesta [!DNL DCS] en una llamada `/event`. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.

Antes de revisar este contenido, consulte [Envío de datos al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parámetros de respuesta de DCS: Una revisión {#dcs-response-parameters}

Su solicitud [!DNL DCS] debe incluir `d_rtbd=json` si desea recibir una respuesta de [!DNL DCS]. El [!DNL DCS] no devolverá datos si omite este parámetro. Una llamada básica a [!DNL DCS] para solicitar datos utiliza esta sintaxis:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Respuesta de ejemplo {#sample-response}

Recuerde que desde la documentación [Send Data to DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md), la empresa ficticia [!DNL Acme, Inc.] realizó esta llamada:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Como esta llamada incluye el parámetro de respuesta requerido, el [!DNL DCS] devuelve el objeto [!DNL JSON] que se muestra a continuación. El suyo puede ser similar o más complejo.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parámetros de repuesta {#response-parameters}

La siguiente tabla enumera y define los parámetros más comunes que puede ver en una respuesta de [!DNL DCS]. Esto se aplica a las llamadas de evento u otras [!DNL DCS] [!DNL API] consultas que devuelven datos.

| Parámetro | Descripción |
|--- |--- |
| `c` | Una dirección URL que se ha establecido como [dirección URL de destino](../../../features/destinations/create-url-destination.md). |
| `cn` | El nombre o ID definido en el campo nombre de cookie de un [destino de cookie](../../../features/destinations/create-cookie-destination.md). |
| `cv` | Los valores enviados al destino definido por el parámetro &quot;cn&quot;:&quot; nombre de destino. |
| `dcs_region` | Las [llamadas del DCS de servidor a servidor](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Este objeto contiene información para todos los destinos URL que están configurados en la interfaz de usuario de . La lista de este objeto es dinámica en función de las acciones del usuario. |
| `dmn` | Este es el dominio especificado en el campo Dominio de cookie para un destino de cookie. Consulte [Configuración opcional para destinos de cookies](../../../features/destinations/cookie-destination-options.md).  Para integraciones de servidor a servidor recomendamos utilizar un dominio como `aam-api.com`. |
| `e` | La dirección URL segura que se ha establecido en un destino de URL. |
| `stuff` | Este objeto contiene información para todos los destinos de cookies. La lista de este objeto es dinámica en función de las acciones del usuario. |
| `tid` | ID de transacción, que es un ID de 12 caracteres único que se utiliza para la depuración. Cada llamada /event al DCS recibe un tid al que puede hacer referencia en consultas de soporte para obtener una respuesta mejor y más rápida. |
| `ttl` | El valor de tiempo de vida de la cookie, en días. |
| `u` y `uuid` | ID de usuario único asignado por el Audience Manager. Esto es necesario si está realizando [llamadas DCS de servidor a servidor](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Tipo de destino, iFrame (`iframe`) o imagen (`img`). |

>[!MORELIKETHIS]
>
>* [Prefijos y variables de clave-valor compatibles con el DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

