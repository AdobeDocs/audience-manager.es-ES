---
description: Describe los segmentos, sus partes constitutivas y la creación de reglas con el Generador de segmentos.
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: Finalidad, composición y reglas de los segmentos
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# Segmentos: propósito, composición y reglas {#segments-purpose-composition-and-rules}

Describe [!UICONTROL segments], sus partes constitutivas y la creación de reglas con [!UICONTROL Segment Builder].

## Propósito de [!UICONTROL Segments]

Un *`segment`* (o un *`audience`*) es un conjunto de usuarios que comparten atributos comunes. En Audience Manager, crea [!UICONTROL segments] con reglas del lado del servidor. Estas reglas permiten crear grupos de audiencia basados en atributos del visitante del sitio como:

* Comportamiento;
* Demografía (edad, sexo, ingresos, etc.);
* Otras características que puede definir en la interfaz de usuario de.

## Composición de [!UICONTROL Segment]

Un Audience Manager [!UICONTROL segment] es una regla del lado del servidor que consta de características individuales o grupos de características. Los rasgos están compuestos por elementos de datos llamados pares clave-valor. Junto con las reglas establecidas en el nivel [!UICONTROL segment], estos pares clave-valor contienen los criterios que califican a los visitantes para la pertenencia de características y [!UICONTROL segment].

## Consideraciones sobre la asignación de [!UICONTROL Adobe Analytics] [!UICONTROL Segment]

Al asignar Adobe Analytics [!UICONTROL segments] o grupos de informes a su organización de Experience Cloud, Audience Manager crea automáticamente [!UICONTROL segments] y características nuevas, correspondientes y de solo lectura. No puede editar ni cambiar la ubicación de almacenamiento de estos [!UICONTROL segments] del Audience Manager. Sin embargo, cualquier cambio que realice en su Adobe Analytics asignado [!UICONTROL segments] o grupos de informes se reflejará en Audience Manager.

>[!TIP]
>
>El Audience Manager [!UICONTROL segments] es diferente de [!DNL Adobe Analytics] [!UICONTROL segments]. Lea [Explicación de los segmentos en Analytics y Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) para ver una descripción detallada de las diferencias.

## Crear [!UICONTROL Segments] Basado En Reglas Con [!UICONTROL Segment Builder]

A diferencia de los píxeles tradicionales que se activan en respuesta a condiciones simples de sí/no, [!UICONTROL Segment Builder] le permite crear requisitos complejos de [!UICONTROL segment]. Al igual que [!UICONTROL traits], [!UICONTROL segments] evalúa los datos con [!DNL Boolean] expresiones ([!DNL AND], [!DNL OR], [!DNL NOT]), operadores de comparación (mayor que, menor que, igual a, etc.) y criterios de actualización/frecuencia. Estas características ayudan a crear la audiencia [!UICONTROL segments] centrada que sea relevante para las necesidades de su empresa.

## Ventajas

[!UICONTROL Segments] mejora los procesos de segmentación/creación de audiencias estándar basados en píxeles porque le permiten:

* Genere [!UICONTROL segments] relevantes y útiles con características de origen y de terceros.
* Cree reglas de segmentación complejas y sofisticadas con operadores booleanos, expresiones de comparación y criterios de actualización/frecuencia.
* Enviar datos de [!UICONTROL segment] a un socio de destino.
* Monitorice el rendimiento con informes de Audience Manager.

>[!MORELIKETHIS]
>
>* [Señales, rasgos y segmentos](../../reference/signal-trait-segment.md)
