---
description: No se está utilizando el Administrador de Audiencias pero se están viendo llamadas de Javascript del Administrador de Audiencias en el depurador Javascript - ¿Por qué?
seo-description: No se están utilizando pero se están viendo llamadas de Javascript del Administrador de Audiencias en el depurador Javascript - ¿Por qué?
seo-title: No se está utilizando el Administrador de Audiencias pero se están viendo llamadas de Javascript del Administrador de Audiencias en el depurador Javascript - ¿Por qué?
solution: Audience Manager
title: No se está utilizando el Administrador de Audiencias pero se están viendo llamadas de Javascript del Administrador de Audiencias en el depurador Javascript - ¿Por qué?
translation-type: tm+mt
source-git-commit: 1f5c1a91f0b5df5291d3143d297e25128b5bb716

---


# No somos clientes del Administrador de Audiencias, pero vemos las llamadas de Javascript del Administrador de Audiencias en nuestro sitio

## pregunta

No estamos utilizando Adobe Audiencia Manager pero vemos llamadas de Javascript del Administrador de Audiencias en el depurador de Javascript.

¿Por qué sucede esto?

## Respuesta

Es probable que esté ejecutando el servicio [de identidad de](https://docs.adobe.com/content/help/en/id-service/using/home.html) Experience Cloud en su propiedad. Si es así, tener esta referencia del Administrador de Audiencias no necesariamente hace referencia a la propiedad que ejecuta el Administrador de Audiencias. En su lugar, significa que el Administrador de Audiencias está alimentando este servicio.

La llamada al servidor del Administrador de Audiencias generalmente se realiza para [sincronizar los ID](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html)de cliente.
