---
description: Preguntas y problemas comunes relacionados con los productos y las funciones.
keywords: cookies de Audience Manager
seo-description: Preguntas y problemas comunes relacionados con los productos y las funciones.
seo-title: Preguntas frecuentes sobre funciones y funciones de productos
solution: Audience Manager
title: Preguntas frecuentes sobre funciones y funciones de productos
uuid: da 5 f 5089-24 a 8-4455-88 a 6-eb 62 d 83939 d 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Product Features and Functions FAQ{#product-features-and-functions-faq}

Preguntas y problemas comunes relacionados con los productos y las funciones.

<br> 

<!-- 

faq_features_functions.xml

 -->

**¿Cuál es mi ID de organización y cómo puedo encontrarlo?**

The *`Organization ID`* is a unique ID that identifies your organization to [!DNL Audience Manager] and the [!DNL Adobe Experience Cloud]. It consists of a case-sensitive, 24-character alphanumeric string followed by [!UICONTROL @AdobeOrg].

For example, an *`Organization ID`* looks like this: `1FD6776A524453CC0A490D44@AdobeOrg`.

The *`Organization ID`* is used by Audience Manager's [DIL](../dil/dil-overview.md) API, the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/), and other [!DNL Experience Cloud] solutions. Users with Administrator permissions can find the *`Organization ID`* on the [!DNL Adobe Admin Console]. See the [Administration - User Management FAQ](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

<br> 

**¿Puedo crear características o destinos de forma masiva?**

Sí. See [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] tools *are not* supported by [!DNL Audience Manager]. Se proporcionan por comodidad y solo por cortesía. For bulk changes, we recommend you work with the [Audience Manager APIs](../api/api.md) instead.

<br> 

**¿[!DNL Audience Manager]Puede reducir la necesidad de etiquetas o píxeles de terceros y mejorar los tiempos de carga de las páginas?**

If [!DNL Audience Manager] is integrated with your third-party data partner, you can replace their pixels and tags with a server-to-server ID call to [!DNL Audience Manager]. In this case, [!DNL Audience Manager] would fire a single ID call the first time we see a user and synchronize that information with your third-party partner. Esto elimina la necesidad de realizar varias llamadas de píxeles desde cada página. Reducir las llamadas de píxeles puede mejorar los tiempos de carga de la página.

<br> 

**He suscrito a una fuente de datos. Where is that data stored?**

Your data feed and all the traits contained in the feed appear as subfolders and traits in [!DNL Audience Manager]. Go to **[!UICONTROL Audience Data > Traits]** and expand the [!UICONTROL 3rd-Party Data] folder to view your traits or create segments and models with this data.

<br> 

**¿Qué es[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager used [!UICONTROL Tag Insertion Manager] (TIM) to create and manage [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. For more information, see [Adobe Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**¿Cuáles son las diferencias entre Modelos algorítmicos y Recomendaciones de rasgos? When should I use each of them?**

**Modelos algorítmicos**

Los modelos algorítmicos no sólo encuentran las características más influyentes sino que también puntuan a los usuarios basándose en dichas características y asigna a cada usuario una puntuación individual. A continuación, cree características algorítmicas para dirigirse a los usuarios. Con los controles de precisión y alcance en el Generador de rasgos, puede especificar qué usuarios entre todos los que tienen las características influyentes que desee segmentar.

Los modelos algorítmicos le permiten seleccionar usuarios en diferentes niveles de precisión y probar en Audience Lab qué grupo de usuarios convierte mejor. See the detailed use case in [Compare Models in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

En Modelos algorítmicos, el modelo se ejecuta cada 8 días y se actualiza los usuarios cualificados para características algorítmicas.

**Trait Recommendations**

Recomendaciones de características es una forma rápida de obtener perspectivas sobre otras características que son similares a las que utiliza en un segmento.

Debe utilizar Recomendaciones de características cuando:

* Necesita perspectivas rápidas al generar un segmento;
* Utiliza los segmentos para campañas cortas o para eliminar rápidamente la audiencia que se convierte;
* Está intentando maximizar el alcance.

<br> 

**¿Hay alguna diferencia entre los segmentos de Adobe Analytics y Audience Manager?**

Yes, please read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.
