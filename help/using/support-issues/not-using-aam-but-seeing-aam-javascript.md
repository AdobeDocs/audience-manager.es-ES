---
description: No se utiliza Audience Manager pero se ven llamadas de Javascript de Audience Manager en el depurador Javascript. ¿Por qué?
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: No se utiliza Audience Manager pero se ven llamadas de Javascript de Audience Manager en el depurador Javascript. ¿Por qué?
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 98%

---

# No somos clientes de Audience Manager, pero vemos las llamadas de Javascript de Audience Manager en nuestra página web

## Pregunta

No utilizamos Adobe Audience Manager pero vemos llamadas de Javascript de Audience Manager en el depurador de Javascript.

¿Por qué?

## Respuesta

Es probable que esté ejecutando [el servicio de identidad de Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html) en su propiedad. En ese caso, tener esta referencia de Audience Manager no necesariamente hace referencia a la propiedad que ejecuta Audience Manager. En lugar de ello, significa que Audience Manager está alimentando este servicio.

La llamada al servidor de Audience Manager generalmente se realiza para [sincronizar los ID de cliente](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html).
