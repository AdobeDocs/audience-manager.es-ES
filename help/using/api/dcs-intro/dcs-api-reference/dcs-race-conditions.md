---
description: Describe cómo evitar las condiciones de carrera y la gestión de errores de DCS.
seo-description: Describe cómo evitar las condiciones de carrera y la gestión de errores de DCS.
seo-title: Condiciones de carrera y gestión de errores
solution: Audience Manager
title: Condiciones de carrera y gestión de errores
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 7%

---

# Condiciones de carrera y gestión de errores {#race-conditions-and-error-handling}

Describe cómo evitar las condiciones de carrera y el manejo de errores [!DNL DCS].

## Prevención de las condiciones de carrera {#prevent-race-conditions}

Se puede producir una condición de carrera si se envían varias llamadas simultáneamente (o en sucesión rápida) al [!DNL DCS] antes de que termine de responder a las consultas iniciales y de escribir datos en la cookie del usuario. Una condición de carrera no es deseable porque puede dañar o sobrescribir incorrectamente los datos de cookies. Como práctica recomendada, considere los siguientes métodos para ayudar a evitar este problema:

* No realice llamadas simultáneas o llamadas sucesivas rápidas a [!DNL DCS] desde el mismo usuario.
* Espere a que se devuelva cada respuesta antes de realizar llamadas posteriores.

## Gestión de errores {#error-handling}

La gestión de errores está limitada para consultas no válidas o mal formadas. Una solicitud no válida devuelve una respuesta `HTTP 200 OK` sin datos. Además, el [!DNL DCS] deja de procesar una solicitud, descarta los datos de características y devuelve una respuesta `HTTP 200 OK` cuando un usuario:

* Excluye el seguimiento en el nivel de Audience Manager o socio.
* Proviene de una región geográfica no válida/no seleccionada.
* Desactiva las cookies del explorador (de todas o de terceros).

Consulte también [Códigos de error DCS, mensajes y ejemplos](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
