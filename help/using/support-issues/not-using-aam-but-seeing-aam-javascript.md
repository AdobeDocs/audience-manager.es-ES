---
description: No se utiliza Audience Manager pero se ven llamadas de Javascript de Audience Manager en el depurador Javascript. ¿Por qué?
seo-description: No se utilizan pero se veno llamadas de Javascript de Audience Manager en el depurador Javascript. ¿Por qué?
seo-title: No se utiliza Audience Manager pero se ven llamadas de Javascript de Audience Manager en el depurador Javascript. ¿Por qué?
solution: Audience Manager
title: No se utiliza Audience Manager pero se ven llamadas de Javascript de Audience Manager en el depurador Javascript. ¿Por qué?
feature: Asistencia
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 100%

---

# No somos clientes de Audience Manager, pero vemos las llamadas de Javascript de Audience Manager en nuestra página web

## Pregunta

No utilizamos Adobe Audience Manager pero vemos llamadas de Javascript de Audience Manager en el depurador de Javascript.

¿Por qué?

## Respuesta

Es probable que esté ejecutando [el servicio de identidad de Experience Cloud](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html) en su propiedad. En ese caso, tener esta referencia de Audience Manager no necesariamente hace referencia a la propiedad que ejecuta Audience Manager. En lugar de ello, significa que Audience Manager está alimentando este servicio.

La llamada al servidor de Audience Manager generalmente se realiza para [sincronizar los ID de cliente](https://docs.adobe.com/content/help/es-ES/id-service/using/id-service-api/methods/setcustomerids.html).
