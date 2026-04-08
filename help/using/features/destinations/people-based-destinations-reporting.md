---
description: People-Based Destinations presenta la noción de audiencias compartibles en Audience Manager. Esta métrica le ayuda a comprender cuántas direcciones de correo electrónico con hash puede compartir Audience Manager con la plataforma de destino.
seo-description: People-Based Destinations introduce the notion of Shareable Audiences to Audience Manager. This metric helps you understand how many of the hashed email addresses Audience Manager can share with the destination platform.
seo-title: Shareable Audiences
solution: Audience Manager
title: Audiencias compartibles
feature: People-based Destinations
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
TQID: https://experienceleague.adobe.com/k-f2lTvCntfTu6pvQm-y4Ah6VqJIDsXkAhTw4sjngj8
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: c814092e-2730-45e8-a12d-e084529f52cb
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 505
ht-degree: 0%

---

# Audiencias compartibles {#shareable-audiences}

>[!IMPORTANT]
>Este artículo contiene documentación del producto que le guiará a través de la configuración y el uso de esta función. Nada de lo que contiene aquí es asesoramiento legal. Por favor, consulte a su propio asesor legal para obtener orientación legal.

[!DNL People-Based Destinations] trajo la noción de [!DNL Shareable Audiences] a Audience Manager. Esta métrica le ayuda a comprender cuántas direcciones de correo electrónico con hash puede compartir Audience Manager con la plataforma de destino.

[!DNL Shareable Audiences] es una métrica que le ayuda a interpretar los datos de audiencia en el contexto de [!DNL People-Based Destinations]. Puede ver esta métrica en la página [!UICONTROL Destinations] y en la página [!UICONTROL Segment].

## Audiencias compartibles de segmentos {#segment-shareable-audiences}

La métrica [!DNL Segment Shareable Audience] de la página del segmento indica el número de direcciones de correo electrónico con hash del origen de datos con [DPUUID](../../reference/ids-in-aam.md) coincidentes, que también cumplen los requisitos para el segmento definido en el período retrospectivo determinado, dada la regla de combinación de perfiles aplicada en él y que Audience Manager puede compartir con la plataforma de destino.

Esta métrica tiene un periodo retrospectivo de 1 día. Esto le ayuda a comprender el alcance de audiencia del segmento en un destino específico.

## Audiencia compartible de destino {#destination-shareable-audience}

La métrica [!DNL Destination Shareable Audience] en una página de destino basada en personas indica el número total de direcciones de correo electrónico con hash del origen de datos con [DPUUID](../../reference/ids-in-aam.md) coincidentes que Audience Manager puede compartir con la plataforma de destino, a partir de todos los segmentos asignados a ese destino.

![audiencias compartibles](assets/dest-shareable-audiences.png)

Esta métrica tiene un período retrospectivo de duración. Esto le ayuda a comprender la escala de la audiencia a la que puede acceder desde la fuente de datos de direcciones de correo electrónico con hash.

## Ejemplo

Un cliente de Audience Manager tiene una fuente de datos con 110 000 [DPUUID](../../reference/ids-in-aam.md) (ID de CRM). Ingresan 100 000 direcciones de correo electrónico con hash en Audience Manager, las utilizan con varios destinos basados en personas y sincronizan los ID con las 100 000 direcciones de correo electrónico con hash con los ID de CRM. El cliente puede usar la regla de combinación [!DNL All Cross-Device Profiles] para crear tres segmentos de audiencia:

* Segmento A con un recuento de población de 10 000, asignado al destino A;
* Segmento B con un recuento de población de 20 000, asignado al destino A;
* Segmento C con un recuento de población de 50 000, asignado al destino B.

En este escenario:

* Segmento A: audiencia compartible = 10 000;
* Audiencia compartible del segmento B = 20 000;
* Audiencia compartible del segmento C = 50 000;
* Destino A: Audiencia Que Se Puede Compartir = Segmento A: Audiencia Que Se Puede Compartir + Segmento B: Audiencia Que Se Puede Compartir = 30 000;
* Destino B Audiencia Compartida = Segmento C Audiencia Compartida = 50 000.

![diagrama-audiencias-compartibles](assets/shareable-audiences.png)

>[!NOTE]
>
>En el ejemplo anterior, no significa que las 80 000 direcciones de correo electrónico con hash de los tres segmentos coincidan con cuentas existentes en las plataformas de destino. Solo significa que Audience Manager envía los identificadores hash de los tres segmentos a sus respectivos destinos. Al enviar segmentos de audiencia a destinos basados en personas, la coincidencia de audiencias se produce en el lado del socio. El destino A puede tener hasta 30 000 cuentas de usuario coincidentes, mientras que el destino B puede tener hasta 50 000 cuentas de usuario coincidentes, pero no hay garantía de tasas de coincidencia. Adobe no tiene acceso a métricas específicas de socios. Consulte [Tasas de coincidencia](../../faq/faq-people-based-destinations.md#match-rates) para ver las preguntas más frecuentes acerca de la visibilidad de los destinos basados en personas en las tasas de coincidencia.
