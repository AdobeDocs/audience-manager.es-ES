---
description: Las API de servidor a servidor ofrecen código y métodos que permiten enviar y recibir datos de usuarios de DCS y trabajar con esta información en sus propios sistemas o aplicaciones.
seo-description: Las API de servidor a servidor ofrecen código y métodos que permiten enviar y recibir datos de usuarios de DCS y trabajar con esta información en sus propios sistemas o aplicaciones.
seo-title: API de DCS para transferencias de datos servidor a servidor
solution: Audience Manager
title: API de DCS para transferencias de datos servidor a servidor
uuid: 8 c 369166-c 8 a 7-46 b 0-9913-4 c 027 f 5 b 1 df 9
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# DCS APIs for Server-to-Server Data Transfers{#dcs-apis-for-server-to-server-data-transfers}

Server-to-server ([!UICONTROL S2S]) [!DNL API]s provide code and methods that let you send and receive [!UICONTROL DCS] user data and work with this information in your own systems or applications.

## Common Use Cases {#common-use-cases}

[!UICONTROL Server-to-server] las transferencias pueden ayudarle a personalizar las páginas de aterrizaje u otras interacciones en función de los intereses del visitante. Algunos casos de uso común son:

* Personalización in situ: Adaptar la experiencia de un visitante en el sitio añadiendo de forma dinámica contenido relevante y llamadas a acción en función de los segmentos a los que pertenecen.
* Improve customer service: Import [!DNL Audience Manager] segments into a [!DNL CRM] or other system through a server-to-server data transfer. Estos datos pueden proporcionar servicios de llamada o operadores de chat en línea con información relevante y personalizada sobre un cliente.

## Requirements: User IDs and Regional Server Names {#requirements}

The [!UICONTROL DCS API] requires user IDs and region IDs to validate and make data requests.

* El ID de usuario es obligatorio porque necesita asociar datos a un visitante concreto.
* El ID de región es necesario para vincular llamadas de vuelta a un nombre de servidor y porque los datos de usuario se almacenan en centros de datos que son geográficamente más cercanos a los visitantes del sitio.

## Introducción {#getting-started}

Actualmente, esta guía cubre cómo:

* Get the user and region IDs from the [!UICONTROL DCS] files you may already receive as an [!DNL Audience Manager] customer.

* Get the user and region IDs if you use the [!DNL Visitor ID Service].
* Make calls to the [!UICONTROL DCS] after you have the user and region ID.

Agregaremos nuevos métodos a medida que estén disponibles. Consulte las secciones siguientes para comenzar.

* [Obtención de ID de usuario y regiones desde una respuesta de DCS](dcs-aam-ids.md)
* [Obtener ID de usuario y regiones mediante Experience Cloud ID…](dcs-mcid-ids.md)
* [Realización de llamadas de API de servidor a servidor](dcs-s2s-calls.md)

>[!MORE_ LIKE_ THIS]
>
>* [Referencia de API de DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

