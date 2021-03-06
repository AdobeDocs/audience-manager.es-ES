---
description: Busque una o varias señales, en función de sus respectivos pares clave-valor.
seo-description: Busque una o varias señales, en función de sus respectivos pares clave-valor.
seo-title: Señales de búsqueda por pares de clave-valor
title: Señales de búsqueda por pares de clave-valor
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: 'Explorador de datos '
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 5%

---

# Señales de búsqueda por pares de clave-valor {#search-signals-by-key-value-pairs}

Busque una o varias señales, en función de sus respectivos pares clave-valor.
Para buscar más de una señal, haga clic en el botón ![Add](assets/icon_add.png). Introduzca los pares clave-valor que desea buscar y, a continuación, utilice los filtros siguientes para reducir los resultados.

* **Estado** de la señal: busque señales incluidas en características, señales no utilizadas o ambas.
* **Ver registros para**: seleccione el intervalo de tiempo en el que desea buscar las señales recibidas.
* **Recuentos** mínimos: mostrar solo las señales con el recuento total mínimo especificado en el intervalo seleccionado.

>[!IMPORTANT]
>
>Para una experiencia de usuario optimizada, los resultados de búsqueda de pares clave-valor se basan en el muestreo de datos. Consulte [Muestreo de datos y tasas de error](/help/using/reporting/report-sampling.md) para obtener más información sobre cómo [!DNL Audience Manager] utiliza el muestreo de datos y por qué pueden aparecer ligeras variaciones de resultados al comparar la búsqueda de valor clave con búsquedas generales.

Al buscar señales utilizando varios pares clave-valor, [!DNL Audience Manager] vincula los pares utilizando el operador lógico **AND**. Por ejemplo, supongamos que está realizando una búsqueda con los siguientes pares clave-valor:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Esta búsqueda solo devolverá resultados que sean aptos para los tres filtros en la misma llamada: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Señales excluidas de la búsqueda de señales {#excluded-signals}

Las variables clave utilizadas por el Audience Manager y con el prefijo `d_` y `h_` no aparecen en [!UICONTROL Signals Search]. Consulte [Requisitos de prefijo para variables clave](../../traits/trait-variable-prefixes.md) para obtener más información.

## Insensibilidad de mayúsculas y minúsculas y autofinalización de búsqueda {#case-insensitivity}

Los campos de búsqueda de clave y valor no distinguen entre mayúsculas y minúsculas. El campo de búsqueda clave incluye sugerencias completadas automáticamente.

![](assets/signal-search-suggestions.png)

Digamos que [!DNL Audience Manager] recibió las siguientes señales:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Al introducir `product` en el campo de búsqueda clave, recibirá sugerencias completadas automáticamente para `productCategory`, `newProduct`, `PRODUCT` y `product`.

Del mismo modo, cuando se busca `product == phone`, [!UICONTROL Data Explorer] devuelve resultados tanto para `PRODUCT == phone` como para `product == PHONE`.
Las realizaciones de rasgos rellenadas no distinguen entre mayúsculas y minúsculas. Un rasgo que contiene la señal con el par clave-valor `PRODUCT == SMARTPHONE` también califica la señal con el par clave-valor `product == smartphone`.
