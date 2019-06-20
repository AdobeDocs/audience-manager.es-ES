---
description: Preguntas y problemas comunes de API.
seo-description: Preguntas y problemas comunes de API.
seo-title: Preguntas más frecuentes sobre API
solution: Audience Manager
title: Preguntas más frecuentes sobre API
uuid: 8222 ebf 0-b 50 e -4 f 48-8021-dbfca 2828 b 7 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API FAQ{#api-faq}

Preguntas y problemas comunes de API.

<!-- 

faq_api.xml

 -->

The [REST API](../api/rest-api-main/rest-api-main.md) documentation contains details about specific methods and code samples.

<br> 

**¿Por qué[!UICONTROL DIL]realiza llamadas y[!UICONTROL GET][!UICONTROL POST]métodos de eventos?**

[!UICONTROL DIL] envía datos a [!DNL Audience Manager] un método `GET` o `POST` a un método basado en la longitud de la cadena de consulta de la llamada de evento. This behavior is built in to `GET` and `POST` methods by default. It is not specific to [!DNL Audience Manager].

* [!UICONTROL DIL] hace llamadas a eventos `GET` cuando una dirección URL contiene 2048 caracteres o menos. A `GET` event call includes data in the URL as query string parameters, which are passed in as key-value pairs.

* [!UICONTROL DIL] hace llamadas de evento cuando `POST` una URL contiene más de 2048 caracteres. A `POST` event call includes data in the body of the request. [!UICONTROL DIL] coloca los datos en pares de valor clave y pasa información como datos de formulario en lugar de en la cadena de consulta URL.

Aunque cada método pasa datos de una forma diferente, esto no afecta a la funcionalidad. For example, with either method, [!DNL Audience Manager] still sends data to destinations, ID syncs works normally, and you can create traits from data signals.

<br> 

**¿Qué debo hacer[!UICONTROL REST API]para hacer?**

The [!UICONTROL REST API]s let you work programmatically with most [!DNL Audience Manager] features and functions that are available in the user interface.

<br> 

**¿Cómo se obtiene un[!UICONTROL REST API]ID de cliente y un secreto?**

Contact your Partner Solutions representative to obtain [!DNL API] access credentials. Our APIs use [OAuth 2.0](https://oauth.net/2/) standards for token authentication, authorization, and renewal. See [OAuth Authentication](../api/rest-api-main/aam-api-getting-started.md#oauth) for more information.
