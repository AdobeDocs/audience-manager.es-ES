---
description: Preguntas y problemas comunes de API.
seo-description: Preguntas y problemas comunes de API.
seo-title: Preguntas frecuentes sobre API
solution: Audience Manager
title: Preguntas frecuentes sobre API
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
exl-id: 9a51220e-3f53-4911-876b-16e968d44d0f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 100%

---

# Preguntas frecuentes sobre API {#api-faq}

Preguntas y problemas comunes de API.

<!-- 

faq_api.xml

 -->

La documentación de la [API de REST](../api/rest-api-main/rest-api-main.md) contiene detalles sobre métodos específicos y ejemplos de código.

<br> 

**¿Por qué [!UICONTROL DIL] realiza llamadas de evento con los métodos [!UICONTROL GET] y [!UICONTROL POST]?**

[!UICONTROL DIL] pasa datos a [!DNL Audience Manager] con un método `GET` o `POST` basado en la longitud de la cadena de consulta de la llamada de evento. Este comportamiento está integrado en los métodos `GET` y `POST` de forma predeterminada. No es específico de [!DNL Audience Manager].

* [!UICONTROL DIL] realiza llamadas de evento con `GET` cuando una dirección URL contiene 2048 caracteres o menos. Una llamada de evento `GET` incluye datos en la dirección URL como parámetros de cadena de consulta, que se pasan como pares clave-valor.

* [!UICONTROL DIL] realiza llamadas de evento con `POST` cuando una dirección URL contiene más de 2048 caracteres. Una llamada de evento `POST` incluye datos en el cuerpo de la solicitud. [!UICONTROL DIL] coloca los datos en pares de clave-valor y pasa la información como datos de formulario en lugar de hacerlo en la cadena de consulta URL.

Aunque cada método pasa los datos de una manera diferente, esto no afecta a la funcionalidad. Por ejemplo, con cualquiera de los métodos, [!DNL Audience Manager] sigue enviando datos a los destinos, la sincronización de ID funciona normalmente y puede crear rasgos a partir de señales de datos.

<br> 

**¿Qué puedo hacer con las [!UICONTROL REST API]?**

Las [!UICONTROL REST API]le permiten trabajar mediante programación con la mayoría de funcionalidades y características de [!DNL Audience Manager] disponibles en la interfaz de usuario.

<br> 

**¿Cómo obtengo un [!UICONTROL REST API] ID de cliente y un secreto de ?**

Póngase en contacto con el representante de soluciones de socios para obtener las credenciales de acceso de [!DNL API]. Nuestras API utilizan los estándares [OAuth 2.0](https://oauth.net/2/) para la autenticación, autorización y renovación de tokens. Consulte [Autenticación OAuth](../api/rest-api-main/aam-api-getting-started.md#oauth) para obtener más información.
