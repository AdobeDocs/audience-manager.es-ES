---
description: Métodos que permiten trabajar mediante programación con las características de destino.
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: Métodos de API de destino
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
TQID: https://experienceleague.adobe.com/8fUlWE0aqgltxB-bS0X1cjE4Dg0-VvHpRjvWQmjKe5s
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 89
ht-degree: 0%

---

# Métodos de API de destino {#destination-api-methods}

Métodos que permiten trabajar mediante programación con las características de destino.

<!-- c_destinations_api.xml -->

En Audience Manager, un destino es cualquier otro sistema (servidor de publicidad, [!DNL DSP], red de publicidad, exchange, su propia cookie de origen, etc.) con el que desee compartir datos.

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
