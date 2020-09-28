---
description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-title: Información general sobre Predictive Audiences
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 8e43da4c8b890fc5f8468f3779918dbfbbf960b8
workflow-type: tm+mt
source-wordcount: '1589'
ht-degree: 7%

---


# [!UICONTROL Predictive Audiences] Información general {#predictive-audiences}

[!UICONTROL Predictive Audiences] ayuda a clasificar una audiencia desconocida en personalidades distintas, en tiempo real, mediante técnicas avanzadas de ciencia de datos.

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

En un contexto de marketing, una personalidad es un segmento de audiencia definido por visitantes, usuarios o compradores potenciales, que comparten un conjunto específico de rasgos, como su demografía, hábitos de navegación, historial de compras, etc.

Los modelos de [!UICONTROL Predictive Audiences] llevan este concepto un paso más allá, ya que permiten utilizar las capacidades de aprendizaje automático de Audience Manager para clasificar audiencias desconocidas en personalidades distintas. Audience Manager le ayuda a conseguirlo calculando la propensión de la audiencia de origen desconocida para un conjunto de audiencias de origen conocidas.

Cuando se crea un [!UICONTROL Predictive Audiences] modelo, el primer paso es elegir las características o segmentos de línea base por los que desea clasificar la audiencia de destinatario. Estas características o segmentos definirán sus personalidades.

Durante la fase de evaluación, el modelo crea un nuevo [!UICONTROL Predictive Audiences] segmento para cada rasgo o segmento que haya definido como línea de base. La próxima vez que el Audience Manager vea un visitante de su audiencia de destinatario que no está clasificado para una persona (no cumple los requisitos para ninguna de sus características o segmentos de base), el [!UICONTROL Predictive Audiences] modelo determinará a qué segmentos predictivos debe pertenecer el visitante y agregará el visitante a ese segmento.

Puede identificar los segmentos predictivos creados por el modelo en la [!UICONTROL Segments] página. Cada [!UICONTROL Predictive Audiences] modelo tiene su propia carpeta debajo de la [!UICONTROL Predictive Audiences] carpeta y puede ver los segmentos de cada modelo haciendo clic en la carpeta del modelo.

![predictive-audiencias-segments](assets/predictive-audiences-segments.png)

## Casos de uso {#use-cases}

Para ayudarle a comprender mejor cómo y cuándo puede usar [!UICONTROL Predictive Audiences], a continuación se indican algunos casos de uso que los clientes Audience Manager pueden resolver con esta función.

### Caso de uso n.º 1

Como especialista en mercadotecnia en una compañía de comercio electrónico, quiero clasificar todos mis visitantes web y móviles en varias categorías de afinidad de marca, para que pueda personalizar su experiencia de usuario.

### Caso de uso n.º 2

Como especialista en mercadotecnia en una compañía de medios, quiero clasificar mis visitantes móviles y web no autenticados por géneros favoritos, para poder sugerirles contenido personalizado en todos los canales.

### Caso de uso n.º 3

Como anunciante de una compañía de aerolíneas, quiero asegurarme de clasificar mi audiencia en función de su interés en los destinos de viaje, para poder anunciarles en tiempo real, dentro de una breve ventana de redireccionamiento.

### Caso de uso n.º 4

Como anunciante, quiero clasificar mi audiencia de origen en tiempo real, para poder reaccionar rápidamente a las noticias de tendencia.

### Caso de uso n.º 5

Como especialista en mercadotecnia, quiero predecir en qué fase de viaje del cliente se encuentran los visitantes de mi sitio web, como descubrimiento, compromiso, compra o retención, para poder realizar el destinatario correspondiente.

### Caso de uso n.º 6

Como compañía de medios, quiero categorizar mi audiencia, para poder vender mi espacio publicitario a precios especiales, mientras ofrezco mis anuncios relevantes de visitantes.

## Cómo funcionan [!UICONTROL Predictive Audiences] los modelos {#how-predictive-audiences-models-work}

Al crear un [!UICONTROL Predictive Audiences] modelo, se siguen tres pasos:

1. Primero, seleccione un mínimo de dos características o dos segmentos que definirán las personas.
1. A continuación, elija una característica o un segmento que defina la audiencia de destinatario que desea clasificar.
1. Por último, puede elegir un nombre para el modelo, un origen de datos que almacenará los segmentos predictivos y un [!UICONTROL Profile Merge Rule] nombre para el modelo.

### Criterios de selección para personas {#selection-personas}

Puede elegir cualquiera de sus características o segmentos de origen para definir sus personalidades. Sin embargo, para obtener resultados óptimos, aquí hay un conjunto de prácticas recomendadas:

* Elija sus características personales o segmentos para que cada persona tenga al menos unos pocos cientos de ID de [dispositivo](../../reference/ids-in-aam.md).
* Si sus características se basan en ID [de](../../reference/ids-in-aam.md)varios dispositivos, puede envolverlas en segmentos con reglas [de combinación de](../profile-merge-rules/merge-rules-overview.md) Perfiles que utilicen ID [de](../../reference/ids-in-aam.md)dispositivos, como [!UICONTROL Device Graph]. Esto garantizará que haya suficientes ID de [dispositivo](../../reference/ids-in-aam.md) de los que pueda aprender el algoritmo.
* Recomendamos elegir características o segmentos simples para sus personalidades, que constan de entre 1 y 3 características.
* Elija características de línea de base o segmentos que tengan una superposición mínima.
* Asegúrese de capturar rasgos granulares en las propiedades digitales.

### Criterios de selección para la Audiencia de Destinatarios {#selection-audience}

Según el caso de uso, si desea clasificar usuarios en tiempo real, en lote o ambos, elija una audiencia de destinatario ([!UICONTROL trait] o [!UICONTROL segment]) que tenga una población total o en tiempo real significativa. De forma similar a la selección de personajes, recomendamos que la audiencia de destinatarios [!UICONTROL trait] o que [!UICONTROL segment] tenga usuarios con perfiles enriquecidos (conjuntos enriquecidos de [!UICONTROL traits]).

Al seleccionar la audiencia de destinatario, analice el caso de uso y decida qué tipos de ID desea clasificar: [!UICONTROL device IDs] o [!UICONTROL cross-device IDs]. El valor [!UICONTROL Profile Merge Rule] que se selecciona al crear el modelo define los datos que se utilizarán para colocar a cada usuario en el predictivo [!UICONTROL segments].

Se recomienda elegir una [!UICONTROL Profile Merge Rule] que tenga la misma configuración que la audiencia de destinatario [!UICONTROL Profile Merge Rule], o una que incluya el tipo de perfil (perfil de dispositivo o perfil autenticado) de la audiencia de destinatario.

### [!UICONTROL Predictive Audiences] Fase de formación del modelo {#model-training}

Antes de que el algoritmo pueda clasificar la audiencia de origen en las personas correctas, debe formarse en los datos.

Para cada persona que defina, el algoritmo analiza su audiencia respectiva y evalúa cualquier actividad de características en tiempo real y/o incorporada para sus usuarios en los últimos 30 días.
Este paso se realiza una vez cada 24 horas para tener en cuenta los cambios en la audiencia de origen.

### [!UICONTROL Predictive Audiences] Fase de clasificación del modelo {#model-classification}

Para la clasificación de audiencia por lotes y en tiempo real, el modelo comprueba en primer lugar si un usuario pertenece a la audiencia de destinatario. Si el usuario cumple los requisitos para la audiencia de destinatario y no pertenece a ninguna de las personas, el modelo les asigna una puntuación de cualificación personal.

Al evaluar audiencias de origen y asignar puntuaciones, el modelo utiliza el valor predeterminado **[!UICONTROL Profile Merge Rule]** definido en la cuenta. Finalmente, el visitante se clasifica en la persona por la que recibió la mayor puntuación.

![audiencias predictivas-gráficas](assets/predictive-audiences-graph.png)

## Consideraciones y limitaciones {#considerations}

>[!IMPORTANT]
> Lea detenidamente esta sección antes de pasar a la fase de implementación.

Al configurar sus [!UICONTROL Predictive Audiences] modelos, tenga en cuenta las siguientes consideraciones y limitaciones:

* Puede crear hasta diez modelos de [!UICONTROL Predictive Audiences]. 
* Para cada modelo, puede elegir hasta 50 características base / segmentos.
* Los datos de segundo y de terceros no son compatibles actualmente con [!UICONTROL Predictive Audiences].
* La clasificación de audiencias solo se realiza para audiencias individuales en tiempo real. La clasificación de audiencia de origen integrada puede admitirse en una actualización futura.

   >[!IMPORTANT]
   > Si agrega un rasgo predictivo a un segmento normal, se convierte en un segmento predictivo. En consecuencia, todos los perfiles asociados no están segmentados.

   >[!IMPORTANT]
   > Actualmente, los segmentos predictivos solo se pueden activar en destinos en tiempo real. El [!UICONTROL Total Segment Population] y [!UICONTROL Addressable Audience] de los segmentos predictivos se muestra como 0 y las transferencias [de datos de salida por](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) lotes no son compatibles con [!UICONTROL Predictive Audiences]. Este comportamiento cambiará en una actualización futura.

* [!UICONTROL Predictive Audiences] realiza la clasificación de audiencias en función de sus características de origen, desde todas sus fuentes de datos de origen.
* La evaluación de segmentos para [!UICONTROL Predictive Audiences] utiliza el **[!UICONTROL Profile Merge Rule]** que elija durante la creación del modelo. Para obtener más información sobre [!UICONTROL Profile Merge Rules] la [documentación](../profile-merge-rules/merge-rules-overview.md)dedicada, consulte .
* Algunas características y segmentos no se admiten como líneas de base o audiencias de destinatario. [!UICONTROL Predictive Audiences] los modelos no se guardarán al elegir una de las siguientes opciones como líneas de base o audiencias de destinatario:
   * Características predictivas y segmentos creados con características predictivas;
   * [Características o segmentos de Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) ;
   * Características algorítmicas;
   * Características de segundo y de terceros.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] no se puede usar en [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

Los segmentos predictivos creados por [!UICONTROL Predictive Audiences] modelos heredan los controles [de exportación de](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) datos de las siguientes fuentes de datos de origen:

1. Origen de datos de origen que se elige al crear el modelo.
1. Las fuentes de datos de origen de la audiencia de destinatario. Específicamente, los controles de exportación de datos de los [!UICONTROL traits] o [!UICONTROL segments] que conforman la audiencia de destinatario.
1. Controles [de exportación](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) de datos del [!UICONTROL Profile Merge Rule] modelo seleccionado.

El predictivo recién creado [!UICONTROL traits] y [!UICONTROL segments] tendrá las mismas restricciones de privacidad que la unión de las fuentes de datos de origen descritas anteriormente.

Las características que tienen restricciones adicionales que no forman parte de las restricciones de privacidad del [!UICONTROL Predictive Audiences] segmento se excluirán de la fase de formación y no influirán en el modelo.

## [!UICONTROL Profile Merge Rules] {#pmr}

A todos los segmentos predictivos se les asignará el [!UICONTROL Profile Merge Rule] que seleccionó al crear el modelo. El [!UICONTROL Profile Merge Rule] que elija es importante por los siguientes motivos:

* Define qué dispositivos y/o perfiles autenticados deben tenerse en cuenta cuando el modelo analiza el elemento influyente [!UICONTROL traits], en el momento de clasificar un usuario en un elemento predictivo [!UICONTROL segment].
* Determina qué [!UICONTROL trait] tipos (nivel de dispositivo o nivel entre dispositivos) deben utilizarse durante el paso de prueba del modelo y aparecer como influyentes [!UICONTROL traits]. Los predictivos [!UICONTROL segments] son subconjuntos de la audiencia de destinatario.
   * Si la audiencia de destinatario es un segmento, le recomendamos que seleccione el mismo [!UICONTROL Profile Merge Rule] modelo que el asignado a la audiencia de destinatario o un [!UICONTROL Profile Merge Rule] que incluya el tipo de perfil de la audiencia de destinatario.
   * Si la audiencia de destinatario es [!UICONTROL trait], se recomienda seleccionar una [!UICONTROL Profile Merge Rule] que pueda acceder al mismo tipo de datos que la característica de audiencia de destinatario (ya sea datos de perfil de dispositivo o datos de perfil entre dispositivos).
* [!UICONTROL Profile Merge Rules] solo se admiten las opciones [!UICONTROL Current Authenticated Profiles] y [!UICONTROL No Device Profile] para la clasificación de audiencias en tiempo real. Para obtener más información, consulte Opciones de reglas de combinación de [Perfil Definidas](../profile-merge-rules/merge-rule-definitions.md).

Al seleccionar un [!UICONTROL Profile Merge Rule] dispositivo que utilice datos de dispositivos y datos entre dispositivos, se maximiza el número de datos [!UICONTROL traits] que se pueden utilizar para la formación de modelos y la clasificación de usuarios en el predictivo [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

Las características y los segmentos que elija para la clasificación de personas y audiencias están sujetos a Controles de acceso [basados en](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)roles de Audience Manager.

Los usuarios Audience Manager solo pueden seleccionar características o segmentos para audiencias de personas y destinatarios, que tienen [permiso para la vista](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
