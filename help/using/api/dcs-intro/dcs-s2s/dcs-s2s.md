---
description: Las API de servidor a servidor (S2S) proporcionan código y métodos que le permiten enviar y recibir datos de usuario de DCS y trabajar con esta información en sus propios sistemas o aplicaciones.
seo-description: Las API de servidor a servidor (S2S) proporcionan código y métodos que le permiten enviar y recibir datos de usuario de DCS y trabajar con esta información en sus propios sistemas o aplicaciones.
seo-title: API de DCS para transferencias de datos de servidor a servidor
solution: Audience Manager
title: API de DCS para transferencias de datos de servidor a servidor
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
translation-type: tm+mt
source-git-commit: e40233ace5cb74743db7d0f9f90707fa596a7e79
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 11%

---


# API de DCS para transferencias de datos de servidor a servidor{#dcs-apis-for-server-to-server-data-transfers}

Servidor a servidor ([!UICONTROL S2S]) [!DNL API]s proporciona código y métodos que permiten enviar y recibir datos de usuario [!DNL DCS] y trabajar con esta información en sus propios sistemas o aplicaciones.

## Casos de uso comunes {#common-use-cases}

[!UICONTROL Server-to-server] las transferencias pueden ayudarle a personalizar páginas de aterrizaje u otras interacciones en función de los intereses del visitante. Algunos casos de uso común incluyen:

* Personalización en el sitio: Adapte la experiencia de un visitante en su sitio agregando de forma dinámica contenido relevante y llamadas a la acción en función de los segmentos a los que pertenece.
* Mejorar el servicio al cliente: Importe segmentos [!DNL Audience Manager] en un [!DNL CRM] u otro sistema a través de una transferencia de datos de servidor a servidor. Estos datos pueden proporcionar a los operadores de servicio de llamadas o chat en línea información relevante y personalizada sobre un cliente.

## Requisitos: ID de usuario y nombres de servidor regionales {#requirements}

El [!UICONTROL DCS API] requiere ID de usuario y de región para validar y realizar solicitudes de datos.

* El ID de usuario es obligatorio porque debe asociar los datos a un visitante en particular.
* El ID de región es necesario para asociar llamadas de vuelta a un nombre de servidor y porque los datos de usuario se almacenan en centros de datos geográficamente más cercanos a los visitantes del sitio.

## Introducción {#getting-started}

Actualmente, esta guía explica cómo:

* Obtenga los ID de usuario y región de los [!DNL DCS] archivos que ya puede recibir como cliente [!DNL Audience Manager].

* Obtenga los ID de usuario y región si utiliza [!DNL Visitor ID Service].
* Realice llamadas a [!DNL DCS] después de disponer del ID de usuario y región.

Añadiremos nuevos métodos a medida que estén disponibles. Consulte las secciones siguientes para empezar.

* [Obtención de ID y regiones de usuario a partir de una respuesta de DCS](dcs-aam-ids.md)
* [Obtención de ID y regiones de usuario mediante el ID de Experience Cloud...](dcs-mcid-ids.md)
* [Realización de llamadas de API de DCS de servidor a servidor](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [Referencia de API de DCS ](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

