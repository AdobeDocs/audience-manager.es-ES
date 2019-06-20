---
description: Al publicar segmentos en el destino del socio mediante una integración servidor a servidor en tiempo real, se puede configurar Audience Manager para que se autentique mediante oauth 2.0 al realizar las solicitudes. Esto presenta la capacidad de emitir solicitudes autenticadas desde Audience Manager al punto final.
seo-description: Al publicar segmentos en el destino del socio mediante una integración servidor a servidor en tiempo real, se puede configurar Audience Manager para que se autentique mediante oauth 2.0 al realizar las solicitudes. Esto presenta la capacidad de emitir solicitudes autenticadas desde Audience Manager al punto final.
seo-title: Integración de oauth 2.0 para transferencias de salida en tiempo real
solution: Audience Manager
title: Integración de oauth 2.0 para transferencias de salida en tiempo real
uuid: a 39 e 370 c-b 3 bd -4 b 06-a 1 af -60 a 024 ee 7 ee 4
translation-type: tm+mt
source-git-commit: 1cc8afd25331528fd67922183b6550288b9939bc

---


# [!DNL OAuth 2.0] Integración de transferencias de salida en tiempo real{#oauth-integration-for-real-time-outbound-transfers}

When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using [!DNL OAuth 2.0] when making the requests. Esto presenta la capacidad de emitir solicitudes autenticadas desde Audience Manager al punto final.

## Authentication Flow {#auth-flow}

The [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) authentication implementation is based on the Client Credentials grant flow and follows these steps:

1. Debe proporcionarnos:
   * The [!DNL OAuth 2.0] endpoint that generates the authentication token.
   * Las credenciales utilizadas para generar un token.
1. [!DNL Audience Manager] Un asesor configura el [destino](../../../features/destinations/destinations.md) utilizando la información proporcionada.
1. Once a segment is mapped to this destination, our real-time data transfer system, [IRIS](../../../reference/system-components/components-data-action.md#iris), makes a `POST` request to the token endpoint to exchange the credentials for a bearer token.
1. For each segment publishing request to the partner endpoint, [!UICONTROL IRIS] uses the bearer token to authenticate.

![](assets/oauth2-iris.png)

## Requisitos {#auth-requirements}

As an [!DNL Audience Manager] partner, the following endpoints are needed to receive authenticated requests:

### Extremo 1 utilizado por IRIS para obtener un token de portador

Este extremo acepta las credenciales proporcionadas en el paso 1 y generará un token de portador que se utilizará en solicitudes posteriores.

* The endpoint must accept `HTTP POST` requests.
* The endpoint must accept and look at the [!DNL Authorization] header. The value for this header will be: `Basic <credentials_provided_by_partner>`.
* The endpoint must look at the [!DNL Content-type] header and validate that its value is `application/x-www-form-urlencoded ; charset=UTF-8`.
* The body of the request will be `grant_type=client_credentials`.

### Ejemplo de solicitud realizada por Audience Manager al punto final del socio para obtener un testigo de portada

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

### Extremo 2 utilizado por IRIS para publicar segmentos usando el token del portador

[!DNL Audience Manager] envía datos a este punto final casi en tiempo real a medida que los usuarios cumplen los segmentos. Además, este método puede enviar lotes de datos sin conexión o onbotados con tanta frecuencia como cada 24 horas.

El testigo del portador generado por el extremo 1 se utiliza para enviar solicitudes a este extremo. The [!DNL Audience Manager] real-time data transfer system, [IRIS](../../../reference/system-components/components-data-action.md#iris), constructs a normal HTTPS request and includes an Authorization header. The value for this header will be: Bearer `<bearer token from step 1>`.

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
>Esta solicitud contiene una carga útil estándar (contenido de solicitud).

## Important Considerations {#considerations}

### Los tokens son contraseñas

The credentials presented by the partner and the tokens obtained by [!DNL Audience Manager] when authenticating using the [!DNL OAuth 2.0] flow, are sensitive information and must not be shared with third parties.

### [!DNL SSL] es obligatorio

[!DNL SSL] debe utilizarse para mantener un proceso de autenticación seguro. All requests, including the ones used to obtain and use the tokens must use `HTTPS` endpoints.