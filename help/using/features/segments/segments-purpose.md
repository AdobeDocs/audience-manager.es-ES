---
description: Describe los segmentos, sus partes constituyentes y la creación de reglas con el Generador de segmentos.
seo-description: Describe los segmentos, sus partes constituyentes y la creación de reglas con el Generador de segmentos.
seo-title: Objetivo, composición y reglas de los segmentos
solution: Audience Manager
title: Objetivo, composición y reglas de los segmentos
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
translation-type: tm+mt
source-git-commit: c229bf71da5b07277811219cbf2794c3ca7bc89d

---


# Segmentos: Propósito, composición y reglas {#segments-purpose-composition-and-rules}

Describe los segmentos, sus partes constituyentes y la creación de reglas con [!UICONTROL Segment Builder].

## Propósito de los segmentos

Un *`segment`* (o un *`audience`*) es un conjunto de usuarios que comparten atributos comunes. En Audience Manager, se crean segmentos con reglas del lado del servidor. Estas reglas le permiten crear grupos de audiencia en función de atributos del visitante del sitio como:

* Comportamiento;
* Datos demográficos (edad, género, ingresos, etc.);
* Otras características que puede definir en la interfaz de usuario.

## Composición de segmentos

Un segmento de Audience Manager es una regla del lado del servidor que consta de características individuales o grupos de características. Las características están compuestas de elementos de datos denominados pares clave-valor. Junto con las reglas establecidas en el nivel de segmento, estos pares de clave-valor contienen los criterios que califican a los visitantes para pertenecer a características y segmentos.

## Consideraciones sobre la asignación de segmentos de Adobe Analytics

Al asignar segmentos o grupos de informes de Adobe Analytics a su organización de Experience Cloud, Audience Manager crea automáticamente segmentos y características nuevos, correspondientes y de solo lectura. No puede editar ni cambiar la ubicación de almacenamiento de estos segmentos desde Audience Manager. Sin embargo, cualquier cambio que realice en los segmentos o grupos de informes de Adobe Analytics asignados se reflejará en Audience Manager.

>[!TIP]
>
>Los segmentos de Audience Manager son diferentes de [!DNL Adobe Analytics] los segmentos. Lea [Explicación de los segmentos en Analytics y Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) para obtener una descripción detallada de las diferencias.

## Crear segmentos basados en reglas con el Generador de segmentos

A diferencia de los píxeles tradicionales que se activan en respuesta a condiciones simples de sí/no, el Generador de segmentos le permite crear requisitos de segmentos complejos. Al igual que las características, los segmentos evalúan los datos mediante [!DNL Boolean] expresiones ([!DNL AND], [!DNL OR], [!DNL NOT]), operadores de comparación (mayores, menores que, iguales a, etc.) y criterios de actualización/frecuencia. Estas funciones ayudan a crear segmentos de audiencia específicos relevantes para sus necesidades comerciales.

## Ventajas

Los segmentos mejoran con los procesos estándar de creación y segmentación de audiencias basados en píxeles porque permiten:

* Cree segmentos útiles y relevantes con características de origen y de terceros.
* Cree reglas de segmentación complejas y sofisticadas con operadores booleanos, expresiones de comparación y criterios de actualización y frecuencia.
* Enviar datos de segmentos a un socio de destino.
* Monitoree el rendimiento con los informes de Audience Manager.

>[!MORE_LIKE_THIS]
>
>* [Señales, características y segmentos](../../reference/signal-trait-segment.md)

