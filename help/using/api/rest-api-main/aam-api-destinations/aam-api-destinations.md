---
description: Métodos que le permiten trabajar mediante programación con funciones de destino.
seo-description: Métodos que le permiten trabajar mediante programación con funciones de destino.
seo-title: 'Métodos de la API de destino '
solution: Audience Manager
title: 'Métodos de la API de destino '
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 16%

---

# Métodos de la API de destino {#destination-api-methods}

Métodos que le permiten trabajar mediante programación con funciones de destino.

<!-- c_destinations_api.xml -->

En Audience Manager, un destino es cualquier otro sistema (servidor de publicidad, [!DNL DSP], red de publicidad, intercambio, su propia cookie de origen, etc.) con el que se desea compartir datos.

## Tipos de destino: URL y cookie {#destination-types}

Enumera las variables utilizadas por el parámetro `destinationType`. Especifique `push` o `ADS` para trabajar con [!UICONTROL URL] o [!UICONTROL cookie destination]. No puede crear [!UICONTROL server-to-server destinations] con los métodos [!DNL API] de destino disponibles.

<!-- r_destination_types.xml -->

| Tipo de destino de API | Tipo de destino de la interfaz de usuario |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Cómo elegir un tipo de destino](../../../features/destinations/destinations.md)

