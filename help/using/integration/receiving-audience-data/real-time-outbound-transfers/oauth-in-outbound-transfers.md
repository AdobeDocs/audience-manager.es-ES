---
description: Al publicar segmentos en el destino del socio mediante una integración servidor a servidor en tiempo real, se puede configurar el Audience Manager para que se autentique con OAuth 2.0 al realizar las solicitudes. Esto presenta la capacidad de emitir solicitudes autenticadas del Audience Manager al extremo.
seo-description: When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using OAuth 2.0 when making the requests. This presents the ability to issue authenticated requests from Audience Manager to your endpoint.
seo-title: OAuth 2.0 Integration for Real-Time Outbound Transfers
solution: Audience Manager
title: Integración de OAuth 2.0 para transferencias salientes en tiempo real
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
exl-id: eef3a3ae-1a3f-47e9-aab6-abf878e4cb77
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# [!DNL OAuth 2.0] Integración para transferencias salientes en tiempo real{#oauth-integration-for-real-time-outbound-transfers}

Al publicar segmentos en el destino del socio mediante una integración servidor a servidor en tiempo real, se puede configurar el Audience Manager para que se autentique mediante [!DNL OAuth 2.0] al realizar las solicitudes. Esto presenta la capacidad de emitir solicitudes autenticadas del Audience Manager al extremo.

## Flujo de autenticación {#auth-flow}

El [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) La implementación de la autenticación se basa en el flujo de concesión de credenciales del cliente y sigue estos pasos:

1. Debe proporcionarnos lo siguiente:
   * El [!DNL OAuth 2.0] extremo que genera el token de autenticación.
   * Las credenciales utilizadas para generar un token.
1. Un [!DNL Audience Manager] El consultor de configura el [destino](../../../features/destinations/destinations.md) usando la información proporcionada.
1. Una vez que un segmento se asigna a este destino, nuestro sistema de transferencia de datos en tiempo real, [IRIS](../../../reference/system-components/components-data-action.md#iris), hace un `POST` solicitud al extremo del token para intercambiar las credenciales por un token portador.
1. Para cada solicitud de publicación de segmento al extremo del socio, [!UICONTROL IRIS] utiliza el token de portador para autenticarse.

![](assets/oauth2-iris.png)

## Requisitos {#auth-requirements}

Como un [!DNL Audience Manager] asociado, se necesitan los siguientes extremos para recibir solicitudes autenticadas:

### Extremo 1 utilizado por IRIS para obtener un token portador

Este extremo aceptará las credenciales proporcionadas en el paso 1 y generará un token de portador que se utilizará en solicitudes posteriores.

* El extremo debe aceptar `HTTP POST` solicitudes.
* El extremo debe aceptar y mirar el [!DNL Authorization] encabezado. El valor de este encabezado es: `Basic <credentials_provided_by_partner>`.
* El punto final debe mirar el [!DNL Content-type] y valide que su valor es `application/x-www-form-urlencoded ; charset=UTF-8`.
* El cuerpo de la solicitud es el siguiente `grant_type=client_credentials`.

### Solicitud de ejemplo realizada por el Audience Manager al extremo del socio para obtener un token de portador

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

[!DNL Audience Manager] envía datos a este extremo en tiempo casi real a medida que los usuarios cumplen los requisitos para los segmentos. Además, este método puede enviar lotes de datos sin conexión o incorporados con la misma frecuencia que cada 24 horas.

El token de portador generado por el punto final 1 se utiliza para emitir solicitudes a este punto final. El [!DNL Audience Manager] sistema de transferencia de datos en tiempo real, [IRIS](../../../reference/system-components/components-data-action.md#iris), construye una solicitud HTTPS normal e incluye un encabezado Autorización. El valor de este encabezado es: Bearer `<bearer token from step 1>`.

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

Las credenciales presentadas por el socio y los tokens obtenidos por [!DNL Audience Manager] al autenticarse mediante [!DNL OAuth 2.0] flujo, son información sensible y no deben compartirse con terceros.

### [!DNL SSL] es obligatorio

[!DNL SSL] debe utilizarse para mantener un proceso de autenticación seguro. Todas las solicitudes, incluidas las utilizadas para obtener y utilizar los tokens, deben utilizar `HTTPS` puntos finales.
