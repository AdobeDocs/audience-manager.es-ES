---
description: Preguntas y problemas frecuentes relacionados con el producto y las funciones.
keywords: cookies de audience manager
seo-description: Common product and function-related questions and issues.
seo-title: Product Features and Functions FAQ
solution: Audience Manager
title: Preguntas frecuentes sobre funciones y características del producto
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
exl-id: b5884d26-0be1-4eaa-99a1-7247942bf6c9
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 87%

---

# Preguntas frecuentes sobre funciones y características del producto{#product-features-and-functions-faq}

Preguntas y problemas frecuentes relacionados con el producto y las funciones.

 

<!-- 

faq_features_functions.xml

 -->

**¿Cuál es mi identificador de organización y cómo puedo encontrarlo?**

El *`Organization ID`* es un identificador único que identifica a su organización en [!DNL Audience Manager] y [!DNL Adobe Experience Cloud]. Consiste en una cadena alfanumérica de 24 caracteres que distingue entre mayúsculas y minúsculas seguida de [!UICONTROL @AdobeOrg].

Por ejemplo, un *`Organization ID`* tiene esta apariencia: `1FD6776A524453CC0A490D44@AdobeOrg`.

El *`Organization ID`* lo utilizan la API [DIL](../dil/dil-overview.md) de Audience Manager, el [servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es) y otras soluciones de [!DNL Experience Cloud]. Los usuarios con permisos de administrador pueden encontrar el *`Organization ID`* en la [!DNL Adobe Admin Console]. Consulte las [preguntas frecuentes sobre Administración - Gestión de usuarios](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=es).

 

**¿Puedo crear rasgos o destinos de forma masiva?**

Sí. Consulte [Herramientas de administración masiva](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>Las herramientas [!UICONTROL Bulk Management Tools] *no son* compatibles con [!DNL Audience Manager]. Se suministran por conveniencia y por cortesía. Para cambios masivos, le recomendamos que trabaje con las [API de Audience Manager](../api/api.md).

 

**Al realizar una exportación masiva de ID a un destino, faltan algunos de los ID de cliente. ¿Por qué ocurre esto?**

AAM Cuando un ID de dispositivo ([UUID de UUID](../reference/ids-in-aam.md)) está vinculado a varios ID de CRM ([DPUUID](../reference/ids-in-aam.md)), solo se exporta la asignación más reciente. Por este motivo, es posible que vea un número de ID de dispositivo exportados inferior al esperado.

 

**¿Puede [!DNL Audience Manager] reducir la necesidad de etiquetas de terceros o píxeles y mejorar los tiempos de carga de las páginas?**

Si [!DNL Audience Manager] está integrado con su socio de datos de terceros, puede reemplazar sus píxeles y etiquetas con una llamada de ID de servidor a servidor a [!DNL Audience Manager]. En este caso, [!DNL Audience Manager] activaría una sola llamada de ID la primera vez que veamos un usuario y sincronizaría esa información con su socio de terceros. Esto elimina la necesidad de realizar llamadas de varios píxeles desde cada página. La reducción de las llamadas en píxeles puede mejorar los tiempos de carga de las páginas.

 

**Me he suscrito a una fuente de datos. ¿Dónde se almacenan esos datos?**

La fuente de datos y todos los rasgos de la fuente se muestran como subcarpetas y rasgos en [!DNL Audience Manager]. Vaya a **[!UICONTROL Audience Data > Traits]** y abra la [!UICONTROL 3rd-Party Data] carpeta para ver sus rasgos o crear segmentos y modelos con estos datos.

 

**¿Qué es [!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager utilizaba [!UICONTROL Tag Insertion Manager] (TIM) para crear y administrar [!UICONTROL data collection code (DIL)]. Esta función está obsoleta y primero se ha reemplazado por [!UICONTROL Dynamic Tag Manager (DTM)] y después por [!DNL Adobe Experience Platform Tags]. Para obtener más información, consulte [Etiquetas de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es).

 

**¿Cuáles son las diferencias entre los modelos algorítmicos y las recomendaciones de rasgos? ¿Cuándo utilizo unos u otros?**

**Modelos algorítmicos**

Los modelos algorítmicos no solo encuentran los rasgos más influyentes, sino que también puntúan a los usuarios según esos rasgos y asignan a cada usuario una puntuación individual. Seguidamente, puede crear rasgos algorítmicos para segmentar los usuarios. Con los controles de precisión y alcance del Generador de rasgos, puede especificar a qué usuarios quiere dirigirse de entre todos los que tienen los rasgos influyentes.

Los modelos algorítmicos le permiten seleccionar usuarios en diferentes niveles de precisión y probar en Audience Lab qué grupo de usuarios se convierte mejor. Consulte el caso de uso detallado en [Comparar modelos en Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

En Modelos algorítmicos, el modelo se ejecuta cada 8 días y actualiza los usuarios clasificados para rasgos algorítmicos.

**Recomendaciones de rasgos**

Las Recomendaciones de rasgos es una forma rápida de obtener perspectivas sobre otros rasgos parecidos a los utilizados en un segmento.

Debe usar Recomendaciones de rasgos cuando:

* Necesita perspectivas rápidas cuando crea un segmento.
* Utiliza los segmentos para campañas cortas o cuando quiere suprimir rápidamente la audiencia que convierte.
* Está intentando maximizar el alcance.

 

**¿Hay alguna diferencia entre los segmentos de Adobe Analytics y Audience Manager?**

Sí. Consulte la [Explicación de los segmentos en Analytics y Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html?lang=es) para ver una descripción detallada de las diferencias.
