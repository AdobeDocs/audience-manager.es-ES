---
description: Al publicar segmentos en el destino socio a través de una integración de servidor a servidor en tiempo real, se puede configurar Audience Manager para que se autentiquen mediante OAuth 2.0 al realizar las solicitudes. Esto presenta la capacidad de emitir solicitudes autenticadas desde el Audience Manager hasta el extremo.
seo-description: When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using OAuth 2.0 when making the requests. This presents the ability to issue authenticated requests from Audience Manager to your endpoint.
seo-title: OAuth 2.0 Integration for Real-Time Outbound Transfers
solution: Audience Manager
title: Integración de OAuth 2.0 para transferencias salientes en tiempo real
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
exl-id: eef3a3ae-1a3f-47e9-aab6-abf878e4cb77
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 0%

---

# [!DNL OAuth 2.0] Integración para transferencias salientes en tiempo real{#oauth-integration-for-real-time-outbound-transfers}

Al publicar segmentos en el destino socio a través de una integración de servidor a servidor en tiempo real, se puede configurar Audience Manager para que se autentiquen al [!DNL OAuth 2.0] realizar las solicitudes. Esto presenta la capacidad de emitir solicitudes autenticadas desde el Audience Manager hasta el extremo.

## Authentication Flujo {#auth-flow}

La [!DNL Adobe Audience Manager] [implementación de autenticación de OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) se basa en el flujo de concesión de credenciales de cliente y sigue estos pasos:

1. Debe proporcionarnos:
   * El [!DNL OAuth 2.0] extremo que genera el token de autenticación.
   * Las credenciales utilizadas para generar un token.
1. Un [!DNL Audience Manager] consultor configura el [destino](../../../features/destinations/destinations.md) con la información proporcionada.
1. Una vez que un segmento se asigna a este destino, nuestro sistema de transferencia de datos en tiempo real, [IRIS,](../../../reference/system-components/components-data-action.md#iris) hace un `POST` solicitud al punto final del token para intercambiar las credenciales por un token al portador.
1. Para cada segmento solicitud de publicación al punto final de socio, [!UICONTROL IRIS] utiliza el token al portador para autenticarse.

![](assets/oauth2-iris.png)

## Requisitos {#auth-requirements}

[!DNL Audience Manager] Como socio, se necesitan los siguientes puntos finales para recibir solicitudes autenticadas:

### Punto final 1 utilizado por IRIS para obtener un token al portador

Este extremo aceptará las credenciales proporcionadas en el paso 1 y generará un token al portador que se utilizará en solicitudes posteriores.

* El extremo debe aceptar `HTTP POST` solicitudes.
* El extremo debe aceptar y mirar el [!DNL Authorization] encabezado. El valor de este encabezado será: `Basic <credentials_provided_by_partner>`.
* El punto final debe mirar el [!DNL Content-type] encabezado y validar que su valor es `application/x-www-form-urlencoded ; charset=UTF-8`.
* El cuerpo del solicitud será `grant_type=client_credentials`.

### Ejemplo solicitud realizado por Audience Manager al punto final socio para obtener un token al portador

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

### Ejemplo de respuesta del punto de conexión del socio

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Punto final 2 utilizado por IRIS para publicar segmentos utilizando el token al portador

[!DNL Audience Manager] Envía datos a este extremo casi en tiempo real, ya que los usuarios cumplen los requisitos para los segmentos. Además, este método puede enviar lotes de datos de sin conexión o incorporados con una frecuencia de hasta cada 24 horas.

El token al portador generado por el extremo 1 se utiliza para emitir solicitudes a este extremo. El [!DNL Audience Manager] sistema de transferencia de datos en tiempo real, [IRIS,](../../../reference/system-components/components-data-action.md#iris) construye un solicitud HTTPS normal e incluye un encabezado de autorización. El valor de este encabezado será: Portador `<bearer token from step 1>`.

### Ejemplo de respuesta del punto de conexión del socio

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
>Este solicitud contiene una carga útil estándar (solicitud contenido).

## Consideraciones importantes {#considerations}

### Los tokens son contraseñas

Las credenciales presentadas por el socio y los tokens obtenidos al [!DNL Audience Manager] autenticarse utilizando el [!DNL OAuth 2.0] flujo, son información sensible y no deben compartirse con terceros.

### [!DNL SSL] es obligatorio

[!DNL SSL] debe utilizarse para mantener un proceso de autenticación seguro. Todas las solicitudes, incluidas las utilizadas para obtener y utilizar los tokens, deben utilizar `HTTPS` extremos.
