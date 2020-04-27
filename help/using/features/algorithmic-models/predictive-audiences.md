---
description: Las Audiencias predictivas ayudan a clasificar audiencias desconocidas en personalidades distintas en tiempo real, mediante el uso de la ciencia de datos.
seo-description: Las Audiencias predictivas ayudan a clasificar audiencias desconocidas en personalidades distintas en tiempo real, mediante el uso de la ciencia de datos.
seo-title: Información general de Audiencias predictivas
solution: Audience Manager
title: Audiencias predictivas del Administrador de Audiencias
translation-type: tm+mt
source-git-commit: 74a5de961b2f9ab6afa2caf998ba1100d40cc93a

---


# Información general de Audiencias predictivas {#predictive-audiences}

[!UICONTROL Predictive Audiences] ayuda a clasificar una audiencia desconocida en personalidades distintas, en tiempo real, mediante técnicas avanzadas de ciencia de datos.

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

En un contexto de marketing, una persona es un segmento de audiencia definido por visitantes, usuarios o compradores potenciales, que comparten un conjunto específico de características, como demografía, hábitos de navegación, historial de compras, etc.

[!UICONTROL Predictive Audiences] los modelos llevan este concepto un paso más allá, permitiéndole utilizar las capacidades de aprendizaje automático del Administrador de Audiencias para clasificar audiencias desconocidas en personalidades distintas. El Administrador de Audiencias le ayuda a conseguirlo calculando la propensión de la audiencia de origen desconocida para un conjunto de audiencias de origen conocidas.

Cuando se crea un [!UICONTROL Predictive Audiences] modelo, el primer paso es elegir las características o segmentos de línea base por los que desea clasificar la audiencia de destinatario. Estas características o segmentos definirán sus personalidades.

Durante la fase de evaluación, el modelo crea un nuevo [!UICONTROL Predictive Audiences] segmento para cada rasgo o segmento que haya definido como línea de base. La próxima vez que el Administrador de Audiencias vea un visitante de la audiencia de destinatarios que no está clasificado para una persona (no cumple los requisitos para ninguna de sus características o segmentos de base), el [!UICONTROL Predictive Audiences] modelo determinará a qué segmentos predictivos debe pertenecer el visitante y agregará el visitante a ese segmento.

Puede identificar los segmentos predictivos creados por el modelo en la [!UICONTROL Segments] página. Cada [!UICONTROL Predictive Audiences] modelo tiene su propia carpeta debajo de la [!UICONTROL Predictive Audiences] carpeta y puede ver los segmentos de cada modelo haciendo clic en la carpeta del modelo.

![predictive-audiencias-segments](assets/predictive-audiences-segments.png)

## Casos de uso {#use-cases}

Para ayudarle a comprender mejor cómo y cuándo puede usar [!UICONTROL Predictive Audiences], a continuación se indican algunos casos de uso que los clientes del Administrador de Audiencias pueden resolver con esta función.

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

## Funcionamiento de los modelos de Audiencias predictivas

Al crear un [!UICONTROL Predictive Audiences] modelo, se siguen tres pasos:

1. Primero, seleccione un mínimo de dos características o dos segmentos que definirán las personas.
1. A continuación, elija una característica o un segmento que defina la audiencia de destinatario que desea clasificar.
1. Finalmente, elija un nombre para el modelo y seleccione un origen de datos que almacenará los segmentos predictivos.

### Criterios de selección para personas {#selection-personas}

Puede elegir cualquiera de sus características o segmentos de origen para definir sus personalidades. Sin embargo, para obtener resultados óptimos, aquí hay un conjunto de prácticas recomendadas:

* Elija sus características personales o segmentos para que cada persona tenga al menos unos pocos cientos de ID de [dispositivo](../../reference/ids-in-aam.md).
* Si sus características se basan en ID [de](../../reference/ids-in-aam.md)varios dispositivos, puede envolverlas en segmentos con reglas [de combinación de](../profile-merge-rules/merge-rules-overview.md) Perfiles que utilicen ID [de](../../reference/ids-in-aam.md)dispositivos, como [!UICONTROL Device Graph]. Esto garantizará que haya suficientes ID de [dispositivo](../../reference/ids-in-aam.md) de los que pueda aprender el algoritmo.
* Recomendamos elegir características o segmentos simples para sus personas, que consisten en entre 1 y 3 características.
* Elija características de línea de base o segmentos que tengan una superposición mínima.
* Asegúrese de capturar rasgos granulares en las propiedades digitales.

### Criterios de selección para la Audiencia de Destinatarios {#selection-audience}

De forma similar a la selección de personajes, debe elegir la característica o el segmento que define la audiencia de destinatarios de forma que tenga usuarios en tiempo real con conjuntos de características enriquecidos, para clasificarlos en la persona adecuada.

### Fase de formación del modelo de Audiencias predictivas {#model-training}

Antes de que el algoritmo pueda clasificar la audiencia de origen en las personas correctas, debe formarse en los datos.

Para cada persona que defina, el algoritmo analiza su audiencia respectiva y evalúa cualquier actividad de características en tiempo real y/o incorporada para sus usuarios en los últimos 30 días.
Este paso se realiza una vez cada 24 horas para tener en cuenta los cambios en la audiencia de origen.

### Fase de clasificación del modelo de Audiencias predictivas {#model-classification}

Cuando un visitante que forma parte de la audiencia de destinatario se ve en tiempo real, el modelo evalúa si el visitante es parte de las personas definidas. Por cada visitante que no pertenece a ninguna de las personas, el modelo asigna una puntuación de cualificación personal.

Al evaluar audiencias de origen y asignar puntuaciones, el modelo utiliza el valor predeterminado **[!UICONTROL Profile Merge Rule]** definido en la cuenta. Finalmente, el visitante se clasifica en la persona por la que recibió la mayor puntuación.

![audiencias predictivas-gráficas](assets/predictive-audiences-graph.png)

## Consideraciones y limitaciones {#considerations}

>[!IMPORTANT]
> Lea detenidamente esta sección antes de pasar a la fase de implementación.

Al configurar sus [!UICONTROL Predictive Audiences] modelos, tenga en cuenta las siguientes consideraciones y limitaciones:

* Puede crear hasta 10 [!UICONTROL Predictive Audiences] modelos.
* Para cada modelo, puede elegir hasta 50 características base / segmentos.
* Los datos de segundo y de terceros no son compatibles actualmente con [!UICONTROL Predictive Audiences].
* La clasificación de Audiencias solo se realiza para audiencias individuales en tiempo real. La clasificación de audiencia de origen integrada puede admitirse en una actualización futura.
   >[!IMPORTANT]
   > Actualmente, el [!UICONTROL Total Segment Population] de los segmentos predictivos se muestra como 0 y las transferencias [de datos de salida por](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) lotes no son compatibles con las Audiencias predictivas. Este comportamiento cambiará en una actualización futura.
* [!UICONTROL Predictive Audiences] realiza la clasificación de audiencias en función de sus características de origen, desde todas sus fuentes de datos de origen.
* La evaluación de segmentos para [!UICONTROL Predictive Audiences] usa el valor predeterminado **[!UICONTROL Profile Merge Rule]** que definió en su cuenta. Para obtener más información sobre [!UICONTROL Profile Merge Rules] la [documentación](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/profile-merge-rules/merge-rules-overview.html)dedicada, consulte .
* Algunas características y segmentos no se admiten como líneas de base o audiencias de destinatario. [!UICONTROL Predictive Audiences] los modelos no se guardarán al elegir una de las siguientes opciones como líneas de base o audiencias de destinatario:
   * Características predictivas y segmentos creados con características predictivas;
   * [Características o segmentos de Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) ;
   * Características algorítmicas;
   * Características de segundo y de terceros.

## Controles de exportación de datos{#dec}

Los segmentos predictivos creados por [!UICONTROL Predictive Audiences] modelos heredan los controles [de exportación de](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) datos de las siguientes fuentes de datos de origen:

1. Origen de datos de origen que se elige al crear el modelo.
1. Las fuentes de datos de origen de la audiencia de destinatario. Específicamente, los controles de exportación de datos de las características o segmentos que conforman la audiencia de destinatario.

Los segmentos y características predictivas recién creados tendrán las mismas restricciones de privacidad que la unión de las fuentes de datos de origen descritas anteriormente.

Las características que tienen restricciones adicionales que no forman parte de las restricciones de privacidad del [!UICONTROL Predictive Audiences] segmento se excluirán de la fase de formación y no influirán en el modelo.

## Controles de acceso basados en roles{#rbac}

Las características y los segmentos que elija para la clasificación de personas y audiencias están sujetos a Controles de acceso [basados en](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)roles del administrador de Audiencias.

Los usuarios del Administrador de Audiencias solo pueden seleccionar características o segmentos para audiencias de personas y destinatarios, que tienen [permiso para la vista](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
