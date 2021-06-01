---
description: Audience Manager requiere que las solicitudes HTTP(S) servidor a servidor se firmen digitalmente para su validez. Este documento describe cómo se pueden firmar solicitudes HTTP con claves privadas.
seo-description: Audience Manager requiere que las solicitudes HTTP(S) servidor a servidor se firmen digitalmente para su validez. Este documento describe cómo se pueden firmar solicitudes HTTP(S) con claves privadas.
seo-title: Solicitudes HTTP(S) firmadas digitalmente
solution: Audience Manager
title: Solicitudes HTTP(S) firmadas digitalmente
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Transferencias de datos de salida
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 0%

---

# Solicitudes `HTTP(S)` firmadas digitalmente {#digitally-signed-http-requests}

El Audience Manager requiere que las `HTTP(S)` solicitudes de servidor a servidor se firmen digitalmente para su validez. Este documento describe cómo se pueden firmar `HTTP(S)` solicitudes con claves privadas.

## Información general {#overview}

<!-- digitally_signed_http_requests.xml -->

Utilizando una clave privada que usted ha proporcionado y que ha compartido con [!DNL Audience Manager], podemos firmar digitalmente las solicitudes `HTTP(S)` que se envían entre [IRIS](../../../reference/system-components/components-data-action.md#iris) y su servidor HTTP(S). Esto garantiza:

* **Autenticidad**: solo el remitente que tiene la clave privada ([!UICONTROL IRIS]) puede enviar  `HTTP(S)` mensajes válidos al socio.
* **Integridad** del mensaje: con este enfoque, incluso en  `HTTP`, estás protegido de un hombre en el ataque intermedio donde los mensajes se distorsionan.

[!UICONTROL IRIS] dispone de soporte integrado para rotar las claves sin downtime, como se muestra en la sección  [Rotar la ](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) clave privada a continuación.

## Información que debe proporcionar {#info-to-provide}

Para obtener un `HTTP(S)` destino de servidor a servidor en tiempo real, póngase en contacto con su [!DNL Audience Manager] consultor y especifique:

* La clave utilizada para firmar la solicitud.
* El nombre del encabezado `HTTP(S)` que contendrá la firma generada (firma X en el encabezado de ejemplo siguiente).
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

1. [!UICONTROL IRIS] crea el  `HTTP(S)` mensaje que se enviará al socio.
1. [!UICONTROL IRIS] crea una firma basada en el  `HTTP(S)` mensaje y en la clave privada comunicada por el socio.
1. [!UICONTROL IRIS] envía la  `HTTP(S)` solicitud al socio. Este mensaje contiene la firma y el mensaje real, como se ve en el ejemplo anterior.
1. El servidor del socio recibe la solicitud `HTTP(S)`. Lee el cuerpo del mensaje y la firma recibida de [!UICONTROL IRIS].
1. En función del cuerpo del mensaje recibido y la clave privada, el servidor socio vuelve a calcular la firma. Consulte la sección [Cómo calcular la firma](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) que aparece a continuación sobre cómo conseguirlo.
1. Compare la firma creada en el servidor del socio (receptor) con la recibida de [!UICONTROL IRIS] (remitente).
1. Si las firmas coinciden, se han validado la **autenticidad** y la **integridad del mensaje**. Solo el remitente, que tiene la clave privada, puede enviar una firma válida (autenticidad). Además, un hombre en el medio no puede modificar el mensaje y generar una nueva firma válida, ya que no tienen la clave privada (integridad del mensaje).

![](assets/iris-digitally-sign-http-request.png)

## Cómo calcular la firma {#calculate-signature}

[!DNL HMAC] (Código de autenticación de mensajes basado en hash) es el método que se utiliza en  [!UICONTROL IRIS] la firma de mensajes. Las implementaciones y bibliotecas están disponibles básicamente en todos los lenguajes de programación. [!DNL HMAC] no tiene ataques de extensión conocidos. Vea un ejemplo en [!DNL Java] a continuación:

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

El RFC para la implementación de hash [!DNL HMAC] es [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Un sitio de prueba: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (tenga en cuenta que debe [convertir](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) la codificación hexadecimal a base64).

## Giro de la clave privada {#rotate-private-key}

Para girar la clave privada, los socios deben comunicar la nueva clave privada a su [!DNL Adobe Audience Manager] consultor. La clave antigua se elimina de [!DNL Audience Manager] y [!UICONTROL IRIS] solo envía el nuevo encabezado de firma. Se han girado las teclas.

## Datos utilizados para firmar {#data-signing}

Para destinos de tipo `GET`, el mensaje utilizado para la firma será *REQUEST_PATH + QUERY STRING* (p. ej. */from-aam-s2s?sids=1,2,3*). IRIS no tiene en cuenta los encabezados hostname o `HTTP(S)` - estos pueden modificarse o configurarse incorrectamente a lo largo de la ruta o notificarse incorrectamente.

Para destinos de tipo `POST`, el mensaje utilizado para firmar es *REQUEST BODY*. De nuevo, se omiten los encabezados u otros parámetros de solicitud.
