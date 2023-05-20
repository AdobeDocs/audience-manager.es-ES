---
description: Envíe datos a la API de DCS mediante métodos de GET o POST.
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: Métodos de API de DCS
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 4%

---

# [!DNL DCS] [!DNL API] Métodos {#dcs-api-methods}

Envío de datos a [!DNL DCS] [!DNL API] usando `GET` o `POST` métodos.

Puede enviar datos a [!DNL DCS] usando cualquiera de las `GET` o `POST` métodos. Eche un vistazo a las llamadas de ejemplo siguientes, usando [rizar](https://curl.haxx.se/). En las tres llamadas de ejemplo, agregamos las señales `c_likes = famous popstar` y `c_loves = famous actress` al perfil del dispositivo `12345678901234567890123456789012345678`.

## Envío de datos mediante [!DNL GET] {#send-data-via-get}

Tenga en cuenta que el tamaño máximo permitido para `GET` llamadas es 8K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Envío de datos mediante [!DNL POST] {#send-data-via-post}

Tenga en cuenta los requisitos para enviar datos mediante el `POST` método:

* El tamaño máximo permitido es 32K.
* Establezca el tipo de contenido en `application/x-www-form-urlencoded`.

### Llamada de ejemplo

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
