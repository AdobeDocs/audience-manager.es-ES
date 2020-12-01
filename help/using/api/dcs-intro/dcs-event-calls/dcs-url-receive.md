---
description: Continúe aquí para obtener información sobre cómo solicitar una respuesta de DCS en una llamada /evento. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.
seo-description: Continúe aquí para obtener información sobre cómo solicitar una respuesta de DCS en una llamada /evento. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.
seo-title: Recibir datos del DCS
solution: Audience Manager
title: Recibir datos del DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 5%

---


# Recibir datos del DCS {#receive-data-from-the-dcs}

Continúe aquí para obtener información sobre cómo solicitar una respuesta [!DNL DCS] en una llamada `/event`. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.

Antes de revisar este contenido, consulte [Enviar datos al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parámetros de respuesta de DCS: Una revisión {#dcs-response-parameters}

Su solicitud [!DNL DCS] debe incluir `d_rtbd=json` si desea recibir una respuesta de [!DNL DCS]. El [!DNL DCS] no devolverá datos si omite este parámetro. Una llamada básica a [!DNL DCS] para solicitar datos utiliza esta sintaxis:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Respuesta de ejemplo {#sample-response}

Recuerde que, a partir de la documentación de [Envío de datos a DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md), la compañía ficticia [!DNL Acme, Inc.] realizó esta llamada:

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

La siguiente tabla lista y define los parámetros más comunes que puede ver en una respuesta de [!DNL DCS]. Esto se aplica a llamadas de evento u otras consultas [!DNL DCS] [!DNL API] que devuelven datos.

| Parámetro | Descripción |
|--- |--- |
| `c` | Dirección URL que se ha establecido como [destino de dirección URL](../../../features/destinations/create-url-destination.md). |
| `cn` | Nombre o ID establecidos en el campo de nombre de la cookie de un [destino de cookie](../../../features/destinations/create-cookie-destination.md). |
| `cv` | Valores enviados al destino definido por el parámetro &quot;cn&quot;:&quot; nombre de destino&quot;. |
| `dcs_region` | El [DCS de servidor a servidor llama](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Este objeto contiene información para todos los destinos URL configurados en la interfaz de usuario. La lista de este objeto es dinámica en función de las acciones del usuario. |
| `dmn` | Dominio especificado en el campo Dominio de la cookie para un destino de cookie. Consulte [Configuración opcional para destinos de cookies](../../../features/destinations/cookie-destination-options.md).  Para integraciones de servidor a servidor, recomendamos usar un dominio como `aam-api.com`. |
| `e` | Dirección URL segura que se ha establecido en un destino de dirección URL. |
| `stuff` | Este objeto contiene información para todos los destinos de Cookie. La lista de este objeto es dinámica en función de las acciones del usuario. |
| `tid` | ID de transacción, que es un ID exclusivo de 12 caracteres utilizado para la depuración. Cada llamada /evento al DCS recibe un tid al que puede hacer referencia en consultas de soporte para obtener una respuesta mejor y más rápida. |
| `ttl` | El valor de tiempo de vida de la cookie en días. |
| `u` y `uuid` | ID de usuario único asignado por el Audience Manager. Esto es necesario si realiza [llamadas de servidor a servidor a DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Tipo de destino, iFrame (`iframe`) o imagen (`img`). |

>[!MORELIKETHIS]
>
>* [Prefijos y variables de clave-valor compatibles con DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

