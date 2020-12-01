---
description: Describe los segmentos, sus partes constituyentes y la creación de reglas con el Generador de segmentos.
seo-description: Describe los segmentos, sus partes constituyentes y la creación de reglas con el Generador de segmentos.
seo-title: Objetivo, composición y reglas de los segmentos
solution: Audience Manager
title: Objetivo, composición y reglas de los segmentos
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 6%

---


# Segmentos: propósito, composición y reglas {#segments-purpose-composition-and-rules}

Describe [!UICONTROL segments], sus partes constituyentes y la creación de reglas con [!UICONTROL Segment Builder].

## Objetivo de [!UICONTROL Segments]

Un *`segment`* (o un *`audience`*) es un conjunto de usuarios que comparten atributos comunes. En Audience Manager, se crea [!UICONTROL segments] con reglas del lado del servidor. Estas reglas le permiten generar grupos de audiencias basados en atributos de visitante del sitio como:

* Comportamiento;
* Datos demográficos (edad, género, ingresos, etc.);
* Otras características que puede definir en la interfaz de usuario.

## [!UICONTROL Segment] Composición

Un Audience Manager [!UICONTROL segment] es una regla del lado del servidor que consta de características individuales o grupos de características. Las características están compuestas de elementos de datos denominados pares clave-valor. Junto con las reglas establecidas en el nivel [!UICONTROL segment], estos pares de clave-valor contienen los criterios que califican a los visitantes para la pertenencia a características y [!UICONTROL segment].

## Consideraciones sobre la [!UICONTROL Adobe Analytics] [!UICONTROL Segment] asignación

Al asignar Adobe Analytics [!UICONTROL segments] o grupos de informes a su organización Experience Cloud, Audience Manager crea automáticamente características [!UICONTROL segments] nuevas, correspondientes y de sólo lectura. No puede editar ni cambiar la ubicación de almacenamiento de estos [!UICONTROL segments] desde el Audience Manager. Sin embargo, cualquier cambio que realice en el Adobe Analytics [!UICONTROL segments] o en los grupos de informes asignados se refleja en Audience Manager.

>[!TIP]
>
>El Audience Manager [!UICONTROL segments] es diferente de [!DNL Adobe Analytics] [!UICONTROL segments]. Lea [Explicación de los segmentos en Analytics y Audience Manager](https://docs.adobe.com/content/help/es-ES/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) para obtener una descripción detallada de las diferencias.

## Crear reglas basadas en [!UICONTROL Segments] con [!UICONTROL Segment Builder]

A diferencia de los píxeles tradicionales que se activan en respuesta a condiciones simples de sí/no, [!UICONTROL Segment Builder] permite crear [!UICONTROL segment] requisitos complejos. Al igual que [!UICONTROL traits], [!UICONTROL segments] evalúe los datos usando [!DNL Boolean] expresiones ([!DNL AND], [!DNL OR], [!DNL NOT]), operadores de comparación (buenos que, menores que, iguales a, etc.) y criterios de actualización/frecuencia. Estas funciones ayudan a crear una audiencia centrada [!UICONTROL segments] relevante para sus necesidades comerciales.

## Ventajas

[!UICONTROL Segments] mejore los procesos de creación y segmentación de audiencias basados en píxeles estándar, ya que permiten:

* Cree [!UICONTROL segments] útiles y relevantes con características de origen y de terceros.
* Cree reglas de segmentación complejas y sofisticadas con operadores booleanos, expresiones de comparación y criterios de actualización y frecuencia.
* Enviar [!UICONTROL segment] datos a un socio de destino.
* Monitoree el rendimiento con los informes de Audience Manager.

>[!MORELIKETHIS]
>
>* [Señales, rasgos y segmentos](../../reference/signal-trait-segment.md)

