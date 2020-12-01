---
description: 'Los destinos basados en personas presentan la noción de Audiencias compartibles al Audience Manager. Esta métrica le ayuda a comprender cuántos de los Audience Manager de direcciones de correo electrónico con hash pueden compartir con la plataforma de destino. '
seo-description: 'Los destinos basados en personas presentan la noción de Audiencias compartibles al Audience Manager. Esta métrica le ayuda a comprender cuántos de los Audience Manager de direcciones de correo electrónico con hash pueden compartir con la plataforma de destino. '
seo-title: Audiencias compartibles
solution: Audience Manager
title: Audiencias compartibles
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---


# Audiencias compartibles {#shareable-audiences}

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

[!DNL People-Based Destinations] llevar la noción de  [!DNL Shareable Audiences] a Audience Manager. Esta métrica le ayuda a comprender cuántos de los Audience Manager de direcciones de correo electrónico con hash pueden compartir con la plataforma de destino.

[!DNL Shareable Audiences] es una métrica que ayuda a interpretar los datos de audiencia en el contexto de  [!DNL People-Based Destinations]. Puede ver esta métrica en la página [!UICONTROL Destinations] y en la página [!UICONTROL Segment].

## Audiencias que se pueden compartir segmentos {#segment-shareable-audiences}

La métrica [!DNL Segment Shareable Audience] de la página de segmentos indica el número de direcciones de correo electrónico con hash del origen de datos con [DPUUID](../../reference/ids-in-aam.md) coincidentes, que también califican para el segmento definido en el período de retroactividad dado, dada la regla de combinación de perfiles aplicada en él, y ese Audience Manager puede compartir con la plataforma de destino.

Esta métrica tiene un período retrospectivo de 1 día. Esto le ayuda a comprender el alcance de la audiencia del segmento en un destino específico.

## Audiencia de destino compartido {#destination-shareable-audience}

La métrica [!DNL Destination Shareable Audience] de una página de destino basada en personas indica el número total de direcciones de correo electrónico con hash desde el origen de datos con [DPUUID](../../reference/ids-in-aam.md) coincidentes que el Audience Manager puede compartir con la plataforma de destino, desde todos los segmentos asignados a ese destino.

![audiencias compartibles](assets/dest-shareable-audiences.png)

Esta métrica tiene un período retroactivo de por vida. Esto le ayuda a comprender la escala de la audiencia a la que puede acceder desde el origen de datos de direcciones de correo electrónico con hash.

## Ejemplo

Un cliente Audience Manager tiene un origen de datos con 110.000 [DPUUID](../../reference/ids-in-aam.md) (ID de CRM). Ingresan 100.000 direcciones de correo electrónico con hash en Audience Manager para usarlas con varios destinos basados en personas y realizan una sincronización de ID para las 100.000 direcciones de correo electrónico con hash con los ID de CRM. El cliente puede utilizar la regla de combinación [!DNL All Cross-Device Profiles] para crear tres segmentos de audiencia:

* Segmento A con un recuento de población de 10.000, asignado al destino A;
* Segmento B con un recuento de población de 20.000, asignado al destino A;
* Segmento C con un recuento de población de 50.000, asignado al destino B.

En este escenario:

* Segmento A Audiencia compartible = 10.000;
* Audiencia compartida del segmento B = 20.000;
* Audiencia compartida del segmento C = 50.000;
* Audiencia de destino A compartible = Audiencia compartible del segmento A + Audiencia compartible del segmento B = 30.000;
* Audiencia compartida de destino B = Audiencia compartida de segmento C = 50.000.

![audiencias-compartibles-diagrama](assets/shareable-audiences.png)

>[!NOTE]
>
>En el ejemplo anterior, no significa que todas las direcciones de correo electrónico con hash de los tres segmentos coincidan con las cuentas existentes en las plataformas de destino. Solo significa que el Audience Manager envía los identificadores con hash de los tres segmentos a sus destinos respectivos. Al enviar segmentos de audiencia a destinos basados en personas, la coincidencia de audiencias se produce en el lado del socio. El destino A puede tener hasta 30.000 cuentas de usuario coincidentes, mientras que el destino B puede tener hasta 50.000 cuentas de usuario coincidentes, pero no hay garantía de tasas de coincidencia. Adobe no tiene acceso a métricas específicas del socio. Consulte [Tasas de coincidencia](../../faq/faq-people-based-destinations.md#match-rates) para ver las preguntas más frecuentes sobre la visibilidad de destinos basados en personas en las tasas de coincidencia.
