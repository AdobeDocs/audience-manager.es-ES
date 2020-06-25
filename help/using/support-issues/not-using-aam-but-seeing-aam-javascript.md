---
description: No utilizamos Audience Manager pero vemos llamadas de Audience Manager Javascript en el depurador Javascript - ¿Por qué?
seo-description: No lo estamos usando pero vemos llamadas de Audience Manager Javascript en el depurador Javascript - ¿Por qué?
seo-title: No utilizamos Audience Manager pero vemos llamadas de Audience Manager Javascript en el depurador Javascript - ¿Por qué?
solution: Audience Manager
title: No utilizamos Audience Manager pero vemos llamadas de Audience Manager Javascript en el depurador Javascript - ¿Por qué?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 1%

---


# No somos un cliente Audience Manager, pero vemos las llamadas del Audience Manager Javascript en nuestro sitio

## pregunta

No estamos usando Adobe Audience Manager pero vemos llamadas de Audience Manager Javascript en el depurador Javascript.

¿Por qué sucede esto?

## Respuesta

Es probable que esté ejecutando el servicio [de identidad de](https://docs.adobe.com/content/help/en/id-service/using/home.html) Experience Cloud en su propiedad. Si es así, tener esta referencia de Audience Manager no necesariamente hace referencia a la propiedad que ejecuta Audience Manager. En cambio, significa que el Audience Manager está impulsando este servicio.

La llamada al servidor Audience Manager se realiza generalmente para [sincronizar los ID](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html)de cliente.
