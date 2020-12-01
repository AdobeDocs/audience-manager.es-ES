---
description: Métodos que le permiten trabajar mediante programación con funciones de destino.
seo-description: Métodos que le permiten trabajar mediante programación con funciones de destino.
seo-title: 'Métodos de la API de destino '
solution: Audience Manager
title: 'Métodos de la API de destino '
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 15%

---


# Métodos de la API de destino {#destination-api-methods}

Métodos que le permiten trabajar mediante programación con funciones de destino.

<!-- c_destinations_api.xml -->

En Audience Manager, un destino es cualquier otro sistema (servidor de publicidad, [!DNL DSP], red de publicidad, intercambio, su propia cookie de origen, etc.) con el que se desea compartir datos.

## Tipos de destino: URL y cookie {#destination-types}

Lista las variables utilizadas por el parámetro `destinationType`. Especifique `push` o `ADS` para trabajar con [!UICONTROL URL] o [!UICONTROL cookie destination]. No puede crear [!UICONTROL server-to-server destinations] con los métodos [!DNL API] de destino disponibles.

<!-- r_destination_types.xml -->

| Tipo de destino de API | Tipo de destino de la interfaz de usuario |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Cómo elegir un tipo de destino](../../../features/destinations/destinations.md)

