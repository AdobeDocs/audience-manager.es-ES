---
description: Describe cómo evitar condiciones de carrera y la administración de errores DCS.
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: Condiciones de carrera y gestión de errores
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 2%

---

# Condiciones de carrera, limitación de velocidad y gestión de errores {#race-conditions-and-error-handling}

Describe cómo prevenir las condiciones raciales y [!DNL DCS] gestión de errores.

## Prevención de las condiciones de carrera {#prevent-race-conditions}

Se puede producir una condición de carrera si envía varias llamadas simultáneamente (o en sucesión rápida) a [!DNL DCS] antes de terminar de responder a las consultas iniciales y escribir datos en la cookie del usuario. Una condición de carrera no es deseable porque puede dañarse o sobrescribir incorrectamente los datos de cookies. Como práctica recomendada, considere los siguientes métodos para evitar este problema:

* No realice llamadas simultáneas, ni llamadas en sucesión rápida, al [!DNL DCS] del mismo usuario.
* Espere a que vuelva cada respuesta antes de realizar llamadas posteriores.

## Limitación de velocidad {#rate-limiting}

El Adobe de puede introducir una limitación de velocidad si detecta llamadas de API de DCS excesivas que podrían tener un impacto negativo en la disponibilidad del servicio.

Si la limitación de velocidad está habilitada, es posible que reciba una `429 Too Many Requests` Código de estado de respuesta HTTP en las llamadas DCS. Cuando reciba esta respuesta HTTP, vuelva a intentar las llamadas a la API más adelante.

## Control de errores {#error-handling}

El control de errores es limitado para consultas no válidas o mal formadas. Una solicitud no válida devuelve un `HTTP 200 OK` respuesta y sin datos. Además, la variable [!DNL DCS] detiene el procesamiento de una solicitud, descarta los datos de rasgos y devuelve un `HTTP 200 OK` respuesta cuando un usuario:

* Excluye el seguimiento en el nivel de Audience Manager o socio.
* Proviene de una región geográfica no válida o no seleccionada.
* Deshabilita las cookies del explorador (todas o de terceros).

Consulte también. [Códigos de error DCS, mensajes y ejemplos](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
