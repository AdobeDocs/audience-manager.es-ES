---
description: Preguntas y problemas comunes de API.
seo-description: Preguntas y problemas comunes de API.
seo-title: Preguntas frecuentes sobre API
solution: Audience Manager
title: Preguntas frecuentes sobre API
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Preguntas frecuentes sobre API{#api-faq}

Preguntas y problemas comunes de API.

<!-- 

faq_api.xml

 -->

La documentación de la API [de](../api/rest-api-main/rest-api-main.md) REST contiene detalles sobre métodos específicos y ejemplos de código.

<br> 

**¿Por qué[!UICONTROL DIL]se realizan llamadas de eventos con[!UICONTROL GET]y con[!UICONTROL POST]métodos?**

[!UICONTROL DIL] pasa datos a [!DNL Audience Manager] con un `GET` método o `POST` según la longitud de la cadena de consulta de la llamada al evento. Este comportamiento está integrado en `GET` y `POST` los métodos de forma predeterminada. No es específico de [!DNL Audience Manager].

* [!UICONTROL DIL] realiza llamadas de evento con `GET` cuando una dirección URL contiene 2048 caracteres o menos. Una llamada `GET` de evento incluye datos en la dirección URL como parámetros de cadena de consulta, que se pasan como pares clave-valor.

* [!UICONTROL DIL] realiza llamadas de eventos con `POST` cuando una dirección URL contiene más de 2048 caracteres. Una llamada `POST` de evento incluye datos en el cuerpo de la solicitud. [!UICONTROL DIL] coloca los datos en pares clave-valor y pasa la información como datos de formulario en lugar de hacerlo en la cadena de consulta URL.

Aunque cada método pasa los datos de una manera diferente, esto no afecta a la funcionalidad. Por ejemplo, con cualquiera de los métodos, [!DNL Audience Manager] sigue enviando datos a destinos, la sincronización de ID funciona normalmente y puede crear características a partir de señales de datos.

<br> 

**¿Qué me permiten[!UICONTROL REST API]hacer?**

Los [!UICONTROL REST API]s le permiten trabajar mediante programación con la mayoría de [!DNL Audience Manager] las funciones y características disponibles en la interfaz de usuario.

<br> 

**¿Cómo obtengo un ID de[!UICONTROL REST API]cliente y un secreto?**

Póngase en contacto con el representante de soluciones de socio para obtener las credenciales de [!DNL API] acceso. Nuestras API utilizan los estándares [OAuth 2.0](https://oauth.net/2/) para la autenticación, autorización y renovación de testigos. Consulte Autenticación [OAuth](../api/rest-api-main/aam-api-getting-started.md#oauth) para obtener más información.
