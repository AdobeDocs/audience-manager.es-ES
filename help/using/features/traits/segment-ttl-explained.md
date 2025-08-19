---
description: Cómo afecta el intervalo de tiempo de vida (TTL) de los rasgos a la pertenencia a segmentos.
seo-description: How trait time-to-live (TTL) interval affects segment membership.
seo-title: Segment and Trait Time to Live Explained
solution: Audience Manager
title: Tiempo de vida del segmento explicado
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# Duración explicada del segmento y el rasgo {#segment-time-to-live-explained}

Cómo afecta el intervalo [!UICONTROL time-to-live] ([!DNL TTL]) del rasgo a la pertenencia al segmento.

<!-- segment-ttl-explained.xml -->

## Tiempo que puede permanecer activo

[!DNL TTL] define cuánto tiempo permanece un visitante del sitio en un segmento después del último evento de clasificación de rasgos. [!DNL TTL] se establece en rasgos y no en segmentos. Los visitantes salen de un segmento si no cumplen los requisitos para una característica antes del final del intervalo [!DNL TTL]. El valor predeterminado [!DNL TTL] para las nuevas características es 120 días. Cuando se establece en 0 días, la característica nunca caduca. [Establezca el valor TTL](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) cuando cree o edite un rasgo en la sección [!UICONTROL Advanced Options] de la interfaz de creación de rasgos.

### TTL de 1 día explicado

Al establecer [!DNL TTL] en 1 día, el temporizador TTL se inicia al día siguiente después de la realización de la característica, sin contar las horas que quedan en el día de la realización de la característica.

Audience Manager calcula la caducidad de [!DNL TTL] para los rasgos con 1 día [!DNL TTL] según la siguiente fórmula:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Ejemplo 1**: Un rasgo realizado a las 1:00 [!DNL UTC], con un [!DNL TTL] de 1 día. [!DNL TTL] caducará 24 + 24 - 1 = 47 horas después.
* **Ejemplo 2**: Un rasgo realizado a las 23:00 [!DNL UTC], con un [!DNL TTL] de 1 día. [!DNL TTL] caducará 24 + 24 - 23 = 25 horas después.

## [!DNL TTL] y abandonando un segmento

Un usuario sale de un segmento si no cumple los requisitos para ninguno de sus rasgos dentro del intervalo [!DNL TTL]. Por ejemplo, si tiene un segmento de 1 característica con un periodo de 30 días [!DNL TTL], el usuario abandonará ese segmento si no vuelve a cumplir los requisitos para la característica en los próximos 30 días.

![](assets/ttl-explained.png)

## [!DNL TTL] y renovación de segmentos

[!DNL TTL] se restablece y el usuario permanece en un segmento si cumple los requisitos para el rasgo de ese segmento dentro del período [!DNL TTL]. Además, debido a que la mayoría de los segmentos contienen múltiples rasgos con sus propios intervalos de [!DNL TTL], un usuario puede permanecer en un segmento y restablecer el intervalo de [!DNL TTL], siempre y cuando siga calificando para cualquier rasgo asociado con el segmento.

Por ejemplo, supongamos que tiene el segmento 1 compuesto por el rasgo A (30 días [!DNL TTL]) y el rasgo B (15 días [!DNL TTL]). Suponiendo que un visitante califica para cada rasgo solo una vez, la siguiente ilustración describe el proceso de renovación [!DNL TTL] y la duración total dentro del segmento.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL son independientes de la configuración de TTL de terceros

Recuerde que el píxel [!DNL TTL] establecido en [!DNL Audience Manager] funciona de forma independiente del conjunto [!DNL TTL] establecido en otros píxeles utilizados por terceros ([!DNL DSP]s, redes de anuncios, etc.).

>[!MORELIKETHIS]
>
>* [Establecer un intervalo de caducidad de rasgo](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)
