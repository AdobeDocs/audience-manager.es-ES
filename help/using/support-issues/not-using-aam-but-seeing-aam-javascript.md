---
description: No se utiliza Audience Manager pero se ven llamadas de Javascript de Audience Manager en el depurador Javascript. ¿Por qué?
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: No se utiliza Audience Manager pero se ven llamadas de Javascript de Audience Manager en el depurador Javascript. ¿Por qué?
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
TQID: 'https://experienceleague.adobe.com/Zpe6ML-WJ5tu4x-gYuPJfAn4IklOxFw2bW8E7ys8YSc'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
    internal-label: Support
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 88%
---
# No somos clientes de Audience Manager, pero vemos las llamadas de Javascript de Audience Manager en nuestra página web

## Pregunta

No utilizamos Adobe Audience Manager pero vemos llamadas de Javascript de Audience Manager en el depurador de Javascript.

¿Por qué?

## Respuesta

Es probable que esté ejecutando [el servicio de identidad de Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es) en su propiedad. En ese caso, tener esta referencia de Audience Manager no necesariamente hace referencia a la propiedad que ejecuta Audience Manager. En lugar de ello, significa que Audience Manager está alimentando este servicio.

La llamada al servidor de Audience Manager generalmente se realiza para [sincronizar los ID de cliente](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=es).
