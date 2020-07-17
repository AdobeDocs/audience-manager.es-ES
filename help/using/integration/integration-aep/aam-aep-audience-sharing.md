---
description: Este artículo describe cómo se comparten las audiencias entre Audience Manager y Adobes Experience Platform.
seo-description: Este artículo describe cómo se comparten las audiencias entre Audience Manager y Adobes Experience Platform.
seo-title: Uso compartido de Audiencias entre Audience Manager y Adobe Experience Platform
solution: Audience Manager
title: Uso compartido de Audiencias entre Audience Manager y Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
feature: Integration with Platform
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 4%

---


# Uso compartido de Audiencias entre Audience Manager y Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> Póngase en contacto con su representante de ventas de Adobe para desbloquear el acceso a esta funcionalidad.

## Información general {#overview}

La funcionalidad de uso compartido de audiencias entre Audience Manager y Adobes Experience Platform le permite compartir sus características de Audience Manager y segmentos en Adobe Experience Platform y viceversa. Necesita el conector [del](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) Audience Manager para habilitar el uso compartido de audiencias entre el Audience Manager y el Adobe Experience Platform.

Puede usar características y segmentos de Audience Manager en Experience Platform para agregar datos de Audience Manager a sus perfiles de clientes y para beneficiarse del servicio [de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)segmentación de Experience Platform.

En Audience Manager, puede utilizar segmentos de Experience Platform para casos de uso de Gestión de datos de Platform, como:
* Añada datos [de](/help/using/overview/data-types-collected.md#third-party-data) terceros a sus segmentos;
* [Modelado algorítmico](/help/using/features/algorithmic-models/understanding-models.md);
* Active los segmentos en destinos que aún no se admiten en el catálogo [de](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)destinos de Experience Platform.

Además, los segmentos del Experience Platform se comparten con otras soluciones de Experience Cloud, a través de los servicios [principales](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

<br> 

Consulte la tabla siguiente para obtener una descripción general de los casos de uso de uso compartido de audiencias:

| **Caso de uso** | **Adobe Experience Platform** | **Audience Manager** | **Servicios principales** |
---------|----------|---------|---------
| **Uso compartido de Audiencias** | <ul><li>Enriquecer los perfiles de los clientes con datos de Audience Manager</li><li>Utilizar datos de Audience Manager en la segmentación de Experience Platform</li></ul> | <ul><li>Añadir datos de terceros en segmentos</li><li>Modelado algorítmico</li><li>Activación a destinos adicionales</li></ul> | Utilice segmentos de Experience Platform en otras soluciones de Experience Cloud, como Adobe Target o Analytics. |

<br> 

## Segmentos y características del Audience Manager en Adobe Experience Platform {#aam-segments-traits-in-aep}

Las características y los segmentos del Audience Manager aparecen en el Experience Platform como **Audiencias** en el flujo de trabajo del segmento. Para obtener más información sobre los segmentos y las características del Audience Manager en Experience Platform, consulte:

* [Descripción general del servicio de segmentación](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Guía del usuario del Generador de segmentos de Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Conector del Audience Manager](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Segmentos de Adobe Experience Platform en Audience Manager {#aep-segments-in-aam}

Los segmentos que se crean en el Experience Platform aparecen en la interfaz del Audience Manager como características y segmentos, con las siguientes reglas de composición:
* Característica: La regla de características es la ID del segmento de Experience Platform.
* Segmento: El segmento consiste en la característica descrita anteriormente.

### Rasgos {#aep-segments-as-aam-traits}

Audience Manager crea automáticamente una carpeta de características denominada Características del **Experience Platform** en el almacenamiento de características.

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

Audience Manager crea automáticamente una carpeta de segmentos denominada Segmentos **Experience Platform** en el almacenamiento de segmentos.

![Captura de pantalla del panel](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Para ver un ejemplo de un segmento creado automáticamente a partir de un segmento de Experience Platform, consulte la captura de pantalla siguiente:

![Captura de pantalla del segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Número de artículo | Nombre | Descripción |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | El código de integración corresponde al ID del segmento en el Experience Platform. |
| 2 | [!UICONTROL Data Source] | Creado automáticamente. Todas las características y segmentos que se crean automáticamente a partir de segmentos de Experience Platform se almacenan en el origen de datos **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica que los segmentos creados automáticamente siguen la configuración de directiva de combinación establecida en Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | El segmento consta de la característica descrita en la sección [](#aep-segments-as-aam-traits)Características. |

## Compatibilidad con el control de exportación de datos de Audience Manager en Experience Platform {#aam-data-export-control-in-aep}

A fin de hacer cumplir la normativa de uso de datos en el Experience Platform, todos los conjuntos de datos y campos aplicables deben recibir las etiquetas [de uso de](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html)datos correspondientes. Además, las directivas [de uso de](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) datos deben habilitarse para acciones de marketing específicas en relación con dichas etiquetas, como se describe en el marco [de aplicación y etiquetado de uso de](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework)datos (DULE).

En el proceso de uso compartido de audiencias entre Audience Manager y Experience Platform, cualquier control de exportación de datos que se haya aplicado a segmentos de Audience Manager se traduce a etiquetas y acciones de marketing equivalentes reconocidas por el Gobierno de datos de Experience Platform, y viceversa.

>[!NOTE] Para obtener información más general sobre los controles de exportación de datos, consulte la documentación [de los controles de exportación de](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)datos.
Este documento proporciona una referencia sobre cómo los controles de exportación de datos de Audience Manager específicos se asignan a las etiquetas de uso de datos y a las acciones de marketing de Platform.

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

## Comprender las diferencias de población de segmentos entre Audience Manager y Experience Platform

Los números de población de segmentos pueden variar entre los segmentos de Audience Manager y de Experience Platform. Mientras que los números de segmento para audiencias similares o idénticas deben ser cercanos, las diferencias en las poblaciones pueden deberse a:

* Tiempo de ejecución de los trabajos de segmentación. Audience Manager ejecuta un trabajo de segmentación que actualiza los números de la interfaz una vez al día. Este trabajo raramente se alinea con los trabajos de segmentación en Experience Platform.
* [Las reglas](/help/using/features/profile-merge-rules/merge-rules-overview.md) de combinación de Perfiles en las directivas [de Audience Manager y](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) combinación en el Experience Platform funcionan de forma diferente, y el gráfico de identidad utilizado para cada una varía. Debido a esto, se esperan algunas diferencias entre las poblaciones de segmentos.

>[!MORELIKETHIS]
>
>* [Descripción general del servicio de segmentación](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Guía del usuario del Generador de segmentos de Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Conector del Audience Manager](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)