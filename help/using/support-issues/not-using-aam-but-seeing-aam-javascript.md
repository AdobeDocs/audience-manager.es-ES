---
description: No se está utilizando el Administrador de Audiencias pero se están viendo llamadas de Javascript del Administrador de Audiencias en el depurador Javascript - ¿Por qué?
seo-description: No se están utilizando pero se están viendo llamadas de Javascript del Administrador de Audiencias en el depurador Javascript - ¿Por qué?
seo-title: No se está utilizando el Administrador de Audiencias pero se están viendo llamadas de Javascript del Administrador de Audiencias en el depurador Javascript - ¿Por qué?
solution: Audience Manager
title: No se está utilizando el Administrador de Audiencias pero se están viendo llamadas de Javascript del Administrador de Audiencias en el depurador Javascript - ¿Por qué?
translation-type: tm+mt
source-git-commit: 7206b43562eded19bfb30f8aea3bcad946a3f834

---


# No somos clientes del Administrador de Audiencias, pero vemos las llamadas de Javascript del Administrador de Audiencias en nuestro sitio

## pregunta

No estamos utilizando Adobe Audiencia Manager pero vemos llamadas de Javascript del Administrador de Audiencias en el depurador de Javascript.  ¿Por qué estaría sucediendo esto?

## Respuesta

Es probable que esté ejecutando el servicio de ID de Visitante en su propiedad. Si lo está, tener esta referencia de AAM no necesariamente hace referencia a la propiedad que ejecuta el Administrador de Audiencias, pero significa que el Administrador de Audiencias está realmente impulsando este servicio.

Tenga en cuenta que la llamada de AAM generalmente se realiza para sincronizar los ID de cliente de Set.
