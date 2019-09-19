---
description: Preguntas y problemas comunes relacionados con el producto y las funciones.
keywords: cookies del administrador de audiencias
seo-description: Preguntas y problemas comunes relacionados con el producto y las funciones.
seo-title: Preguntas más frecuentes sobre funciones y características del producto
solution: Audience Manager
title: Preguntas más frecuentes sobre funciones y características del producto
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Preguntas más frecuentes sobre funciones y características del producto{#product-features-and-functions-faq}

Preguntas y problemas comunes relacionados con el producto y las funciones.

<br> 

<!-- 

faq_features_functions.xml

 -->

**¿Cuál es mi identificador de organización y cómo lo encuentro?**

El *`Organization ID`* es un identificador único que identifica a su organización [!DNL Audience Manager] y a la [!DNL Adobe Experience Cloud]. Consiste en una cadena alfanumérica de 24 caracteres que distingue entre mayúsculas y minúsculas seguida de [!UICONTROL @AdobeOrg].

Por ejemplo, un *`Organization ID`* aspecto es el siguiente: `1FD6776A524453CC0A490D44@AdobeOrg`.

El *`Organization ID`* lo utilizan la API [DIL](../dil/dil-overview.md) de Audience Manager, el servicio [de ID de](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud y otras [!DNL Experience Cloud] soluciones. Los usuarios con permisos de administrador pueden encontrar el *`Organization ID`* en la [!DNL Adobe Admin Console]. Consulte las preguntas más frecuentes [](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)sobre administración y administración de usuarios.

<br> 

**¿Puedo crear características o destinos de forma masiva?**

Sí. Consulte Herramientas [de administración masiva](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>Las [!UICONTROL Bulk Management Tools] herramientas no *son* compatibles con [!DNL Audience Manager]. Son provistos por conveniencia y sólo por cortesía. Para los cambios masivos, se recomienda trabajar con las API [de](../api/api.md) Audience Manager en su lugar.

<br> 

**¿Puede[!DNL Audience Manager]reducir la necesidad de etiquetas de terceros o píxeles y mejorar los tiempos de carga de las páginas?**

Si [!DNL Audience Manager] está integrado con su socio de datos de terceros, puede reemplazar sus píxeles y etiquetas con una llamada de ID de servidor a servidor a [!DNL Audience Manager]. En este caso, [!DNL Audience Manager] activaría una sola llamada de ID la primera vez que veamos a un usuario y sincronizaría esa información con su socio de terceros. Esto elimina la necesidad de realizar llamadas de varios píxeles desde cada página. La reducción de las llamadas en píxeles puede mejorar los tiempos de carga de las páginas.

<br> 

**Me he suscrito a una fuente de datos. ¿Dónde se almacenan esos datos?**

La fuente de datos y todas las características de la fuente aparecen como subcarpetas y características en [!DNL Audience Manager]. Vaya a **[!UICONTROL Audience Data > Traits]** y expanda la [!UICONTROL 3rd-Party Data] carpeta para ver sus características o cree segmentos y modelos con estos datos.

<br> 

**¿Qué es[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager utilizó [!UICONTROL Tag Insertion Manager] (TIM) para crear y administrar [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. Para obtener más información, consulte [Adobe Launch](https://docs.adobelaunch.com/) y Administración [dinámica de etiquetas](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**¿Cuáles son las diferencias entre los modelos algorítmicos y las recomendaciones de características? ¿Cuándo debo usar cada uno de ellos?**

**Modelos algorítmicos**

Los modelos algorítmicos no sólo encuentran las características más influyentes, sino que también puntuan a los usuarios en función de esas características y asignan a cada usuario una puntuación individual. A continuación, puede crear características algorítmicas para dirigirse a los usuarios. Con los controles de precisión y alcance del Generador de características, puede especificar qué usuarios de entre todos los que tienen las características influyentes que desea definir como objetivo.

Los modelos algorítmicos le permiten seleccionar usuarios en diferentes niveles de precisión y probar en Audience Lab qué grupo de usuarios se convierte mejor. Consulte el caso de uso detallado en [Comparar modelos en Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

En Modelos algorítmicos, el modelo se ejecuta cada 8 días y actualiza los usuarios calificados para características algorítmicas.

**Trait Recommendations**

Recomendaciones de características es una forma rápida de obtener perspectivas sobre otras características similares a las que se utilizan en un segmento.

Debe usar Recomendaciones de características cuando:

* Necesita perspectivas rápidas al crear un segmento;
* Utiliza los segmentos para campañas cortas o cuando desea suprimir rápidamente a la audiencia que realiza la conversión;
* Está intentando maximizar el alcance.

<br> 

**¿Hay alguna diferencia entre los segmentos de Adobe Analytics y Audience Manager?**

Sí, lea [Explicación de los segmentos en Analytics y Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) para obtener una descripción detallada de las diferencias.
