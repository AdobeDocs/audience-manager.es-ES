---
description: Envíe datos a la API de DCS mediante métodos de GET o POST.
seo-description: Envíe datos a la API de DCS mediante métodos de GET o POST.
seo-title: Métodos de API de DCS
solution: Audience Manager
title: Métodos de API de DCS
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 6%

---


# [!DNL DCS] [!DNL API] Métodos {#dcs-api-methods}

Envíe datos a [!DNL DCS] [!DNL API] mediante los métodos `GET` o `POST`.

Puede enviar datos a [!DNL DCS] mediante uno de los métodos `GET` o `POST`. Eche un vistazo a las llamadas de ejemplo que se muestran a continuación, utilizando [curl](https://curl.haxx.se/). En las tres llamadas de muestra, agregamos las señales `c_likes = famous popstar` y `c_loves = famous actress` al perfil del dispositivo `12345678901234567890123456789012345678`.

## Enviar datos mediante [!DNL GET] {#send-data-via-get}

Tenga en cuenta que el tamaño máximo permitido para `GET` llamadas es de 8 K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Enviar datos mediante [!DNL POST] {#send-data-via-post}

Tenga en cuenta los requisitos para enviar datos mediante el método `POST`:

* El tamaño máximo permitido es de 32K.
* Establezca el tipo de contenido en `application/x-www-form-urlencoded`.

### Llamada de muestra

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
