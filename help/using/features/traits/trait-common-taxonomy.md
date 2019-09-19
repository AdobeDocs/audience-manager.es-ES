---
description: Este artículo proporciona información general sobre la clasificación de características con una taxonomía común.
keywords: DIL
seo-description: Este artículo proporciona información general sobre la clasificación de características con una taxonomía común.
seo-title: Clasificación de características con una taxonomía común
solution: Audience Manager
title: Clasificación de características con una taxonomía común
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# Clasificación de características con una taxonomía común {#classifying-traits-with-a-common-taxonomy}

Este artículo proporciona información general sobre la clasificación de características con una taxonomía común.

## La taxonomía de Audience Manager

<!-- c_common_taxonomy_about.xml -->

La taxonomía [!DNL Audience Manager] es una función opcional que clasifica características mediante convenciones de nombres uniformes, lógicas y comúnmente conocidas. Funciona a nivel de plataforma para ayudar a garantizar la coherencia de los nombres en todo el [!DNL Audience Manager] ecosistema. En última instancia, la taxonomía común está diseñada para que nuestro producto se ajuste mejor a las normas del sector relativas a la privacidad del consumidor y a los procesos de exclusión.

## Ventajas de la clasificación de características

Permitir a nuestros clientes crear segmentos personalizados y modelos de datos es fundamental para el [!DNL Audience Manager] modelo y para su capacidad de capturar valor desde nuestra plataforma. Sin embargo, lo que también se necesita es un medio robusto y escalable para comunicar información sobre segmentos a sus clientes y socios. Además, esta comunicación requiere que la información del segmento se comparta en un lenguaje fácil de entender y universalmente entendido, al tiempo que se protege su característica propia y los nombres de segmentos. La taxonomía [!DNL Audience Manager] común proporciona este lenguaje y esta capacidad.

## La Taxonomía Utiliza Categorías De Clasificación Estándar De La Industria

La taxonomía común se basa en las clasificaciones creadas por el [!DNL Interactive Advertising Bureau (IAB)]. Consulte el [!DNL IAB]sitio web [](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) del usuario para obtener más información sobre las directrices de garantía de calidad para redes e intercambios.

## Organización taxonómica

La taxonomía [!DNL Audience Manager] organiza los datos en categorías anidadas denominadas niveles. Cada categoría puede contener hasta 3 niveles distintos para la clasificación de datos. En el nivel más alto, una categoría de nivel 1 agrupa los datos en su forma más general (por ejemplo, geografía). Los niveles posteriores proporcionan una mayor especificidad a la categoría general de nivel superior (por ejemplo, *geografía —&gt; Estados Unidos —&gt; Nueva York*). Sin embargo, no todas las categorías tienen 3 niveles, algunas usan sólo 2.

## Clasificar características en categorías de datos

Las clasificaciones taxonómicas se asignan al crear o editar características en el [!UICONTROL Add New Trait Wizard] (ubicado en * **[!UICONTROL Audience Data > Traits]***). Consulte la [documentación sobre la creación de características](../../features/traits/create-onboarded-rule-based-traits.md) para obtener más información.

## Uso de la taxonomía: Consideraciones adicionales

Si decide clasificar características según nuestra taxonomía común, es importante recordar:

* La clasificación es *opcional*.
* Las características no *se asignan* a una categoría taxonómica de forma predeterminada (es decir, las características no se clasifican como "desconocidas" o "sin categoría", etc.).
* Las características solo pueden pertenecer a *una* categoría taxonómica (no se permiten clasificaciones múltiples y entre categorías).