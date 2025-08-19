---
description: Describe segmentos, sus partes constituyentes y regla creación con el Generador de segmentos.
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: Propósito, composición y reglas de los segmentos
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# Segmentos: propósito, composición y reglas {#segments-purpose-composition-and-rules}

Describe [!UICONTROL segments], sus partes constituyentes, y regla creación con [!UICONTROL Segment Builder].

## Propósito de [!UICONTROL Segments]

A *`segment`* (o un *`audience`*) es un conjunto de usuarios que comparten atributos comunes. En Audience Manager, se crea [!UICONTROL segments] con del lado del servidor reglas. Estas reglas le permiten versión audiencia grupos en función de atributos visitante del sitio como:

* Comportamiento;
* Datos demográficos (edad, sexo, ingresos, etc.);
* Otras características que puede definir en la interfaz de usuario.

## [!UICONTROL Segment] Composición

Un Audience Manager [!UICONTROL segment] es un regla de del lado del servidor que consiste en rasgos individuales o grupos de características. Las características se componen de elementos de datos denominados pares clave-valor. Junto con las reglas que establezca en el nivel, estos pares clave-valor contienen los criterios que califican a los visitantes para rasgos [!UICONTROL segment] y [!UICONTROL segment] abono.

## Consideraciones sobre la [!UICONTROL Adobe Analytics] [!UICONTROL Segment] asignación

Al asignar grupos de Adobe Analytics [!UICONTROL segments] o de informes a su organización Experience Cloud, crea automáticamente Audience Manager nuevos rasgos nuevos, correspondientes, de solo [!UICONTROL segments] lectura y características. No puede editar ni cambiar la ubicación almacenamiento de estos [!UICONTROL segments] desde Audience Manager. Sin embargo, cualquier cambio que realice en el Adobe Analytics [!UICONTROL segments] asignado o en los grupos de informes se refleja en Audience Manager.

>[!TIP]
>
>[!UICONTROL segments] Audience Manager son diferentes de [!DNL Adobe Analytics] [!UICONTROL segments]. Lea [Comprender los segmentos en Analytics y Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) para obtener una descripción detallada de las diferencias.

## Crear basado en [!UICONTROL Segments] reglas con [!UICONTROL Segment Builder]

A diferencia de los píxeles tradicionales que se activan en respuesta a condiciones simples de sí / no, [!UICONTROL Segment Builder] le permiten crear requisitos complejos [!UICONTROL segment] . Al igual [!UICONTROL traits]que , [!UICONTROL segments] evalúe los datos utilizando [!DNL Boolean] expresiones ([!DNL AND], [!DNL OR], ), [!DNL NOT]operadores de comparación (mayor que, menor que, igual que, etc.) y criterios de actualización / Frecuencia. Estas características ayudan a crear audiencia [!UICONTROL segments] enfocados relevantes para las necesidades de su negocio.

## Ventajas

[!UICONTROL Segments] Mejora los procesos estándar de creación/segmentación de audiencia basadas en píxeles, ya que te permiten:

* Cree características relevantes y útiles [!UICONTROL segments] con características propias y terceros.
* Crear reglas de segmentación sofisticadas y complejas con operadores booleanos, expresiones de comparación y criterios de actualización/Frecuencia.
* Enviar [!UICONTROL segment] datos a un socio de destino.
* Monitoree el rendimiento con informes Audience Manager.

>[!MORELIKETHIS]
>
>* [Señales, rasgos y segmentos](../../reference/signal-trait-segment.md)
