---
description: 'People-Based Destinations presenta la noción de Audiencias compartibles con el Audience Manager. Esta métrica le ayuda a comprender cuántas de las direcciones de correo electrónico con hash puede compartir el Audience Manager con la plataforma de destino. '
seo-description: 'People-Based Destinations presenta la noción de Audiencias compartibles con el Audience Manager. Esta métrica le ayuda a comprender cuántas de las direcciones de correo electrónico con hash puede compartir el Audience Manager con la plataforma de destino. '
seo-title: Audiencias compartibles
solution: Audience Manager
title: Audiencias compartibles
feature: Destinos basados en personas
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# Audiencias compartibles {#shareable-audiences}

>[!IMPORTANT]
>Este artículo contiene documentación del producto pensada para guiarle en la configuración y uso de esta función. Nada de lo contenido en este documento es asesoramiento jurídico. Consulte a su propio asesor jurídico para obtener asesoramiento jurídico.

[!DNL People-Based Destinations] llevar la noción de  [!DNL Shareable Audiences] a Audience Manager. Esta métrica le ayuda a comprender cuántas de las direcciones de correo electrónico con hash puede compartir el Audience Manager con la plataforma de destino.

[!DNL Shareable Audiences] es una métrica que le ayuda a interpretar los datos de audiencia en el contexto de  [!DNL People-Based Destinations]. Puede ver esta métrica en la página [!UICONTROL Destinations] y en la página [!UICONTROL Segment].

## Audiencias compartibles con segmentos {#segment-shareable-audiences}

La métrica [!DNL Segment Shareable Audience] de la página de segmentos indica el número de direcciones de correo electrónico con hash del origen de datos que coinciden con [DPUUID](../../reference/ids-in-aam.md), que también cumplen los requisitos para el segmento definido en el periodo retroactivo dado, dada la regla de combinación de perfiles aplicada en él, y que el Audience Manager puede compartir con la plataforma de destino.

Esta métrica tiene un período retrospectivo de 1 día. Esto le ayuda a comprender el alcance de la audiencia para el segmento en un destino específico.

## Audiencia compartible de destino {#destination-shareable-audience}

La métrica [!DNL Destination Shareable Audience] de una página de destino basada en personas indica el número total de direcciones de correo electrónico con hash desde la fuente de datos con [DPUUIDs](../../reference/ids-in-aam.md) coincidentes que el Audience Manager puede compartir con la plataforma de destino, desde todos los segmentos asignados a ese destino.

![audiencias compartibles](assets/dest-shareable-audiences.png)

Esta métrica tiene un período retroactivo de por vida. Esto le ayuda a comprender la escala de audiencia a la que puede llegar desde la fuente de datos de direcciones de correo electrónico con hash.

## Ejemplo

Un cliente Audience Manager tiene una fuente de datos con 110 000 [DPUUID](../../reference/ids-in-aam.md) (ID de CRM). Ingesta 100 000 direcciones de correo electrónico con hash en Audience Manager para usarlas con varios destinos basados en personas y realizan una sincronización de ID para las 100 000 direcciones de correo electrónico con hash con respecto a los ID de CRM. El cliente puede utilizar la regla de combinación [!DNL All Cross-Device Profiles] para crear tres segmentos de audiencia:

* Segmento A con un recuento de población de 10 000, asignado al destino A;
* Segmento B con un recuento de población de 20 000, asignado al destino A;
* Segmento C con un recuento de población de 50 000, asignado al destino B.

En este escenario:

* Audiencia compartible del segmento A = 10 000;
* Audiencia compartible del segmento B = 20 000;
* Audiencia compartible del segmento C = 50 000;
* Destino A Audiencia Compartida = Segmento A Audiencia Compartida + Segmento B Audiencia Compartida = 30 000;
* Destino B Audiencia compartible = Audiencia compartible del segmento C = 50 000.

![shareable-audiences-chart](assets/shareable-audiences.png)

>[!NOTE]
>
>En el ejemplo anterior, no significa que todas las direcciones de correo electrónico con hash de los tres segmentos coincidan con cuentas existentes en las plataformas de destino. Solo significa que el Audience Manager envía los identificadores hash de los tres segmentos a sus respectivos destinos. Al enviar segmentos de audiencia a destinos basados en personas, la coincidencia de audiencias se produce en el lado del socio. El destino A puede tener hasta 30 000 cuentas de usuario coincidentes, mientras que el destino B puede tener hasta 50 000 cuentas de usuario coincidentes, pero no hay garantía de tasas de coincidencia. Adobe no tiene acceso a métricas específicas del socio. Consulte [Tasas de coincidencia](../../faq/faq-people-based-destinations.md#match-rates) para ver las preguntas más frecuentes sobre la visibilidad de los destinos basados en personas en las tasas de coincidencia.
