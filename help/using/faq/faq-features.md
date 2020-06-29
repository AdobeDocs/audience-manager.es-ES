---
description: Preguntas y problemas comunes relacionados con el producto y las funciones.
keywords: audience manager cookies
seo-description: Preguntas y problemas comunes relacionados con el producto y las funciones.
seo-title: Preguntas más frecuentes sobre funciones y características del producto
solution: Audience Manager
title: Preguntas más frecuentes sobre funciones y características del producto
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 0%

---


# Preguntas más frecuentes sobre funciones y características del producto{#product-features-and-functions-faq}

Preguntas y problemas comunes relacionados con el producto y las funciones.

 

<!-- 

faq_features_functions.xml

 -->

**¿Cuál es mi identificador de organización y cómo puedo encontrarlo?**

El *`Organization ID`* es un identificador único que identifica a su organización [!DNL Audience Manager] y a la [!DNL Adobe Experience Cloud]. Consiste en una cadena alfanumérica de 24 caracteres que distingue entre mayúsculas y minúsculas seguida de [!UICONTROL @AdobeOrg].

Por ejemplo, un *`Organization ID`* aspecto es el siguiente: `1FD6776A524453CC0A490D44@AdobeOrg`.

El *`Organization ID`* lo utilizan la API [DIL](../dil/dil-overview.md) de Audience Manager, el servicio [de identidad de](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform y otras [!DNL Experience Cloud] soluciones. Los usuarios con permisos de administrador pueden encontrar el *`Organization ID`* en la [!DNL Adobe Admin Console]. Consulte las preguntas más frecuentes [](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)sobre administración y administración de usuarios.

 

**¿Puedo crear características o destinos de forma masiva?**

Sí. Consulte Herramientas [de administración masiva](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>Las [!UICONTROL Bulk Management Tools] herramientas no *son* compatibles con [!DNL Audience Manager]. Son provistos por conveniencia y sólo por cortesía. Para los cambios masivos, le recomendamos que trabaje con las API [de](../api/api.md) Audience Manager.

 

**Al realizar una exportación masiva de ID a un destino, faltan algunos de los ID de cliente. Why does that happen?**

Cuando un ID de dispositivo ([AAM UUID](../reference/ids-in-aam.md)) está vinculado a varios ID de CRM ([DPUUID](../reference/ids-in-aam.md)), solo se exporta la asignación más reciente. Por este motivo, es posible que vea un número de ID de dispositivo inferior al esperado que se está exportando.

 

**¿Puede[!DNL Audience Manager]reducir la necesidad de etiquetas de terceros o píxeles y mejorar los tiempos de carga de las páginas?**

Si [!DNL Audience Manager] está integrado con su socio de datos de terceros, puede reemplazar sus píxeles y etiquetas con una llamada de ID de servidor a servidor a [!DNL Audience Manager]. En este caso, [!DNL Audience Manager] activaría una sola llamada de ID la primera vez que veamos a un usuario y sincronizaría esa información con su socio de terceros. Esto elimina la necesidad de realizar llamadas de varios píxeles desde cada página. La reducción de las llamadas en píxeles puede mejorar los tiempos de carga de las páginas.

 

**Me he suscrito a una fuente de datos. ¿Dónde se almacenan esos datos?**

La fuente de datos y todas las características de la fuente aparecen como subcarpetas y características en [!DNL Audience Manager]. Vaya a **[!UICONTROL Audience Data > Traits]** y expanda la [!UICONTROL 3rd-Party Data] carpeta para vista de sus características o crear segmentos y modelos con estos datos.

 

**¿Qué es[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager utilizado [!UICONTROL Tag Insertion Manager] (TIM) para crear y administrar [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Experience Platform Launch]. For more information, see [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html).

 

**¿Cuáles son las diferencias entre los modelos algorítmicos y las recomendaciones de características? ¿Cuándo debo usar cada uno de ellos?**

**Modelos algorítmicos**

Los modelos algorítmicos no sólo encuentran las características más influyentes, sino que también puntuan a los usuarios en función de esas características y asignan a cada usuario una puntuación individual. A continuación, puede crear características algorítmicas para el destinatario de los usuarios. Con los controles de precisión y alcance del Generador de características, puede especificar qué usuarios de entre todos los que tienen las características influyentes que desea destinatario.

Los modelos algorítmicos le permiten seleccionar usuarios en diferentes niveles de precisión y probar en el laboratorio de Audiencia qué grupo de usuarios se convierte mejor. Consulte el caso de uso detallado en [Comparar modelos en el laboratorio](../features/audience-lab/audience-lab-use-cases.md#compare-models)de Audiencia.

En Modelos algorítmicos, el modelo se ejecuta cada 8 días y actualiza los usuarios calificados para características algorítmicas.

**Trait Recommendations**

Recomendaciones de características es una forma rápida de obtener perspectivas sobre otras características similares a las que se utilizan en un segmento.

Debe usar Recomendaciones de características cuando:

* Necesita perspectivas rápidas al crear un segmento;
* Está utilizando los segmentos para campañas cortas o cuando desea suprimir rápidamente la audiencia que convierte;
* Está intentando maximizar el alcance.

 

**¿Hay alguna diferencia entre los segmentos de Adobe Analytics y Audience Manager?**

Sí, lea [Explicación de los segmentos en Analytics y Audience Manager](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) para obtener una descripción detallada de las diferencias.
