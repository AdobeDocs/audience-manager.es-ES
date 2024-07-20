---
description: Las API de servidor a servidor (S2S) proporcionan código y métodos que le permiten enviar y recibir datos de usuario de DCS y trabajar con esta información en sus propios sistemas o aplicaciones.
seo-description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-title: DCS APIs for Server-to-Server Data Transfers
solution: Audience Manager
title: API de DCS para transferencias de datos de servidor a servidor
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# API de DCS para transferencias de datos de servidor a servidor{#dcs-apis-for-server-to-server-data-transfers}

Los [!DNL API]s de servidor a servidor ([!UICONTROL S2S]) proporcionan código y métodos que le permiten enviar y recibir datos de usuario de [!DNL DCS] y trabajar con esta información en sus propios sistemas o aplicaciones.

## Casos de uso comunes {#common-use-cases}

Las transferencias de [!UICONTROL Server-to-server] pueden ayudarle a personalizar páginas de aterrizaje u otras interacciones en función de los intereses de los visitantes. Algunos casos de uso comunes incluyen:

* Personalización en el sitio: adapte la experiencia de un visitante en su sitio añadiendo dinámicamente contenido relevante y llamadas a la acción en función de los segmentos a los que pertenece.
* Mejorar el servicio al cliente: importe [!DNL Audience Manager] segmentos a [!DNL CRM] u otro sistema mediante una transferencia de datos de servidor a servidor. Estos datos pueden proporcionar servicio de llamadas o operadores de chat en línea con información relevante y personalizada sobre un cliente.

## Requisitos: ID de usuario y nombres de servidor regionales {#requirements}

[!UICONTROL DCS API] requiere identificadores de usuario y de región para validar y realizar solicitudes de datos.

* El ID de usuario es obligatorio porque necesita asociar datos con un visitante en particular.
* El ID de región es necesario para enlazar llamadas de nuevo con un nombre de servidor y porque los datos de usuario se almacenan en centros de datos geográficamente más cercanos a los visitantes del sitio.

## Introducción {#getting-started}

Actualmente, esta guía explica cómo:

* Obtenga los identificadores de usuario y región de los [!DNL DCS] archivos que quizá ya reciba como cliente de [!DNL Audience Manager].

* Obtenga los identificadores de usuario y región si usa [!DNL Visitor ID Service].
* Realice llamadas a [!DNL DCS] después de que tenga el usuario y el ID de región.

Agregaremos nuevos métodos a medida que estén disponibles. Consulte las secciones siguientes para empezar.

* [Obtención de ID y regiones de usuario a partir de una respuesta de DCS](dcs-aam-ids.md)
* [Obtención de ID y regiones de usuario mediante el ID de Experience Cloud...](dcs-mcid-ids.md)
* [Realización de llamadas de API de DCS de servidor a servidor](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [Referencia de API de DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)
