---
description: Continúe aquí para obtener información sobre cómo solicitar una respuesta de DCS en una llamada /event. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.
seo-description: Continúe aquí para obtener información sobre cómo solicitar una respuesta de DCS en una llamada /event. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.
seo-title: Recibir datos del DCS
solution: Audience Manager
title: Recibir datos del DCS
uuid: fbb 77197-8530-48 a 8-b 708-d 785 f 7214494
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Receive Data From the DCS {#receive-data-from-the-dcs}

Continue here for information about how to request a [!UICONTROL DCS] response in a `/event` call. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.

Before reviewing this content, see [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS Response Parameters: A Review {#dcs-response-parameters}

Your [!UICONTROL DCS] request must include `d_rtbd=json` if you want to receive a response from the [!UICONTROL DCS]. The [!UICONTROL DCS] will not return data if you omit this parameter. A basic call to the [!UICONTROL DCS] to request data uses this syntax:

<pre><code>https://domain alias.demdex.net/event<i></i>?<i>key 1</i>= <i>val 1</i>, &amp;<i>key 2</i>= <i>val 2</i>&amp; d_ dst = 1 &amp; d_ rtbd = json &amp; d_ cb =<i>callback</i></code>
</pre>

## Respuesta de ejemplo {#sample-response}

Recall that from the [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) documentation, the fictional company [!DNL Acme, Inc.] made this call:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

As this call includes the required response parameter, the [!UICONTROL DCS] sent back the [!DNL JSON] object shown below. El suyo puede ser similar o más complejo.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parámetros de repuesta {#response-parameters}

The table below lists and defines the more common parameters you may see in a response from the [!UICONTROL DCS]. This applies to event calls or other [!UICONTROL DCS] [!DNL API] queries that return data.

| Parámetro | Descripción |
|--- |--- |
| `c` | A URL that has been set as a [URL destination](../../../features/destinations/manage-destinations.md#configure-url-destination). |
| `cn` | The name or ID set in the cookie name field of a [cookie destination](../../../features/destinations/manage-destinations.md#create-cookie-destination). |
| `cv` | Valores enviados al destino definido por «cn»: parámetro "destinaton name". |
| `dcs_region` | The [server-to-server DCS calls](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Este objeto contiene información para todos los destinos URL configurados en la interfaz de usuario. La lista de objetos es dinámica en función de las acciones del usuario. |
| `dmn` | Este es el dominio especificado en el campo Dominio de cookie para un destino de cookie. See [Optional Settings for Cookie Destinations](../../../features/destinations/manage-destinations.md#optional-settings-cookies).  For  Server to Server integrations we recommend using a domain like `aam-api.com`. |
| `e` | La URL segura que se ha configurado en un destino de URL. |
| `stuff` | Este objeto contiene información para todos los destinos de Cookie. La lista de objetos es dinámica en función de las acciones del usuario. |
| `tid` | ID de transacción, que es un ID exclusivo de 12 caracteres utilizado con fines de depuración. Cada llamada /event al DCS recibe un tid que puede hacer referencia en las instalaciones de soporte para obtener una respuesta mejor y más rápida. |
| `ttl` | El valor de tiempo de vida de la cookie en días. |
| `u` y `uuid` | ID de usuario único asignado por Audience Manager. This is required if you're making [server-to-server DCS calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Destination type,  iFrame (`iframe`) or image (`img`). |

>[!MORE_ LIKE_ THIS]
>
>* [Prefijos y variables de valor clave admitidos por el DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

