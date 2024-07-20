---
description: Métodos que permiten trabajar mediante programación con las características de destino.
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: Métodos de API de destino
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 0%

---

# Métodos de API de destino {#destination-api-methods}

Métodos que permiten trabajar mediante programación con las características de destino.

<!-- c_destinations_api.xml -->

En Audience Manager, un destino es cualquier otro sistema (servidor de publicidad, [!DNL DSP], red de publicidad, exchange, su propia cookie de origen, etc.) con el que desea compartir datos.

## Tipos de destino: URL y cookie {#destination-types}

Enumera las variables que usa el parámetro `destinationType`. Especifique `push` o `ADS` para trabajar con [!UICONTROL URL] o [!UICONTROL cookie destination]. No puede crear [!UICONTROL server-to-server destinations] con los métodos de destino disponibles [!DNL API].

<!-- r_destination_types.xml -->

| Tipo de destino de API | Tipo de destino de IU |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Cómo elegir un tipo de destino](../../../features/destinations/destinations.md)
