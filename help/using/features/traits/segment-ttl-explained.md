---
description: Cómo afecta el intervalo de tiempo de vida (TTL) del rasgo a la pertenencia a segmentos.
seo-description: Cómo afecta el intervalo de tiempo de vida (TTL) del rasgo a la pertenencia a segmentos.
seo-title: Tiempo de permanencia explicado por segmentos y características
solution: Audience Manager
title: Tiempo de vida del segmento explicado
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
translation-type: tm+mt
source-git-commit: 7e9aada98fe9c18c6fc484255b3c9ff33dc59324

---


# Tiempo de vida explicado del segmento y la característica {#segment-time-to-live-explained}

Cómo afecta el intervalo de características [!UICONTROL time-to-live] ([!DNL TTL]) a la pertenencia a segmentos.

<!-- segment-ttl-explained.xml -->

## Tiempo de vida

[!DNL TTL] define cuánto tiempo permanece un visitante del sitio en un segmento después del último evento de calificación de características. [!DNL TTL] se configura en características y no en segmentos. Los visitantes abandonan un segmento si no ven un rasgo de calificación antes del final del [!DNL TTL] intervalo. El valor predeterminado [!DNL TTL] para las nuevas características es de 120 días. Cuando se establece en 0 días, la característica nunca caduca. [Establezca el valor](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) TTL cuando cree o edite una característica en la [!UICONTROL Advanced Options] sección de la interfaz de creación de características.

## [!DNL TTL] y abandono de un segmento

Un usuario sale de un segmento si no ve ninguna de sus características dentro del [!DNL TTL] intervalo. Por ejemplo, si tiene un segmento de 1 característica con 30 días [!DNL TTL], el usuario dejará ese segmento si no vuelve a ver la característica en los 30 días.

![](assets/ttl_1.png)

## [!DNL TTL] y renovación de segmentos

Se restablece [!DNL TTL] y el usuario permanece en un segmento, si ve la característica de ese segmento dentro del [!DNL TTL] período. Además, como la mayoría de los segmentos contienen varias características con sus propios [!DNL TTL] períodos, un usuario puede permanecer en un segmento (y restablecer el [!DNL TTL] intervalo) siempre que siga viendo las características asociadas con un segmento. Por ejemplo: supongamos que tiene el segmento 1 compuesto por la característica A (30 días [!DNL TTL]) y la característica B (15 días [!DNL TTL]). Suponiendo que el usuario ve cada característica una sola vez, la siguiente ilustración describe el proceso de renovación y la duración total del [!DNL TTL] segmento.

![](assets/ttl_2.png)

## [!DNL Audience Manager] Los TTL son independientes de la configuración TTL de terceros

Recuerde que el [!DNL TTL] conjunto de píxeles [!DNL Audience Manager] funciona de forma independiente del [!DNL TTL] conjunto en otros píxeles utilizados por terceros (redes[!DNL DSP]de publicidad, etc.).

>[!MORE_LIKE_THIS]
>
>* [Configurar un intervalo de caducidad de características](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

