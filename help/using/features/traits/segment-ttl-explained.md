---
description: Cómo afecta el intervalo de tiempo de vida (TTL) del rasgo a la pertenencia a segmentos.
seo-description: Cómo afecta el intervalo de tiempo de vida (TTL) del rasgo a la pertenencia a segmentos.
seo-title: Tiempo de permanencia explicado por segmentos y características
solution: Audience Manager
title: Tiempo de vida del segmento explicado
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Tiempo de vida explicado del segmento y la característica {#segment-time-to-live-explained}

Cómo afecta el intervalo de características [!UICONTROL time-to-live] ([!DNL TTL]) a la pertenencia a segmentos.

<!-- segment-ttl-explained.xml -->

## Tiempo de vida

[!DNL TTL] define cuánto tiempo permanece un visitante del sitio en un segmento después del último evento de calificación de características. [!DNL TTL] se configura en características y no en segmentos. Los visitantes abandonan un segmento si no cumplen los requisitos para una característica antes del final del [!DNL TTL] intervalo. El valor predeterminado [!DNL TTL] para las nuevas características es de 120 días. Cuando se establece en 0 días, la característica nunca caduca. [Establezca el valor](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) TTL cuando cree o edite una característica en la [!UICONTROL Advanced Options] sección de la interfaz de creación de características.

### 1 día TTL explicado

Al establecer el valor [!DNL TTL] en 1 día, el temporizador TTL comienza al día siguiente de la realización de características, sin contar las horas restantes en el día de realización de características.

Audience Manager calcula la caducidad [!DNL TTL] de las características con 1 día [!DNL TTL] basándose en la fórmula siguiente:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Ejemplo 1**: Un rasgo realizado a la 1:00 [!DNL UTC], con un día [!DNL TTL]. [!DNL TTL] caducará 24 + 24 - 1 = 47 horas después.
* **Ejemplo 2**: Un rasgo realizado a las 23:00 [!DNL UTC], con un día [!DNL TTL]. [!DNL TTL] caducará 24 + 24 - 23 = 25 horas después.

## [!DNL TTL] y abandono de un segmento

Un usuario sale de un segmento si no cumple los requisitos para ninguna de sus características dentro del [!DNL TTL] intervalo. Por ejemplo, si tiene un segmento de 1 característica con 30 días [!DNL TTL], el usuario dejará ese segmento si no cumple los requisitos para la característica de nuevo en los próximos 30 días.

![](assets/ttl-explained.png)

## [!DNL TTL] y renovación de segmentos

Se restablece [!DNL TTL] y el usuario permanece en un segmento si cumple los requisitos para la característica de ese segmento dentro del [!DNL TTL] período. Además, dado que la mayoría de los segmentos contienen varias características con sus propios intervalos, un usuario puede permanecer en un segmento y restablecer el [!DNL TTL] [!DNL TTL] intervalo, siempre que siga siendo adecuado para cualquier característica asociada al segmento.

Por ejemplo: supongamos que tiene el segmento 1 compuesto por la característica A (30 días [!DNL TTL]) y la característica B (15 días [!DNL TTL]). Suponiendo que un visitante se califica para cada característica una sola vez, la siguiente ilustración describe el proceso de renovación y la duración total en el segmento del [!DNL TTL] visitante.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] Los TTL son independientes de la configuración TTL de terceros

Recuerde que el [!DNL TTL] conjunto de píxeles [!DNL Audience Manager] funciona de forma independiente del [!DNL TTL] conjunto en otros píxeles utilizados por terceros (redes[!DNL DSP]de publicidad, etc.).

>[!MORELIKETHIS]
>
>* [Configurar un intervalo de caducidad de características](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

