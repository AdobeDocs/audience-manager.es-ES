---
description: Search para una o varias señales, en función de sus respectivos pares clave-valor.
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: Search señales por pares clave-Valor
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# Search señales por pares clave-valor {#search-signals-by-key-value-pairs}

Search para una o varias señales, en función de sus respectivos pares clave-valor.
Para búsqueda más de una señal, haga clic en la botón añadir![](assets/icon_add.png). Introduzca los pares clave-valor que desea búsqueda y, a continuación, utilice el siguiente filtros para reducir los resultados.

* **Estado de la** señal: búsqueda para las señales incluidas en los rasgos, las señales no utilizadas o ambas.
* **Ver registros para**: seleccione el intervalo de tiempo en el que desea búsqueda las señales recibidas.
* **Recuentos mínimos**: muestra solo señales con el recuento total mínimo especificado en el intervalo seleccionado.

>[!IMPORTANT]
>
>Para una experiencia del usuario optimizada, los resultados búsqueda par clave-valor se basan en la muestreo de datos. Consulte [Muestreo de datos y tasas](/help/using/reporting/report-sampling.md) de Error para obtener detalles sobre cómo [!DNL Audience Manager] se utiliza la muestreo de datos y por qué pueden aparecer ligeras variaciones en los resultados al comparar búsqueda de valor clave con búsquedas generales.

Cuando se buscan señales con varios pares clave-valor, [!DNL Audience Manager] vincula los pares mediante el operador lógico **AND** . Por instancia, supongamos que realiza un búsqueda con los siguientes pares clave-valor:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Este búsqueda solo devolverá los resultados que califiquen para las tres filtros en la misma convocatoria: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"` .

![](assets/signals-search.png)

## Señales excluidas del búsqueda de señales {#excluded-signals}

Las variables clave utilizadas por Audience Manager y prefijadas por los `d_` prefijos and `h_` no aparecen en la superficie mediante [!UICONTROL Signals Search]. Consulte [Requisitos de prefijo para variables](../../traits/trait-variable-prefixes.md) clave para obtener más detalles.

## Distinción entre mayúsculas y minúsculas y finalización automática de búsqueda {#case-insensitivity}

Los campos búsqueda clave y valor son con distinción de mayúsculas y minúsculas. El campo búsqueda clave incluye las sugerencias autocompletadas.

![](assets/signal-search-suggestions.png)

Digamos que [!DNL Audience Manager] recibió las siguientes señales:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Cuando introduzca `product` en el campo de búsqueda clave, recibirá sugerencias autocompletadas para `productCategory` y `product`.

Del mismo modo, cuando búsqueda para `product == PHONE`, [!UICONTROL Data Explorer] devuelve resultados sólo para `product == PHONE`.

Las realizaciones de rasgos rellenados también son con distinción de mayúsculas y minúsculas. Un rasgo que contiene la señal con el par `PRODUCT == SMARTPHONE` clave-valor no califica la señal con el par `product == smartphone`clave-valor.
