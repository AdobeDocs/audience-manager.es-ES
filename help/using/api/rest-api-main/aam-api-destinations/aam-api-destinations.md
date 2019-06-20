---
description: Métodos que permiten trabajar de forma programática con funciones de destino.
seo-description: Métodos que permiten trabajar de forma programática con funciones de destino.
seo-title: Métodos de API de destino
solution: Audience Manager
title: Métodos de API de destino
uuid: 048 bcdb 9-2 b 31-46 f 4-8 b 80-4 ba 25 bf 06640
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Destination API Methods {#destination-api-methods}

Métodos que permiten trabajar de forma programática con funciones de destino.

<!-- c_destinations_api.xml -->

In Audience Manager, a destination is any other system (ad server, [!DNL DSP], ad network, exchange, your own first-party cookie, etc.) a los que desee compartir datos.

## Destination Types: URL and Cookie {#destination-types}

Lists the variables used by the `destinationType` parameter. Specify `push` or `ADS` to work with a [!UICONTROL URL] or [!UICONTROL cookie destination]. You cannot create [!UICONTROL server-to-server destinations] with the available destination [!DNL API] methods.

<!-- r_destination_types.xml -->

| Tipo de destino de API | Tipo de destino de la interfaz de usuario |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORE_ LIKE_ THIS]
>
>* [Cómo elegir un tipo de destino](../../../features/destinations/destinations.md)

