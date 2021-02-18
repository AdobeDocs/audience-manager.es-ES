---
description: Este artículo describe cómo se comparten las audiencias entre Audience Manager y Adobe Experience Platform.
seo-description: Este artículo describe cómo se comparten las audiencias entre Audience Manager y Adobe Experience Platform.
seo-title: Uso compartido de Audiencias entre Audience Manager y Adobe Experience Platform
solution: Audience Manager
title: Uso compartido de Audiencias entre Audience Manager y Adobe Experience Platform
keywords: Uso compartido de audiencias AEP, segmentos AEP, segmentos de plataforma, uso compartido de segmentos, uso compartido de audiencias, uso compartido de segmentos
feature: Integration with Platform
translation-type: tm+mt
source-git-commit: 62938e95fa9eed3e747fa4dabf8695c5dbefde17
workflow-type: tm+mt
source-wordcount: '1504'
ht-degree: 2%

---


# Uso compartido de segmentos de Experience Platform con Audience Manager y otras soluciones de Experience Cloud {#aam-aep-audience-sharing}

>[!NOTE]
>
> Póngase en contacto con el representante de ventas de Adobe para desbloquear el acceso a esta funcionalidad.

## Información general {#overview}

La funcionalidad de uso compartido de audiencias entre Audience Manager y Adobe Experience Platform le permite compartir sus características y segmentos de Audience Manager con Adobe Experience Platform y viceversa. Necesita el [[!DNL Audience Manager Connector]](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) para habilitar el uso compartido de audiencias entre Audience Manager y Adobe Experience Platform.

Puede usar características y segmentos de Audience Manager en Experience Platform para agregar datos de Audience Manager a sus perfiles de clientes y para beneficiarse del servicio de segmentación [Experience Platform](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md).

En Audience Manager, puede utilizar segmentos de Experience Platform para casos de uso de la Plataforma de Gestión de datos, como:
* Añada [datos de terceros](/help/using/overview/data-types-collected.md#third-party-data) a sus segmentos;
* [Modelado algorítmico](/help/using/features/algorithmic-models/understanding-models.md);
* Active los segmentos en destinos que aún no se admiten en el catálogo de destinos [del Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

Además, los segmentos de Experience Platform se comparten con otras soluciones de Experience Cloud mediante [servicios principales](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * Necesita una licencia de Audience Manager para habilitar los casos de uso de la Plataforma de Gestión de datos mencionados anteriormente.
> * *no necesita* una licencia de Audience Manager para compartir segmentos de Experience Platform con Adobe Advertising Cloud, Adobe Target, Marketing y otras soluciones de Experience Cloud mediante la integración de los servicios principales.


<br> 

Consulte la tabla siguiente para obtener una descripción general de los casos de uso de uso compartido de audiencias:

| **Caso de uso** | **Adobe Experience Platform** | **Audience Manager** | **Servicios principales** |
---------|----------|---------|---------
| **Uso compartido de audiencias** | <ul><li>Enriquecer los perfiles de los clientes con datos de Audience Manager</li><li>Utilizar datos de Audience Manager en la segmentación de Experience Platform</li></ul> | <ul><li>Añadir datos de terceros en segmentos</li><li>Modelado algorítmico</li><li>Activación a destinos adicionales</li></ul> | Utilice segmentos de Experience Platform en otras soluciones de Experience Cloud, como Adobe Target, Advertising Cloud o Marketing. |

<br> 

## Segmentos y características de Audience Manager en Adobe Experience Platform {#aam-segments-traits-in-aep}

Las características y los segmentos del Audience Manager aparecen en el Experience Platform como **Audiencias** en el flujo de trabajo del segmento. Para obtener más información sobre los segmentos y las características del Audience Manager en Experience Platform, consulte:

* [Descripción general del servicio de segmentación](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Guía del usuario del Generador de segmentos de Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Conector del Audience Manager](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Segmentos de Adobe Experience Platform en Audience Manager {#aep-segments-in-aam}

Los segmentos que se crean en el Experience Platform aparecen en la interfaz del Audience Manager como señales, características y segmentos, con las siguientes reglas de composición:

* Señal: Para cada segmento de Experience Platform, debe ver las señales en el formato `segID = segment ID`.
* Característica: La regla de características es la ID del segmento de Experience Platform.
* Segmento: El segmento consiste en la característica descrita anteriormente.

### Señales {#aep-segments-as-aam-signals}

Seleccione **[!UICONTROL Audience Data > Signals > General Online Data]** y busque por `SegId` para encontrar las señales procedentes del Experience Platform. Puede utilizar esta pantalla con fines de depuración para comprobar si la integración entre Experience Platform y Audience Manager se ha configurado correctamente.

![Ver las señales de Experience Platform en el Audience Manager en el panel de señales](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Rasgos {#aep-segments-as-aam-traits}

Audience Manager crea automáticamente una carpeta de características denominada **Características del Experience Platform** en el almacenamiento de características.

![Características del panel de Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Puede utilizar características creadas automáticamente en segmentos junto con otras características. Por ejemplo, puede combinar características creadas a partir de segmentos de Experience Platform con características de terceros adquiridas a través del [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Para ver un ejemplo de una característica creada automáticamente a partir de un segmento de Experience Platform, consulte la captura de pantalla siguiente:

![Característica del Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Número de artículo | Nombre | Descripción |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | Las características creadas a partir de segmentos de Experience Platform se crean como características integradas en Audience Manager. |
| 2 | [!UICONTROL Data Source] | Creado automáticamente. Todas las características y segmentos que se crean automáticamente a partir de segmentos de Experience Platform se almacenan en el origen de datos **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | El código de integración corresponde al ID del segmento en el Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | La expresión de rasgo es `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Segmento creado automáticamente que utiliza esta característica como composición. |

<br> 

### Segmentos {#aep-segments-as-aam-segments}

Audience Manager crea automáticamente una carpeta de segmentos denominada **Segmentos de Experience Platform** en el almacenamiento de segmentos.

![Captura de pantalla del panel](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Para ver un ejemplo de un segmento creado automáticamente a partir de un segmento de Experience Platform, consulte la captura de pantalla siguiente:

![Captura de pantalla del segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Número de artículo | Nombre | Descripción |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | El código de integración corresponde al ID del segmento en el Experience Platform. |
| 2 | [!UICONTROL Data Source] | Creado automáticamente. Todas las características y segmentos que se crean automáticamente a partir de segmentos de Experience Platform se almacenan en el origen de datos **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 1 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica que los segmentos creados automáticamente siguen la configuración de directiva de combinación establecida en Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | El segmento consiste en la característica descrita en la sección [Características](#aep-segments-as-aam-traits). |

## Compatibilidad con el control de exportación de datos de Audience Manager en Experience Platform {#aam-data-export-control-in-aep}

A fin de hacer cumplir la normativa de uso de datos en el Experience Platform, todos los campos y conjuntos de datos aplicables deben recibir las [etiquetas de uso de datos correspondientes](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html). Además, [las políticas de uso de datos](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) deben habilitarse para acciones de mercadotecnia específicas en relación con esas etiquetas, como se describe en el marco [de cumplimiento y etiquetado de uso de datos (DULE)](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework).

En el proceso de uso compartido de audiencias entre Audience Manager y Experience Platform, cualquier control de exportación de datos que se haya aplicado a segmentos de Audience Manager se traduce a etiquetas y acciones de marketing equivalentes reconocidas por el Gobierno de datos de Experience Platform, y viceversa.

>[!NOTE]
>
>Para obtener información más general sobre los controles de exportación de datos, consulte la [documentación de controles de exportación de datos](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html).
>
>Este documento proporciona una referencia sobre cómo los controles de exportación de datos de Audience Manager específicos se asignan a las etiquetas de uso de datos y a las acciones de marketing de Platform.

### Controles de exportación de datos a etiquetas de uso de datos

La siguiente tabla describe cómo los controles de exportación de datos específicos se asignan a etiquetas de uso de datos reconocidas:

| Control de exportación de datos | Etiqueta de uso de datos |
| --- | --- |
| No se puede utilizar con información de identificación personal | C3: Los datos no pueden combinarse ni utilizarse de otro modo con información directamente identificable |
| No se puede usar para la segmentación de anuncios externos | C5: Los datos no se pueden usar para dirigir contenido o anuncios en varios sitios basados en intereses |
| No se puede usar para el objetivo de publicidad en el sitio | C6: No se pueden usar datos para la segmentación de anuncios en el sitio |
| No se puede utilizar para la personalización en el sitio | C7: No se pueden usar datos para dirigir el contenido en el sitio |

### Controles de exportación de datos a acciones de marketing

La siguiente tabla describe cómo las etiquetas de exportación de datos específicas se asignan a las acciones de marketing reconocidas:

| Etiqueta de exportación de datos | Acción de mercadotecnia |
| --- | --- |
| Este destino puede permitir una combinación con información de identificación personal (PII) | Combinar con PII |
| Este destino se puede usar para la segmentación de publicidad fuera del sitio | Objetivos entre sitios |
| Este destino se puede usar para el objetivo de publicidad en el sitio | Publicidad en el sitio |
| Este destino se puede utilizar para la personalización de publicidad en el sitio | Personalización en el sitio |

## Comprender las diferencias de población de segmentos entre Audience Manager y Experience Platform {#aep-aam-segment-population-differences}

Los números de población de segmentos pueden variar entre los segmentos de Audience Manager y de Experience Platform. Aunque los números de segmento para audiencias similares o idénticas deben ser estrechos, las diferencias en la población pueden deberse a los factores enumerados a continuación.

### Evaluación de segmentos en el Experience Platform

Audience Manager actualiza los números de sistema de informes en la interfaz una vez al día.   El tiempo de esta actualización raramente se alinea con el tiempo de la evaluación del segmento en el Experience Platform.

### Diferencias entre reglas de combinación de Perfiles y políticas de combinación

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) en el Audience Manager y  [[!UICONTROL Merge Policies]](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) en el Experience Platform funcionan de forma diferente, y el gráfico de identidad utilizado para cada uno varía. Debido a esto, se esperan algunas diferencias entre las poblaciones de segmentos.

### Composición de segmentos en el Experience Platform

La integración entre Adobe Experience Platform y Audience Manager comparte una serie de [Áreas de nombres de identidad estándar](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html#identity-types) para todos los clientes: ECID, IDFA, GAID, direcciones de correo electrónico con hash (EMAIL_LC_SHA256), ID de AdCloud. Si los segmentos del Experience Platform utilizan cualquiera de estos elementos como identidad principal para los perfiles cualificados, los perfiles se cuentan en los rasgos y segmentos del Audience Manager.

Además, el Audience Manager puede registrar las realizaciones entrantes para cualquier Área de nombres de identidad personalizada que utilice en los segmentos de Experience Platform si:
* la identidad se marca como principal *y*
* ya tiene una fuente de datos entre dispositivos correspondiente en Audience Manager.

>[!NOTE]
>
> Las audiencias en Experience Platform con identidades marcadas como clave de los correos electrónicos sin procesar nunca aparecen en el Audience Manager.

Por ejemplo, si tuviera un segmento de Experience Platform &quot;Todos mis clientes&quot; y los perfiles cualificados fueran ID de CRM, ID de ECID, IDFA, direcciones de correo electrónico sin procesar y con hash, el segmento correspondiente en Audience Manager solo incluiría perfiles de ID de CRM, ECID, IDFA y direcciones de correo electrónico con hash. La población de segmentos en Audience Manager sería menor que la del Experience Platform.

![Compartir segmentos de Experience Platform a Audience Manager: composición de segmentos](/help/using/integration/integration-aep/assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Descripción general del servicio de segmentación](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Guía del usuario del Generador de segmentos de Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Conector del Audience Manager](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)