---
description: Continúe aquí para obtener información sobre cómo solicitar una respuesta de DCS en una llamada /event. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes de una respuesta.
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: Recibir datos del DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 1%

---

# Recibir datos del DCS {#receive-data-from-the-dcs}

Continúe aquí para obtener información sobre cómo solicitar una respuesta de [!DNL DCS] en una llamada de `/event`. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes de una respuesta.

Antes de revisar este contenido, consulte [Enviar datos al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parámetros de respuesta de DCS: una revisión {#dcs-response-parameters}

Su solicitud de [!DNL DCS] debe incluir `d_rtbd=json` si desea recibir una respuesta de [!DNL DCS]. [!DNL DCS] no devolverá datos si omite este parámetro. Una llamada básica a [!DNL DCS] para solicitar datos usa esta sintaxis:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Respuesta de ejemplo {#sample-response}

Recuerde que de la documentación de [Enviar datos al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md), la compañía ficticia [!DNL Acme, Inc.] hizo esta llamada:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Como esta llamada incluye el parámetro de respuesta requerido, [!DNL DCS] devolvió el objeto [!DNL JSON] que se muestra a continuación. El suyo puede ser similar o más complejo.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parámetros de respuesta {#response-parameters}

En la tabla siguiente se enumeran y definen los parámetros más comunes que puede ver en una respuesta de [!DNL DCS]. Esto se aplica a las llamadas de evento u otras [!DNL DCS] [!DNL API] consultas que devuelven datos.

| Parámetro | Descripción |
|--- |--- |
| `c` | Una dirección URL que se ha establecido como [destino URL](../../../features/destinations/create-url-destination.md). |
| `cn` | El nombre o ID establecido en el campo de nombre de cookie de un [destino de cookie](../../../features/destinations/create-cookie-destination.md). |
| `cv` | Los valores enviados al destino definido por el parámetro &quot;cn&quot;: &quot;nombre de destino&quot;. |
| `dcs_region` | Las [llamadas DCS de servidor a servidor](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Este objeto contiene información para todos los destinos URL configurados en la interfaz de usuario. La lista de este objeto es dinámica en función de las acciones del usuario. |
| `dmn` | Este es el dominio especificado en el campo Dominio de cookies para un destino de cookie. Consulte [Configuración opcional para destinos de cookies](../../../features/destinations/cookie-destination-options.md).  Para integraciones de servidor a servidor recomendamos usar un dominio como `aam-api.com`. |
| `e` | La dirección URL segura que se ha establecido en un destino de dirección URL. |
| `stuff` | Este objeto contiene información para todos los destinos de cookies. La lista de este objeto es dinámica en función de las acciones del usuario. |
| `tid` | ID de transacción, que es un ID único de 12 caracteres que se utiliza para la depuración. Cada llamada /event al DCS recibe un tid al que puede hacer referencia en las consultas de soporte para obtener una respuesta mejor y más rápida. |
| `ttl` | El valor de tiempo de vida de la cookie en días. |
| `u` y `uuid` | ID único de usuario asignado por el Audience Manager. Esto es necesario si realiza [llamadas de DCS de servidor a servidor](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Tipo de destino, iFrame (`iframe`) o imagen (`img`). |

>[!MORELIKETHIS]
>
>* [Prefijos clave-valor y variables compatibles con el DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
