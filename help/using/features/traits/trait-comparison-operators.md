---
description: En este artículo se describen los operadores de comparación utilizados por el Generador de características.
seo-description: En este artículo se describen los operadores de comparación utilizados por el Generador de características.
seo-title: Uso de operadores de comparación en el generador de rasgos
solution: Audience Manager
title: Uso de operadores de comparación en el generador de rasgos
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 11%

---


# Uso de operadores de comparación en el generador de rasgos {#working-with-comparison-operators-in-trait-builder}

Este artículo describe los operadores de comparación utilizados por [!UICONTROL Trait Builder].

## Propósito de los operadores de comparación

<!-- c_tb_comparison_operators.xml -->

Los operadores de comparación (o los operadores relacionales) se utilizan para comparar, probar o evaluar la relación entre diferentes valores. En [!UICONTROL Trait Builder], al generar reglas de señal, los operadores de comparación permiten probar la relación entre diferentes pares clave-valor. Por ejemplo, puede crear una regla de señal para definir una audiencia para compradores de cámaras costosas. En este caso, puede crear un par de clave-valor de precio/cámara y calificar a un usuario si ha buscado una cámara con un precio igual o bueno a una cantidad establecida.

## Ventajas de los operadores de comparación

Los operadores de comparación son útiles cuando necesita evaluar y crear características basadas en varios valores. El observar los precios de los bienes y servicios puede ilustrar esta situación. Por ejemplo: es posible que su empresa desee identificar visitantes en función de los precios de los productos que vista. Sin embargo, puede ser administrativamente ineficiente definir segmentos individuales basados en valores específicos. Los operadores de comparación ayudan a superar este obstáculo estableciendo activadores de segmentación basados en umbrales de precios o intervalos.

## Operadores de comparación

Puede generar reglas con los siguientes operadores de comparación:

| Operador | Definición |
|---|---|
| **==** | Igual a |
| **!=** | No es igual a |
| **>** | Mayor que |
| **&lt;>** | Menor que |
| **=>** | Bueno mayor o igual que |
| **&lt;>** | Menor o igual que |

## Operadores con nombre

Puede generar reglas con los siguientes operadores con nombre:

| Operador | Evalúa a [!DNL True] cuando |
|---|---|
| **[!UICONTROL Contains]** | El valor de un par clave-valor *contiene* caracteres especificados por este operador. |
| **[!UICONTROL Matcheswords]** | El valor de un par clave-valor *coincide con* el patrón especificado por este operador. |
| **[!UICONTROL Startswith]** | El valor de un par de valor clave *inicios con* caracteres especificados por este operador. |
| **[!UICONTROL Endswith]** | El valor de un par clave-valor *termina con* los caracteres especificados por este operador. |
| **[!UICONTROL Matchesregex]** | El valor de un par clave-valor *coincide con* el patrón especificado por una expresión regular. [Obtenga ](../../features/traits/trait-builder-regex.md) más información sobre el uso de expresiones regulares en  [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Expresiones booleanas en el Generador de rasgos y segmentos](../../reference/boolean-expressions-tsb.md)
>* [Explicación de las Expresiones booleanas en TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Orden de operaciones en Expresiones de TraitBuilder](../../features/traits/trait-operator-precedence.md)
>* [Expresiones de muestra con operadores booleanos y de comparación](../../features/traits/trait-expression-samples.md)

