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
source-wordcount: '310'
ht-degree: 3%

---

# Segmentos: propósito, composición y reglas {#segments-purpose-composition-and-rules}

Describe [!UICONTROL segments], sus partes constitutivas y la creación de reglas con [!UICONTROL Segment Builder].

## Finalidad de [!UICONTROL Segments]

A *`segment`* (o un *`audience`*) es un conjunto de usuarios que comparten atributos comunes. En Audience Manager, puede crear lo siguiente [!UICONTROL segments] con reglas de servidor. Estas reglas permiten crear grupos de audiencia basados en atributos del visitante del sitio como:

* Comportamiento;
* Demografía (edad, sexo, ingresos, etc.);
* Otras características que puede definir en la interfaz de usuario de.

## [!UICONTROL Segment] Composición

Un Audience Manager [!UICONTROL segment] es una regla del lado del servidor que consta de características individuales o grupos de características. Los rasgos están compuestos por elementos de datos llamados pares clave-valor. Junto con las reglas que establezca en [!UICONTROL segment] nivel de, estos pares clave-valor contienen los criterios que clasifican a los visitantes para rasgo y [!UICONTROL segment] abono.

## Consideraciones sobre [!UICONTROL Adobe Analytics] [!UICONTROL Segment] Asignación

Al asignar Adobe Analytics [!UICONTROL segments] Para los grupos de informes de su organización Experience Cloud, Audience Manager crea automáticamente grupos de informes nuevos, correspondientes y de solo lectura [!UICONTROL segments] y rasgos. No puede editar ni cambiar la ubicación de almacenamiento de estos elementos [!UICONTROL segments] del Audience Manager. Sin embargo, cualquier cambio que realice en la Adobe Analytics asignada [!UICONTROL segments] o grupos de informes reflejados en el Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] son diferentes de [!DNL Adobe Analytics] [!UICONTROL segments]. Leer [Explicación de los segmentos en Analytics y Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) para obtener una descripción detallada de las diferencias.

## Crear basado en reglas [!UICONTROL Segments] Con [!UICONTROL Segment Builder]

A diferencia de los píxeles tradicionales que se activan en respuesta a condiciones simples de sí/no, [!UICONTROL Segment Builder] permite crear elementos complejos [!UICONTROL segment] requisitos. Like [!UICONTROL traits], [!UICONTROL segments] evaluación de datos mediante [!DNL Boolean] expresiones ([!DNL AND], [!DNL OR], [!DNL NOT]), operadores de comparación (bueno que, menor que, igual a, etc.) y criterios de actualización/frecuencia. Estas funciones ayudan a crear audiencias centradas [!UICONTROL segments] relevante para sus necesidades comerciales.

## Ventajas

[!UICONTROL Segments] mejore los procesos estándar de creación/segmentación de audiencias basados en píxeles porque le permiten:

* Cree contenido relevante y útil [!UICONTROL segments] con características de origen y de terceros.
* Cree reglas de segmentación complejas y sofisticadas con operadores booleanos, expresiones de comparación y criterios de actualización/frecuencia.
* Enviar [!UICONTROL segment] datos a un socio de destino.
* Monitorice el rendimiento con informes de Audience Manager.

>[!MORELIKETHIS]
>
>* [Señales, rasgos y segmentos](../../reference/signal-trait-segment.md)

