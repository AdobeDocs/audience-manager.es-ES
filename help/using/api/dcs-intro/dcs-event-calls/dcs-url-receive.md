---
description: Continúe aquí para obtener información sobre cómo solicitar una respuesta de DCS en una llamada /event. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.
seo-description: Continúe aquí para obtener información sobre cómo solicitar una respuesta de DCS en una llamada /event. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.
seo-title: Recibir datos del DCS
solution: Audience Manager
title: Recibir datos del DCS
uuid: fbb 77197-8530-48 a 8-b 708-d 785 f 7214494
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# Recibir datos del DCS {#receive-data-from-the-dcs}

Continúe aquí para obtener información sobre cómo solicitar [!UICONTROL DCS] una respuesta en `/event` una llamada. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.

Antes de revisar este contenido, consulte [Enviar datos al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parámetros de respuesta de DCS: Una revisión {#dcs-response-parameters}

Su [!UICONTROL DCS] solicitud debe incluir `d_rtbd=json` si desea recibir una respuesta del [!UICONTROL DCS]. No [!UICONTROL DCS] devolverá datos si omite este parámetro. Una llamada básica a la [!UICONTROL DCS] solicitud de datos usa esta sintaxis:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Respuesta de ejemplo {#sample-response}

Recuerde que, desde [Enviar datos a](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) la documentación de DCS, la empresa ficticia [!DNL Acme, Inc.] realizó esta llamada:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Dado que esta llamada incluye el parámetro de respuesta requerido, se [!UICONTROL DCS] devuelve el [!DNL JSON] objeto que se muestra a continuación. El suyo puede ser similar o más complejo.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parámetros de repuesta {#response-parameters}

La tabla siguiente enumera y define los parámetros más comunes que puede ver en una respuesta del [!UICONTROL DCS]. Esto se aplica a las llamadas de evento u otras [!UICONTROL DCS][!DNL API] consultas que devuelven datos.

| Parámetro | Descripción |
|--- |--- |
| `c` | Dirección URL que se ha configurado como destino [de URL](../../../features/destinations/create-url-destination.md). |
| `cn` | El nombre o ID establecidos en el campo nombre de cookie de un destino [de cookie](../../../features/destinations/create-cookie-destination.md). |
| `cv` | Valores enviados al destino definido por «cn»: parámetro "destinaton name". |
| `dcs_region` | Llamadas del DCS [servidor a servidor](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Este objeto contiene información para todos los destinos URL configurados en la interfaz de usuario. La lista de objetos es dinámica en función de las acciones del usuario. |
| `dmn` | Este es el dominio especificado en el campo Dominio de cookie para un destino de cookie. Consulte [Configuración opcional para destinos de cookies](../../../features/destinations/cookie-destination-options.md). Para integraciones Servidor a servidor recomendamos utilizar un dominio como `aam-api.com`. |
| `e` | La URL segura que se ha configurado en un destino de URL. |
| `stuff` | Este objeto contiene información para todos los destinos de Cookie. La lista de objetos es dinámica en función de las acciones del usuario. |
| `tid` | ID de transacción, que es un ID exclusivo de 12 caracteres utilizado con fines de depuración. Cada llamada /event al DCS recibe un tid que puede hacer referencia en las instalaciones de soporte para obtener una respuesta mejor y más rápida. |
| `ttl` | El valor de tiempo de vida de la cookie en días. |
| `u` y `uuid` | ID de usuario único asignado por Audience Manager. Esto es necesario si está realizando [llamadas de servidor a servidor](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Tipo de destino, iframe (`iframe`) o imagen (`img`). |

>[!MORE_ LIKE_ THIS]
>
>* [Prefijos y variables de valor clave admitidos por el DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

