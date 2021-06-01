---
description: Envíe datos a la API de DCS mediante métodos de GET o POST.
seo-description: Envíe datos a la API de DCS mediante métodos de GET o POST.
seo-title: Métodos de API de DCS
solution: Audience Manager
title: Métodos de API de DCS
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 6%

---

# [!DNL DCS] [!DNL API] Métodos {#dcs-api-methods}

Envíe datos a [!DNL DCS] [!DNL API] utilizando los métodos `GET` o `POST` .

Puede enviar datos a [!DNL DCS] utilizando uno de los métodos `GET` o `POST`. Eche un vistazo a las llamadas de ejemplo que se muestran a continuación, utilizando [curl](https://curl.haxx.se/). En las tres llamadas de ejemplo, agregamos las señales `c_likes = famous popstar` y `c_loves = famous actress` al perfil del dispositivo `12345678901234567890123456789012345678`.

## Enviar datos mediante [!DNL GET] {#send-data-via-get}

Tenga en cuenta que el tamaño máximo permitido para llamadas `GET` es de 8 K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Enviar datos mediante [!DNL POST] {#send-data-via-post}

Tenga en cuenta los requisitos para enviar datos mediante el método `POST`:

* El tamaño máximo permitido es de 32 000.
* Establezca el tipo de contenido en `application/x-www-form-urlencoded`.

### Llamada de ejemplo

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
