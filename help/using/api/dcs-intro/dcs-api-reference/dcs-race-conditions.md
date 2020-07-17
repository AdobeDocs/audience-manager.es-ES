---
description: Describe cómo evitar las condiciones de carrera y el manejo de errores de DCS.
seo-description: Describe cómo evitar las condiciones de carrera y el manejo de errores de DCS.
seo-title: Condiciones de carrera y gestión de errores
solution: Audience Manager
title: Condiciones de carrera y gestión de errores
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 7%

---


# Condiciones de carrera y gestión de errores {#race-conditions-and-error-handling}

Describe cómo evitar las condiciones de carrera y el manejo de [!DNL DCS] errores.

## Prevención de las condiciones de carrera {#prevent-race-conditions}

Se puede producir una condición de carrera si se envían varias llamadas simultáneamente (o en rápida sucesión) a la cookie [!DNL DCS] antes de que termine de responder a las consultas iniciales y de escribir datos en la cookie del usuario. Una condición de carrera no es deseable porque puede dañar o sobrescribir incorrectamente los datos de cookies. Como práctica recomendada, considere los siguientes métodos para ayudar a evitar este problema:

* No realice llamadas simultáneas, ni llamadas sucesivas, al mismo usuario [!DNL DCS] de manera rápida.
* Espere a que se devuelva cada respuesta antes de realizar llamadas posteriores.

## Administración de errores {#error-handling}

La gestión de errores está limitada para consultas no válidas o mal formadas. Una solicitud no válida devuelve una `HTTP 200 OK` respuesta sin datos. Además, el [!DNL DCS] deja de procesar una solicitud, descarta los datos de características y devuelve una `HTTP 200 OK` respuesta cuando un usuario:

* Exclusión de seguimiento en el nivel de Audience Manager o socio.
* Proviene de una región geográfica no válida o no seleccionada.
* Deshabilita las cookies del explorador (de todos o de terceros).

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).