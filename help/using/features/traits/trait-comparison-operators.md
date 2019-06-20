---
description: Este artículo describe los operadores de comparación que utiliza el Generador de rasgos.
seo-description: Este artículo describe los operadores de comparación que utiliza el Generador de rasgos.
seo-title: Uso de operadores de comparación en el Generador de rasgos
solution: Audience Manager
title: Uso de operadores de comparación en el Generador de rasgos
uuid: 41 bec 3 b 3-e 5 df -4 a 6 f-abb 0-80 ce 4 c 75 f 5 e 7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Working with Comparison Operators in Trait Builder {#working-with-comparison-operators-in-trait-builder}

This article describes the comparison operators used by [!UICONTROL Trait Builder].

## Finalidad de los operadores de comparación

<!-- c_tb_comparison_operators.xml -->

Los operadores de comparación (o operadores relacionales) se utilizan para comparar, probar o evaluar la relación entre los distintos valores. In [!UICONTROL Trait Builder], when building signal rules, comparison operators let you test the relationship between different key-value pairs. Por ejemplo, puede crear una regla de señal para definir una audiencia para compradores costosos de cámara. En este caso, puede crear un par de valor clave de cámara/precio y calificar a un usuario si ha buscado una cámara con un precio igual o mayor que una cantidad establecida.

## Ventajas de los operadores de comparación

Los operadores de comparación son útiles cuando se necesita evaluar y crear características basadas en valores múltiples. Si observa los precios de bienes y servicios puede ilustrar esta condición. Por ejemplo: es posible que su negocio desee identificar a los visitantes según los precios de los productos que ven. Sin embargo, puede ser administrativamente ineficaz definir segmentos individuales basados en valores específicos. Los operadores de comparación ayudan a superar este obstáculo estableciendo activadores de segmentación basados en umbrales o intervalos de precios.

## Operadores de comparación

Puede generar reglas con los siguientes operadores de comparación:

| Operador | Definición |
|---|---|
| **==** | Igual a |
| **!=** | No es igual a |
| **&gt;** | Mayor que |
| **&lt;** | Menor que |
| **=&gt;** | Mayor que/igual a |
| **&lt;=** | Menor que/igual a |

## Operadores con nombre

Puede generar reglas con los operadores designados siguientes:

| Operador | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Matcheswords]** | The value in a key-value pair *matches* the pattern specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |
| **[!UICONTROL Matchesregex]** | The value in a key-value pair *matches* the pattern specified by a regular expression. [Más información](../../features/traits/trait-builder-regex.md) sobre el uso de expresiones regulares en [!UICONTROL Trait Builder]. |

>[!MORE_ LIKE_ THIS]
>
>* [Expresiones booleanas en el Generador de segmentos y características](../../reference/boolean-expressions-tsb.md)
>* [Explicación de las expresiones booleanas en traitbuilder](../../reference/boolean-expressions-tsb.md)
>* [Orden de las operaciones en expresiones traitbuilder](../../features/traits/trait-operator-precedence.md)
>* [Expresiones de muestra con operadores booleanos y de comparación](../../features/traits/trait-expression-samples.md)

