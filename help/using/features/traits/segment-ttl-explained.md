---
description: Cómo afecta el intervalo de tiempo de vida (TTL) del rasgo a la pertenencia a segmentos.
seo-description: Cómo afecta el intervalo de tiempo de vida (TTL) del rasgo a la pertenencia a segmentos.
seo-title: Tiempo de permanencia explicado por segmentos y características
solution: Audience Manager
title: Tiempo de vida del segmento explicado
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 3%

---


# Tiempo de vida explicado del segmento y el rasgo {#segment-time-to-live-explained}

Cómo afecta el intervalo de características [!UICONTROL time-to-live] ([!DNL TTL]) a la pertenencia a segmentos.

<!-- segment-ttl-explained.xml -->

## Tiempo de vida

[!DNL TTL] define cuánto tiempo permanece un visitante del sitio en un segmento después del último evento de calificación de rasgos. [!DNL TTL]El se establece en rasgos y no en segmentos. Los visitantes salen de un segmento si no cumplen los requisitos para una característica antes del final del intervalo [!DNL TTL]. El valor predeterminado [!DNL TTL] para las nuevas características es de 120 días. Cuando se establece en 0 días, la característica nunca caduca. [Establezca el ](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) valor TTL cuando cree o edite una característica en la  [!UICONTROL Advanced Options] sección de la interfaz de creación de características.

### 1 día TTL explicado

Al establecer el [!DNL TTL] en 1 día, el temporizador TTL inicio al día siguiente de la realización de rasgos, sin contar las horas restantes en el día de realización de rasgos.

El Audience Manager calcula la [!DNL TTL] caducidad de las características con 1 día [!DNL TTL] en función de la fórmula siguiente:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Ejemplo 1**: Un rasgo realizado a la 1:00  [!DNL UTC], con un día  [!DNL TTL]. [!DNL TTL] caducará 24 + 24 - 1 = 47 horas después.
* **Ejemplo 2**: Un rasgo realizado a las 23:00  [!DNL UTC], con un día  [!DNL TTL]. [!DNL TTL] caducará 24 + 24 - 23 = 25 horas después.

## [!DNL TTL] y abandono de un segmento

Un usuario sale de un segmento si no cumple los requisitos para ninguna de sus características dentro del intervalo [!DNL TTL]. Por ejemplo: si tiene un segmento de 1 característica con 30 días [!DNL TTL], el usuario dejará de participar en ese segmento si no cumple los requisitos para la característica nuevamente en los próximos 30 días.

![](assets/ttl-explained.png)

## [!DNL TTL] y renovación de segmentos

El [!DNL TTL] se restablece y el usuario permanece en un segmento si cumple los requisitos para la característica de ese segmento dentro del período [!DNL TTL]. Además, como la mayoría de los segmentos contienen varias características con sus propios intervalos [!DNL TTL], un usuario puede permanecer en un segmento y restablecer el intervalo [!DNL TTL], siempre y cuando siga calificando para cualquier característica asociada con el segmento.

Por ejemplo: supongamos que tiene el segmento 1 compuesto por la característica A (30 días [!DNL TTL]) y la característica B (15 días [!DNL TTL]). Suponiendo que un visitante se califica para cada característica una sola vez, la siguiente ilustración describe el proceso de renovación [!DNL TTL] y la duración total en el segmento.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] Los TTL son independientes de la configuración TTL de terceros

Recuerde que el [!DNL TTL] conjunto en el píxel [!DNL Audience Manager] funciona de forma independiente del [!DNL TTL] conjunto en otros píxeles utilizados por terceros ([!DNL DSP]s, redes de publicidad, etc.).

>[!MORELIKETHIS]
>
>* [Configurar un intervalo de caducidad de características](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

