---
description: Métodos que permiten trabajar mediante programación con funciones de destino.
seo-description: Métodos que permiten trabajar mediante programación con funciones de destino.
seo-title: Métodos de la API de destino
solution: Audience Manager
title: Métodos de la API de destino
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Métodos de la API de destino {#destination-api-methods}

Métodos que permiten trabajar mediante programación con funciones de destino.

<!-- c_destinations_api.xml -->

En Audience Manager, un destino es cualquier otro sistema (servidor de publicidad, red de publicidad, intercambio, su propia cookie de origen, etc.) [!DNL DSP] que desea compartir datos.

## Tipos de destino: URL y cookie {#destination-types}

Enumera las variables utilizadas por el `destinationType` parámetro. Especifique `push` o `ADS` trabaje con un [!UICONTROL URL] o [!UICONTROL cookie destination]. No puede crear [!UICONTROL server-to-server destinations] con los [!DNL API] métodos de destino disponibles.

<!-- r_destination_types.xml -->

| Tipo de destino de API | Tipo de destino de UI |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORE_LIKE_THIS]
>
>* [Cómo elegir un tipo de destino](../../../features/destinations/destinations.md)

