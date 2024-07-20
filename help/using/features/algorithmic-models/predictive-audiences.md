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
source-wordcount: '1470'
ht-degree: 3%

---

# Información general de [!UICONTROL Predictive Audiences] {#predictive-audiences}

[!UICONTROL Predictive Audiences] le ayuda a clasificar una audiencia desconocida en personalidades distintas, en tiempo real, mediante técnicas avanzadas de ciencia de datos.

>[!IMPORTANT]
>Este artículo contiene documentación del producto que le guiará a través de la configuración y el uso de esta función. Nada de lo que contiene aquí es asesoramiento legal. Por favor, consulte a su propio asesor legal para obtener orientación legal.

En un contexto de marketing, una persona es un segmento de audiencia definido por visitantes, usuarios o compradores potenciales, que comparten un conjunto específico de rasgos, como su demografía, hábitos de navegación, historial de compras, etc.

Los modelos de [!UICONTROL Predictive Audiences] llevan este concepto un paso más allá, ya que permiten utilizar las capacidades de aprendizaje automático de Audience Manager para clasificar audiencias desconocidas en personalidades distintas. Audience Manager le ayuda a conseguirlo calculando la propensión de la audiencia de origen desconocida para un conjunto de audiencias de origen conocidas.

Cuando crea un modelo [!UICONTROL Predictive Audiences], el primer paso es elegir los rasgos o segmentos de línea de base por los que desea que se clasifique la audiencia de destino. Estos rasgos o segmentos definirán sus personalidades.

Durante la fase de evaluación, el modelo crea un nuevo segmento [!UICONTROL Predictive Audiences] para cada rasgo o segmento definido como línea de base. La próxima vez que el Audience Manager vea un visitante de su audiencia objetivo que no esté clasificado para una persona (que no cumpla con ninguno de sus segmentos o rasgos de línea de base), el modelo [!UICONTROL Predictive Audiences] determinará a cuál de los segmentos predictivos debe pertenecer el visitante y lo agregará a ese segmento.

Puede identificar los segmentos predictivos creados por el modelo en la página [!UICONTROL Segments]. Cada modelo [!UICONTROL Predictive Audiences] tiene su propia carpeta en la carpeta [!UICONTROL Predictive Audiences], y puede ver los segmentos de cada modelo haciendo clic en la carpeta del modelo.

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## Casos de uso {#use-cases}

Para ayudarle a comprender mejor cómo y cuándo puede usar [!UICONTROL Predictive Audiences], a continuación se indican algunos casos de uso que los clientes de Audience Manager pueden solucionar mediante esta característica.

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

## Cómo funcionan los modelos [!UICONTROL Predictive Audiences] {#how-predictive-audiences-models-work}

Cuando crea un modelo [!UICONTROL Predictive Audiences], debe seguir tres pasos:

1. En primer lugar, debe seleccionar un mínimo de dos rasgos o dos segmentos que definirán las personalidades.
1. A continuación, elija un rasgo o segmento que defina la audiencia de destino que desee clasificar.
1. Finalmente, elige un nombre para el modelo, una fuente de datos que almacenará los segmentos predictivos y un [!UICONTROL Profile Merge Rule] para el modelo.

### Criterios de selección para personalidades {#selection-personas}

Puede elegir cualquiera de sus rasgos de origen o segmentos para definir sus personalidades. Sin embargo, para obtener resultados óptimos, aquí tiene un conjunto de prácticas recomendadas:

* Elija sus rasgos o segmentos de personalidad para que cada personalidad tenga al menos unos cientos de [ID de dispositivo](../../reference/ids-in-aam.md).
* Si sus rasgos se basan en [ID entre dispositivos](../../reference/ids-in-aam.md), puede envolverlos en segmentos con [Reglas de combinación de perfiles](../profile-merge-rules/merge-rules-overview.md) que usan [ID de dispositivos](../../reference/ids-in-aam.md), como [!UICONTROL Device Graph]. Esto garantizará que haya suficientes [ID de dispositivo](../../reference/ids-in-aam.md) de los que el algoritmo pueda aprender.
* Recomendamos elegir rasgos o segmentos simples para sus personalidades, que consten de 1 a 3 rasgos.
* Elija rasgos de línea de base o segmentos que tengan una superposición mínima.
* Asegúrese de capturar rasgos granulares en las propiedades digitales.

### Criterios de selección para la audiencia de destino {#selection-audience}

Según el caso de uso, tanto si desea clasificar usuarios en tiempo real, por lotes o ambos, elija una audiencia de destino ([!UICONTROL trait] o [!UICONTROL segment]) que tenga una población total o en tiempo real significativa. De forma similar a la selección de personas, recomendamos que la audiencia de destino [!UICONTROL trait] o [!UICONTROL segment] tenga usuarios con perfiles enriquecidos (conjuntos enriquecidos de [!UICONTROL traits]).

Al seleccionar la audiencia de destino, analice el caso de uso y decida qué tipos de ID desea clasificar: [!UICONTROL device IDs] o [!UICONTROL cross-device IDs]. El [!UICONTROL Profile Merge Rule] que seleccionó al crear el modelo define los datos que se utilizarán para colocar a cada usuario en el elemento predictivo [!UICONTROL segments].

Se recomienda elegir un(a) [!UICONTROL Profile Merge Rule] que tenga la misma configuración que la audiencia de destino [!UICONTROL Profile Merge Rule], o uno que incluya el tipo de perfil (perfil de dispositivo o perfil autenticado) de la audiencia de destino.

### Fase de formación del modelo [!UICONTROL Predictive Audiences] {#model-training}

Antes de que el algoritmo pueda clasificar la audiencia de origen en las personas adecuadas, debe formarse a sí misma en sus datos.

Para cada personalidad que defina, el algoritmo analiza su audiencia respectiva y evalúa cualquier actividad de rasgos en tiempo real o integrada para sus usuarios en los últimos 30 días.
Este paso se realiza una vez cada 24 horas, para tener en cuenta los cambios en la audiencia de origen.

### Fase de clasificación del modelo [!UICONTROL Predictive Audiences] {#model-classification}

Para la clasificación de audiencias en tiempo real y por lotes, el modelo comprueba primero si un usuario pertenece a la audiencia de destino. Si el usuario cumple los requisitos de la audiencia de destino y no pertenece a ninguna de las personas, el modelo les asigna una puntuación de calificación de persona.

Al evaluar audiencias de origen y asignar puntuaciones, el modelo utiliza el valor predeterminado **[!UICONTROL Profile Merge Rule]** definido en su cuenta. Por último, el visitante se clasifica en la persona para la que recibió la puntuación más alta.

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## Consideraciones y limitaciones {#considerations}

>[!IMPORTANT]
> Lea esta sección detenidamente antes de pasar a la fase de implementación.

Al configurar sus modelos de [!UICONTROL Predictive Audiences], tenga en cuenta las siguientes consideraciones y limitaciones:

* Puede crear hasta 10 [!UICONTROL Predictive Audiences] modelos.
* Para cada modelo, puede elegir hasta 50 rasgos o segmentos base.
* En este momento no se admiten datos de segundo nivel y de terceros en [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] realiza la clasificación de audiencias en función de sus rasgos de origen, a partir de todas sus fuentes de datos de origen.
* La evaluación de segmentos de [!UICONTROL Predictive Audiences] usa el **[!UICONTROL Profile Merge Rule]** que eligió durante la creación del modelo. Para obtener más información acerca de [!UICONTROL Profile Merge Rules], consulte la [documentación](../profile-merge-rules/merge-rules-overview.md) dedicada.
* Algunos rasgos y segmentos no se admiten como líneas de base o audiencias de destino. [!UICONTROL Predictive Audiences] modelos no se podrán guardar al elegir uno de los siguientes como líneas de base o audiencias de destino:
   * Características predictivas y segmentos creados con características predictivas;
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) rasgos o segmentos;
   * Características algorítmicas;
   * Rasgos de segundo nivel y de terceros.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] no se puede usar en [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

Los segmentos predictivos creados por modelos [!UICONTROL Predictive Audiences] heredan los [controles de exportación de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) de las siguientes fuentes de datos de origen:

1. La fuente de datos de origen que elija al crear el modelo.
1. Las fuentes de datos de origen de la audiencia de destino. En concreto, los controles de exportación de datos de [!UICONTROL traits] o [!UICONTROL segments] que conforman la audiencia de destino.
1. [Controles de exportación de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) de [!UICONTROL Profile Merge Rule] que seleccionó para el modelo.

Los predictivos [!UICONTROL traits] y [!UICONTROL segments] recién creados tendrán las mismas restricciones de privacidad que la unión de los orígenes de datos de origen descritos anteriormente.

Las características que tengan restricciones adicionales que no formen parte de las restricciones de privacidad del segmento [!UICONTROL Predictive Audiences] se excluirán de la fase de formación y no tendrán influencia en el modelo.

## [!UICONTROL Profile Merge Rules] {#pmr}

A todos los segmentos predictivos se les asignará el [!UICONTROL Profile Merge Rule] que seleccionó al crear el modelo. El(la) [!UICONTROL Profile Merge Rule] que elija es importante por los siguientes motivos:

* Define qué dispositivos o perfiles autenticados deben tenerse en cuenta cuando el modelo analiza el elemento influyente [!UICONTROL traits], en el momento de clasificar un usuario en un elemento predictivo [!UICONTROL segment].
* Establece qué tipos de [!UICONTROL trait] (nivel de dispositivo o nivel de dispositivo cruzado) deben usarse durante el paso de formación del modelo y mostrarse como influyentes [!UICONTROL traits]. Los predictivos [!UICONTROL segments] son subconjuntos de la audiencia de destino.
   * Si la audiencia de destino es un segmento, le recomendamos que seleccione el mismo [!UICONTROL Profile Merge Rule] para el modelo que el asignado a su audiencia de destino, o un [!UICONTROL Profile Merge Rule] que incluya el tipo de perfil de su audiencia de destino.
   * Si la audiencia de destino es un(a) [!UICONTROL trait], le recomendamos que seleccione un(a) [!UICONTROL Profile Merge Rule] que pueda acceder al mismo tipo de datos que el rasgo de audiencia de destino (ya sean datos de perfil de dispositivo o datos de perfil entre dispositivos).
* [!UICONTROL Profile Merge Rules] con las opciones [!UICONTROL Current Authenticated Profiles] y [!UICONTROL No Device Profile] solo se admiten para la clasificación de audiencia en tiempo real. Para obtener más información, vea [Opciones definidas de reglas de combinación de perfiles](../profile-merge-rules/merge-rule-definitions.md).

Si se selecciona un(a) [!UICONTROL Profile Merge Rule] que usa datos de dispositivos y entre dispositivos, se maximiza el número de [!UICONTROL traits] que se podrían usar para la formación de modelos y la clasificación de usuarios en el elemento predictivo [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

Los rasgos y segmentos que elija para las personalidades y la clasificación de audiencias están sujetos a los [controles de acceso basados en roles](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html) del Audience Manager.

Los usuarios del Audience Manager solo pueden seleccionar características o segmentos para personalidades y audiencias de destino para las que tengan [permiso de visualización](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
