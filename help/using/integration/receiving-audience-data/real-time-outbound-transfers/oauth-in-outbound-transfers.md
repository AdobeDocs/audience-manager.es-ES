---
description: Al publicar segmentos en el destino del socio mediante una integración servidor a servidor en tiempo real, Audience Manager se puede configurar para autenticarse con OAuth 2.0 al realizar las solicitudes. Esto presenta la capacidad de emitir solicitudes autenticadas de Audience Manager al extremo.
seo-description: When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using OAuth 2.0 when making the requests. This presents the ability to issue authenticated requests from Audience Manager to your endpoint.
seo-title: OAuth 2.0 Integration for Real-Time Outbound Transfers
solution: Audience Manager
title: Integración de OAuth 2.0 para transferencias salientes en tiempo real
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
exl-id: eef3a3ae-1a3f-47e9-aab6-abf878e4cb77
TQID: https://experienceleague.adobe.com/NPCwMOqwZjtbeS2K9z2Z499bQE3mPp22XWKWVtOPSv0
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: c814092e-2730-45e8-a12d-e084529f52cb
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 450
ht-degree: 0%

---

# Integración de [!DNL OAuth 2.0] para transferencias salientes en tiempo real{#oauth-integration-for-real-time-outbound-transfers}

Al publicar segmentos en el destino del socio mediante una integración servidor a servidor en tiempo real, Audience Manager se puede configurar para autenticarse con [!DNL OAuth 2.0] al realizar las solicitudes. Esto presenta la capacidad de emitir solicitudes autenticadas de Audience Manager al extremo.

## Flujo de autenticación {#auth-flow}

La implementación de autenticación [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) se basa en el flujo de concesión de credenciales de cliente y sigue estos pasos:

1. Debe proporcionarnos lo siguiente:
   * Extremo [!DNL OAuth 2.0] que genera el token de autenticación.
   * Las credenciales utilizadas para generar un token.
1. Un consultor de [!DNL Audience Manager] configura [destino](../../../features/destinations/destinations.md) con la información que ha proporcionado.
1. Una vez que un segmento se asigna a este destino, nuestro sistema de transferencia de datos en tiempo real, [IRIS](../../../reference/system-components/components-data-action.md#iris), realiza una solicitud de `POST` al extremo del token para intercambiar las credenciales por un token portador.
1. Para cada solicitud de publicación de segmento al extremo del socio, [!UICONTROL IRIS] utiliza el token de portador para autenticarse.

![](assets/oauth2-iris.png)

## Requisitos {#auth-requirements}

Como socio de [!DNL Audience Manager], se necesitan los siguientes extremos para recibir solicitudes autenticadas:

### Extremo 1 utilizado por IRIS para obtener un token portador

Este extremo aceptará las credenciales proporcionadas en el paso 1 y generará un token de portador que se utilizará en solicitudes posteriores.

* El extremo debe aceptar `HTTP POST` solicitudes.
* El extremo debe aceptar y mirar el encabezado [!DNL Authorization]. El valor de este encabezado será: `Basic <credentials_provided_by_partner>`.
* El extremo debe mirar el encabezado [!DNL Content-type] y validar que su valor es `application/x-www-form-urlencoded ; charset=UTF-8`.
* El cuerpo de la solicitud será `grant_type=client_credentials`.

### Solicitud de ejemplo realizada por Audience Manager al extremo del socio para obtener un token de portador

```
POST /oauth2/token HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Basic zq2LOO1CcYGrODS5nXiNHpEz97eCpVHAoMF8pAgCntXAzxp5uRV7DTAE2qtPLjhMQwrEX3O6MHV4S
Content-Type: application/x-www-form-urlencoded;charset=UTF-8
Content-Length: 29
Accept-Encoding: gzip
  
grant_type=client_credentials
```

### Respuesta de ejemplo del extremo del socio

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Extremo 2 utilizado por IRIS para publicar segmentos mediante el token de portador

[!DNL Audience Manager] envía datos a este extremo en tiempo casi real cuando los usuarios cumplen los requisitos para los segmentos. Además, este método puede enviar lotes de datos sin conexión o incorporados con la misma frecuencia que cada 24 horas.

El token de portador generado por el punto final 1 se utiliza para emitir solicitudes a este punto final. El sistema de transferencia de datos en tiempo real [!DNL Audience Manager], [IRIS](../../../reference/system-components/components-data-action.md#iris), crea una solicitud HTTPS normal e incluye un encabezado Autorización. El valor de este encabezado será: Portador `<bearer token from step 1>`.

### Respuesta de ejemplo del extremo del socio

```
GET /segments/aam HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Bearer glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY
Content-Type: application/json
Accept-Encoding: gzip
   
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
         }
      ]
   }]
}
```

>[!NOTE]
>
>Esta solicitud contiene una carga útil estándar (solicitar contenido).

## Consideraciones importantes {#considerations}

### Los token son contraseñas

Las credenciales presentadas por el socio y los tokens obtenidos por [!DNL Audience Manager] al autenticarse mediante el flujo [!DNL OAuth 2.0] son información confidencial y no se deben compartir con terceros.

### Se requiere [!DNL SSL].

[!DNL SSL] debe usarse para mantener un proceso de autenticación seguro. Todas las solicitudes, incluidas las que se usan para obtener y usar los tokens, deben usar `HTTPS` extremos.
