---
description: Continúe aquí para obtener información sobre cómo solicitar una respuesta de DCS en una llamada /event. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.
seo-description: Continúe aquí para obtener información sobre cómo solicitar una respuesta de DCS en una llamada /event. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.
seo-title: Recibir datos del DCS
solution: Audience Manager
title: Recibir datos del DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Recibir datos del DCS {#receive-data-from-the-dcs}

Continúe aquí para obtener información sobre cómo solicitar una [!UICONTROL DCS] respuesta en una `/event` llamada. Esta sección incluye un ejemplo de respuesta y definiciones para elementos de datos comunes en una respuesta.

Antes de revisar este contenido, consulte [Envío de datos al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parámetros de respuesta de DCS: Una revisión {#dcs-response-parameters}

Su [!UICONTROL DCS] solicitud debe incluir `d_rtbd=json` si desea recibir una respuesta del [!UICONTROL DCS]. El [!UICONTROL DCS] no devolverá datos si omite este parámetro. Una llamada básica a los datos [!UICONTROL DCS] para solicitar utiliza esta sintaxis:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Respuesta de ejemplo {#sample-response}

Recuerde que desde la documentación de [Enviar datos a DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) , la empresa ficticia [!DNL Acme, Inc.] hizo esta llamada:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Como esta llamada incluye el parámetro de respuesta requerido, el [!UICONTROL DCS] devuelve el [!DNL JSON] objeto que se muestra a continuación. El suyo puede ser similar o más complejo.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parámetros de repuesta {#response-parameters}

La siguiente tabla enumera y define los parámetros más comunes que puede ver en una respuesta de la [!UICONTROL DCS]. Esto se aplica a las llamadas de evento u otras [!UICONTROL DCS] consultas [!DNL API] que devuelven datos.

| Parámetro | Descripción |
|--- |--- |
| `c` | Dirección URL que se ha establecido como destino [](../../../features/destinations/create-url-destination.md)URL. |
| `cn` | Nombre o ID establecidos en el campo de nombre de la cookie de un destino [de](../../../features/destinations/create-cookie-destination.md)cookie. |
| `cv` | Valores enviados al destino definido por el parámetro "cn":" nombre de destino". |
| `dcs_region` | Llamadas [DCS de](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)servidor a servidor. |
| `dests` | Este objeto contiene información para todos los destinos URL configurados en la interfaz de usuario. La lista de este objeto es dinámica en función de las acciones del usuario. |
| `dmn` | Dominio especificado en el campo Dominio de la cookie para un destino de cookie. Consulte Configuración [opcional para destinos](../../../features/destinations/cookie-destination-options.md)de cookies.  Para integraciones de servidor a servidor, recomendamos usar un dominio como `aam-api.com`. |
| `e` | Dirección URL segura que se ha establecido en un destino de dirección URL. |
| `stuff` | Este objeto contiene información para todos los destinos de cookie. La lista de este objeto es dinámica en función de las acciones del usuario. |
| `tid` | ID de transacción, que es un ID exclusivo de 12 caracteres utilizado para la depuración. Cada llamada /event al DCS recibe un tid al que puede hacer referencia en consultas de soporte para obtener una respuesta mejor y más rápida. |
| `ttl` | El valor de tiempo de vida de la cookie en días. |
| `u` y `uuid` | ID de usuario único asignado por Audience Manager. Esto es necesario si realiza llamadas [DCS de](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)servidor a servidor. |
| `y` | Tipo de destino, iFrame (`iframe`) o imagen (`img`). |

>[!MORELIKETHIS]
>
>* [Prefijos y variables de clave-valor compatibles con DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

