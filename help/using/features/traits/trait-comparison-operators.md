---
description: Este artículo describe los operadores de comparación utilizados por el generador de rasgos.
seo-description: This article describes the comparison operators used by Trait Builder.
seo-title: Working with Comparison Operators in Trait Builder
solution: Audience Manager
title: Uso de operadores de comparación en el generador de rasgos
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 10%

---

# Uso de operadores de comparación en el generador de rasgos {#working-with-comparison-operators-in-trait-builder}

Este artículo describe los operadores de comparación utilizados por [!UICONTROL Trait Builder].

## Objetivo de los operadores de comparación

<!-- c_tb_comparison_operators.xml -->

Los operadores de comparación (u operadores relacionales) se utilizan para comparar, probar o evaluar la relación entre diferentes valores. Entrada [!UICONTROL Trait Builder]Sin embargo, al crear reglas de señal, los operadores de comparación permiten probar la relación entre diferentes pares clave-valor. Por ejemplo, puede crear una regla de señal para definir una audiencia para compradores de cámaras caros. En este caso, puede crear un par clave-valor cámara/precio y calificar a un usuario si ha buscado una cámara con un precio igual o bueno a una cantidad fija.

## Ventajas de los operadores de comparación

Los operadores de comparación son útiles cuando necesita evaluar y crear rasgos basados en varios valores. El examen de los precios de los bienes y servicios puede ilustrar esta condición. Por ejemplo: es posible que su empresa desee identificar a los visitantes en función de los precios de los productos que ven. Sin embargo, puede resultar ineficiente desde el punto de vista administrativo definir segmentos individuales basados en valores específicos. Los operadores de comparación ayudan a superar este obstáculo estableciendo déclencheur de segmentación basados en umbrales o intervalos de precios.

## Operadores de comparación

Puede crear reglas con los siguientes operadores de comparación:

| Operador | Definición |
|---|---|
| **==** | Igual a |
| **!=** | No igual a |
| **>** | Mayor que |
| **&lt;** | Menor que |
| **=>** | Bueno que/igual a |
| **&lt;=** | Menor/igual que |

## Operadores con nombre

Puede crear reglas con los siguientes operadores asignados:

| Operador | Se evalúa como [!DNL True] Cuándo |
|---|---|
| **[!UICONTROL Contains]** | El valor en un par clave-valor *contains* caracteres especificados por este operador. |
| **[!UICONTROL Matcheswords]** | El valor en un par clave-valor *matches* el patrón especificado por este operador. |
| **[!UICONTROL Startswith]** | El valor en un par clave-valor *empieza por* caracteres especificados por este operador. |
| **[!UICONTROL Endswith]** | El valor en un par clave-valor *termina por* los caracteres especificados por este operador. |
| **[!UICONTROL Matchesregex]** | El valor en un par clave-valor *matches* el patrón especificado por una expresión regular. [Más información](../../features/traits/trait-builder-regex.md) acerca del uso de expresiones regulares en [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Expresiones booleanas en el Generador de rasgos y segmentos](../../reference/boolean-expressions-tsb.md)
>* [Explicación de las expresiones booleanas en TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Orden de las operaciones en expresiones de TraitBuilder](../../features/traits/trait-operator-precedence.md)
>* [Expresiones de muestra con operadores booleanos y de comparación](../../features/traits/trait-expression-samples.md)

