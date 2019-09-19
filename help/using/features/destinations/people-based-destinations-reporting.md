---
description: 'Los destinos basados en personas introducen la noción de audiencias compartibles en Audience Manager. Esta métrica le ayuda a comprender cuántas de las direcciones de correo electrónico con hash puede compartir Audience Manager con la plataforma de destino. '
seo-description: 'Los destinos basados en personas introducen la noción de audiencias compartibles en Audience Manager. Esta métrica le ayuda a comprender cuántas de las direcciones de correo electrónico con hash puede compartir Audience Manager con la plataforma de destino. '
seo-title: Audiencias compartibles
solution: Audience Manager
title: Audiencias compartibles
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# Audiencias compartibles {#shareable-audiences}

[!DNL People-Based Destinations] traer la noción de [!DNL Shareable Audiences] a Audience Manager. Esta métrica le ayuda a comprender cuántas de las direcciones de correo electrónico con hash puede compartir Audience Manager con la plataforma de destino.

[!DNL Shareable Audiences] es una métrica que ayuda a interpretar los datos de audiencia en el contexto de [!DNL People-Based Destinations]. Puede ver esta métrica en la [!UICONTROL Destinations] página y en la [!UICONTROL Segment] página.

## Audiencias que se pueden compartir segmentos {#segment-shareable-audiences}

La [!DNL Segment Shareable Audience] métrica de la página de segmentos indica el número de direcciones de correo electrónico con hash del origen de datos con [DPUUID](../../reference/ids-in-aam.md)coincidentes, que también califican para el segmento definido en el período de retroactividad dado, dada la regla de combinación de perfiles aplicada en él, y que Audience Manager puede compartir con la plataforma de destino.

Esta métrica tiene un período retrospectivo de 1 día. Esto le ayuda a comprender el alcance de la audiencia para el segmento en un destino específico.

## Audiencia de destino compartida {#destination-shareable-audience}

La [!DNL Destination Shareable Audience] métrica de una página de destino basada en personas indica el número total de direcciones de correo electrónico con hash del origen de datos con [DPUUID](../../reference/ids-in-aam.md)coincidentes, que Audience Manager puede compartir con la plataforma de destino, de todos los segmentos asignados a ese destino.

![audiencias compartibles](assets/dest-shareable-audiences.png)

Esta métrica tiene un período retroactivo de por vida. Esto le ayuda a comprender la escala de la audiencia a la que puede llegar desde el origen de datos de direcciones de correo electrónico con hash.

## Ejemplo

Un cliente de Audience Manager tiene un origen de datos con 110.000 [DPUUID](../../reference/ids-in-aam.md) (ID de CRM). Ingresan 100.000 direcciones de correo electrónico con hash en Audience Manager para usarlas con varios destinos basados en personas y realizan una sincronización de ID para las 100.000 direcciones de correo electrónico con hash con los ID de CRM. El cliente puede utilizar la regla de [!DNL All Cross-Device Profiles] combinación para crear tres segmentos de audiencia:

* Segmento A con un recuento de población de 10.000, asignado al destino A;
* Segmento B con un recuento de población de 20.000, asignado al destino A;
* Segmento C con un recuento de población de 50.000, asignado al destino B.

En este escenario:

* Segmento A Audiencia Compartida = 10.000;
* Audiencia compartible del segmento B = 20.000;
* Audiencia compartible del segmento C = 50.000;
* Destino A Audiencia Compartida = Audiencia Compartida Del Segmento A + Audiencia Compartida Del Segmento B = 30.000;
* Audiencia compartida de destino B = audiencia compartible de segmento C = 50.000.

![shareable-audiences-chart](assets/shareable-audiences.png)

> [!NOTE]
>
> En el ejemplo anterior, no significa que todas las direcciones de correo electrónico con hash de los tres segmentos coincidan con las cuentas existentes en las plataformas de destino. Solo significa que Audience Manager envía los identificadores con hash de los tres segmentos a sus destinos respectivos. Al enviar segmentos de audiencia a destinos basados en personas, la coincidencia de audiencia se produce en el lado del socio. El destino A puede tener hasta 30.000 cuentas de usuario coincidentes, mientras que el destino B puede tener hasta 50.000 cuentas de usuario coincidentes, pero no hay garantía de tasas de coincidencia. Adobe no tiene acceso a métricas específicas del socio. Consulte Tasas de [coincidencia](../../faq/faq-people-based-destinations.md#match-rates) para ver las preguntas más frecuentes sobre la visibilidad de destinos basados en personas en las tasas de coincidencia.
