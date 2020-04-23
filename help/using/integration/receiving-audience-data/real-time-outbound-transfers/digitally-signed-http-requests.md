---
description: El Administrador de Audiencias requiere que las solicitudes de servidor a servidor HTTP(S) se firmen digitalmente para su validez. Este documento describe cómo puede firmar solicitudes HTTP con claves privadas.
seo-description: El Administrador de Audiencias requiere que las solicitudes de servidor a servidor HTTP(S) se firmen digitalmente para su validez. Este documento describe cómo puede firmar solicitudes HTTP(S) con claves privadas.
seo-title: Solicitudes HTTP(S) firmadas digitalmente
solution: Audience Manager
title: Solicitudes HTTP(S) firmadas digitalmente
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
translation-type: tm+mt
source-git-commit: 5dddaaae3a5cb2ce4c4649e2a153edf1992fa964

---


# Solicitudes firmadas `HTTP(S)` digitalmente {#digitally-signed-http-requests}

El Administrador de Audiencias requiere que las solicitudes `HTTP(S)` servidor a servidor estén firmadas digitalmente para su validez. Este documento describe cómo puede firmar `HTTP(S)` solicitudes con claves privadas.

## Información general {#overview}

<!-- digitally_signed_http_requests.xml -->

Con una clave privada proporcionada por usted y compartida con [!DNL Audience Manager], podemos firmar digitalmente las `HTTP(S)` solicitudes enviadas entre [IRIS](../../../reference/system-components/components-data-action.md#iris) y su servidor HTTP(S). Esto garantiza:

* **Autenticidad**: solo el remitente que tiene la clave privada ([!UICONTROL IRIS]) puede enviar `HTTP(S)` mensajes válidos al socio.
* **Integridad** del mensaje: con este enfoque, incluso en `HTTP`, estás protegido de un hombre en el ataque medio donde los mensajes se distorsionan.

[!UICONTROL IRIS] cuenta con soporte integrado para rotar las claves con cero downtime, como se muestra en la sección [Rotar la clave](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) privada a continuación.

## Información que debe proporcionar {#info-to-provide}

Para un destino de servidor a servidor en tiempo `HTTP(S)` real, póngase en contacto con su [!DNL Audience Manager] asesor y especifique:

* Clave utilizada para firmar la solicitud.
* El nombre del `HTTP(S)` encabezado que contendrá la firma generada (firma X en el encabezado de ejemplo siguiente).
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

## How it works {#how-it-works}

1. [!UICONTROL IRIS] crea el `HTTP(S)` mensaje que se enviará al socio.
1. [!UICONTROL IRIS] crea una firma basada en el mensaje `HTTP(S)` y la clave privada comunicada por el socio.
1. [!UICONTROL IRIS] envía la `HTTP(S)` solicitud al socio. Este mensaje contiene la firma y el mensaje real, como se muestra en el ejemplo anterior.
1. El servidor asociado recibe la `HTTP(S)` solicitud. Lee el cuerpo del mensaje y la firma recibida de [!UICONTROL IRIS].
1. Según el cuerpo del mensaje recibido y la clave privada, el servidor asociado vuelve a calcular la firma. Consulte la sección [Cómo calcular la firma](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) que aparece a continuación sobre cómo conseguirlo.
1. Compare la firma creada en el servidor del socio (receptor) con la que recibió [!UICONTROL IRIS] (remitente).
1. Si las firmas coinciden, se validan la **autenticidad** y la integridad **del** mensaje. Solo el remitente, que tiene la clave privada, puede enviar una firma válida (autenticidad). Además, un hombre del medio no puede modificar el mensaje ni generar una nueva firma válida, ya que no tienen la clave privada (integridad del mensaje).

![](assets/iris-digitally-sign-http-request.png)

## Cómo calcular la firma {#calculate-signature}

[!DNL HMAC] (Código de autenticación de mensajes basado en hash) es el método que se utiliza [!UICONTROL IRIS] para la firma de mensajes. Las implementaciones y bibliotecas están disponibles básicamente en todos los lenguajes de programación. [!DNL HMAC] no tiene ataques de extensión conocidos. Vea un ejemplo en [!DNL Java] la siguiente sección:

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

El RFC para la implementación del [!DNL HMAC] hash es [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Un sitio de prueba: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (tenga en cuenta que debe [convertir](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) la codificación hexadecimal a base64).

## Rotación de la clave privada {#rotate-private-key}

Por motivos de seguridad, se recomienda rotar periódicamente la clave privada. Depende de usted decidir la clave privada y el período de rotación. Para lograr la rotación de claves sin tiempo de inactividad, [!UICONTROL IRIS] admite la adición de varios encabezados de firma. Un encabezado contendrá la firma generada con la clave antigua, otro encabezado contendrá la firma generada con la nueva clave privada. Consulte los siguientes pasos en detalle:

1. El socio comunica la nueva clave privada a [!DNL Adobe Audience Manager].
1. La clave antigua se elimina [!DNL Audience Manager] y [!UICONTROL IRIS] sólo envía el nuevo encabezado de firma. Se han rotado las teclas.

## Datos utilizados para firmar {#data-signing}

Para los destinos de `GET` tipo, el mensaje utilizado para la firma será *REQUEST_PATH + CADENA* de CONSULTA (p. ej. */from-aam-s2s?sids=1,2,3*). IRIS no tiene en cuenta el nombre de host o los encabezados, ya que estos pueden modificarse o configurarse incorrectamente a lo largo de la ruta o informarse incorrectamente. `HTTP(S)`

Para los destinos de `POST` tipo, el mensaje utilizado para firmar es el CUERPO DE *SOLICITUD*. De nuevo, se omiten los encabezados u otros parámetros de solicitud.
