---
description: Busque una o varias señales, según sus pares de clave-valor respectivos.
seo-description: Busque una o varias señales, según sus pares de clave-valor respectivos.
seo-title: Buscar señales por pares clave-valor
title: Buscar señales por pares clave-valor
uuid: 2 a 38 d 0 d 4-4 a 2 e -4 ca 5-b 9 ec-af 9 d 4963 d 876
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Search Signals by Key-Value Pairs {#search-signals-by-key-value-pairs}

Busque una o varias señales, según sus pares de clave-valor respectivos.
To search for more than one signal, click the ![Add](assets/icon_add.png) button. Introduzca los pares de valor clave que desee buscar y, a continuación, utilice los filtros siguientes para reducir los resultados.

* **Estado de señal**: buscar señales incluidas en características, señales no utilizadas o ambos.
* **Ver registros para**: seleccione el intervalo de tiempo en el que buscar señales recibidas.
* **Recuento mínimo**: solo muestran señales con el recuento mínimo especificado en el intervalo seleccionado.

>[!IMPORTANT]
>
>Para una experiencia de usuario optimizada, los resultados de búsqueda de pares clave-valor se basan en muestras de datos. See [Data Sampling and Error Rates](/help/using/reporting/report-sampling.md) for details on how [!DNL Audience Manager] uses data sampling and why slight result variations may appear when comparing key-value search to general searches.

When searching for signals using multiple key-value pairs, [!DNL Audience Manager] links the pairs using the logical **AND** operator. Por ejemplo, supongamos que está realizando una búsqueda con los siguientes pares clave-valor:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

This search will return only results that qualify for all three filters on the same call: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Case Insensitivity and Search Auto-Completion {#case-insensitivity}

Los campos de búsqueda de valor y clave no distinguen mayúsculas de minúsculas. El campo de búsqueda clave incluye sugerencias completadas automáticamente.

![](assets/signal-search-suggestions.png)

Let&#39;s say [!DNL Audience Manager] received the following signals:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

When you enter `product` in the key search field, you receive auto-completed suggestions for `productCategory`, `newProduct`, `PRODUCT`, and `product`.

Similarly, when you search for `product == phone`, [!UICONTROL Data Explorer] returns results for both `PRODUCT == phone` and `product == PHONE`.
Las características de características rellenadas no distinguen entre mayúsculas y minúsculas. A trait containing the signal with the key-value pair `PRODUCT == SMARTPHONE` also qualifies the signal with the key-value pair `product == smartphone`.