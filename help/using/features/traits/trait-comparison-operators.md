---
description: En este artículo se describen los operadores de comparación utilizados por el Generador de rasgos.
seo-description: En este artículo se describen los operadores de comparación utilizados por el Generador de rasgos.
seo-title: Uso de operadores de comparación en el generador de rasgos
solution: Audience Manager
title: Uso de operadores de comparación en el generador de rasgos
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: 'Rasgos '
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 12%

---

# Uso de operadores de comparación en el generador de rasgos {#working-with-comparison-operators-in-trait-builder}

Este artículo describe los operadores de comparación utilizados por [!UICONTROL Trait Builder].

## Objetivo de los operadores de comparación

<!-- c_tb_comparison_operators.xml -->

Los operadores de comparación (u operadores relacionales) se utilizan para comparar, probar o evaluar la relación entre diferentes valores. En [!UICONTROL Trait Builder], al crear reglas de señal, los operadores de comparación permiten probar la relación entre diferentes pares clave-valor. Por ejemplo, puede crear una regla de señal para definir una audiencia para compradores de cámaras caras. En este caso, puede crear un par clave-valor de precio/cámara y calificar a un usuario si ha buscado una cámara con un precio igual o bueno a una cantidad establecida.

## Ventajas de los operadores de comparación

Los operadores de comparación son útiles cuando necesita evaluar y crear características basadas en varios valores. El análisis de los precios de los bienes y servicios puede ilustrar esta situación. Por ejemplo: es posible que su empresa desee identificar a los visitantes en función de los precios de los productos que ven. Sin embargo, puede ser administrativamente ineficiente definir segmentos individuales basados en valores específicos. Los operadores de comparación ayudan a superar este obstáculo estableciendo déclencheur de segmentación basados en umbrales de precios o intervalos.

## Operadores de comparación

Puede generar reglas con los siguientes operadores de comparación:

| Operador | Definición |
|---|---|
| **==** | Igual a |
| **!=** | Distinto a |
| **>** | Mayor que |
| **&lt;>** | Menor que |
| **=>** | Bueno que/igual a |
| **&lt;>** | Menor o igual que |

## Operadores con nombre

Puede generar reglas con los siguientes operadores asignados:

| Operador | Evalúa a [!DNL True] Cuando |
|---|---|
| **[!UICONTROL Contains]** | El valor de un par clave-valor *contiene* caracteres especificados por este operador. |
| **[!UICONTROL Matcheswords]** | El valor de un par clave-valor *coincide con* el patrón especificado por este operador. |
| **[!UICONTROL Startswith]** | El valor de un par clave-valor *comienza con los caracteres* especificados por este operador. |
| **[!UICONTROL Endswith]** | El valor de un par clave-valor *termina con* los caracteres especificados por este operador. |
| **[!UICONTROL Matchesregex]** | El valor de un par clave-valor *coincide con* el patrón especificado por una expresión regular. [Obtenga ](../../features/traits/trait-builder-regex.md) más información sobre el uso de expresiones regulares en  [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Expresiones booleanas en el Generador de rasgos y segmentos](../../reference/boolean-expressions-tsb.md)
* [Expresiones booleanas en TraitBuilder](../../reference/boolean-expressions-tsb.md)
* [Orden de operaciones en expresiones de TraitBuilder](../../features/traits/trait-operator-precedence.md)
* [Expresiones de muestra con operadores booleanos y de comparación](../../features/traits/trait-expression-samples.md)

