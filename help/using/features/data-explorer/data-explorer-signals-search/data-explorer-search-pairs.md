---
description: Busque una o varias señales, en función de sus pares clave-valor respectivos.
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: Señales de búsqueda por pares clave-valor
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# Señales de búsqueda por pares clave-valor {#search-signals-by-key-value-pairs}

Busque una o varias señales, en función de sus pares clave-valor respectivos.
Para buscar más de una señal, haga clic en el botón ![Agregar](assets/icon_add.png). Introduzca los pares de clave-valor que desea buscar y, a continuación, utilice los siguientes filtros para reducir los resultados.

* **Estado de señal**: busque señales incluidas en rasgos, señales no utilizadas o ambas.
* **Ver registros para**: seleccione el intervalo de tiempo en el que desea buscar las señales recibidas.
* **Recuentos mínimos**: mostrar solo las señales con el recuento total mínimo especificado en el intervalo seleccionado.

>[!IMPORTANT]
>
>Para una experiencia de usuario optimizada, los resultados de búsqueda de pares de clave-valor se basan en el muestreo de datos. Consulte [Muestreo de datos y tasas de error](/help/using/reporting/report-sampling.md) para obtener detalles sobre cómo [!DNL Audience Manager] usa el muestreo de datos y por qué pueden aparecer ligeras variaciones de resultados al comparar la búsqueda de clave-valor con las búsquedas generales.

Al buscar señales usando varios pares clave-valor, [!DNL Audience Manager] vincula los pares usando el operador lógico **AND**. Por ejemplo, supongamos que está realizando una búsqueda con los siguientes pares clave-valor:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Esta búsqueda solo arrojará resultados que cumplan los requisitos para los tres filtros en la misma llamada: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Señales excluidas de la búsqueda de señales {#excluded-signals}

Las variables clave utilizadas por el Audience Manager y prefijadas por los prefijos `d_` y `h_` no aparecen en [!UICONTROL Signals Search]. Consulte [Requisitos de prefijo para variables clave](../../traits/trait-variable-prefixes.md) para obtener más información.

## Distinción entre mayúsculas y minúsculas y finalización automática de búsquedas {#case-insensitivity}

Los campos de búsqueda de clave y valor distinguen entre mayúsculas y minúsculas. El campo de búsqueda clave incluye sugerencias autocompletadas.

![](assets/signal-search-suggestions.png)

Supongamos que [!DNL Audience Manager] recibió las siguientes señales:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Cuando escriba `product` en el campo de búsqueda de claves, recibirá sugerencias autocompletadas para `productCategory` y `product`.

Del mismo modo, cuando busca `product == PHONE`, [!UICONTROL Data Explorer] devuelve resultados solamente para `product == PHONE`.

Las realizaciones de rasgos rellenados también distinguen entre mayúsculas y minúsculas. Un rasgo que contiene la señal con el par clave-valor `PRODUCT == SMARTPHONE` no califica la señal con el par clave-valor `product == smartphone`.
