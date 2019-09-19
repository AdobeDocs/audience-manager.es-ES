---
description: Utilice operadores lógicos para agrupar pares de clave-valor y características de relleno.
seo-description: Utilice operadores lógicos para agrupar pares de clave-valor y características de relleno.
seo-title: Operadores lógicos admitidos
title: Operadores lógicos admitidos
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Operadores lógicos admitidos {#supported-logical-operators}

Utilice operadores lógicos para agrupar pares de clave-valor y características de relleno.

## Operadores admitidos para la búsqueda de señales {#supported-operators-search}

Utilice los siguientes operadores lógicos admitidos para buscar pares clave-valor:

### Operadores de comparación

| Operador | Definición |
|---|---|
| **==** | Igual a |
| **&gt;** | Mayor que |
| **&lt;** | Menor que |
| **=&gt;** | Mayor o igual que |
| **&lt;=** | Menor o igual que |

### Operadores con nombre

| Operador | Evalúa a [!DNL True] Cuándo |
|---|---|
| **[!UICONTROL Contains]** | El valor de un par clave-valor *contiene* caracteres especificados por este operador. |
| **[!UICONTROL Startswith]** | El valor de un par clave-valor *comienza con* los caracteres especificados por este operador. |
| **[!UICONTROL Endswith]** | El valor de un par clave-valor *termina con* los caracteres especificados por este operador. |

## Operadores admitidos para rellenar y calcular características {#supported-operators-backfilling}

Puede rellenar características que incluyan expresiones que contengan cualquiera de los operadores admitidos por [!UICONTROL Signal Search]. Además de estos operadores, el rellenado y la estimación de características también admiten los operadores [!UICONTROL AND], [!UICONTROL OR], y [!UICONTROL AND NOT] lógicos, utilizados para combinar pares de clave-valor dentro de las expresiones de rasgo rellenadas.