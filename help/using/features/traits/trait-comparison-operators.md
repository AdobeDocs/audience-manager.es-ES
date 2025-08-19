---
description: Este artículo describe los operadores de comparación utilizados por el generador de rasgos.
seo-description: This article describes the comparison operators used by Trait Builder.
seo-title: Working with Comparison Operators in Trait Builder
solution: Audience Manager
title: Trabajar con operadores de comparación en el generador de rasgos
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 6%

---

# Trabajar con operadores de comparación en el generador de rasgos {#working-with-comparison-operators-in-trait-builder}

Este artículo describe los operadores de comparación utilizados por [!UICONTROL Trait Builder].

## Finalidad de los operadores de comparación

<!-- c_tb_comparison_operators.xml -->

Los operadores de comparación (u operadores relacionales) se utilizan para comparar, prueba o evaluar la relación entre diferentes valores. En [!UICONTROL Trait Builder], al crear reglas de señal, los operadores de comparación permiten prueba la relación entre diferentes pares clave-valor. Por ejemplo, puede crear un regla de señal para definir un audiencia para los compradores caros de cámaras. En este caso, puede crear un par clave-valor cámara / precio y calificar a un usuario si han buscado una cámara con un precio igual o superior a una cantidad establecida.

## Ventajas de los Operadores de Comparación

Los operadores de comparación son útiles cuando necesita evaluar y crear características basadas en varios valores. Mirar los precios de los bienes y servicios puede ilustrar esta condición. Por ejemplo, es posible que su empresa quiera identificar a los visitantes en función de los precios de los productos que vista. Sin embargo, desde el punto de vista administrativo puede ser ineficaz definir segmentos individuales basados en valores específicos. Los operadores de comparación ayudan a superar este obstáculo estableciendo segmentación desencadenantes basados en umbrales o rangos de precios.

## Operadores de comparación

Puede versión reglas con los siguientes operadores de comparación:

| Operador | Definición |
|---|---|
| **==** | Igual a |
| **!=** | No es igual a |
| **>** | Mayor que |
| **&#x200B;**&#x200B;| Menor que |
| **=>** | Mayor que/igual que |
| **&lt;=** | Menor que/igual que |

## Operadores con nombre

Puede versión reglas con los siguientes operadores con nombre:

| Operador | Se evalúa hasta [!DNL True] cuándo |
|---|---|
| **[!UICONTROL Contains]** | El valor de un par *clave-valor contiene* caracteres especificados por este operador. |
| **[!UICONTROL Matcheswords]** | El valor de un par *clave-valor coincide con* el patrón especificado por este operador. |
| **[!UICONTROL Startswith]** | El valor en un par *clave-valor comienza con* caracteres especificados por este operador. |
| **[!UICONTROL Endswith]** | El valor de un par *clave-valor termina con* los caracteres especificados por este operador. |
| **[!UICONTROL Matchesregex]** | El valor de un par *clave-valor coincide con* el patrón especificado por un expresión regular. [&#128279;](../../features/traits/trait-builder-regex.md) Más información sobre el uso de expresiones regulares en [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Expresiones booleanas en el Generador de rasgos y segmentos](../../reference/boolean-expressions-tsb.md)
>* [Descripción de las expresiones booleanas en TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Orden de operaciones en expresiones TraitBuilder](../../features/traits/trait-operator-precedence.md)
>* [Expresiones de muestra con operadores booleanos y de comparación](../../features/traits/trait-expression-samples.md)
