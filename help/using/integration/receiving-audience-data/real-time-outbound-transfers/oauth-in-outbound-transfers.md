---
description: Al publicar segmentos en el destino del socio mediante una integración de servidor a servidor en tiempo real, el Audience Manager puede configurarse para autenticarse con OAuth 2.0 al realizar las solicitudes. Esto presenta la capacidad de emitir solicitudes autenticadas del Audience Manager al extremo.
seo-description: Al publicar segmentos en el destino del socio mediante una integración de servidor a servidor en tiempo real, el Audience Manager puede configurarse para autenticarse con OAuth 2.0 al realizar las solicitudes. Esto presenta la capacidad de emitir solicitudes autenticadas del Audience Manager al extremo.
seo-title: Integración de OAuth 2.0 para transferencias salientes en tiempo real
solution: Audience Manager
title: Integración de OAuth 2.0 para transferencias salientes en tiempo real
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---


# [!DNL OAuth 2.0] Integración para transferencias de salida en tiempo real{#oauth-integration-for-real-time-outbound-transfers}

Al publicar segmentos en el destino del socio mediante una integración de servidor a servidor en tiempo real, el Audience Manager puede configurarse para autenticarse mediante [!DNL OAuth 2.0] al realizar las solicitudes. Esto presenta la capacidad de emitir solicitudes autenticadas del Audience Manager al extremo.

## Flujo de autenticación {#auth-flow}

La implementación de autenticación [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) se basa en el flujo de concesión de credenciales de cliente y sigue estos pasos:

1. Debe proporcionarnos:
   * El extremo [!DNL OAuth 2.0] que genera el autentificador.
   * Las credenciales utilizadas para generar un token.
1. Un [!DNL Audience Manager] consultor configura el [destino](../../../features/destinations/destinations.md) utilizando la información proporcionada.
1. Una vez asignado un segmento a este destino, nuestro sistema de transferencia de datos en tiempo real, [IRIS](../../../reference/system-components/components-data-action.md#iris), realiza una solicitud `POST` al extremo del token para intercambiar las credenciales de un token portador.
1. Para cada solicitud de publicación de segmentos al extremo del socio, [!UICONTROL IRIS] utiliza el token del portador para autenticarse.

![](assets/oauth2-iris.png)

## Requisitos {#auth-requirements}

Como socio [!DNL Audience Manager], se necesitan los siguientes extremos para recibir solicitudes autenticadas:

### Extremo 1 utilizado por el IRIS para obtener una ficha portadora

Este extremo aceptará las credenciales proporcionadas en el paso 1 y generará un token de portador que se utilizará en solicitudes posteriores.

* El extremo debe aceptar solicitudes `HTTP POST`.
* El extremo debe aceptar y mirar el encabezado [!DNL Authorization]. El valor de este encabezado será: `Basic <credentials_provided_by_partner>`.
* El extremo debe mirar el encabezado [!DNL Content-type] y validar que su valor sea `application/x-www-form-urlencoded ; charset=UTF-8`.
* El cuerpo de la solicitud será `grant_type=client_credentials`.

### Ejemplo de solicitud realizada por el Audience Manager al extremo del socio para obtener un token de portador

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

### Ejemplo de respuesta del extremo del socio

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Extremo 2 utilizado por IRIS para publicar segmentos utilizando el distintivo portador

[!DNL Audience Manager] envía datos a este extremo en tiempo casi real a medida que los usuarios cumplen los requisitos para los segmentos. Además, este método puede enviar lotes de datos sin conexión o incorporados con la misma frecuencia que cada 24 horas.

El token portador generado por el extremo 1 se utiliza para emitir solicitudes a este extremo. El [!DNL Audience Manager] sistema de transferencia de datos en tiempo real, [IRIS](../../../reference/system-components/components-data-action.md#iris), construye una solicitud HTTPS normal e incluye un encabezado de Autorización. El valor de este encabezado será: Portador `<bearer token from step 1>`.

### Ejemplo de respuesta del extremo del socio

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
>Esta solicitud contiene una carga útil estándar (contenido de la solicitud).

## Consideraciones importantes {#considerations}

### Los tokens son contraseñas

Las credenciales presentadas por el socio y los tokens obtenidos por [!DNL Audience Manager] al autenticarse con el flujo [!DNL OAuth 2.0] son información confidencial y no deben compartirse con terceros.

### [!DNL SSL] es obligatorio

[!DNL SSL] debe utilizarse para mantener un proceso de autenticación seguro. Todas las solicitudes, incluidas las que se utilizan para obtener y utilizar los tokens, deben utilizar `HTTPS` extremos.