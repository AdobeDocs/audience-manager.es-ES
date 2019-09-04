---
description: Envíe datos a la API de DCS utilizando métodos GET o POST.
seo-description: Envíe datos a la API de DCS utilizando métodos GET o POST.
seo-title: Métodos de API de DCS
solution: Audience Manager
title: Métodos de API de DCS
uuid: 6 e 407458-11 d 4-4342-a 84 a -512 afa 5 fc 183
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Métodos de API de DCS {#dcs-api-methods}

Enviar datos al [!UICONTROL DCS][!DNL API] uso o `GET``POST` a los métodos.

Puede enviar datos al [!UICONTROL DCS] uso de uno o varios `GET``POST` métodos. Eche un vistazo a las llamadas de muestra a continuación usando [curl](https://curl.haxx.se/). En las tres llamadas de ejemplo, agregamos las señales `c_likes = famous popstar` y `c_loves = famous actress` el perfil `12345678901234567890123456789012345678`del dispositivo.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Sustituya un valor real del marcador de posición cuando envíe datos al [!UICONTROL DCS] con este método.

## Enviar datos a través de GET {#send-data-via-get}

Tenga en cuenta que el tamaño máximo permitido para `GET` llamadas es de 8 K.

<pre><code>curl -i "<i>yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&amp;d_rtbd=jsonc_likes=famous%20popstar&amp;c_loves=famous%20actress</i><i></i><i></i><i></i>"</code></pre>

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
