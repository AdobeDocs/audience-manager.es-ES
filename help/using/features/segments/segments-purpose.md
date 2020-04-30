---
description: Describe los segmentos, sus partes constituyentes y la creación de reglas con el Generador de segmentos.
seo-description: Describe los segmentos, sus partes constituyentes y la creación de reglas con el Generador de segmentos.
seo-title: Objetivo, composición y reglas de los segmentos
solution: Audience Manager
title: Objetivo, composición y reglas de los segmentos
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Segmentos: Propósito, composición y reglas {#segments-purpose-composition-and-rules}

Describe los segmentos, sus partes constituyentes y la creación de reglas con [!UICONTROL Segment Builder].

## Propósito de los segmentos

Un *`segment`* (o un *`audience`*) es un conjunto de usuarios que comparten atributos comunes. En el Administrador de Audiencias, puede crear segmentos con reglas del lado del servidor. Estas reglas le permiten generar grupos de audiencias basados en atributos de visitante del sitio como:

* Comportamiento;
* Datos demográficos (edad, género, ingresos, etc.);
* Otras características que puede definir en la interfaz de usuario.

## Composición de segmentos

Un segmento del Administrador de Audiencias es una regla del lado del servidor que consta de características individuales o grupos de características. Las características están compuestas de elementos de datos denominados pares clave-valor. Junto con las reglas establecidas en el nivel de segmento, estos pares de clave-valor contienen los criterios que califican a los visitantes para pertenecer a características y segmentos.

## Consideraciones sobre la asignación de segmentos de Adobe Analytics

Al asignar segmentos o grupos de informes de Adobe Analytics a su organización de Experience Cloud, el Administrador de Audiencias crea automáticamente segmentos y características nuevos, correspondientes y de solo lectura. No puede editar ni cambiar la ubicación de almacenamiento de estos segmentos desde el Administrador de Audiencias. Sin embargo, cualquier cambio que realice en los segmentos o grupos de informes de Adobe Analytics asignados se reflejará en el Administrador de Audiencias.

>[!TIP]
>
>Los segmentos del Administrador de Audiencias son diferentes de los [!DNL Adobe Analytics] segmentos. Lea [Explicación de los segmentos en Analytics y Administrador](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) de Audiencias para obtener una descripción detallada de las diferencias.

## Crear segmentos basados en reglas con el Generador de segmentos

A diferencia de los píxeles tradicionales que se activan en respuesta a condiciones simples de sí/no, el Generador de segmentos le permite crear requisitos de segmentos complejos. Al igual que las características, los segmentos evalúan los datos mediante [!DNL Boolean] expresiones ([!DNL AND], [!DNL OR], [!DNL NOT]), operadores de comparación (buenos que, menores que, iguales a, etc.) y criterios de frecuencia/actualización. Estas funciones ayudan a crear segmentos de audiencia específicos relevantes para sus necesidades comerciales.

## Ventajas

Los segmentos mejoran con los procesos estándar de creación/segmentación de audiencias basados en píxeles porque permiten:

* Cree segmentos útiles y relevantes con características de origen y de terceros.
* Cree reglas de segmentación complejas y sofisticadas con operadores booleanos, expresiones de comparación y criterios de actualización y frecuencia.
* Enviar datos de segmentos a un socio de destino.
* Monitoree el rendimiento con los informes del Administrador de Audiencias.

>[!MORELIKETHIS]
>
>* [Señales, características y segmentos](../../reference/signal-trait-segment.md)

