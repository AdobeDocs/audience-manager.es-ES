---
description: Busque una o varias señales, en función de sus respectivos pares clave-valor.
seo-description: Busque una o varias señales, en función de sus respectivos pares clave-valor.
seo-title: Señales de búsqueda por pares de clave-valor
title: Señales de búsqueda por pares de clave-valor
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 4%

---


# Señales de búsqueda por pares de clave-valor {#search-signals-by-key-value-pairs}

Busque una o varias señales, en función de sus respectivos pares clave-valor.
Para buscar más de una señal, haga clic en el botón ![Añadir](assets/icon_add.png). Introduzca los pares clave-valor que desea buscar y, a continuación, utilice los siguientes filtros para reducir los resultados.

* **Estado** de la señal: buscar señales incluidas en características, señales no utilizadas o ambas.
* **Registros de vista para**: seleccione el intervalo de tiempo en el que desea buscar las señales recibidas.
* **Recuentos** mínimos: mostrar sólo las señales con el recuento total mínimo especificado en el intervalo seleccionado.

>[!IMPORTANT]
>
>Para una experiencia de usuario optimizada, los resultados de búsqueda de pares de clave-valor se basan en el muestreo de datos. Consulte [Muestreo de datos y tasas de error](/help/using/reporting/report-sampling.md) para obtener más información sobre cómo [!DNL Audience Manager] utiliza el muestreo de datos y por qué pueden aparecer ligeras variaciones de resultados al comparar la búsqueda de valor clave con las búsquedas generales.

Al buscar señales utilizando varios pares clave-valor, [!DNL Audience Manager] vincula los pares utilizando el operador lógico **AND**. Por ejemplo: supongamos que está realizando una búsqueda con los siguientes pares clave-valor:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Esta búsqueda sólo devolverá resultados que califiquen para los tres filtros en la misma llamada: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Señales excluidas de la búsqueda de señales {#excluded-signals}

Las variables clave utilizadas por el Audience Manager y con el prefijo `d_` y `h_` no aparecen en [!UICONTROL Signals Search]. Consulte [Requisitos de prefijo para variables clave](../../traits/trait-variable-prefixes.md) para obtener más información.

## Insensibilidad de los casos y finalización automática de la búsqueda {#case-insensitivity}

Los campos de búsqueda de clave y valor no distinguen entre mayúsculas y minúsculas. El campo de búsqueda clave incluye sugerencias completadas automáticamente.

![](assets/signal-search-suggestions.png)

Digamos que [!DNL Audience Manager] recibió las siguientes señales:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Al ingresar `product` en el campo de búsqueda clave, recibirá sugerencias autocompletadas para `productCategory`, `newProduct`, `PRODUCT` y `product`.

Del mismo modo, cuando busca `product == phone`, [!UICONTROL Data Explorer] devuelve resultados tanto para `PRODUCT == phone` como para `product == PHONE`.
Las realizaciones de características rellenadas con versiones anteriores no distinguen entre mayúsculas y minúsculas. Una característica que contiene la señal con el par clave-valor `PRODUCT == SMARTPHONE` también califica la señal con el par clave-valor `product == smartphone`.