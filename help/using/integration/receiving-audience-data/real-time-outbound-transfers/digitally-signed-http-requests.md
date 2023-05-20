---
description: El Audience Manager requiere que las solicitudes HTTP(S) de servidor a servidor se firmen digitalmente para su validez. Este documento describe cómo puede firmar solicitudes HTTP con claves privadas.
seo-description: Audience Manager requires the HTTP(S) server-to-server requests to be digitally signed for validity. This document describes how you can sign HTTP(S) requests with private keys.
seo-title: Digitally Signed HTTP(S) Requests
solution: Audience Manager
title: Solicitudes HTTP(S) firmadas digitalmente
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 0%

---

# Firmado digitalmente `HTTP(S)` Solicitudes {#digitally-signed-http-requests}

El Audience Manager requiere el `HTTP(S)` solicitudes de servidor a servidor para firmar digitalmente con fines de validez. Este documento describe cómo puede firmar `HTTP(S)` solicitudes con claves privadas.

## Información general {#overview}

<!-- digitally_signed_http_requests.xml -->

Utilizando una clave privada proporcionada por usted y compartida con [!DNL Audience Manager], podemos firmar digitalmente el `HTTP(S)` solicitudes enviadas entre [IRIS](../../../reference/system-components/components-data-action.md#iris) y su servidor HTTP(S). Esto garantiza:

* **Autenticidad**: solo el remitente que tiene la clave privada ([!UICONTROL IRIS]) puede enviar datos válidos `HTTP(S)` mensajes al socio.
* **Integridad del mensaje**: con este enfoque, incluso en `HTTP`, usted está protegido de un hombre en el ataque del medio donde los mensajes se distorsionan.

[!UICONTROL IRIS] tiene compatibilidad integrada para girar las claves sin tiempo de inactividad, como se muestra en la [Rotación de la clave privada](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) más abajo.

## Información que debe proporcionar {#info-to-provide}

Para un `HTTP(S)` destino servidor a servidor en tiempo real, póngase en contacto con su [!DNL Audience Manager] consultor y especifique:

* La clave utilizada para firmar la solicitud.
* El nombre del `HTTP(S)` encabezado que contendrá la firma generada (X-Signature en el encabezado de ejemplo siguiente).
* Opcional: el tipo de hash utilizado para la firma (md5, sha1, sha256).

```
* Connected to partner.website.com (127.0.0.1) port 80 (#0)
> POST /webpage HTTP/1.1
> Host: partner.host.com
> Accept: */*
> Content-Type: application/json
> Content-Length: 20
> X-Signature: +wFdR/afZNoVqtGl8/e1KJ4ykPU=
POST message content
```

## Cómo funciona {#how-it-works}

1. [!UICONTROL IRIS] crea el `HTTP(S)` mensaje que se enviará al socio.
1. [!UICONTROL IRIS] crea una firma basada en la variable `HTTP(S)` y la clave privada comunicada por el socio.
1. [!UICONTROL IRIS] envía el `HTTP(S)` solicitud al socio. Este mensaje contiene la firma y el mensaje real, tal como se ve en el ejemplo anterior.
1. El servidor asociado recibe el `HTTP(S)` solicitud. Lee el cuerpo del mensaje y la firma recibida de [!UICONTROL IRIS].
1. En función del cuerpo del mensaje recibido y de la clave privada, el servidor del socio vuelve a calcular la firma. Consulte la [Cómo calcular la firma](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) justo debajo de la sección sobre cómo conseguirlo.
1. Comparar la firma creada en el servidor asociado (receptor) con la recibida desde [!UICONTROL IRIS] (remitente).
1. Si las firmas coinciden, la variable **autenticidad** y **integridad del mensaje** se han validado. Solo el remitente, que tiene la clave privada, puede enviar una firma válida (autenticidad). Además, un hombre en el medio no puede modificar el mensaje y generar una nueva firma válida, ya que no tienen la clave privada (integridad del mensaje).

![](assets/iris-digitally-sign-http-request.png)

## Cómo calcular la firma {#calculate-signature}

[!DNL HMAC] (Código de autenticación de mensaje basado en hash) es el método que utiliza [!UICONTROL IRIS] para firmar mensajes. Las implementaciones y bibliotecas están disponibles básicamente en todos los lenguajes de programación. [!DNL HMAC] no tiene ataques de extensión conocidos. Vea un ejemplo en [!DNL Java] a continuación:

```
// Message to be signed.
// For GET type HTTP(S) destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP(S) destinations, the message used for signing will be the REQUEST_BODY.
// String getData = "/from-aam-s2s?sids=1,2,3";
String postData = "POST message content";
// Algorithm used. Currently supported: HmacSHA1, HmacSHA256, HmacMD5.
String algorithm = "HmacSHA1";
// Private key shared between the partner and Adobe Audience Manager.
String key = "sample_partner_private_key";
  
// Perform signing.
SecretKeySpec signingKey = new SecretKeySpec(key.getBytes(), algorithm);
Mac mac = Mac.getInstance(algorithm);
mac.init(signingKey);
byte[] result = mac.doFinal(postData.getBytes());
  
String signature = Base64.encodeBase64String(result).trim(); 
// signature = +wFdR/afZNoVqtGl8/e1KJ4ykPU=
```

El RFC de [!DNL HMAC] la implementación de hash es [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Un sitio de prueba: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (tenga en cuenta que debe [convertir](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) la codificación hex a base64).

## Rotación de la clave privada {#rotate-private-key}

Para rotar la clave privada, los socios deben comunicar la nueva clave privada a su [!DNL Adobe Audience Manager] consultor. La clave antigua se ha eliminado de [!DNL Audience Manager] y [!UICONTROL IRIS] solo envía el nuevo encabezado de firma. Las llaves han sido giradas.

## Datos utilizados para la firma {#data-signing}

Para `GET` destinos de tipo, el mensaje utilizado para la firma será el *RUTA_SOLICITUD + CADENA DE CONSULTA* (p. ej., */from-aam-s2s?sids=1,2,3*). IRIS no tiene en cuenta el nombre de host o `HTTP(S)` encabezados: se pueden modificar o configurar incorrectamente a lo largo de la ruta o se pueden registrar de forma incorrecta.

Para `POST` destinos de tipo, el mensaje utilizado para la firma es el *CUERPO DE SOLICITUD*. De nuevo, se ignoran los encabezados u otros parámetros de solicitud.
