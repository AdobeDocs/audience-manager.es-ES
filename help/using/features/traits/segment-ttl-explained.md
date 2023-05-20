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
source-wordcount: '354'
ht-degree: 3%

---

# Tiempo de vida explicado del segmento y el rasgo {#segment-time-to-live-explained}

Qué rasgo [!UICONTROL time-to-live] ([!DNL TTL]) afecta a la pertenencia a segmentos.

<!-- segment-ttl-explained.xml -->

## Tiempo que puede permanecer activo

[!DNL TTL] define cuánto tiempo permanece un visitante del sitio en un segmento después del último evento de clasificación de rasgos. [!DNL TTL]El se establece en rasgos y no en segmentos. Los visitantes salen de un segmento si no cumplen los requisitos para un rasgo antes del final del [!DNL TTL] intervalo. El valor predeterminado [!DNL TTL] para los rasgos nuevos es de 120 días. Cuando se establece en 0 días, la característica nunca caduca. [Establecer el valor TTL](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) cuando se crea o edita un rasgo en [!UICONTROL Advanced Options] de la interfaz de creación de rasgos.

### TTL de 1 día explicado

Al configurar el [!DNL TTL] Para 1 día, el temporizador TTL se inicia al día siguiente después de la realización de características, sin contar las horas que quedan en el día de realización de características.

El Audience Manager calcula [!DNL TTL] caducidad para rasgos con 1 día [!DNL TTL] se basa en la fórmula siguiente:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Ejemplo 1**: Un rasgo realizado a la 1 [!DNL UTC], con un día [!DNL TTL]. [!DNL TTL] caducará 24 + 24 - 1 = 47 horas después.
* **Ejemplo 2**: Un rasgo realizado a las 23:00 [!DNL UTC], con un día [!DNL TTL]. [!DNL TTL] caducará 24 + 24 - 23 = 25 horas después.

## [!DNL TTL] y exclusión de un segmento

Un usuario queda fuera de un segmento si no cumple los requisitos para ninguno de sus rasgos dentro de la variable [!DNL TTL] intervalo. Por ejemplo, si tiene un segmento de 1 característica con una duración de 30 días [!DNL TTL]Por lo tanto, el usuario abandonará ese segmento si no vuelve a cumplir los requisitos para la característica en los próximos 30 días.

![](assets/ttl-explained.png)

## [!DNL TTL] y renovación de segmentos

El [!DNL TTL] restablece, y el usuario permanece en un segmento, si cumple los requisitos para el rasgo de ese segmento dentro del [!DNL TTL] punto. Además, debido a que la mayoría de los segmentos contienen varios rasgos con los suyos propios [!DNL TTL] intervalos, un usuario puede permanecer en un segmento y restablecer el [!DNL TTL] , siempre que sigan cumpliendo los requisitos para cualquier rasgo asociado con el segmento.

Por ejemplo, supongamos que tiene el segmento 1 compuesto por el rasgo A (30 días) [!DNL TTL]) y rasgo B (15 días) [!DNL TTL]). Suponiendo que un visitante cumple los requisitos para cada rasgo solo una vez, la siguiente ilustración describe el [!DNL TTL] proceso de renovación y duración total en el segmento.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] Los TTL son independientes de la configuración de TTL de terceros

Recuerde, el [!DNL TTL] establezca en su [!DNL Audience Manager] el píxel funciona de forma independiente del [!DNL TTL] se configura en otros píxeles utilizados por terceros ([!DNL DSP]s, redes de anuncios, etc.).

>[!MORELIKETHIS]
>
>* [Definir un intervalo de caducidad de rasgo](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

