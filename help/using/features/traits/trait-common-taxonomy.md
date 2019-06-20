---
description: Este artículo proporciona información general general sobre la clasificación de características con una taxonomía común.
keywords: DIL
seo-description: Este artículo proporciona información general general sobre la clasificación de características con una taxonomía común.
seo-title: Clasificación de características con una taxonomía común
solution: Audience Manager
title: Clasificación de características con una taxonomía común
uuid: 2 e 177344-07 d 9-40 a 7-8 c 99-c 6 c 6518 b 9 d 97
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# Classifying Traits with a Common Taxonomy {#classifying-traits-with-a-common-taxonomy}

Este artículo proporciona información general general sobre la clasificación de características con una taxonomía común.

## La taxonomía de Audience Manager

<!-- c_common_taxonomy_about.xml -->

[!DNL Audience Manager] La taxonomía es una característica opcional que clasifica las características utilizando convenciones de nombres uniformes, lógicos y comúnmente interpretadas. It operates at the platform level to help ensure naming consistency throughout the [!DNL Audience Manager] ecosystem. Finalmente, la taxonomía común está diseñada para que el producto sea más coherente con los estándares del sector con respecto a los procesos de exclusión y privacidad del consumidor.

## Ventajas de la clasificación de características

Enabling our customers to build custom segments and data models is core to the [!DNL Audience Manager] model and to your ability to capture value from our platform. Sin embargo, lo que también es necesario es un medio sólido y escalable para comunicar información sobre segmentos a sus clientes y socios. Además, esta comunicación requiere que la información de segmentos se comparte en un lenguaje fácil de comprender y universalmente comprensible al mismo tiempo que protege los nombres de segmentos y de rasgos propios. The [!DNL Audience Manager] common taxonomy provides this language and capability.

## La Taxonomía usa categorías de clasificación estándar del sector

The common taxonomy is based on the classifications created by the [!DNL Interactive Advertising Bureau (IAB)]. Refer to the [!DNL IAB]&#39;s [website](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) for more information about quality assurance guidelines for networks and exchanges.

## Organización taxonómica

[!DNL Audience Manager] La taxonomía organiza los datos en categorías anidadas denominadas niveles. Cada categoría puede contener hasta 3 niveles distintos para la clasificación de datos. En el nivel más alto, una categoría de nivel 1 agrupa los datos en su formulario más general (p. ej., geografía). Subsequent tiers provide greater specificity to the higher level, general category (e.g., *geography --&gt; United States --&gt; New York*). Sin embargo, no todas las categorías tienen 3 niveles, algunos usan solo 2.

## Clasificar características en categorías de datos

You assign taxonomic classifications when creating or editing traits in the [!UICONTROL Add New Trait Wizard] (located in * **[!UICONTROL Audience Data > Traits]***). Refer to the [documentation on creating traits](../../features/traits/create-onboarded-rule-based-traits.md) for more information.

## Uso de la taxonomía: Consideraciones adicionales

Si decide clasificar características según nuestra taxonomía común, es importante recordar:

* Classification is *optional*.
* Traits *are not* assigned to a taxonomic category by default (i.e., traits are not classified as &quot;unknown&quot; or &quot;uncategorized&quot; etc.).
* Traits can belong to *one* taxonomic category only (multiple and cross-category classifications are not allowed).