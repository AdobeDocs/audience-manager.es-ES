---
description: Describe cómo evitar las condiciones de carrera y la gestión de errores de DCS.
seo-description: Describe cómo evitar las condiciones de carrera y la gestión de errores de DCS.
seo-title: Condiciones de carrera y administración de errores
solution: Audience Manager
title: Condiciones de carrera y administración de errores
uuid: b 0 aac 960-6732-4 e 96-87 a 5-40 ba 2755 e 02 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Race Conditions and Error Handling {#race-conditions-and-error-handling}

Describes how to prevent race conditions and [!UICONTROL DCS] error handling.

## Preventing Race Conditions {#prevent-race-conditions}

A race condition can occur if you send multiple calls simultaneously (or in rapid succession) to the [!UICONTROL DCS] before it finishes responding to the initial queries and writing data to the user’s cookie. Una condición de carrera no es deseable porque puede dañar o sobrescribir incorrectamente los datos de cookies. Como práctica recomendada, considere los siguientes métodos para evitar este problema:

* Don't make simultaneous calls, or calls in rapid succession, to the [!UICONTROL DCS] from the same user.
* Espere a que cada respuesta regrese antes de realizar llamadas subsiguientes.

## Error Handling {#error-handling}

La gestión de errores está limitada para consultas no válidas o mal formadas. An invalid request returns an `HTTP 200 OK` response and no data. [!UICONTROL DCS] Asimismo, detiene el procesamiento de una solicitud, descarta los datos de características y devuelve `HTTP 200 OK` una respuesta cuando un usuario:

* Desactiva el seguimiento a nivel de Audience Manager o de socio.
* Proviene de una zona geográfica no válida/no seleccionada.
* Desactiva las cookies del navegador (todo o de terceros).

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).