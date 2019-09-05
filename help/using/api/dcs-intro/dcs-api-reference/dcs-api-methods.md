---
description: Envíe datos a la API de DCS utilizando métodos GET o POST.
seo-description: Envíe datos a la API de DCS utilizando métodos GET o POST.
seo-title: Métodos de API de DCS
solution: Audience Manager
title: Métodos de API de DCS
uuid: 6 e 407458-11 d 4-4342-a 84 a -512 afa 5 fc 183
translation-type: tm+mt
source-git-commit: bdea2609b84d7f80d67452b4c43e11cbef01a368

---


# Métodos de API de DCS {#dcs-api-methods}

Enviar datos al [!UICONTROL DCS][!DNL API] uso o `GET``POST` a los métodos.

Puede enviar datos al [!UICONTROL DCS] uso de uno o varios `GET``POST` métodos. Eche un vistazo a las llamadas de muestra a continuación usando [curl](https://curl.haxx.se/). En las tres llamadas de ejemplo, agregamos las señales `c_likes = famous popstar` y `c_loves = famous actress` el perfil `12345678901234567890123456789012345678`del dispositivo.


## Enviar datos a través de GET {#send-data-via-get}

Tenga en cuenta que el tamaño máximo permitido para `GET` llamadas es de 8 K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Enviar datos a través de POST {#send-data-via-post}

Tenga en cuenta los requisitos para enviar datos mediante `POST` el método:

* El tamaño máximo permitido es 32 K.
* Defina el tipo de contenido como `application/x-www-form-urlencoded`.

### Llamada de muestra

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
