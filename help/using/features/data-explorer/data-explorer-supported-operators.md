---
description: Utilice operadores lógicos para agrupar pares de clave-valor y características de relleno.
seo-description: Use logical operators to group key-value pairs and backfill traits.
seo-title: Supported Logical Operators
title: Operadores lógicos admitidos
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 4%

---

# Operadores lógicos admitidos {#supported-logical-operators}

Utilice operadores lógicos para agrupar pares de clave-valor y características de relleno.

## Operadores admitidos para la búsqueda de señales {#supported-operators-search}

Utilice los siguientes operadores lógicos admitidos para buscar pares clave-valor:

### Operadores de comparación

| Operador | Definición |
|---|---|
| **==** | Igual a |
| **>** | Mayor que |
| **&lt;** | Menor que |
| **=>** | Mayor/igual que |
| **&lt;=** | Menor/igual que |

### Operadores con nombre

| Operador | Se evalúa como [!DNL True] cuando |
|---|---|
| **[!UICONTROL Contains]** | El valor de un par clave-valor *contiene* caracteres especificados por este operador. |
| **[!UICONTROL Startswith]** | El valor de un par clave-valor *comienza con* caracteres especificados por este operador. |
| **[!UICONTROL Endswith]** | El valor de un par clave-valor *termina con* los caracteres especificados por este operador. |

## Operadores admitidos para el relleno y la estimación de características {#supported-operators-backfilling}

Puede rellenar características que incluyan expresiones que contengan cualquiera de los operadores admitidos por [!UICONTROL Signal Search]. Además de estos operadores, el relleno y la estimación de características también admiten los operadores lógicos [!UICONTROL AND], [!UICONTROL OR] y [!UICONTROL AND NOT], utilizados para combinar pares clave-valor dentro de las expresiones de características rellenadas.
