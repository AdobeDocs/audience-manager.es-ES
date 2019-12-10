---
description: Este artículo describe cómo se comparten las audiencias entre Audience Manager y Adobe Experience Platform.
seo-description: Este artículo describe cómo se comparten las audiencias entre Audience Manager y Adobe Experience Platform.
seo-title: Uso compartido de público entre Audience Manager y Adobe Experience Platform
solution: Audience Manager
title: Uso compartido de público entre Audience Manager y Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing
translation-type: tm+mt
source-git-commit: e27ce2f607cadd7318a171359a5ae4daa071c486

---


# Uso compartido de público entre Audience Manager y Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> La funcionalidad descrita en esta página está disponible para los clientes de Audience Manager y Adobe Experience Platform.
>
> Póngase en contacto con su representante de ventas de Adobe para desbloquear el acceso a esta funcionalidad.

## Información general {#overview}

La funcionalidad de uso compartido de público entre Audience Manager y Adobe Experience Platform le permite compartir sus características y segmentos de Audience Manager con Adobe Experience Platform y viceversa.

Puede utilizar características y segmentos de Audience Manager en la plataforma de experiencia para agregar datos de Audience Manager a sus perfiles de cliente y beneficiarse del servicio [de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)segmentación de la plataforma de experiencia.

En Audience Manager, puede utilizar los segmentos de la plataforma de experiencia para casos de uso de la plataforma de administración de datos, como:
* Adición de datos [de](/help/using/overview/data-types-collected.md#third-party-data) terceros a los segmentos;
* [Modelado algorítmico](/help/using/features/algorithmic-models/understanding-models.md);
* Activación de segmentos en destinos no admitidos actualmente en la plataforma de experiencias.

Además, los segmentos de la plataforma de experiencia se comparten con otras soluciones de Experience Cloud, a través de los servicios [principales](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

<br> 

Consulte la tabla siguiente para obtener una descripción general de los casos de uso de uso de uso compartido de audiencia:

| **Caso de uso** | **Adobe Experience Platform** | **Audience Manager** | **Servicios principales** |
---------|----------|---------|---------
| **Uso compartido de audiencias** | <ul><li>Enriquecer perfiles de cliente con datos de Audience Manager</li><li>Uso de datos de Audience Manager en la segmentación de la plataforma de experiencia</li></ul> | <ul><li>Agregar datos de terceros a segmentos</li><li>Modelado algorítmico</li><li>Activación en destinos adicionales</li></ul> | Utilice segmentos de la plataforma de experiencia en otras soluciones de Experience Cloud, como Adobe Target o Analytics. |

<br> 

## Segmentos y características de Audience Manager en Adobe Experience Platform {#aam-segments-traits-in-aep}

Las características y los segmentos de Audience Manager aparecen en la plataforma de experiencia como **Audiencias** en el flujo de trabajo de segmentos. Para obtener más información sobre los segmentos y las características de Audience Manager en la plataforma de experiencia, consulte:

* [Descripción general del servicio de segmentación](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)
* [Guía del usuario del Generador de segmentos de la plataforma de experiencia](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segment-builder-guide.md)

<br> 

## Segmentos de Adobe Experience Platform en Audience Manager {#aep-segments-in-aam}

Los segmentos que cree en la plataforma de experiencia aparecerán en la interfaz de Audience Manager como características y segmentos, con las siguientes reglas de composición:
* Característica: La regla de características es el ID del segmento de la plataforma de experiencia.
* Segmento: El segmento consiste en la característica descrita anteriormente.

### Características {#aep-segments-as-aam-traits}

Audience Manager crea automáticamente en el almacenamiento de características una carpeta de características denominada Características **de la plataforma de** experiencia.

![Características del tablero de la plataforma de experiencia](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Puede utilizar características creadas automáticamente en segmentos junto con otras características. Por ejemplo, puede combinar características creadas a partir de segmentos de la plataforma de experiencia con características de terceros adquiridas a través de [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Para ver un ejemplo de una característica creada automáticamente a partir de un segmento de la plataforma de experiencia, consulte la captura de pantalla siguiente:

![Característica de la plataforma de experiencia](/help/using/integration/integration-aep/assets/aep-trait.png)


| Número de artículo | Nombre | Descripción |
---------|----------|---------
| 1 | Tipo de característica | Las características creadas a partir de segmentos de la plataforma de experiencia se crean como características integradas en Audience Manager. |
| 2 | Fuente de datos | Creado automáticamente. Todas las características y los segmentos que se crean automáticamente a partir de segmentos de la plataforma de experiencia se almacenan en el origen de datos Uso compartido de la audiencia de la plataforma de **Adobe Experience**. |
| 3 | Código de integración | El código de integración corresponde al ID del segmento en la plataforma de experiencia. |
| 4 | Expresión de características | La expresión de rasgo es `segID = segment ID in Experience Platform`. |
| 5 | Segmentos con esta característica | Segmento creado automáticamente que utiliza esta característica como composición. |

<br> 

### Segmentos {#aep-segments-as-aam-segments}

Audience Manager crea automáticamente una carpeta de segmentos denominada Segmentos **de la plataforma de** experiencia en el almacenamiento de segmentos.

![Captura de pantalla del tablero](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Para ver un ejemplo de un segmento creado automáticamente a partir de un segmento de la plataforma de experiencia, consulte la captura de pantalla siguiente:

![Captura de pantalla del segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Número de artículo | Nombre | Descripción |
---------|----------|---------
| 1 | Código de integración | El código de integración corresponde al ID del segmento en la plataforma de experiencia. |
| 2 | Fuente de datos | Creado automáticamente. Todas las características y los segmentos que se crean automáticamente a partir de segmentos de la plataforma de experiencia se almacenan en el origen de datos Uso compartido de la audiencia de la plataforma de **Adobe Experience**. |
| 3 | Regla de combinación de perfiles | **La directiva** de combinación externa indica que los segmentos creados automáticamente siguen la directiva de combinación establecida en la plataforma de experiencia. |
| 4 | Regla de segmento | El segmento consta de la característica descrita en la sección [](#aep-segments-as-aam-traits)Características. |