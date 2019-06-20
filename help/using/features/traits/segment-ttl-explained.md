---
description: Cómo afecta el intervalo de tiempo a vida (TTL) a la pertenencia al segmento.
seo-description: Cómo afecta el intervalo de tiempo a vida (TTL) a la pertenencia al segmento.
seo-title: Se explicó el segmento y el tiempo de características en Live
solution: Audience Manager
title: Tiempo de segmentación en vivo explicado
uuid: 5 b 2 c 6911-50 b 9-4 b 68-9 dd 4-21128 d 112 eab
translation-type: tm+mt
source-git-commit: 7e9aada98fe9c18c6fc484255b3c9ff33dc59324

---


# Segment and Trait Time-to-Live Explained {#segment-time-to-live-explained}

How trait [!UICONTROL time-to-live] ([!DNL TTL]) interval affects segment membership.

<!-- segment-ttl-explained.xml -->

## Tiempo de lanzamiento

[!DNL TTL] define cuánto tiempo permanece un visitante del sitio en un segmento después del último evento de cualificación de características. [!DNL TTL] se configura en características y no en segmentos. Visitors fall out of a segment if they do not see a qualifying trait before the end of the [!DNL TTL] interval. The default [!DNL TTL] for new traits is 120 days. Cuando se establece en 0 días, la característica nunca caduca. [Configure el valor](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) de TTL cuando cree o edite un rasgo en la [!UICONTROL Advanced Options] sección de la interfaz de creación de rasgos.

## [!DNL TTL] Abandono de un segmento

A user falls out of a segment if they do not see any of its traits within the [!DNL TTL] interval. For example, if you have a 1-trait segment with a 30 days [!DNL TTL], the user will drop out of that segment if they do not see the trait again within the 30 days.

![](assets/ttl_1.png)

## [!DNL TTL] y Renovación de segmentos

The [!DNL TTL] resets, and the user remains in a segment, if they see that segment’s trait within the [!DNL TTL] period. Also, because most segments contain multiple traits with their own [!DNL TTL] periods, a user can remain in a segment (and reset the [!DNL TTL] interval) as long as they keep seeing any traits associated with a segment. For example, say you have Segment 1 composed of Trait A (30 day [!DNL TTL]) and Trait B (15 day [!DNL TTL]). Assuming the user sees each trait only once, the illustration below outlines the [!DNL TTL] renewal process and total in-segment duration.

![](assets/ttl_2.png)

## [!DNL Audience Manager] TTL es independiente de la configuración de TTL de terceros

Remember, the [!DNL TTL] set on your [!DNL Audience Manager] pixel operates independently from the [!DNL TTL] set on other pixels used by third parties ([!DNL DSP]s, ad networks, etc.).

>[!MORE_ LIKE_ THIS]
>
>* [Configurar un intervalo de caducidad de características](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

