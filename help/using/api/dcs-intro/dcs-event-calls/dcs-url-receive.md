---
description: Continuar aquí para obtener información sobre cómo solicitud una respuesta DCS en una llamada /evento. Esta sección incluye un ejemplo de respuesta y definiciones de elementos de datos comunes en una respuesta.
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

Continuar aquí para obtener información sobre cómo solicitud una [!DNL DCS] respuesta en una `/event` llamada. Esta sección incluye un ejemplo de respuesta y definiciones de elementos de datos comunes en una respuesta.

Antes de revisar este contenido, consulte [Enviar datos al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parámetros de respuesta de DCS: una revisión {#dcs-response-parameters}

Su [!DNL DCS] solicitud debe incluirse `d_rtbd=json` si desea recibir una respuesta del [!DNL DCS]. Si [!DNL DCS] omite este parámetro, no devuelve datos. Una llamada básica a los [!DNL DCS] datos de solicitud utiliza esta sintaxis:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Respuesta de ejemplo {#sample-response}

Recuerde que desde la [documentación de Enviar datos al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) , el compañía [!DNL Acme, Inc.] ficticio hizo esta llamada:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Como esta llamada incluye el parámetro de respuesta requerido, el [!DNL DCS] objeto enviado se [!DNL JSON] muestra a continuación. El suyo puede ser similar o más complejo.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parámetros de respuesta {#response-parameters}

La tabla siguiente enumera y define los parámetros más comunes que puede ver en una respuesta de .[!DNL DCS] Esto se aplica a llamadas de evento u otras [!DNL DCS] [!DNL API] consultas que devuelven datos.

| Parámetro | Descripción |
|--- |--- |
| `c` | Un URL que se ha establecido como destino [](../../../features/destinations/create-url-destination.md)URL. |
| `cn` | El nombre o ID establecidos en el campo cookie nombre de un [destino](../../../features/destinations/create-cookie-destination.md) cookie. |
| `cv` | Los valores enviados al destino definidos por el parámetro &quot;cn&quot;:&quot; destinaton name&quot;. |
| `dcs_region` | Las [llamadas](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) DCS de servidor a servidor. |
| `dests` | Este objeto contiene información de todos los destinos URL que están configurados en el IU. La lista de este objeto es dinámica en función de las acciones del usuario. |
| `dmn` | Este es el dominio especificado en el campo Dominio de cookies para un destino cookie. Consulte [los Configuración opcionales para destinos](../../../features/destinations/cookie-destination-options.md) de cookies.  Para integraciones de servidor a servidor, recomendamos utilizar un gustar `aam-api.com`de dominio . |
| `e` | El URL seguro que se ha establecido en un destino URL. |
| `stuff` | Este objeto contiene información para todos los destinos de cookies. La lista de este objeto es dinámica en función de las acciones del usuario. |
| `tid` | ID de transacción, que es un ID único de 12 caracteres que se utiliza para la depuración. Cada llamada /evento al DCS recibe una orden que puede consultar en consultas de soporte para obtener una respuesta mejor y más rápida. |
| `ttl` | La cookie valor de tiempo de vida en días. |
| `u` y `uuid` | ID de usuario único asignado por Audience Manager. Esto es necesario si realiza [llamadas](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md) DCS de servidor a servidor. |
| `y` | Tipo de destino, iFrame (`iframe`) o imagen (`img`). |

>[!MORELIKETHIS]
>
>* [Prefijos de Valor clave y variables compatibles con el DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
