---
description: Describe cómo crear segmentos con el Generador de segmentos.
seo-description: Describe cómo crear segmentos con el Generador de segmentos.
seo-title: Generador de segmentos
solution: Audience Manager
title: Generador de segmentos
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
translation-type: tm+mt
source-git-commit: 9326b61f27f6c529567ab9b26694998f0b5dafb3
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---


# [!UICONTROL Segment Builder] {#segment-builder}

Describe los pasos opcionales y requeridos para crear un segmento en [!UICONTROL Segment Builder].

## Demostración en video

Inicio viendo el vídeo [](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)Crear segmentos en Audience Manager. El vídeo lo acompaña durante el proceso de creación de segmentos. Lea las secciones siguientes para obtener más información.

## Cree un [!UICONTROL Segment] {#create-segment}

### Sección Generador de segmentos

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] consta de tres secciones separadas: [!UICONTROL Basic Information], [!UICONTROL Traits], y [!UICONTROL Destinations Mapping]. Para crear un [!UICONTROL segment], complete los campos obligatorios en las [!UICONTROL Basic Information] secciones y [!UICONTROL Traits] . [!UICONTROL Destinations Mapping] son opcionales. Consulte las instrucciones siguientes para obtener ayuda adicional.

1. En la sección Información [](../../features/segments/segment-builder.md#segment-builder-controls-basics) básica:

   ![create-segment](assets/create-segment.png)

   * Asigne un nombre al [!UICONTROL segment]. La longitud máxima de un [!UICONTROL segment] nombre es de 255 caracteres.
   * Establezca el [!UICONTROL segment] estado (activo es el predeterminado).
   * Elija un [!UICONTROL data source]. Utilice el primer menú desplegable para filtrar entre Audience Manager [!UICONTROL data sources], grupos de informes de Adobe Analytics o ambos. A continuación, utilice el segundo menú desplegable para elegir su [!UICONTROL data source]. Si no utiliza grupos de informes de Adobe Analytics, el selector de [!UICONTROL data source] tipos se desactiva y se asigna de forma predeterminada únicamente a las fuentes de datos de Audience Manager.
   * Seleccione una [!UICONTROL profile merge rule] opción para [!UICONTROL segment] la cualificación.
   * Asigne el [!UICONTROL segment] a una carpeta de almacenamiento.

1. En la sección [Características](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Busque el segmento [!UICONTROL trait] que desee agregar y haga clic en **[!UICONTROL Add Trait]**. Añada otro [!UICONTROL trait] para crear un [!UICONTROL trait] grupo.
   * Para subir el [!UICONTROL Advanced Search] modal, haga clic en **[!UICONTROL Browse All Traits]**. Busque [!UICONTROL traits] por nombre, ID, descripción o [!UICONTROL data source]. Haga clic en una carpeta mientras busca para limitar los resultados a esa carpeta y sus subcarpetas. También puede filtrar [!UICONTROL traits] por [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]y [!UICONTROL Algorithmic]) o por tipo de población (ID[](../../reference/ids-in-aam.md) del dispositivo e ID [](../../reference/ids-in-aam.md)cruzado del dispositivo).
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Obtenga recomendaciones [](trait-recommendations.md) de características activas a medida que crea su [!UICONTROL segment].
   * Haga clic y arrastre [!UICONTROL traits] para crear grupos independientes.
   * Pase el ratón entre grupos para establecer relaciones con valores booleanos [!UICONTROL AND][!UICONTROL OR], [!UICONTROL AND NOT] .
   * Pase el ratón sobre el icono del reloj para agregar reglas de [actualización y frecuencia](../../features/segments/recency-and-frequency.md) al [!UICONTROL trait].
   * Datos de población de segmentos de Vista a medida que agrega o elimina [!UICONTROL traits]. Haga clic en **[!UICONTROL Calculate Estimates]** para ver (o actualizar) los números de población estimados. Obtenga más información sobre los datos [de población de](../../features/segments/segment-builder-data.md#segment-populations) segmentos en la [!UICONTROL Segment Builder].
   * Haga clic **[!UICONTROL Save]** cuando termine.

1. *(Opcional)* Asigne un [!UICONTROL segment] a un [!UICONTROL destination] en la sección Asignación [de](../../features/segments/segment-builder.md#segment-builder-controls-destinations) destino:
   * Busque el [!UICONTROL destination] y haga clic en **[!UICONTROL Add Destination]**. Tenga en cuenta que [!UICONTROL destination] debe existir antes de poder agregarlo a un [!UICONTROL segment].
   * Haga clic **[!UICONTROL Save]** cuando termine.

Vea el siguiente vídeo para ver en detalle cómo funcionan las métricas entre dispositivos.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## [!UICONTROL Segment Builder] Controles: [!UICONTROL Basic Information] Sección {#segment-builder-controls-basics}

En [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] los ajustes le permiten crear nuevas características o editar las existentes. Para crear una nueva carpeta [!UICONTROL segment], especifique un nombre, un [!UICONTROL data source]y seleccione una carpeta de almacenamiento. El resto de campos son opcionales. Continúe con la [!UICONTROL Traits] sección cuando termine.

<!-- r_segment_basic_info_section.xml -->

<!--

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Name</b> </td> 
   <td colname="col2"> <p>Give the segment a short, logical name that describes its function or purpose. Avoid abbreviations and special characters. The maximum length of a segment name is 255 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>A field for additional descriptive information about the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integration Code</b> </td> 
   <td colname="col2"> <p>A field for a user-defined ID or other company-specific information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <p>Associates the segment with a specific data provider. <p>Use the first drop-down menu to filter between Audience Manager data sources, Adobe Analytics report suites, or both. Then, use the second drop-down menu to choose your data source.</p><p> If you are not using Adobe Analytics report suites, the data source type selector is disabled and defaulted to Audience Manager data sources only.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Profile Merge Rule</b> </td> 
   <td colname="col2"> <p>Selects the Profile Merge Rule to use for segment qualification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Activates or deactivates the segment (active by default). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Folder Storage</b> </td> 
   <td colname="col2"> <p>Determines which storage folder the segment belongs to. </p> </td> 
  </tr> 
 </tbody> 
</table>

-->

| Campo | Descripción |
---------|----------
| **[!UICONTROL Name]** | Asigne al segmento un nombre lógico y corto que describa su función o propósito. Evite abreviaciones y caracteres especiales. La longitud máxima del nombre de un segmento es de 255 caracteres. |
| **[!UICONTROL Description]** | Campo para obtener información descriptiva adicional sobre el segmento. |
| **[!UICONTROL Integration Code]** | Campo para un ID definido por el usuario u otra información específica de la compañía. |
| **[!UICONTROL Data Source]** | Asocia el segmento con un proveedor de datos específico. <br> Utilice el primer menú desplegable para filtrar entre fuentes de datos de Audience Manager, grupos de informes de Adobe Analytics o ambos. A continuación, utilice el segundo menú desplegable para elegir el origen de datos. <br> Si no utiliza grupos de informes de Adobe Analytics, el selector de tipo de fuente de datos se desactiva y se asigna de forma predeterminada únicamente a las fuentes de datos de Audience Manager. |
| **[!UICONTROL Profile Merge Rule]** | Selecciona la regla de combinación de Perfiles que se usará para la calificación de segmentos. |
| **[!UICONTROL Status]** | Activa o desactiva el segmento (activo de forma predeterminada). |
| **Almacenamiento de carpetas** | Determina a qué carpeta de almacenamiento pertenece el segmento. |

## [!UICONTROL Segment Builder] Controles: [!UICONTROL Traits] Sección {#segment-builder-controls-traits}

En [!UICONTROL Segment Builder], la [!UICONTROL Traits] sección le permite administrar [!UICONTROL traits] en una [!UICONTROL segment], crear [!UICONTROL trait] grupos y definir criterios de cualificación. Para agregar un [!UICONTROL trait] a un [!UICONTROL segment], escriba el [!UICONTROL trait] nombre en el campo de búsqueda y haga clic en [!UICONTROL Add Trait]. Guarde el [!UICONTROL trait] (si ha terminado) o continúe con [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Requisitos previos:** Complete los campos obligatorios de la [!UICONTROL Basic Information] sección.

| Campo | Descripción |
|--- |--- |
| **[!UICONTROL Basic View]** | Esta sección proporciona controles visuales que le permiten: <ul><li>Cree nuevos y administre los existentes [!UICONTROL segments].</li><li>Quitar [!UICONTROL traits] de un [!UICONTROL segment].</li><li>Añadir hasta 50 (máximo) [!UICONTROL traits] a un [!UICONTROL segment].</li><li>Arrastre y suelte [!UICONTROL traits] para crear nuevos grupos.</li><li>Vista [!UICONTROL traits] y [!UICONTROL trait] grupos en una [!UICONTROL segment].</li><li>Establezca criterios de cualificación con expresiones booleanas, operadores de comparación y ajustes de actualización y frecuencia.</li></ul> |
| **[!UICONTROL Code View]** | Abre un entorno de desarrollo que le permite crear y administrar [!UICONTROL traits]grupos y requisitos de cualificación con código en lugar de con la interfaz visual. La vista de código es útil si [!UICONTROL segments]: <ul><li>Contener más de 50 [!UICONTROL traits] en una persona [!UICONTROL segment]. Nota: [!UICONTROL Segments] están limitadas a 5000 [!UICONTROL traits] (máximo).</li><li>Contiene muchos [!UICONTROL trait] grupos.</li><li>Tienen requisitos de cualificación complejos.</li></ul> |
| Buscar | Ayuda a encontrar [!UICONTROL traits] agregarlos a un [!UICONTROL segment]. |
| Las actividades de | Obtenga recomendaciones en directo para fuentes similares [!UICONTROL traits], de sus fuentes de datos [!UICONTROL traits] y de [!UICONTROL Audience Marketplace] origen a las que está suscrito. Añada estas recomendaciones a la [!UICONTROL segment] regla para expandir la audiencia. Lea más en Recomendaciones [de características](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Obtenga recomendaciones activas para fuentes similares [!UICONTROL traits][!UICONTROL Audience Marketplace] , a partir de fuentes de datos a las que no está suscrito. Lea más en Recomendaciones [de características](trait-recommendations.md). |
| Datos de tamaño real y [!UICONTROL Segment] estimado | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Quitar [!UICONTROL Traits] de un [!UICONTROL Segment] {#remove-traits}

La gestión de los [!UICONTROL traits] en su [!UICONTROL segments] sitio es una parte importante para mantener la [!UICONTROL segments] viabilidad. Siga estos pasos si necesita quitar [!UICONTROL traits] de un [!UICONTROL segment].

Para quitar [!UICONTROL traits] de un [!UICONTROL segment]:

1. Vaya a **[!UICONTROL Audience Data > Segments]**. Desplácese por la lista o utilice la función de búsqueda para encontrar el [!UICONTROL segment] que desea utilizar.
2. Haga clic en el [!UICONTROL segment] nombre para abrir la pantalla de [!UICONTROL segment] detalles.
3. Haga clic en **Editar** para abrir [!UICONTROL Segment Builder] y, a continuación, haga clic en **Características** para abrir el [!UICONTROL traits] panel.
4. Pase el ratón sobre el elemento [!UICONTROL trait] que desee eliminar y haga clic en la X. Esta acción elimina inmediatamente el [!UICONTROL trait] de su [!UICONTROL segment].

## [!UICONTROL Segment Builder] Controles: [!UICONTROL Destinations Mappings] Sección {#segment-builder-controls-destinations}

En [!UICONTROL Segment Builder], la [!UICONTROL Destinations Mapping] sección opcional le permite enviar [!UICONTROL segment] datos a un tercero [!DNL cookie], [!DNL URL]o [!UICONTROL server-to-server destination]. Para agregar un [!UICONTROL destination], busque (o busque) un [!UICONTROL destination], proporcione información [!UICONTROL destination] específica y haga clic en **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Requisitos previos

Complete los campos obligatorios de las secciones [!UICONTROL Basic Information] y [!UICONTROL Traits] . Además, el destino ya debe existir.

### [!UICONTROL Destination Mappings] Herramientas de búsqueda

El **[!UICONTROL Destination Mappings]** panel contiene las herramientas de búsqueda que se describen en la tabla siguiente.

| Tipo de búsqueda | Descripción |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Permite buscar un nombre específico [!UICONTROL destination] por nombre. Para buscar, escriba el inicio. El campo se completará automáticamente según los términos de búsqueda. Haga clic **[!UICONTROL Add Destination]** cuando termine. |
| **[!UICONTROL Browse All Destinations]** | Examine una lista de *todos* los [!UICONTROL destinations] disponibles. Seleccione y agregue [!UICONTROL destinations] a su [!UICONTROL segment] página desde la lista emergente. |

## Campos en las ventanas emergentes [!UICONTROL Destination Mappings] {#fields-in-dest-mappings}

En [!UICONTROL Segment Builder], el cuadro de diálogo [!UICONTROL Add Destination] aparece después de seleccionar un [!UICONTROL destination]. Esta ventana muestra información estática sobre los campos [!UICONTROL destination] y que varían según el [!UICONTROL destination] tipo. Proporcione la información necesaria en los campos vacíos para configurar una [!UICONTROL destination mapping].

>[!NOTE]
>
>Las fechas de publicación son opcionales. Cuando está en blanco, el destino se activa y nunca caduca.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Campos

En los [!UICONTROL Destination Mapping] campos, especifique los pares clave-valor utilizados para enviar datos al [!UICONTROL destination]. Introduzca la clave en el primer campo y los valores en el segundo. El [!UICONTROL cookie destination] pop podría tener un aspecto similar al siguiente:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Campos

En los campos [!UICONTROL URL] y [!UICONTROL Secure URL] , especifique la dirección segura o estándar completa utilizada para enviar datos al [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Campos

En el [!UICONTROL Destination Value] campo, especifique el valor (parte de un par clave-valor) utilizado para enviar datos al [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Crear un destino de cookie](../../features/destinations/create-cookie-destination.md)
>* [Crear un destino de dirección URL](../../features/destinations/create-url-destination.md)

