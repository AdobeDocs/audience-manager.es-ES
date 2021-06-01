---
description: Utilice operadores lógicos para agrupar pares de clave-valor y rasgos de relleno.
seo-description: Utilice operadores lógicos para agrupar pares de clave-valor y rasgos de relleno.
seo-title: Operadores lógicos admitidos
title: Operadores lógicos admitidos
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: 'Explorador de datos '
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 10%

---

# Operadores lógicos admitidos {#supported-logical-operators}

Utilice operadores lógicos para agrupar pares de clave-valor y rasgos de relleno.

## Operadores admitidos para la búsqueda de señales {#supported-operators-search}

Utilice los siguientes operadores lógicos admitidos para buscar pares clave-valor:

### Operadores de comparación

| Operador | Definición |
|---|---|
| **==** | Igual a |
| **>** | Mayor que |
| **&lt;>** | Menor que |
| **=>** | Bueno que/igual a |
| **&lt;>** | Menor o igual que |

### Operadores con nombre

| Operador | Evalúa a [!DNL True] Cuando |
|---|---|
| **[!UICONTROL Contains]** | El valor de un par clave-valor *contiene* caracteres especificados por este operador. |
| **[!UICONTROL Startswith]** | El valor de un par clave-valor *comienza con los caracteres* especificados por este operador. |
| **[!UICONTROL Endswith]** | El valor de un par clave-valor *termina con* los caracteres especificados por este operador. |

## Operadores admitidos para relleno y estimación de rasgos {#supported-operators-backfilling}

Puede rellenar rasgos que incluyen expresiones que contienen cualquiera de los operadores admitidos por [!UICONTROL Signal Search]. Además de estos operadores, el rellenado y la estimación de rasgos también admiten los operadores lógicos [!UICONTROL AND], [!UICONTROL OR] y [!UICONTROL AND NOT], que se utilizan para combinar pares de clave-valor dentro de las expresiones de rasgos rellenadas.
