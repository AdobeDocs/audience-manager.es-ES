---
description: Cómo afecta el intervalo de tiempo de vida (TTL) del rasgo a la pertenencia al segmento.
seo-description: Cómo afecta el intervalo de tiempo de vida (TTL) del rasgo a la pertenencia al segmento.
seo-title: Tiempo de vida explicado del segmento y el rasgo
solution: Audience Manager
title: Tiempo de vida explicado en el segmento
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: 'Rasgos '
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 3%

---

# Tiempo de vida explicado del segmento y el rasgo {#segment-time-to-live-explained}

Cómo afecta el intervalo de rasgos [!UICONTROL time-to-live] ([!DNL TTL]) a la pertenencia a los segmentos.

<!-- segment-ttl-explained.xml -->

## Tiempo de vida

[!DNL TTL] define cuánto tiempo permanece un visitante del sitio en un segmento después del último evento de calificación de rasgos. [!DNL TTL]El se establece en rasgos y no en segmentos. Los visitantes salen de un segmento si no cumplen los requisitos para un rasgo antes del final del intervalo [!DNL TTL]. El valor predeterminado [!DNL TTL] para las nuevas características es de 120 días. Cuando se establece en 0 días, el rasgo nunca caduca. [Establezca el ](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) valor TTL cuando cree o edite un rasgo en la  [!UICONTROL Advanced Options] sección de la interfaz de creación de rasgos.

### Explicación de TTL de 1 día

Al establecer [!DNL TTL] en 1 día, el temporizador TTL se inicia al día siguiente de la realización del rasgo, sin contar las horas restantes en el día de realización del rasgo.

El Audience Manager calcula la [!DNL TTL] caducidad de los rasgos con 1 día [!DNL TTL] en función de la fórmula siguiente:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Ejemplo 1**: Un rasgo realizado a la 1:00  [!DNL UTC], con un día  [!DNL TTL]. [!DNL TTL] caducará 24 + 24 - 1 = 47 horas después.
* **Ejemplo 2**: Un rasgo realizado a las 23:00  [!DNL UTC], con un día  [!DNL TTL]. [!DNL TTL] caducará 24 + 24 - 23 = 25 horas después.

## [!DNL TTL] y salir de un segmento

Un usuario abandona un segmento si no cumple los requisitos para ninguno de sus rasgos dentro del intervalo [!DNL TTL]. Por ejemplo, si tiene un segmento de 1 característica con un segmento [!DNL TTL] de 30 días, el usuario abandonará ese segmento si no vuelve a cumplir los requisitos para el rasgo en los próximos 30 días.

![](assets/ttl-explained.png)

## [!DNL TTL] y renovación de segmentos

El [!DNL TTL] se restablece y el usuario permanece en un segmento si cumple los requisitos para el rasgo de ese segmento dentro del [!DNL TTL] período. Además, como la mayoría de los segmentos contienen varios rasgos con sus propios intervalos [!DNL TTL] , un usuario puede permanecer en un segmento y restablecer el intervalo [!DNL TTL] siempre que siga cumpliendo los requisitos para cualquier rasgo asociado con el segmento.

Por ejemplo, supongamos que tiene el segmento 1 compuesto por el rasgo A (30 días [!DNL TTL]) y el rasgo B (15 días [!DNL TTL]). Suponiendo que un visitante se califica para cada rasgo solo una vez, la siguiente ilustración describe el proceso de renovación [!DNL TTL] y la duración total del segmento.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] Los TTL son independientes de la configuración de TTL de terceros

Recuerde que el [!DNL TTL] configurado en su [!DNL Audience Manager] píxel funciona de forma independiente del [!DNL TTL] configurado en otros píxeles utilizados por terceros ([!DNL DSP]s, redes de publicidad, etc.).

>[!MORELIKETHIS]
>
>* [Establecer un intervalo de caducidad del rasgo](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

