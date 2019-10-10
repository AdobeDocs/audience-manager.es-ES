---
description: Describe cómo crear segmentos con el Generador de segmentos.
seo-description: Describe cómo crear segmentos con el Generador de segmentos.
seo-title: Generador de segmentos
solution: Audience Manager
title: Generador de segmentos
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
translation-type: tm+mt
source-git-commit: 9215942bd33af0eabf5143e52edcb249d4ca2cac

---


# Generador de segmentos {#segment-builder}

Describe los pasos opcionales y requeridos para crear un segmento en [!UICONTROL Segment Builder].

## Demostración en video

Comience viendo el vídeo [](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)Crear segmentos en Audience Manager. El vídeo lo acompaña durante el proceso de creación de segmentos. Lea las secciones siguientes para obtener más información.

## Creación de segmentos {#create-segment}

### Sección Generador de segmentos

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] consta de tres secciones separadas: [!UICONTROL Basic Information], [!UICONTROL Traits], y [!UICONTROL Destinations Mapping]. Para crear un segmento, complete los campos requeridos en las secciones [!UICONTROL Basic Information] y [!UICONTROL Traits] . [!UICONTROL Destinations Mapping] son opcionales. Consulte las instrucciones siguientes para obtener ayuda adicional.

![create-segment](assets/create-segment.png)

1. En la sección Información [](../../features/segments/segment-builder.md#segment-builder-controls-basics) básica:
   * Asigne un nombre al segmento. La longitud máxima del nombre de un segmento es de 255 caracteres.
   * Establezca el estado del segmento (activo es predeterminado).
   * Elija una fuente de datos. Utilice el primer menú desplegable para filtrar entre fuentes de datos de Audience Manager, grupos de informes de Adobe Analytics o ambos. A continuación, utilice el segundo menú desplegable para elegir el origen de datos. Si no utiliza grupos de informes de Adobe Analytics, el selector de tipo de fuente de datos se desactiva y se establece de forma predeterminada únicamente en las fuentes de datos de Audience Manager.
   * Seleccione una regla de combinación de perfiles para utilizarla en la calificación de segmentos.
   * Asigne el segmento a una carpeta de almacenamiento.
2. En la sección [Características](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   * Busque la característica que desee agregar a un segmento y haga clic en **[!UICONTROL Add Trait]**. Agregue otra característica para crear un grupo de características.
   * Para abrir el modal Búsqueda avanzada, haga clic en **[!UICONTROL Browse All Traits]**. Busque características por nombre, ID, descripción o fuente de datos. Haga clic en una carpeta mientras busca para limitar los resultados a esa carpeta y sus subcarpetas. También puede filtrar características por tipo de característica.
   * Obtenga recomendaciones [de](trait-recommendations.md) características activas a medida que crea el segmento.
   * Haga clic y arrastre características para crear grupos independientes.
   * Pase el ratón entre grupos para establecer relaciones con valores booleanos [!UICONTROL AND][!UICONTROL OR], [!UICONTROL AND NOT] .
   * Pase el ratón sobre el icono del reloj para agregar reglas de [actualización y frecuencia](../../features/segments/recency-and-frequency.md) a la característica.
   * Ver datos de población de segmentos a medida que agrega o elimina características. Haga clic **[!UICONTROL Calculate Estimates]** para ver (o actualizar) los números de población estimados. Obtenga más información sobre los datos [de población de](../../features/segments/segment-builder-data.md#segment-populations) segmentos en el Generador de segmentos.
   * Click **[!UICONTROL Save]** when done.
3. *(Opcional)* Asigne un segmento a un destino en la sección Asignación [de](../../features/segments/segment-builder.md#segment-builder-controls-destinations) destino:
   * Busque el destino y haga clic en **[!UICONTROL Add Destination]**. Tenga en cuenta que el destino ya debe existir para poder agregarlo a un segmento.
   * Click **[!UICONTROL Save]** when done.

## Controles del Generador de segmentos: Sección de información básica {#segment-builder-controls-basics}

En [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] los ajustes le permiten crear nuevas características o editar las existentes. Para crear un nuevo segmento, especifique un nombre, un origen de datos y seleccione una carpeta de almacenamiento. El resto de campos son opcionales. Continúe con la [!UICONTROL Traits] sección cuando termine.

<!-- r_segment_basic_info_section.xml -->

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Nombre</b> </td> 
   <td colname="col2"> <p>Asigne al segmento un nombre lógico y corto que describa su función o propósito. Evite abreviaciones y caracteres especiales. La longitud máxima del nombre de un segmento es de 255 caracteres. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Descripción</b> </td> 
   <td colname="col2"> <p>Campo para obtener información descriptiva adicional sobre el segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Código de integración</b> </td> 
   <td colname="col2"> <p>Campo para un ID definido por el usuario u otra información específica de la empresa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fuente de datos</b> </td> 
   <td colname="col2"> <p>Asocia el segmento con un proveedor de datos específico. <p>Utilice el primer menú desplegable para filtrar entre fuentes de datos de Audience Manager, grupos de informes de Adobe Analytics o ambos. A continuación, utilice el segundo menú desplegable para elegir el origen de datos.</p><p> Si no utiliza grupos de informes de Adobe Analytics, el selector de tipo de fuente de datos se desactiva y se establece de forma predeterminada únicamente en las fuentes de datos de Audience Manager.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Regla de combinación de perfiles</b> </td> 
   <td colname="col2"> <p>Selecciona la regla de combinación de perfiles que se usará para la calificación de segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estado</b> </td> 
   <td colname="col2"> <p>Activa o desactiva el segmento (activo de forma predeterminada). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Almacenamiento de carpetas</b> </td> 
   <td colname="col2"> <p>Determina a qué carpeta de almacenamiento pertenece el segmento. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Controles del Generador de segmentos: Sección de características {#segment-builder-controls-traits}

En [!UICONTROL Segment Builder], la [!UICONTROL Traits] sección le permite administrar características en un segmento, crear grupos de características y establecer criterios de cualificación. Para agregar una característica a un segmento, escriba el nombre de la característica en el campo de búsqueda y haga clic en [!UICONTROL Add Trait]. Guarde la característica (si ha terminado) o continúe con [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**** Requisitos previos: Complete los campos obligatorios de la [!UICONTROL Basic Information] sección.

| Campo | Descripción |
|--- |--- |
| Vista básica | Esta sección proporciona controles visuales que le permiten: <ul><li>Cree nuevos segmentos y administre los existentes.</li><li>Eliminar características de un segmento.</li><li>Agregue hasta 50 características (máximo) a un segmento.</li><li>Arrastre y suelte las características para crear nuevos grupos.</li><li>Ver características y grupos de características en un segmento.</li><li>Establezca criterios de cualificación con expresiones booleanas, operadores de comparación y ajustes de actualización y frecuencia.</li></ul> |
| Vista de código | Abre un entorno de desarrollo que permite crear y administrar características, grupos y requisitos de cualificación con código en lugar de con la interfaz visual. La vista de código resulta útil si los segmentos: <ul><li>Contiene más de 50 características en un segmento individual. Nota: Los segmentos están limitados a 5000 características (máximo).</li><li>Contiene muchos grupos de características.</li><li>Tienen requisitos de cualificación complejos.</li></ul> |
| Buscar | Ayuda a encontrar características que agregar a un segmento. |
| Las actividades de | Obtenga recomendaciones activas para características similares para agregarlas a la regla de segmento. Lea más en Recomendaciones [de características](trait-recommendations.md). |
| Datos reales y estimados del tamaño del segmento | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Eliminar características de un segmento {#remove-traits}

La administración de las características de los segmentos es una parte importante para mantener viables los segmentos. Siga estos pasos si necesita eliminar características de un segmento.

Para eliminar características de un segmento:

1. Vaya a Datos de **audiencia &gt; Segmentos**. Desplácese por la lista o utilice la función de búsqueda para encontrar el segmento con el que desee trabajar.
2. Haga clic en el nombre del segmento para abrir la pantalla de detalles del segmento.
3. Haga clic en **Editar** para abrir el Generador de segmentos y, a continuación, haga clic en **Características** para abrir el panel Características.
4. Pase el ratón sobre la característica que desee eliminar y, a continuación, haga clic en la X. Esta acción elimina inmediatamente la característica del segmento.

## Controles del Generador de segmentos: Sección Asignaciones de destinos {#segment-builder-controls-destinations}

En [!UICONTROL Segment Builder], la [!UICONTROL Destinations Mapping] sección opcional permite enviar datos de segmentos a un destino de terceros [!DNL cookie], [!DNL URL]o de servidor a servidor. Para agregar un destino, busque (o busque) un destino, proporcione información específica del destino y haga clic en **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Requisitos previos

Complete los campos obligatorios de las secciones [!UICONTROL Basic Information] y [!UICONTROL Traits] . Además, el destino ya debe existir.

### Herramientas de búsqueda de asignaciones de destino

El **[!UICONTROL Destination Mappings]** panel contiene las herramientas de búsqueda que se describen en la tabla siguiente.

| Tipo de búsqueda | Descripción |
|---|---|
| **Buscar por nombre de destino** | Permite buscar un destino específico por nombre. Para buscar, empiece a escribir. El campo se completará automáticamente según los términos de búsqueda. Click **[!UICONTROL Add Destination]** when done. |
| **Examinar todos los destinos** | Busque una lista de *todos los* destinos disponibles. Seleccione y agregue destinos al segmento desde la lista emergente. |

## Campos en las ventanas emergentes Asignaciones de destino {#fields-in-dest-mappings}

En [!UICONTROL Segment Builder], el cuadro de diálogo [!UICONTROL Add Destination] aparece después de seleccionar un destino. Esta ventana muestra información estática sobre el destino y los campos que varían según el tipo de destino. Proporcione la información necesaria en los campos vacíos para configurar una asignación de destino.

>[!NOTE]
>
>Las fechas de publicación son opcionales. Cuando está en blanco, el destino se activa y nunca caduca.

<!-- r_add_mappings_pop.xml -->

### Campos de destino de la cookie

En los [!UICONTROL Destination Mapping] campos, especifique los pares clave-valor utilizados para enviar datos al destino. Introduzca la clave en el primer campo y los valores en el segundo. La ventana emergente de destino de la cookie podría tener un aspecto similar a este:

![](assets/cookie_modal.PNG)

### Campos de destino de la dirección URL

En los campos [!UICONTROL URL] y [!UICONTROL Secure URL] , especifique la dirección segura o estándar completa utilizada para enviar datos al destino.

![](assets/url_modal.PNG)

### Campos de destino de servidor a servidor

En el [!UICONTROL Destination Value] campo, especifique el valor (parte de un par clave-valor) utilizado para enviar datos al destino.

![](assets/s2s_modal.PNG)

>[!MORE_LIKE_THIS]
>
>* [Crear un destino de cookie](../../features/destinations/create-cookie-destination.md)
>* [Crear un destino de dirección URL](../../features/destinations/create-url-destination.md)

