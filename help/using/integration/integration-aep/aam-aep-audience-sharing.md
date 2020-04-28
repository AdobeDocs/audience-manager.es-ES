---
description: Este artículo describe cómo se comparten las audiencias entre el Administrador de Audiencias y Adobe Experience Platform.
seo-description: Este artículo describe cómo se comparten las audiencias entre el Administrador de Audiencias y Adobe Experience Platform.
seo-title: Uso compartido de Audiencias entre Audiencia Manager y Adobe Experience Platform
solution: Audience Manager
title: Uso compartido de Audiencias entre Audiencia Manager y Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
translation-type: tm+mt
source-git-commit: 100767fe1d8baaa49fb6e83fdae23144ce9748a7

---


# Uso compartido de Audiencias entre Audiencia Manager y Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> Póngase en contacto con su representante de ventas de Adobe para desbloquear el acceso a esta funcionalidad.

## Información general {#overview}

La funcionalidad de uso compartido de audiencias entre Audiencia Manager y Adobe Experience Platform le permite compartir sus características y segmentos de Audiencia Manager con Adobe Experience Platform y viceversa. Necesita el conector [del administrador de](https://docs.adobe.com/content/help/en/experience-platform/source-connectors/adobe-applications/audience-manager.html) Audiencias para habilitar el uso compartido de audiencias entre el administrador de Audiencias y la plataforma de Adobe Experience.

Puede utilizar las características y los segmentos de Audiencia Manager en la plataforma de experiencia para agregar datos del Administrador de Audiencias a sus perfiles de clientes y beneficiarse del servicio [de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)segmentación de la plataforma de experiencia.

En el Administrador de Audiencias, puede utilizar los segmentos de la plataforma de experiencia para casos de uso de la plataforma de Gestión de datos, como:
* Añada datos [de](/help/using/overview/data-types-collected.md#third-party-data) terceros a sus segmentos;
* [Modelado algorítmico](/help/using/features/algorithmic-models/understanding-models.md);
* Active los segmentos en destinos que aún no se admiten en el catálogo [de](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)destinos de la plataforma de experiencia.

Además, los segmentos de la plataforma de experiencia se comparten con otras soluciones de Experience Cloud, a través de los servicios [principales](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

<br> 

Consulte la tabla siguiente para obtener una descripción general de los casos de uso de uso compartido de audiencias:

| **Caso de uso** | **Adobe Experience Platform** | **Audience Manager** | **Servicios principales** |
---------|----------|---------|---------
| **Uso compartido de Audiencias** | <ul><li>Enriquecer los perfiles de los clientes con los datos de Audiencia Manager</li><li>Utilizar datos del Administrador de Audiencias en la segmentación de la plataforma de experiencia</li></ul> | <ul><li>Añadir datos de terceros en segmentos</li><li>Modelado algorítmico</li><li>Activación a destinos adicionales</li></ul> | Utilice los segmentos de la plataforma de experiencia en otras soluciones de Experience Cloud, como Adobe Destinatario o Analytics. |

<br> 

## Segmentos y características de Audiencia Manager en Adobe Experience Platform {#aam-segments-traits-in-aep}

Las características y los segmentos del Administrador de Audiencias aparecen en la plataforma de experiencia como **Audiencias** en el flujo de trabajo de segmentos. Para obtener más información sobre los segmentos y las características del Administrador de Audiencias en la plataforma de experiencias, consulte:

* [Descripción general del servicio de segmentación](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Guía del usuario del Generador de segmentos de la plataforma de experiencia](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Conector del Administrador de Audiencias](https://docs.adobe.com/content/help/en/experience-platform/source-connectors/adobe-applications/audience-manager.html)

<br> 

## Segmentos de Adobe Experience Platform en el Administrador de Audiencias {#aep-segments-in-aam}

Los segmentos que cree en la plataforma de experiencia aparecerán en la interfaz del Administrador de Audiencias como características y segmentos, con las siguientes reglas de composición:
* Característica: La regla de características es el ID del segmento de la plataforma de experiencia.
* Segmento: El segmento consiste en la característica descrita anteriormente.

### Características {#aep-segments-as-aam-traits}

El Administrador de Audiencias crea automáticamente una carpeta de características denominada Características **de la plataforma de** experiencias en el almacenamiento de características.

![Características del panel de la plataforma de experiencia](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Puede utilizar características creadas automáticamente en segmentos junto con otras características. Por ejemplo, puede combinar características creadas a partir de segmentos de la plataforma de experiencia con características de terceros adquiridas a través del Mercado de [Audiencia](/help/using/features/audience-marketplace/audience-marketplace.md).

Para ver un ejemplo de una característica creada automáticamente a partir de un segmento de la plataforma de experiencia, consulte la captura de pantalla siguiente:

![Característica de la plataforma de experiencia](/help/using/integration/integration-aep/assets/aep-trait.png)


| Número de artículo | Nombre | Descripción |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | Las características creadas a partir de segmentos de la plataforma de experiencia se crean como características integradas en el Administrador de Audiencias. |
| 2 | [!UICONTROL Data Source] | Creado automáticamente. Todas las características y segmentos que se crean automáticamente a partir de segmentos de la plataforma de experiencia se almacenan en el origen de datos **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | El código de integración corresponde al ID del segmento en la plataforma de experiencia. |
| 4 | [!UICONTROL Trait Expression] | La expresión de rasgo es `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Segmento creado automáticamente que utiliza esta característica como composición. |

<br> 

### Segmentos {#aep-segments-as-aam-segments}

El Administrador de Audiencias crea automáticamente una carpeta de segmentos denominada Segmentos **de la plataforma de** experiencias en el almacenamiento de segmentos.

![Captura de pantalla del panel](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Para ver un ejemplo de un segmento creado automáticamente a partir de un segmento de la plataforma de experiencia, consulte la captura de pantalla siguiente:

![Captura de pantalla del segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Número de artículo | Nombre | Descripción |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | El código de integración corresponde al ID del segmento en la plataforma de experiencia. |
| 2 | [!UICONTROL Data Source] | Creado automáticamente. Todas las características y segmentos que se crean automáticamente a partir de segmentos de la plataforma de experiencia se almacenan en el origen de datos **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica que los segmentos creados automáticamente siguen la directiva de combinación establecida en la plataforma de experiencia. |
| 4 | [!UICONTROL Segment Rule] | El segmento consta de la característica descrita en la sección [](#aep-segments-as-aam-traits)Características. |

## Comprender las diferencias de población de segmentos entre el Administrador de Audiencias y la Plataforma de experiencia

Los números de población de segmentos pueden variar entre los segmentos del Administrador de Audiencias y de la Plataforma de experiencia. Aunque los números de segmento siempre estarán razonablemente cerca, las pequeñas diferencias en las poblaciones pueden deberse a:

* Tiempo de ejecución de los trabajos de segmentación. El Administrador de Audiencias ejecuta un trabajo de segmentación que actualiza los números de la interfaz una vez al día. Este trabajo raramente se alinea con los trabajos de segmentación en la plataforma de experiencia.
* [Las reglas](/help/using/features/profile-merge-rules/merge-rules-overview.md) de combinación de Perfiles del Administrador de Audiencias y las políticas [de](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) combinación de la plataforma de experiencia funcionan de forma distinta, y el gráfico de identidad que se utiliza para cada una varía. Debido a esto, se esperan algunas diferencias entre las poblaciones de segmentos.


>[!MORELIKETHIS]
>
>* [Descripción general del servicio de segmentación](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Guía del usuario del Generador de segmentos de la plataforma de experiencia](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Conector del Administrador de Audiencias](https://docs.adobe.com/content/help/en/experience-platform/source-connectors/adobe-applications/audience-manager.html)