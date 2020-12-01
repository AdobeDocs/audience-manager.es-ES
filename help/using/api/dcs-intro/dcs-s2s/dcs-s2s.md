---
description: Las API de servidor a servidor (S2S) proporcionan código y métodos que le permiten enviar y recibir datos de usuario de DCS y trabajar con esta información en sus propios sistemas o aplicaciones.
seo-description: Las API de servidor a servidor (S2S) proporcionan código y métodos que le permiten enviar y recibir datos de usuario de DCS y trabajar con esta información en sus propios sistemas o aplicaciones.
seo-title: API de DCS para transferencias de datos de servidor a servidor
solution: Audience Manager
title: API de DCS para transferencias de datos de servidor a servidor
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 11%

---


# API de DCS para transferencias de datos de servidor a servidor{#dcs-apis-for-server-to-server-data-transfers}

Servidor a servidor ([!UICONTROL S2S]) [!DNL API]s proporciona código y métodos que permiten enviar y recibir [!DNL DCS] datos de usuario y trabajar con esta información en sus propios sistemas o aplicaciones.

## Casos de uso común {#common-use-cases}

[!UICONTROL Server-to-server] las transferencias pueden ayudarle a personalizar páginas de aterrizaje u otras interacciones en función de los intereses del visitante. Algunos casos de uso común incluyen:

* Personalización in situ: Personalice la experiencia de un visitante en el sitio agregando de forma dinámica contenido relevante y llamadas a acción en función de los segmentos a los que pertenecen.
* Mejorar el servicio al cliente: Importar [!DNL Audience Manager] segmentos a un [!DNL CRM] u otro sistema mediante una transferencia de datos de servidor a servidor. Estos datos pueden proporcionar al servicio de llamadas o a los operadores de chat en línea información relevante y personalizada sobre un cliente.

## Requisitos: ID de usuario y nombres de servidor regionales {#requirements}

El [!UICONTROL DCS API] requiere ID de usuario e ID de región para validar y realizar solicitudes de datos.

* El ID de usuario es obligatorio porque necesita asociar datos con un visitante en particular.
* El ID de región es necesario para volver a enlazar las llamadas al nombre de un servidor y porque los datos de usuario se almacenan en centros de datos geográficamente más cercanos a los visitantes del sitio.

## Introducción {#getting-started}

Actualmente, esta guía explica cómo:

* Obtenga los ID de usuario y región de los [!DNL DCS] archivos que ya puede recibir como cliente [!DNL Audience Manager].

* Obtenga los ID de usuario y región si utiliza [!DNL Visitor ID Service].
* Realice llamadas al [!DNL DCS] después de tener el ID de usuario y región.

Agregaremos nuevos métodos a medida que estén disponibles. Consulte las siguientes secciones para comenzar.

* [Obtención de ID y regiones de usuario a partir de una respuesta de DCS](dcs-aam-ids.md)
* [Obtener ID de usuario y regiones a través del ID de Experience Cloud...](dcs-mcid-ids.md)
* [Realización de llamadas de API de DCS de servidor a servidor](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [Referencia de API de DCS ](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

