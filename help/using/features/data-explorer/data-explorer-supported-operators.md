---
description: Utilice operadores lógicos para agrupar pares de clave-valor y características de relleno.
seo-description: Utilice operadores lógicos para agrupar pares de clave-valor y características de relleno.
seo-title: Operadores lógicos admitidos
title: Operadores lógicos admitidos
uuid: 645 fcb 6 f -50 ac -49 bc -8 df 9-c 699 c 749 cf 8 f
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Supported Logical Operators {#supported-logical-operators}

Utilice operadores lógicos para agrupar pares de clave-valor y características de relleno.

## Supported Operators for Signal Search {#supported-operators-search}

Utilice los siguientes operadores lógicos admitidos para buscar pares clave-valor:

### Operadores de comparación

| Operador | Definición |
|---|---|
| **==** | Igual a |
| **&gt;** | Mayor que |
| **&lt;** | Menor que |
| **=&gt;** | Mayor que/igual a |
| **&lt;=** | Menor que/igual a |

### Operadores con nombre

| Operador | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |

## Supported Operators for Trait Backfilling and Estimation {#supported-operators-backfilling}

You can backfill traits that include expressions containing any of the operators supported by [!UICONTROL Signal Search]. In addition to these operators, trait backfilling and estimation also support the [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL AND NOT] logical operators, used to combine key-value pairs within the backfilled trait expressions.