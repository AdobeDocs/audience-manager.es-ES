---
description: Describe cómo crear segmentos con el Generador de segmentos.
seo-description: Describe cómo crear segmentos con el Generador de segmentos.
seo-title: Generador de segmentos
solution: Audience Manager
title: Generador de segmentos
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: 'Segmentos '
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 2%

---

# [!UICONTROL Segment Builder] {#segment-builder}

Describe los pasos opcionales y requeridos para crear un segmento en [!UICONTROL Segment Builder].

## Demostración en vídeo

Comience por ver el [Create Segments in Audience Manager video](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). El vídeo lo acompaña durante el proceso de creación de segmentos. Lea las secciones siguientes para obtener más información.

## Cree un [!UICONTROL Segment] {#create-segment}

### Sección del Generador de segmentos

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] consta de 3 secciones separadas:  [!UICONTROL Basic Information],  [!UICONTROL Traits], y  [!UICONTROL Destinations Mapping]. Para crear un [!UICONTROL segment], complete los campos obligatorios en las secciones [!UICONTROL Basic Information] y [!UICONTROL Traits] . [!UICONTROL Destinations Mapping] son opcionales. Consulte las instrucciones siguientes para obtener más ayuda.

1. En la sección [Información básica](../../features/segments/segment-builder.md#segment-builder-controls-basics):

   ![create-segment](assets/create-segment.png)

   * Asigne un nombre a [!UICONTROL segment]. La longitud máxima de un nombre [!UICONTROL segment] es de 255 caracteres.
   * Establezca el estado [!UICONTROL segment] (activo es el valor predeterminado).
   * Elija un [!UICONTROL data source]. Utilice el primer menú desplegable para filtrar entre el Audience Manager [!UICONTROL data sources], los grupos de informes de Adobe Analytics o ambos. A continuación, utilice el segundo menú desplegable para elegir su [!UICONTROL data source]. Si no utiliza grupos de informes de Adobe Analytics, el selector de tipo [!UICONTROL data source] está desactivado y solo se asigna de forma predeterminada a las fuentes de datos del Audience Manager.
   * Seleccione un [!UICONTROL profile merge rule] para usar con la calificación [!UICONTROL segment].
   * Asigne el [!UICONTROL segment] a una carpeta de almacenamiento.

1. En la sección [Rasgos](../../features/segments/segment-builder.md#segment-builder-controls-traits):
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Busque el [!UICONTROL trait] que desea agregar a un segmento y haga clic en **[!UICONTROL Add Trait]**. Agregue otro [!UICONTROL trait] para crear un grupo [!UICONTROL trait].
   * Para visualizar el modal [!UICONTROL Advanced Search], haga clic en **[!UICONTROL Browse All Traits]**. Busque [!UICONTROL traits] por nombre, ID, descripción o [!UICONTROL data source]. Haga clic en una carpeta mientras busca para limitar los resultados a esa carpeta y sus subcarpetas. También puede filtrar [!UICONTROL traits] por [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] y [!UICONTROL Algorithmic]) o por tipo de población ([ID del dispositivo](../../reference/ids-in-aam.md) y [ID entre dispositivos](../../reference/ids-in-aam.md)).
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Obtenga recomendaciones de características [activas](trait-recommendations.md) a medida que crea su [!UICONTROL segment].
   * Haga clic y arrastre [!UICONTROL traits] para crear grupos separados.
   * Pase el ratón entre grupos para establecer relaciones con valores booleanos [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT].
   * Pase el ratón sobre el icono del reloj para añadir las reglas [actualización y frecuencia](../../features/segments/recency-and-frequency.md) a la [!UICONTROL trait].
   * Vea los datos de población del segmento a medida que agrega o elimina [!UICONTROL traits]. Haga clic en **[!UICONTROL Calculate Estimates]** para ver (o actualizar) los números de población estimados. Obtenga más información sobre [datos de población de segmentos](../../features/segments/segment-builder-data.md#segment-populations) en [!UICONTROL Segment Builder].
   * Haga clic en **[!UICONTROL Save]** cuando termine.

1. *(Opcional)* Asigne un  [!UICONTROL segment] a  [!UICONTROL destination] en la sección  [Asignación de ](../../features/segments/segment-builder.md#segment-builder-controls-destinations) destino :
   * Busque [!UICONTROL destination] y haga clic en **[!UICONTROL Add Destination]**. Tenga en cuenta que [!UICONTROL destination] ya debe existir antes de agregarlo a [!UICONTROL segment].
   * Haga clic en **[!UICONTROL Save]** cuando termine.

Vea el siguiente vídeo para obtener una vista detallada del funcionamiento de las métricas entre dispositivos.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] Controles:  [!UICONTROL Basic Information] Sección  {#segment-builder-controls-basics}

En [!UICONTROL Segment Builder], la configuración [!UICONTROL the Basic Information] permite crear nuevas características o editar las existentes. Para crear un nuevo [!UICONTROL segment], proporcione un nombre, un [!UICONTROL data source] y seleccione una carpeta de almacenamiento. Todos los demás campos son opcionales. Continúe en la sección [!UICONTROL Traits] cuando termine.

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
| **[!UICONTROL Name]** | Asigne un nombre corto y lógico al segmento que describa su función o propósito. Evite abreviaciones y caracteres especiales. La longitud máxima de un nombre de segmento es de 255 caracteres. |
| **[!UICONTROL Description]** | Campo para obtener información descriptiva adicional sobre el segmento. |
| **[!UICONTROL Integration Code]** | Campo para un ID definido por el usuario u otra información específica de la empresa. |
| **[!UICONTROL Data Source]** | Asocia el segmento a un proveedor de datos específico. <br> Utilice el primer menú desplegable para filtrar entre fuentes de datos de Audience Manager, grupos de informes de Adobe Analytics o ambos. A continuación, utilice el segundo menú desplegable para elegir el origen de los datos. <br> Si no utiliza grupos de informes de Adobe Analytics, el selector de tipo de fuente de datos se deshabilita y, de forma predeterminada, solo se usa como fuentes de datos de Audience Manager. |
| **[!UICONTROL Profile Merge Rule]** | Selecciona la regla de combinación de perfiles que se utilizará para la calificación de segmentos. |
| **[!UICONTROL Status]** | Activa o desactiva el segmento (activo de forma predeterminada). |
| **Almacenamiento de carpetas** | Determina a qué carpeta de almacenamiento pertenece el segmento. |

## [!UICONTROL Segment Builder] Controles:  [!UICONTROL Traits] Sección  {#segment-builder-controls-traits}

En [!UICONTROL Segment Builder], la sección [!UICONTROL Traits] permite administrar [!UICONTROL traits] en un [!UICONTROL segment], crear [!UICONTROL trait] grupos y establecer criterios de clasificación. Para agregar [!UICONTROL trait] a un [!UICONTROL segment], escriba el nombre [!UICONTROL trait] en el campo de búsqueda y haga clic en [!UICONTROL Add Trait]. Guarde el [!UICONTROL trait] (si ha terminado) o continúe con [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Requisitos previos:** complete los campos obligatorios de la  [!UICONTROL Basic Information] sección .

| Campo | Descripción |
|--- |--- |
| **[!UICONTROL Basic View]** | Esta sección proporciona controles visuales que le permiten: <ul><li>Cree nuevos y administre los [!UICONTROL segments] existentes.</li><li>Elimine [!UICONTROL traits] de un [!UICONTROL segment].</li><li>Agregue hasta 50 (máximo) [!UICONTROL traits] a [!UICONTROL segment].</li><li>Arrastre y suelte [!UICONTROL traits] para crear nuevos grupos.</li><li>Ver grupos [!UICONTROL traits] y [!UICONTROL trait] en un [!UICONTROL segment].</li><li>Establezca criterios de calificación con expresiones booleanas, operadores de comparación y ajustes de actualización/frecuencia.</li></ul> |
| **[!UICONTROL Code View]** | Abre un entorno de desarrollo que le permite crear y administrar [!UICONTROL traits], grupos y requisitos de calificación con código en lugar de con la interfaz visual. La vista de código es útil si su [!UICONTROL segments]: <ul><li>Contiene más de 50 [!UICONTROL traits] en un [!UICONTROL segment] individual. Nota: [!UICONTROL Segments] están limitados a 5000 [!UICONTROL traits] (máximo).</li><li>Contiene muchos grupos [!UICONTROL trait].</li><li>Tienen requisitos de calificación complejos.</li></ul> |
| Buscar | Ayuda a encontrar [!UICONTROL traits] para agregarlo a [!UICONTROL segment]. |
| Las actividades de | Obtenga recomendaciones activas para fuentes de datos similares [!UICONTROL traits], de [!UICONTROL traits] y [!UICONTROL Audience Marketplace] de origen a las que está suscrito. Agregue estas recomendaciones a la regla [!UICONTROL segment] para ampliar la audiencia. Obtenga más información en [Trait Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Obtenga recomendaciones activas para fuentes de datos similares [!UICONTROL traits] de [!UICONTROL Audience Marketplace] a las que no está suscrito. Obtenga más información en [Trait Recommendations](trait-recommendations.md). |
| Datos de tamaño [!UICONTROL Segment] reales y estimados | Consulte [Datos de tamaño de segmentos y rasgos en el Generador de segmentos](segment-builder-data.md) |

## Eliminar [!UICONTROL Traits] de un [!UICONTROL Segment] {#remove-traits}

La administración del [!UICONTROL traits] en su [!UICONTROL segments] es una parte importante para mantener el [!UICONTROL segments] viable. Siga estos pasos si necesita eliminar [!UICONTROL traits] de un [!UICONTROL segment].

Para quitar [!UICONTROL traits] de un [!UICONTROL segment]:

1. Vaya a **[!UICONTROL Audience Data > Segments]**. Desplácese por la lista o utilice la función de búsqueda para encontrar el [!UICONTROL segment] con el que desee trabajar.
2. Haga clic en el nombre [!UICONTROL segment] para abrir la pantalla de detalles [!UICONTROL segment] .
3. Haga clic en **Editar** para abrir [!UICONTROL Segment Builder] y, a continuación, haga clic en **Características** para abrir el panel [!UICONTROL traits].
4. Pase el ratón sobre el [!UICONTROL trait] que desea eliminar y haga clic en la X. Esta acción elimina inmediatamente el [!UICONTROL trait] de su [!UICONTROL segment].

## [!UICONTROL Segment Builder] Controles:  [!UICONTROL Destinations Mappings] Sección  {#segment-builder-controls-destinations}

En [!UICONTROL Segment Builder], la sección opcional [!UICONTROL Destinations Mapping] le permite enviar [!UICONTROL segment] datos a un [!DNL cookie], [!DNL URL] o [!UICONTROL server-to-server destination] de terceros. Para agregar un [!UICONTROL destination], busque (o busque) un [!UICONTROL destination], proporcione [!UICONTROL destination] información específica y haga clic en **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Requisitos previos

Rellene los campos obligatorios de las secciones [!UICONTROL Basic Information] y [!UICONTROL Traits] . Además, el destino ya debe existir.

### [!UICONTROL Destination Mappings] Herramientas de búsqueda

El panel **[!UICONTROL Destination Mappings]** contiene las herramientas de búsqueda que se describen en la tabla siguiente.

| Tipo de búsqueda | Descripción |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Permite buscar un [!UICONTROL destination] específico por su nombre. Para buscar, empiece a escribir. El campo se completará automáticamente en función de los términos de búsqueda. Haga clic en **[!UICONTROL Add Destination]** cuando termine. |
| **[!UICONTROL Browse All Destinations]** | Examine una lista de *todos* [!UICONTROL destinations] disponibles para usted. Seleccione y añada [!UICONTROL destinations] a su [!UICONTROL segment] en la lista emergente. |

## Campos en las ventanas emergentes [!UICONTROL Destination Mappings] {#fields-in-dest-mappings}

En [!UICONTROL Segment Builder], aparece el cuadro de diálogo [!UICONTROL Add Destination] después de seleccionar un [!UICONTROL destination]. Esta ventana muestra información estática sobre [!UICONTROL destination] y los campos que varían según el tipo [!UICONTROL destination]. Proporcione la información necesaria en los campos vacíos para configurar un [!UICONTROL destination mapping].

>[!NOTE]
>
>Las fechas de publicación son opcionales. Cuando está en blanco, el destino se activa y nunca caduca.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Campos

En los campos [!UICONTROL Destination Mapping] , especifique los pares clave-valor utilizados para enviar datos a [!UICONTROL destination]. Introduzca la clave en el primer campo y los valores en el segundo. Su elemento emergente [!UICONTROL cookie destination] podría tener un aspecto similar a este:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Campos

En los campos [!UICONTROL URL] y [!UICONTROL Secure URL] , especifique la dirección estándar o segura completa utilizada para enviar datos a [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Campos

En el campo [!UICONTROL Destination Value] especifique el valor (parte de un par clave-valor) utilizado para enviar datos a [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Crear un destino de cookie](../../features/destinations/create-cookie-destination.md)
* [Crear un destino de URL](../../features/destinations/create-url-destination.md)

