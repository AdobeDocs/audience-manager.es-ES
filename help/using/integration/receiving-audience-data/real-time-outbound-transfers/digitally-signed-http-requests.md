---
description: Audience Manager requiere que las solicitudes de servidor a servidor HTTP se firmen digitalmente para su validez. Este documento describe cómo se pueden firmar solicitudes HTTP con claves privadas.
seo-description: Audience Manager requiere que las solicitudes de servidor a servidor HTTP se firmen digitalmente para su validez. Este documento describe cómo se pueden firmar solicitudes HTTP con claves privadas.
seo-title: Solicitudes HTTP con firma digital
solution: Audience Manager
title: Solicitudes HTTP con firma digital
uuid: 1183 a 70 f -0 c 96-42 cf-a 4 f 5-37 a 83 ffa 1286
translation-type: tm+mt
source-git-commit: 9bf1f3771b6a4b9bb9a52149e812b37d1c8e27f8

---


# Digitally Signed `HTTP` Requests {#digitally-signed-http-requests}

Audience Manager requires the `HTTP` server-to-server requests to be digitally signed for validity. This document describes how you can sign `HTTP` requests with private keys.

## Información general {#overview}

<!-- digitally_signed_http_requests.xml -->

Using a private key provided by you and shared with [!DNL Audience Manager], we can digitally sign the `HTTP` requests that are sent between [IRIS](../../../reference/system-components/components-data-action.md#iris) and your HTTP server. Esto garantiza lo siguiente:

* **Authenticity**: solo el remitente que tenga la clave privada ([!UICONTROL IRIS]) puede enviar `HTTP(S)` mensajes válidos al socio.
* **Integridad del mensaje**: con este enfoque, está `HTTP`protegido contra un hombre en el ataque medio, donde los mensajes se distorsionan.

[!UICONTROL IRIS] tiene compatibilidad integrada para rotar las claves con cero tiempos de inactividad, como se muestra en [la sección Rotar la clave](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) privada abajo.

## Information you need to provide {#info-to-provide}

For an `HTTP` real-time server-to-server destination, contact your [!DNL Audience Manager] consultant and specify:

* Clave utilizada para firmar la solicitud.
* The name of the `HTTP` header that will hold the generated signature (X-Signature in the example header below).
* Opcional: el tipo de hash utilizado para la firma (md 5, sha 1, sha 256).

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

## How it works {#how-it-works}

1. [!UICONTROL IRIS] crea `HTTP` el mensaje que se va a enviar al socio.
1. [!UICONTROL IRIS] crea una firma basada en `HTTP` el mensaje y la clave privada comunicada por el socio.
1. [!UICONTROL IRIS] envía la `HTTP(S)` solicitud al socio. Este mensaje contiene la firma y el mensaje real, como se muestra en el ejemplo anterior.
1. The partner server receives the `HTTP(S)` request. It reads the message body and the signature received from [!UICONTROL IRIS].
1. Según el cuerpo del mensaje recibido y la clave privada, el servidor del socio vuelve a calcular la firma. See the [How to calculate the signature](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) section just below on how to achieve this.
1. Compare the signature created on the partner server (receiver) with the one received from [!UICONTROL IRIS] (sender).
1. If the signatures match, then the **authenticity** and **message integrity** have been validated. Solo el remitente, que tiene la clave privada, puede enviar una firma válida (authenticity). Además, un hombre en el centro no puede modificar el mensaje y generar una nueva firma válida, ya que no dispone de la clave privada (integridad del mensaje).

![](assets/iris-digitally-sign-http-request.png)

## How to calculate the signature {#calculate-signature}

[!DNL HMAC] (Código de autenticación de mensaje basado en hash) es el método utilizado para [!UICONTROL IRIS] la firma del mensaje. Las implementaciones y bibliotecas están disponibles básicamente en todos los lenguajes de programación. [!DNL HMAC] no tiene ataques de extensión conocidos. See an example in [!DNL Java] below:

```
// Message to be signed.
// For GET type HTTP destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP destinations, the message used for signing will be the REQUEST_BODY.
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

The RFC for the [!DNL HMAC] hash implementation is [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). A test site: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (note that you have to [convert](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) the hex encoding to base64).

## Rotating the private key {#rotate-private-key}

Por razones de seguridad, se recomienda rotar periódicamente la clave privada. Depende de usted decidir la clave privada y el período de rotación. In order to achieve the key rotation with zero downtime, [!UICONTROL IRIS] supports adding multiple signature headers. Un encabezado contendrá la firma generada con la clave antigua, otro encabezado contendrá la firma generada con la nueva clave privada. Consulte los pasos detallados en detalle:

1. Partner communicates the new private key to [!DNL Adobe Audience Manager].
1. [!UICONTROL IRIS] comenzará a enviar dos encabezados de firma (uno usando la clave antigua, el otro usando la clave nueva).
1. Una vez que empiece a recibir ambos encabezados, puede optar por descartar la vieja clave y ver solo la nueva firma.
1. The old key is removed from [!DNL Audience Manager] and [!UICONTROL IRIS] only sends the new signature header. Se rotan las claves.

## Data used for signing {#data-signing}

For `GET` type destinations, the message used for signing will be the *REQUEST_PATH + QUERY STRING* (e.g. */from-aam-s2s?sids=1,2,3*). IRIS does not take into account the hostname or `HTTP` headers - these can be modified / misconfigured along the path or reported incorrectly.

For `POST` type destinations, the message used for signing is the *REQUEST BODY*. Nuevamente, se ignoran los encabezados u otros parámetros de solicitud.
