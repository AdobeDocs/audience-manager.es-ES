---
description: This article provides general overview about classifying traits with a common taxonomy.
keywords: DIL
seo-description: This article provides general overview about classifying traits with a common taxonomy.
seo-title: Classifying Traits with a Common Taxonomy
solution: Audience Manager
title: Classifying Traits with a Common Taxonomy
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---


# Classifying Traits with a Common Taxonomy {#classifying-traits-with-a-common-taxonomy}

This article provides general overview about classifying traits with a common taxonomy.

## The Audience Manager Taxonomy

<!-- c_common_taxonomy_about.xml -->

La taxonomía [!DNL Audience Manager] es una función opcional que clasifica características mediante convenciones de nombres uniformes, lógicas y comúnmente conocidas. It operates at the platform level to help ensure naming consistency throughout the [!DNL Audience Manager] ecosystem. En última instancia, la taxonomía común está diseñada para hacer que nuestro producto se ajuste bueno a las normas del sector relativas a la privacidad del consumidor y a los procesos de exclusión.

## Ventajas de la clasificación de características

Permitir a nuestros clientes crear segmentos personalizados y modelos de datos es fundamental para el [!DNL Audience Manager] modelo y para su capacidad de capturar valor desde nuestra plataforma. Sin embargo, lo que también se necesita es un medio robusto y escalable para comunicar información sobre segmentos a sus clientes y socios. Además, esta comunicación requiere que la información de los segmentos se comparta en un lenguaje fácil de entender y universalmente entendido, al tiempo que se protege su característica propia y los nombres de los segmentos. La taxonomía [!DNL Audience Manager] común proporciona este lenguaje y esta capacidad.

## La Taxonomía Utiliza Categorías De Clasificación Estándar De La Industria

La taxonomía común se basa en las clasificaciones creadas por el [!DNL Interactive Advertising Bureau (IAB)]. Consulte el [!DNL IAB]sitio web [](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) del usuario para obtener más información sobre las directrices de garantía de calidad para redes e intercambios.

## Organización taxonómica

La [!DNL Audience Manager] taxonomía organiza los datos en categorías anidadas denominadas niveles. Cada categoría puede contener hasta 3 niveles distintos para la clasificación de datos. En el nivel más alto, una categoría de Nivel 1 agrupa los datos en su forma más general (por ejemplo, geografía). Los niveles subsiguientes proporcionan buena especificidad al nivel superior, categoría general (por ejemplo, *geografía —> Estados Unidos —> Nueva York*). Sin embargo, no todas las categorías tienen 3 niveles, algunos usan sólo 2.

## Clasificar características en Categorías de datos

Las clasificaciones taxonómicas se asignan al crear o editar características en el [!UICONTROL Add New Trait Wizard] (ubicado en * **[!UICONTROL Audience Data > Traits]***). Consulte la [documentación sobre la creación de características](../../features/traits/create-onboarded-rule-based-traits.md) para obtener más información.

## Uso de la taxonomía: Consideraciones adicionales

Si decide clasificar características según nuestra taxonomía común, es importante recordar:

* La clasificación es *opcional*.
* Las características no *se asignan* de forma predeterminada a una categoría taxonómica (es decir, las características no se clasifican como &quot;desconocidas&quot; o &quot;sin categoría&quot;, etc.).
* Las características solo pueden pertenecer a *una* categoría taxonómica (no se permiten clasificaciones múltiples y de categorías cruzadas).