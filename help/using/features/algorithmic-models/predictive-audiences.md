---
description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Overview
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1485'
ht-degree: 7%

---

# [!UICONTROL Predictive Audiences] Información general {#predictive-audiences}

[!UICONTROL Predictive Audiences] le ayuda a clasificar una audiencia desconocida en personalidades distintas, en tiempo real, mediante técnicas avanzadas de ciencia de datos.

>[!IMPORTANT]
>Este artículo contiene documentación del producto que le guiará a través de la configuración y el uso de esta función. Nada de lo que contiene aquí es asesoramiento legal. Por favor, consulte a su propio asesor legal para obtener orientación legal.

En un contexto de marketing, una personalidad es un segmento de audiencia definido por visitantes, usuarios o compradores potenciales, que comparten un conjunto específico de rasgos, como su demografía, hábitos de navegación, historial de compras, etc.

Los modelos de [!UICONTROL Predictive Audiences] llevan este concepto un paso más allá, ya que permiten utilizar las capacidades de aprendizaje automático de Audience Manager para clasificar audiencias desconocidas en personalidades distintas. Audience Manager le ayuda a conseguirlo calculando la propensión de la audiencia de origen desconocida para un conjunto de audiencias de origen conocidas.

Al crear un [!UICONTROL Predictive Audiences] En este modelo, el primer paso es elegir los rasgos o segmentos de línea de base por los que desea que se clasifique la audiencia de destino. Estos rasgos o segmentos definirán sus personalidades.

Durante la fase de evaluación, el modelo crea un nuevo [!UICONTROL Predictive Audiences] segmento para cada rasgo o segmento definido como línea de base. La próxima vez que el Audience Manager vea un visitante de su audiencia de destinatario que no esté clasificado para una persona (que no cumpla ninguno de sus rasgos o segmentos de base), la variable [!UICONTROL Predictive Audiences] Este modelo determinará a cuál de los segmentos predictivos debe pertenecer el visitante y agregará al visitante a ese segmento.

Puede identificar los segmentos predictivos creados por el modelo en la variable [!UICONTROL Segments] página. Cada [!UICONTROL Predictive Audiences] El modelo tiene su propia carpeta en [!UICONTROL Predictive Audiences] y puede ver los segmentos de cada modelo haciendo clic en la carpeta del modelo.

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## Casos de uso {#use-cases}

Para ayudarle a comprender mejor cómo y cuándo puede utilizar [!UICONTROL Predictive Audiences]Sin embargo, estos son algunos casos de uso que los clientes de Audience Manager pueden solucionar mediante esta función.

### #1 de casos de uso

Como especialista en marketing de una empresa de comercio electrónico, quiero clasificar a todos mis visitantes web y móviles en varias categorías de afinidad de marca para poder personalizar su experiencia de usuario.

### #2 de casos de uso

Como especialista en marketing de una empresa de medios de comunicación, quiero clasificar a mis visitantes web y móviles no autenticados por géneros favoritos, de modo que pueda sugerirles contenido personalizado en todos los canales.

### #3 de casos de uso

Como anunciante de una compañía aérea, quiero asegurarme de clasificar mi audiencia en función de su interés en destinos de viaje, para poder anunciarla en tiempo real, en un corto periodo de resegmentación.

### #4 de casos de uso

Como anunciante, quiero clasificar mi audiencia de origen en tiempo real, de modo que pueda reaccionar rápidamente a las noticias de tendencia.

### #5 de casos de uso

Como especialista en marketing, quiero predecir en qué fase del recorrido de clientes se encuentran los visitantes de mi sitio web, como la detección, la participación, la compra o la retención, para poder dirigirlos en consecuencia.

### #6 de casos de uso

Como empresa multimedia, quiero categorizar mi audiencia para poder vender mi espacio publicitario a precios premium, mientras ofrezco a mis visitantes anuncios relevantes.

## Cómo [!UICONTROL Predictive Audiences] Los modelos funcionan {#how-predictive-audiences-models-work}

Al crear un [!UICONTROL Predictive Audiences] Modelo, siga tres pasos:

1. En primer lugar, debe seleccionar un mínimo de dos rasgos o dos segmentos que definirán las personalidades.
1. A continuación, elija un rasgo o segmento que defina la audiencia de destino que desee clasificar.
1. Finalmente, elige un nombre para el modelo, una fuente de datos que almacenará los segmentos predictivos y una [!UICONTROL Profile Merge Rule] para el modelo.

### Criterios de selección para personalidades {#selection-personas}

Puede elegir cualquiera de sus rasgos de origen o segmentos para definir sus personalidades. Sin embargo, para obtener resultados óptimos, aquí tiene un conjunto de prácticas recomendadas:

* Elija sus rasgos o segmentos de personalidad para que cada personalidad tenga unos cientos como mínimo [ID de dispositivo](../../reference/ids-in-aam.md).
* Si los rasgos se basan en [ID entre dispositivos](../../reference/ids-in-aam.md), puede envolverlos en segmentos con [Reglas de combinación de perfiles](../profile-merge-rules/merge-rules-overview.md) que utilizan [ID de dispositivo](../../reference/ids-in-aam.md), como [!UICONTROL Device Graph]. Esto garantizará que haya suficientes [ID de dispositivo](../../reference/ids-in-aam.md) que el algoritmo pueda aprovechar.
* Recomendamos elegir rasgos o segmentos simples para sus personalidades, que consten de 1 a 3 rasgos.
* Elija rasgos de línea de base o segmentos que tengan una superposición mínima.
* Asegúrese de capturar rasgos granulares en las propiedades digitales.

### Criterios de selección para la audiencia de destino {#selection-audience}

Según el caso de uso, tanto si desea clasificar usuarios en tiempo real, por lotes o ambos, elija una audiencia objetivo ([!UICONTROL trait] o [!UICONTROL segment]) que tenga una población significativa en tiempo real o total. De forma similar a la selección de personas, recomendamos que su audiencia de destino [!UICONTROL trait] o [!UICONTROL segment] tiene usuarios con perfiles enriquecidos (conjuntos enriquecidos de [!UICONTROL traits]).

Al seleccionar la audiencia de destino, analice el caso de uso y decida qué tipos de ID desea clasificar: [!UICONTROL device IDs] o [!UICONTROL cross-device IDs]. El [!UICONTROL Profile Merge Rule] que seleccione al crear el modelo, define los datos que se utilizarán para colocar a cada usuario en el predictivo [!UICONTROL segments].

Como práctica recomendada, le recomendamos que elija una [!UICONTROL Profile Merge Rule] que tenga la misma configuración que la audiencia de destino [!UICONTROL Profile Merge Rule]o uno que incluya el tipo de perfil (perfil de dispositivo o perfil autenticado) de la audiencia de destino.

### [!UICONTROL Predictive Audiences] Fase de formación del modelo {#model-training}

Antes de que el algoritmo pueda clasificar la audiencia de origen en las personas adecuadas, debe formarse a sí misma en sus datos.

Para cada personalidad que defina, el algoritmo analiza su audiencia respectiva y evalúa cualquier actividad de rasgos en tiempo real o integrada para sus usuarios en los últimos 30 días.
Este paso se realiza una vez cada 24 horas, para tener en cuenta los cambios en la audiencia de origen.

### [!UICONTROL Predictive Audiences] Fase de clasificación del modelo {#model-classification}

Para la clasificación de audiencias en tiempo real y por lotes, el modelo comprueba primero si un usuario pertenece a la audiencia de destino. Si el usuario cumple los requisitos de la audiencia de destino y no pertenece a ninguna de las personas, el modelo les asigna una puntuación de calificación de persona.

Al evaluar audiencias de origen y asignar puntuaciones, el modelo utiliza el valor predeterminado **[!UICONTROL Profile Merge Rule]** definido en su cuenta de. Por último, el visitante se clasifica en la persona para la que recibió la puntuación más alta.

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## Consideraciones y limitaciones {#considerations}

>[!IMPORTANT]
> Lea esta sección detenidamente antes de pasar a la fase de implementación.

Al configurar su [!UICONTROL Predictive Audiences] Para los modelos de, tenga en cuenta las siguientes consideraciones y limitaciones:

* Puede crear hasta diez modelos de [!UICONTROL Predictive Audiences]. 
* Para cada modelo, puede elegir hasta 50 rasgos o segmentos base.
* Actualmente, no se admiten datos de segundo nivel y de terceros en [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] realiza la clasificación de audiencias en función de los rasgos de origen, desde todas las fuentes de datos de origen.
* Evaluación de segmentos para [!UICONTROL Predictive Audiences] utiliza el **[!UICONTROL Profile Merge Rule]** que elija durante la creación del modelo. Para obtener más información acerca de [!UICONTROL Profile Merge Rules] consulte la sección dedicada [documentación](../profile-merge-rules/merge-rules-overview.md).
* Algunos rasgos y segmentos no se admiten como líneas de base o audiencias de destino. [!UICONTROL Predictive Audiences] Los modelos de no se podrán guardar al elegir una de las siguientes opciones como líneas de base o audiencias de destino:
   * Características predictivas y segmentos creados con características predictivas;
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) rasgos o segmentos;
   * Características algorítmicas;
   * Rasgos de segundo nivel y de terceros.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] no se puede usar en [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

Segmentos predictivos creados por [!UICONTROL Predictive Audiences] los modelos heredan el [Controles de exportación de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) de las siguientes fuentes de datos de origen:

1. La fuente de datos de origen que elija al crear el modelo.
1. Las fuentes de datos de origen de la audiencia de destino. En concreto, los controles de exportación de datos del [!UICONTROL traits] o [!UICONTROL segments] que conforman la audiencia de destino.
1. El [Controles de exportación de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) de la [!UICONTROL Profile Merge Rule] que ha seleccionado para el modelo.

El predictivo recién creado [!UICONTROL traits] y [!UICONTROL segments] tendrá las mismas restricciones de privacidad que la unión de las fuentes de datos de origen descritas anteriormente.

Características que tienen restricciones adicionales que no forman parte del [!UICONTROL Predictive Audiences] las restricciones de privacidad del segmento se excluirán de la fase de formación y no tendrán influencia en el modelo.

## [!UICONTROL Profile Merge Rules] {#pmr}

Todos los segmentos predictivos se asignarán al [!UICONTROL Profile Merge Rule] que seleccionó al crear el modelo. El [!UICONTROL Profile Merge Rule] que elija es importante por los siguientes motivos:

* Define qué dispositivos o perfiles autenticados deben tenerse en cuenta cuando el modelo analiza el elemento influyente [!UICONTROL traits], en el momento de clasificar un usuario en un predictivo [!UICONTROL segment].
* Establece cuáles [!UICONTROL trait] Los tipos de dispositivo (nivel de dispositivo o nivel de dispositivo cruzado) deben utilizarse durante el paso de formación del modelo y mostrarse como influyentes [!UICONTROL traits]. Predictivo [!UICONTROL segments] son subconjuntos de la audiencia de destino.
   * Si la audiencia de destino es un segmento, le recomendamos que seleccione lo mismo [!UICONTROL Profile Merge Rule] para el modelo como el asignado a su audiencia de target, o un [!UICONTROL Profile Merge Rule] que incluye el tipo de perfil de la audiencia de destino.
   * Si la audiencia de destino es un [!UICONTROL trait], le recomendamos que seleccione una [!UICONTROL Profile Merge Rule] que pueden acceder al mismo tipo de datos que el rasgo de audiencia de destino (ya sean datos de perfil del dispositivo o datos de perfil entre dispositivos).
* [!UICONTROL Profile Merge Rules] uso del [!UICONTROL Current Authenticated Profiles] y [!UICONTROL No Device Profile] Las opciones de solo son compatibles con la clasificación de audiencias en tiempo real. Para obtener más información, consulte [Opciones definidas de reglas de combinación de perfiles](../profile-merge-rules/merge-rule-definitions.md).

Selección de una [!UICONTROL Profile Merge Rule] que utiliza datos de dispositivos y datos entre dispositivos maximiza el número de [!UICONTROL traits] que podrían utilizarse para la formación de modelos y la clasificación de usuarios en el predictivo [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

Los rasgos y segmentos que elija para las personalidades y la clasificación de audiencias están sujetos a Audience Manager [Controles de acceso basados en roles](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html).

Los usuarios de Audience Manager solo pueden seleccionar características o segmentos para personalidades y audiencias de destino que tengan [permiso para ver](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
