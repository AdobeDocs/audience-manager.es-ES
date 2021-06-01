---
description: Describe los segmentos, sus partes constitutivas y la creación de reglas con el Generador de segmentos.
seo-description: Describe los segmentos, sus partes constitutivas y la creación de reglas con el Generador de segmentos.
seo-title: Objetivo, composición y reglas de los segmentos
solution: Audience Manager
title: Objetivo, composición y reglas de los segmentos
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: 'Segmentos '
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 6%

---

# Segmentos: propósito, composición y reglas {#segments-purpose-composition-and-rules}

Describe [!UICONTROL segments], sus partes constituyentes y la creación de reglas con [!UICONTROL Segment Builder].

## Objetivo de [!UICONTROL Segments]

Un *`segment`* (o un *`audience`*) es un conjunto de usuarios que comparten atributos comunes. En Audience Manager, se crea [!UICONTROL segments] con reglas del lado del servidor. Estas reglas permiten crear grupos de audiencia basados en atributos de visitantes del sitio como:

* Comportamiento;
* Información demográfica (edad, sexo, ingresos, etc.);
* Otras características que puede definir en la interfaz de usuario.

## [!UICONTROL Segment] Composición

Un Audience Manager [!UICONTROL segment] es una regla del lado del servidor que consta de características individuales o grupos de características. Los rasgos están compuestos por elementos de datos llamados pares clave-valor. Junto con las reglas establecidas en el nivel [!UICONTROL segment], estos pares clave-valor contienen los criterios que califican a los visitantes para la pertenencia a rasgos y [!UICONTROL segment].

## Consideraciones sobre la asignación [!UICONTROL Adobe Analytics] [!UICONTROL Segment]

Al asignar Adobe Analytics [!UICONTROL segments] o grupos de informes a su organización Experience Cloud, el Audience Manager crea automáticamente características y características nuevas, correspondientes y de solo lectura [!UICONTROL segments]. No puede editar ni cambiar la ubicación de almacenamiento de estos [!UICONTROL segments] desde el Audience Manager. Sin embargo, cualquier cambio que realice en los grupos de informes o Adobe Analytics [!UICONTROL segments] asignados se reflejará en el Audience Manager.

>[!TIP]
>
>El Audience Manager [!UICONTROL segments] es diferente de [!DNL Adobe Analytics] [!UICONTROL segments]. Lea [Explicación de los segmentos en Analytics y Audience Manager](https://docs.adobe.com/content/help/es-ES/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) para obtener una descripción detallada de las diferencias.

## Crear [!UICONTROL Segments] basado en reglas con [!UICONTROL Segment Builder]

A diferencia de los píxeles tradicionales que se activan en respuesta a condiciones de sí/no simples, [!UICONTROL Segment Builder] permite crear requisitos [!UICONTROL segment] complejos. Al igual que [!UICONTROL traits], [!UICONTROL segments] evalúa los datos utilizando expresiones [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]), operadores de comparación (buenos que, menores que, iguales a, etc.) y criterios de actualización y frecuencia. Estas funciones ayudan a crear audiencias específicas [!UICONTROL segments] relevantes para sus necesidades comerciales.

## Ventajas

[!UICONTROL Segments] mejore los procesos estándar de creación/segmentación de audiencias basados en píxeles porque le permiten:

* Genere [!UICONTROL segments] relevantes y útiles con características de origen y de terceros.
* Cree reglas de segmentación complejas y sofisticadas con operadores booleanos, expresiones de comparación y criterios de actualización y frecuencia.
* Envíe datos [!UICONTROL segment] a un socio de destino.
* Monitorice el rendimiento con informes de Audience Manager.

>[!MORELIKETHIS]
>
>* [Señales, rasgos y segmentos](../../reference/signal-trait-segment.md)

