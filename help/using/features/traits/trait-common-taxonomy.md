---
description: Este artículo proporciona información general sobre la clasificación de rasgos con una taxonomía común.
keywords: DIL
seo-description: This article provides general overview about classifying traits with a common taxonomy.
seo-title: Classifying Traits with a Common Taxonomy
solution: Audience Manager
title: Clasificación de rasgos con una taxonomía común
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# Clasificación de rasgos con una taxonomía común {#classifying-traits-with-a-common-taxonomy}

Este artículo proporciona información general sobre la clasificación de rasgos con una taxonomía común.

## La taxonomía de Audience Manager

<!-- c_common_taxonomy_about.xml -->

La taxonomía [!DNL Audience Manager] es una característica opcional que clasifica características mediante convenciones de nomenclatura uniformes, lógicas y de uso común. Funciona en el nivel de plataforma para ayudar a garantizar la coherencia de los nombres en todo el ecosistema [!DNL Audience Manager]. En última instancia, la taxonomía común está diseñada para alinear mejor nuestro producto con los estándares del sector en cuanto a los procesos de privacidad del consumidor y exclusión.

## Ventajas de la clasificación de rasgos

Permitir que nuestros clientes creen segmentos personalizados y modelos de datos es fundamental para el modelo [!DNL Audience Manager] y para su capacidad de capturar valor de nuestra plataforma. Sin embargo, también se necesita un medio sólido y escalable para comunicar información sobre segmentos a sus clientes y socios. Además, esta comunicación requiere que la información del segmento se comparta en un lenguaje fácil de entender y comprendido universalmente, a la vez que protege sus rasgos propietarios y nombres de segmento. La taxonomía común [!DNL Audience Manager] proporciona este idioma y esta capacidad.

## La Taxonomía Utiliza Categorías De Clasificación Estándar Del Sector

La taxonomía común se basa en las clasificaciones creadas por [!DNL Interactive Advertising Bureau (IAB)]. Consulte el [!DNL IAB]sitio web[&#x200B; de &#x200B;](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) para obtener más información sobre las directrices de garantía de calidad para redes e intercambios.

## Organización taxonómica

La taxonomía [!DNL Audience Manager] organiza los datos en categorías anidadas denominadas niveles. Cada categoría puede contener hasta 3 niveles independientes para la clasificación de datos. En el nivel más alto, una categoría de nivel 1 agrupa los datos en su forma más general (por ejemplo, geografía). Los niveles posteriores proporcionan una mayor especificidad al nivel superior, categoría general (por ejemplo, *geografía —> Estados Unidos —> Nueva York*). Sin embargo, no todas las categorías tienen 3 niveles, algunos utilizan solo 2.

## Clasificar rasgos en categorías de datos

Las clasificaciones taxonómicas se asignan al crear o editar características en [!UICONTROL Add New Trait Wizard] (ubicado en ***[!UICONTROL Audience Data > Traits]***). Consulte la [documentación sobre la creación de características](../../features/traits/create-onboarded-rule-based-traits.md) para obtener más información.

## Uso de la taxonomía: consideraciones adicionales

Si decide clasificar los rasgos según nuestra taxonomía común, es importante recordar lo siguiente:

* La clasificación es *opcional*.
* Los rasgos *no son* asignados a una categoría taxonómica de forma predeterminada (es decir, los rasgos no se clasifican como &quot;desconocidos&quot; o &quot;sin clasificar&quot;, etc.).
* Los rasgos solo pueden pertenecer a *una* categoría taxonómica (no se permiten clasificaciones múltiples y entre categorías).
