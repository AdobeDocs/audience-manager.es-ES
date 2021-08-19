---
description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-title: Información general sobre Predictive Audiences
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Modelos algorítmicos
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1505'
ht-degree: 8%

---

# [!UICONTROL Predictive Audiences] Información general {#predictive-audiences}

[!UICONTROL Predictive Audiences] le ayuda a clasificar una audiencia desconocida en personalidades distintas, en tiempo real, mediante técnicas avanzadas de ciencia de datos.

>[!IMPORTANT]
>Este artículo contiene documentación del producto pensada para guiarle en la configuración y uso de esta función. Nada de lo contenido en este documento es asesoramiento jurídico. Consulte a su propio asesor jurídico para obtener asesoramiento jurídico.

En un contexto de marketing, una personalidad es un segmento de audiencia definido por visitantes, usuarios o compradores potenciales, que comparten un conjunto específico de rasgos, como su demografía, hábitos de navegación, historial de compras, etc.

Los modelos de [!UICONTROL Predictive Audiences] llevan este concepto un paso más allá, ya que permiten utilizar las capacidades de aprendizaje automático de Audience Manager para clasificar audiencias desconocidas en personalidades distintas. Audience Manager le ayuda a conseguirlo calculando la propensión de la audiencia de origen desconocida para un conjunto de audiencias de origen conocidas.

Al crear un modelo [!UICONTROL Predictive Audiences], el primer paso es elegir los rasgos o segmentos de línea de base por los que desea clasificar la audiencia de destino. Estos rasgos o segmentos definirán sus personalidades.

Durante la fase de evaluación, el modelo crea un nuevo segmento [!UICONTROL Predictive Audiences] para cada rasgo o segmento que haya definido como línea de base. La próxima vez que el Audience Manager vea un visitante de su audiencia de destino que no está clasificado para una personalidad (no cumplía los requisitos para ninguno de sus rasgos o segmentos de línea de base), el modelo [!UICONTROL Predictive Audiences] determinará a cuál de los segmentos predictivos debe pertenecer el visitante y lo agregará a ese segmento.

Puede identificar los segmentos predictivos creados por el modelo en la página [!UICONTROL Segments]. Cada modelo [!UICONTROL Predictive Audiences] tiene su propia carpeta en la carpeta [!UICONTROL Predictive Audiences] y puede ver los segmentos de cada modelo haciendo clic en la carpeta del modelo.

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## Casos de uso {#use-cases}

Para ayudarle a comprender mejor cómo y cuándo puede utilizar [!UICONTROL Predictive Audiences], estos son algunos casos de uso que los clientes Audience Manager pueden resolver usando esta función.

### Caso de uso n.º 1

Como especialista en marketing en una empresa de comercio electrónico, quiero clasificar todos mis visitantes web y móviles en varias categorías de afinidad de marca, de modo que pueda personalizar su experiencia de usuario.

### Caso de uso n.º 2

Como especialista en marketing en una empresa de medios, quiero clasificar mis visitantes móviles y web no autenticados por géneros favoritos, de modo que pueda sugerirles contenido personalizado en todos los canales.

### Caso de uso n.º 3

Como anunciante de una aerolínea, quiero asegurarme de clasificar mi audiencia en función de su interés en destinos de viaje, para que pueda anunciarles en tiempo real, dentro de una breve ventana de redireccionamiento.

### Caso de uso n.º 4

Como anunciante, quiero clasificar mi audiencia de origen en tiempo real, para que pueda reaccionar rápidamente a las noticias de tendencia.

### Caso de uso n.º 5

Como especialista en marketing, quiero predecir en qué fase de recorrido de clientes se encuentran los visitantes de mi sitio web, como descubrimiento, participación, compra o retención, de modo que pueda dirigirlos en consecuencia.

### Caso de uso n.º 6

Como empresa de medios, quiero categorizar mi audiencia, de modo que pueda vender mi espacio publicitario a precios especiales, mientras ofrezco a mis visitantes anuncios relevantes.

## Funcionamiento de los modelos [!UICONTROL Predictive Audiences] {#how-predictive-audiences-models-work}

Al crear un modelo [!UICONTROL Predictive Audiences], se siguen tres pasos:

1. En primer lugar, seleccione un mínimo de dos rasgos o dos segmentos que definirán sus personalidades.
1. A continuación, elija un rasgo o segmento que defina la audiencia de destino que desea clasificar.
1. Finalmente, elija un nombre para el modelo, una fuente de datos que almacenará los segmentos predictivos y un [!UICONTROL Profile Merge Rule] para el modelo.

### Criterios de selección para personas {#selection-personas}

Puede elegir cualquiera de los rasgos o segmentos de origen para definir las personas. Sin embargo, para obtener resultados óptimos, le presentamos un conjunto de prácticas recomendadas:

* Elija sus rasgos o segmentos personales para que cada personalidad tenga al menos unos pocos cientos de [ID de dispositivo](../../reference/ids-in-aam.md).
* Si sus rasgos se basan en [ID entre dispositivos](../../reference/ids-in-aam.md), puede ajustarlos en segmentos con [Reglas de combinación de perfiles](../profile-merge-rules/merge-rules-overview.md) que utilicen [ID de dispositivo](../../reference/ids-in-aam.md), como [!UICONTROL Device Graph]. Esto garantizará que haya suficientes [ID de dispositivo](../../reference/ids-in-aam.md) que el algoritmo pueda aprender.
* Se recomienda elegir características o segmentos simples para las personas, que constan de entre 1 y 3 características.
* Elija características de línea de base o segmentos que tengan una superposición mínima.
* Asegúrese de que está capturando rasgos granulares en sus propiedades digitales.

### Criterios de selección para la audiencia de destino {#selection-audience}

Según el caso de uso, si desea clasificar a los usuarios en tiempo real, por lotes o ambos, elija una audiencia de destino ([!UICONTROL trait] o [!UICONTROL segment]) que tenga una población total o en tiempo real importante. De forma similar a la selección de personalidad, recomendamos que la audiencia de destino [!UICONTROL trait] o [!UICONTROL segment] tenga usuarios con perfiles enriquecidos (conjuntos enriquecidos de [!UICONTROL traits]).

Al seleccionar la audiencia de destino, analice su caso de uso y decida qué tipos de ID desea clasificar: [!UICONTROL device IDs] o [!UICONTROL cross-device IDs]. El [!UICONTROL Profile Merge Rule] que selecciona al crear el modelo define los datos que se utilizarán para colocar cada usuario en el [!UICONTROL segments] predictivo.

Se recomienda elegir un [!UICONTROL Profile Merge Rule] que tenga la misma configuración que la audiencia de destino [!UICONTROL Profile Merge Rule] o uno que incluya el tipo de perfil (perfil de dispositivo o perfil autenticado) de la audiencia de destino.

### [!UICONTROL Predictive Audiences] Fase de formación del modelo {#model-training}

Para que el algoritmo pueda clasificar la audiencia de origen en las personas adecuadas, debe formarse en los datos.

Para cada personalidad que defina, el algoritmo analiza su audiencia respectiva y evalúa cualquier actividad de rasgos en tiempo real o integrada para sus usuarios en los últimos 30 días.
Este paso se realiza una vez cada 24 horas para tener en cuenta los cambios en la audiencia de origen.

### [!UICONTROL Predictive Audiences] Fase de clasificación de modelo {#model-classification}

Para la clasificación de audiencias en tiempo real y por lotes, el modelo primero comprueba si un usuario pertenece a la audiencia de destino. Si el usuario cumple los requisitos para la audiencia de destino y no pertenece a ninguna de las personalidades, el modelo les asigna una puntuación de calificación de personalidad.

Al evaluar audiencias de origen y asignar puntuaciones, el modelo utiliza el **[!UICONTROL Profile Merge Rule]** predeterminado definido en la cuenta. Finalmente, el visitante se clasifica en la personalidad para la que recibió la puntuación más alta.

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## Consideraciones y limitaciones {#considerations}

>[!IMPORTANT]
> Lea esta sección detenidamente antes de pasar a la fase de implementación.

Al configurar los modelos [!UICONTROL Predictive Audiences], tenga en cuenta las siguientes consideraciones y limitaciones:

* Puede crear hasta diez modelos de [!UICONTROL Predictive Audiences]. 
* Para cada modelo, puede elegir hasta 50 rasgos/segmentos base.
* Actualmente, [!UICONTROL Predictive Audiences] no se admiten datos de segundo nivel y de terceros.
* [!UICONTROL Predictive Audiences] realiza la clasificación de audiencias en función de sus características de origen, a partir de todas las fuentes de datos de origen.
* La evaluación de segmentos para [!UICONTROL Predictive Audiences] utiliza el **[!UICONTROL Profile Merge Rule]** que elija durante la creación del modelo. Para obtener más información sobre [!UICONTROL Profile Merge Rules], consulte la [documentación](../profile-merge-rules/merge-rules-overview.md) dedicada.
* Algunos rasgos y segmentos no son compatibles como líneas de base ni como audiencias de destino. [!UICONTROL Predictive Audiences] Los modelos no se guardarán al elegir una de las siguientes opciones como líneas de base o audiencias de destino:
   * Rasgos predictivos y segmentos creados con rasgos predictivos;
   * [Características o segmentos de Adobe Experience ](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) Platform;
   * Rasgos algorítmicos;
   * Rasgos de segundo nivel y de terceros.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] no se puede usar en  [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

Los segmentos predictivos creados por modelos [!UICONTROL Predictive Audiences] heredan los [Controles de exportación de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) de las siguientes fuentes de datos de origen:

1. La fuente de datos de origen que elija al crear el modelo.
1. Las fuentes de datos de origen de la audiencia de destino. Específicamente, los controles de exportación de datos de [!UICONTROL traits] o [!UICONTROL segments] que conforman la audiencia de destino.
1. Los [Controles de exportación de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) del [!UICONTROL Profile Merge Rule] que ha seleccionado para el modelo.

Los predictivos [!UICONTROL traits] y [!UICONTROL segments] recién creados tendrán las mismas restricciones de privacidad que la unión de las fuentes de datos de origen descritas anteriormente.

Las características que tienen restricciones adicionales que no forman parte de las restricciones de privacidad del segmento [!UICONTROL Predictive Audiences] se excluirán de la fase de formación y no tendrán influencia para el modelo.

## [!UICONTROL Profile Merge Rules] {#pmr}

A todos los segmentos predictivos se les asignará el [!UICONTROL Profile Merge Rule] que seleccionó al crear el modelo. El [!UICONTROL Profile Merge Rule] que elija es importante por los siguientes motivos:

* Define qué dispositivos y/o perfiles autenticados deben tenerse en cuenta cuando el modelo analiza el [!UICONTROL traits] influyente, en el momento de clasificar a un usuario en un [!UICONTROL segment] predictivo.
* Determina qué tipos [!UICONTROL trait] (nivel de dispositivo o nivel entre dispositivos) deben utilizarse durante el paso de formación del modelo y aparecer como influyentes [!UICONTROL traits]. Predictive [!UICONTROL segments] son subconjuntos de la audiencia de destino.
   * Si la audiencia de destino es un segmento, se recomienda seleccionar el mismo [!UICONTROL Profile Merge Rule] para el modelo que el asignado a la audiencia de destino, o un [!UICONTROL Profile Merge Rule] que incluya el tipo de perfil de la audiencia de destino.
   * Si la audiencia de destino es [!UICONTROL trait], le recomendamos que seleccione un [!UICONTROL Profile Merge Rule] que pueda acceder al mismo tipo de datos que el rasgo de audiencia de destino (ya sea datos de perfil de dispositivo o datos de perfil entre dispositivos).
* [!UICONTROL Profile Merge Rules] el uso de  [!UICONTROL Current Authenticated Profiles] las  [!UICONTROL No Device Profile] opciones y solo se admite para la clasificación de audiencias en tiempo real. Para obtener más información, consulte [Opciones definidas de reglas de combinación de perfiles](../profile-merge-rules/merge-rule-definitions.md).

Al seleccionar un [!UICONTROL Profile Merge Rule] que utilice tanto datos de dispositivo como datos de varios dispositivos, se maximiza el número de [!UICONTROL traits] que podrían utilizarse para la capacitación de modelos y la clasificación de usuarios en el [!UICONTROL segments] predictivo.

## [!UICONTROL Role-Based Access Controls] {#rbac}

Los rasgos y segmentos que elija para las personas y la clasificación de audiencias están sujetos a los [Controles de acceso basados en roles](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html) del Audience Manager.

Los usuarios Audience Manager solo pueden seleccionar características o segmentos para personalidades y audiencias de destino que tengan [permiso para ver](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
