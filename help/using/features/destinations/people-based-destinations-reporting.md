---
description: 'Los destinos basados en personas introducen la noción de Audiencias compartibles a Audience Manager. Esta métrica le ayuda a comprender cuántas direcciones de correo electrónico con hash puede compartir Audience Manager con la plataforma de destino. '
seo-description: 'Los destinos basados en personas introducen la noción de Audiencias compartibles a Audience Manager. Esta métrica le ayuda a comprender cuántas direcciones de correo electrónico con hash puede compartir Audience Manager con la plataforma de destino. '
seo-title: Audiencias compartibles
solution: Audience Manager
title: Audiencias compartibles
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# Audiencias compartibles {#shareable-audiences}

[!DNL People-Based Destinations] traer la noción [!DNL Shareable Audiences] a Audience Manager. Esta métrica le ayuda a comprender cuántas direcciones de correo electrónico con hash puede compartir Audience Manager con la plataforma de destino.

[!DNL Shareable Audiences] es una métrica que ayuda a interpretar los datos de audiencia en el contexto de [!DNL People-Based Destinations]. Puede ver esta métrica en [!UICONTROL Destinations] la página y en [!UICONTROL Segment] la página.

## Audiencias compartibles en segmentos {#segment-shareable-audiences}

La [!DNL Segment Shareable Audience] métrica de la página de segmentos indica el número de direcciones de correo electrónico con hash de la fuente de datos con [los DPUUID coincidentes](../../reference/ids-in-aam.md), que también cumplen los criterios del segmento definido en un período de retroceso determinado, teniendo en cuenta la regla de combinación de perfiles aplicada y que Audience Manager puede compartir con la plataforma de destino.

Esta métrica tiene un período de espera de 1 día. Esto ayuda a comprender el alcance de la audiencia para el segmento en un destino específico.

## Audiencia compartible de destino {#destination-shareable-audience}

La [!DNL Destination Shareable Audience] métrica de una página de destino basada en personas indica el número total de direcciones de correo electrónico con hash del origen de datos que coinciden con [los DPUUID coincidentes](../../reference/ids-in-aam.md), que Audience Manager puede compartir con la plataforma de destino, de todos los segmentos asignados a ese destino.

![audiencias compartibles](assets/dest-shareable-audiences.png)

Esta métrica tiene un período de espera de duración. Esto ayuda a comprender la escala de la audiencia a la que puede acceder desde la fuente de datos con hash dirección de correo electrónico.

## Ejemplo

Un cliente de Audience Manager tiene un origen de datos con 110 000 [dpuuid](../../reference/ids-in-aam.md) (ID de CRM). Insertan 100 000 direcciones de correo electrónico con hash en Audience Manager para usarlas con varios destinos basados en personas y realizan una sincronización de ID para las 100 000 direcciones de correo electrónico con hash frente a los ID de CRM. El cliente puede utilizar la regla [!DNL All Cross-Device Profiles] de combinación para crear tres segmentos de audiencia:

* Segmento A con un recuento de población de 10.000, asignado al Destino A;
* Segmento B con un recuento de población de 20.000, asignado al Destino A;
* Segmento C con un recuento de población de 50.000, asignado al Destino B.

En este escenario:

* Segmentar audiencia compartible = 10 000;
* Audiencia compartible B = 20 000;
* Audiencia compartible C = 50 000;
* Audiencia compartible Audiencia = Segmento A Audiencia compartible + Segmento B Compartible Audiencia = 30 000;
* Audiencia compartible B = Audiencia compartible del segmento C = 50 000.

![sharable-audiences-diagram](assets/shareable-audiences.png)

> [!NOTE]
>
> En el ejemplo anterior, no significa que todas las 80.000 direcciones de correo electrónico con hash de los tres segmentos coincidan con las cuentas existentes en las plataformas de destino. Solo significa que Audience Manager envía los identificadores hash de los tres segmentos a sus respectivos destinos. Al enviar segmentos de audiencia a destinos basados en personas, la coincidencia de audiencias se produce en el lado del socio. El destino A puede tener hasta 30.000 cuentas de usuario coincidentes, mientras que el destino B puede tener hasta 50.000 cuentas de usuario coincidentes, pero no existe garantía de tasas de coincidencia. Adobe no tiene acceso a las métricas específicas del socio. Consulte [Tasas](../../faq/faq-people-based-destinations.md#match-rates) de coincidencia para las preguntas más frecuentes sobre la visibilidad de destinos basados en personas en tasas de coincidencia.
