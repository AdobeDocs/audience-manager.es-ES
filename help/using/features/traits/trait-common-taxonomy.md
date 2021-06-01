---
description: Este artículo proporciona información general sobre la clasificación de características con una taxonomía común.
keywords: DIL
seo-description: Este artículo proporciona información general sobre la clasificación de características con una taxonomía común.
seo-title: Clasificación de rasgos con una taxonomía común
solution: Audience Manager
title: Clasificación de rasgos con una taxonomía común
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: 'Rasgos '
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 5%

---

# Clasificación de rasgos con una taxonomía común {#classifying-traits-with-a-common-taxonomy}

Este artículo proporciona información general sobre la clasificación de características con una taxonomía común.

## La taxonomía del Audience Manager

<!-- c_common_taxonomy_about.xml -->

La taxonomía [!DNL Audience Manager] es una función opcional que clasifica los rasgos mediante convenciones de nomenclatura uniformes, lógicas y comúnmente entendidas. Funciona a nivel de plataforma para ayudar a garantizar la coherencia de los nombres en todo el ecosistema [!DNL Audience Manager]. En última instancia, la taxonomía común está diseñada para llevar nuestro producto a una buena alineación con los estándares del sector respecto a los procesos de privacidad del consumidor y exclusión.

## Ventajas de la clasificación de rasgos

Habilitar a nuestros clientes para que creen segmentos personalizados y modelos de datos es básico para el modelo [!DNL Audience Manager] y para su capacidad de capturar valor de nuestra plataforma. Sin embargo, lo que también se necesita es un medio robusto y escalable para comunicar información sobre segmentos a sus clientes y socios. Además, esta comunicación requiere que la información del segmento se comparta en un lenguaje fácil de entender y universalmente entendido, al tiempo que protege sus rasgos propietarios y nombres de segmentos. La taxonomía común [!DNL Audience Manager] proporciona este idioma y esta capacidad.

## La taxonomía utiliza las categorías de clasificación estándar del sector

La taxonomía común se basa en las clasificaciones creadas por [!DNL Interactive Advertising Bureau (IAB)]. Consulte el [!DNL IAB] [sitio web](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) para obtener más información sobre las directrices de control de calidad para redes e intercambios.

## Organización taxonómica

La taxonomía [!DNL Audience Manager] organiza los datos en categorías anidadas denominadas niveles. Cada categoría puede contener hasta 3 niveles separados para la clasificación de datos. En el nivel más alto, una categoría de Nivel 1 agrupa los datos en su forma más general (por ejemplo, geografía). Los niveles posteriores proporcionan buena especificidad a la categoría general de nivel superior (por ejemplo, *geografía —> Estados Unidos —> Nueva York*). Sin embargo, no todas las categorías tienen 3 niveles, algunos utilizan solo 2.

## Clasificación de características en categorías de datos

Las clasificaciones taxonómicas se asignan al crear o editar características en [!UICONTROL Add New Trait Wizard] (ubicado en * **[!UICONTROL Audience Data > Traits]***). Consulte la [documentación sobre la creación de características](../../features/traits/create-onboarded-rule-based-traits.md) para obtener más información.

## Uso de la taxonomía: Consideraciones adicionales

Si decide clasificar los rasgos según nuestra taxonomía común, es importante recordar:

* La clasificación es *opcional*.
* Los rasgos *no se asignan* a una categoría taxonómica de forma predeterminada (es decir, los rasgos no se clasifican como &quot;desconocidos&quot; ni &quot;sin categoría&quot;, etc.).
* Los rasgos solo pueden pertenecer a la categoría taxonómica *one* (no se permiten clasificaciones múltiples y entre categorías).
