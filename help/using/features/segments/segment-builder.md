---
description: Describe cómo crear segmentos con el Generador de segmentos.
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: Generador de segmentos
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 2%

---

# [!UICONTROL Segment Builder] {#segment-builder}

Describe los pasos opcionales y requeridos para crear un segmento en [!UICONTROL Segment Builder].

## Demostración en vídeo

Comience por ver el vídeo [Crear segmentos en Audience Manager](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). El vídeo lo acompaña durante el proceso de creación de segmentos. Lea las secciones siguientes para obtener más información.

## Crear un(a) [!UICONTROL Segment] {#create-segment}

### Sección del Generador de segmentos

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] consta de 3 secciones independientes: [!UICONTROL Basic Information], [!UICONTROL Traits] y [!UICONTROL Destinations Mapping]. Para crear un(a) [!UICONTROL segment], complete los campos obligatorios en las secciones [!UICONTROL Basic Information] y [!UICONTROL Traits]. La configuración de [!UICONTROL Destinations Mapping] es opcional. Consulte las instrucciones siguientes para obtener ayuda adicional.

1. En la sección [Información básica](../../features/segments/segment-builder.md#segment-builder-controls-basics):

   ![create-segment](assets/create-segment.png)

   * Asigne un nombre a [!UICONTROL segment]. La longitud máxima de un nombre de [!UICONTROL segment] es de 255 caracteres.
   * Establecer el estado [!UICONTROL segment] (activo de forma predeterminada).
   * Elija un [!UICONTROL data source]. Utilice el primer menú desplegable para filtrar entre Audience Manager [!UICONTROL data sources], grupos de informes de Adobe Analytics o ambos. A continuación, utilice el segundo menú desplegable para elegir su [!UICONTROL data source]. Si no usa grupos de informes de Adobe Analytics, el selector de tipo [!UICONTROL data source] se deshabilita y se establece de forma predeterminada solo en las fuentes de datos de Audience Manager.
   * Seleccione un(a) [!UICONTROL profile merge rule] para usar en la calificación [!UICONTROL segment].
   * Asignar [!UICONTROL segment] a una carpeta de almacenamiento.

1. En la sección [Características](../../features/segments/segment-builder.md#segment-builder-controls-traits):
   ![rasgos del generador de segmentos](assets/segment-builder-traits.png)
   * Busque el(la) [!UICONTROL trait] que desee agregar a un segmento y haga clic en **[!UICONTROL Add Trait]**. Agregar otro(a) [!UICONTROL trait] para crear un grupo [!UICONTROL trait].
   * Visualice el modal [!UICONTROL Advanced Search] haciendo clic en **[!UICONTROL Browse All Traits]**. Busque [!UICONTROL traits] por nombre, ID, descripción o [!UICONTROL data source]. Haga clic en una carpeta mientras busca para limitar los resultados a esa carpeta y sus subcarpetas. También puede filtrar [!UICONTROL traits] por [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] y [!UICONTROL Algorithmic]) o tipo de población ([ID de dispositivo](../../reference/ids-in-aam.md) e [ID entre dispositivos](../../reference/ids-in-aam.md)).
     ![rasgos del explorador-generador-de-segmentos](assets/segment-builder-browse-traits.png)
   * Recibe [recomendaciones de características](trait-recommendations.md) mientras creas tu [!UICONTROL segment].
   * Haga clic y arrastre [!UICONTROL traits] para crear grupos separados.
   * Pase el ratón sobre los grupos para establecer relaciones con los valores booleanos [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT].
   * Pase el ratón sobre el icono del reloj para agregar [reglas de actualización y frecuencia](../../features/segments/recency-and-frequency.md) a [!UICONTROL trait].
   * Vea los datos de población de segmentos a medida que agrega o quita [!UICONTROL traits]. Haga clic en **[!UICONTROL Calculate Estimates]** para ver (o actualizar) los números de población estimados. Obtenga más información sobre [datos de población de segmentos](../../features/segments/segment-builder-data.md#segment-populations) en [!UICONTROL Segment Builder].
   * Haga clic en **[!UICONTROL Save]** cuando termine.

1. *(Opcional)* Asigne un [!UICONTROL segment] a un [!UICONTROL destination] en la sección [Asignación de destino](../../features/segments/segment-builder.md#segment-builder-controls-destinations):
   * Busque [!UICONTROL destination] y haga clic en **[!UICONTROL Add Destination]**. Tenga en cuenta que [!UICONTROL destination] ya debe existir para poder agregarlo a [!UICONTROL segment].
   * Haga clic en **[!UICONTROL Save]** cuando termine.

Vea el siguiente vídeo para obtener una visión detallada de cómo funcionan las métricas entre dispositivos.

>[!VIDEO](https://video.tv.adobe.com/v/36789?captions=spa)

## [!UICONTROL Segment Builder] Controles: Sección [!UICONTROL Basic Information] {#segment-builder-controls-basics}

En [!UICONTROL Segment Builder], la configuración de [!UICONTROL the Basic Information] le permite crear características nuevas o editar las existentes. Para crear un(a) nuevo(a) [!UICONTROL segment], proporcione un nombre, un(a) [!UICONTROL data source], y seleccione una carpeta de almacenamiento. El resto de campos son opcionales. Pasar a la sección [!UICONTROL Traits] cuando termine.

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
| **[!UICONTROL Name]** | Asigne al segmento un nombre corto y lógico que describa su función o propósito. Evite las abreviaciones y los caracteres especiales. La longitud máxima de un nombre de segmento es de 255 caracteres. |
| **[!UICONTROL Description]** | Campo para obtener información descriptiva adicional sobre el segmento. |
| **[!UICONTROL Integration Code]** | Campo para un ID definido por el usuario u otra información específica de la compañía. |
| **[!UICONTROL Data Source]** | Asocia el segmento con un proveedor de datos específico. <br> Utilice el primer menú desplegable para filtrar entre orígenes de datos de Audience Manager, grupos de informes de Adobe Analytics o ambos. A continuación, utilice el segundo menú desplegable para elegir la fuente de datos. <br> Si no usa grupos de informes de Adobe Analytics, el selector de tipo de origen de datos estará deshabilitado y solo tendrá valores predeterminados en las fuentes de datos de Audience Manager. |
| **[!UICONTROL Profile Merge Rule]** | Selecciona la regla de combinación de perfiles que se utilizará para la calificación de segmentos. |
| **[!UICONTROL Status]** | Activa o desactiva el segmento (activo de forma predeterminada). |
| **Almacenamiento de carpetas** | Determina a qué carpeta de almacenamiento pertenece el segmento. |

## [!UICONTROL Segment Builder] Controles: Sección [!UICONTROL Traits] {#segment-builder-controls-traits}

En [!UICONTROL Segment Builder], la sección [!UICONTROL Traits] le permite administrar [!UICONTROL traits] en un [!UICONTROL segment], crear [!UICONTROL trait] grupos y establecer criterios de calificación. Para agregar un [!UICONTROL trait] a un [!UICONTROL segment], escriba el nombre de [!UICONTROL trait] en el campo de búsqueda y haga clic en [!UICONTROL Add Trait]. Guarde [!UICONTROL trait] (si ha finalizado) o continúe con [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Requisitos previos:** Complete los campos requeridos en la sección [!UICONTROL Basic Information].

| Campo | Descripción |
|--- |--- |
| **[!UICONTROL Basic View]** | Esta sección proporciona controles visuales que le permiten: <ul><li>Generar nuevo y administrar [!UICONTROL segments] existente.</li><li>Quitar [!UICONTROL traits] de [!UICONTROL segment].</li><li>Agregar hasta 50 (máximo) [!UICONTROL traits] a [!UICONTROL segment].</li><li>Arrastre y suelte [!UICONTROL traits] para crear nuevos grupos.</li><li>Ver [!UICONTROL traits] y [!UICONTROL trait] grupos en un [!UICONTROL segment].</li><li>Defina criterios de calificación con expresiones booleanas, operadores de comparación y configuración de actualización/frecuencia.</li></ul> |
| **[!UICONTROL Code View]** | Abre un entorno de desarrollo que le permite crear y administrar [!UICONTROL traits], grupos y requisitos de calificación con código en lugar de la interfaz visual. La vista de código resulta útil si su [!UICONTROL segments]: <ul><li>Incluir más de 50 [!UICONTROL traits] en un(a) [!UICONTROL segment] individual(a). Nota: [!UICONTROL Segments] están limitadas a 5000 [!UICONTROL traits] (máximo).</li><li>Contiene muchos [!UICONTROL trait] grupos.</li><li>Tiene requisitos de cualificación complejos.</li></ul> |
| Buscar | Ayuda a encontrar [!UICONTROL traits] para agregar a [!UICONTROL segment]. |
| Las actividades de | Obtenga recomendaciones activas para [!UICONTROL traits] similares de sus fuentes de datos de origen [!UICONTROL traits] y [!UICONTROL Audience Marketplace] a las que está suscrito. Agregue estas recomendaciones a la regla [!UICONTROL segment] para expandir su audiencia. Obtenga más información en [Recomendaciones de características](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Obtenga recomendaciones activas para [!UICONTROL traits] similares, desde [!UICONTROL Audience Marketplace] fuentes de datos a las que no está suscrito. Obtenga más información en [Recomendaciones de características](trait-recommendations.md). |
| Datos de tamaño real y estimado de [!UICONTROL Segment] | Consulte [Datos de tamaño de segmentos y rasgos en el Generador de segmentos](segment-builder-data.md) |

## Quitar [!UICONTROL Traits] de [!UICONTROL Segment] {#remove-traits}

Administrar [!UICONTROL traits] en [!UICONTROL segments] es una parte importante para mantener la viabilidad de [!UICONTROL segments]. Siga estos pasos si necesita quitar [!UICONTROL traits] de un(a) [!UICONTROL segment].

Para quitar [!UICONTROL traits] de [!UICONTROL segment]:

1. Ir a **[!UICONTROL Audience Data > Segments]**. Desplácese por la lista o use la característica de búsqueda para encontrar el(la) [!UICONTROL segment] con el(la) que desea trabajar.
2. Haga clic en el nombre de [!UICONTROL segment] para abrir la pantalla de detalles de [!UICONTROL segment].
3. Haga clic en **Editar** para abrir [!UICONTROL Segment Builder] y, a continuación, haga clic en **Características** para abrir el panel [!UICONTROL traits].
4. Pase el ratón sobre el(la) [!UICONTROL trait] que quiera eliminar y luego haga clic en la X. Esta acción elimina inmediatamente [!UICONTROL trait] de su [!UICONTROL segment].

## [!UICONTROL Segment Builder] Controles: Sección [!UICONTROL Destinations Mappings] {#segment-builder-controls-destinations}

En [!UICONTROL Segment Builder], la sección opcional [!UICONTROL Destinations Mapping] le permite enviar datos de [!UICONTROL segment] a [!DNL cookie], [!DNL URL] o [!UICONTROL server-to-server destination] de terceros. Para agregar un(a) [!UICONTROL destination], busque (o examine) un(a) [!UICONTROL destination], proporcione [!UICONTROL destination] información específica y haga clic en **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Requisitos previos

Rellene los campos obligatorios de las secciones [!UICONTROL Basic Information] y [!UICONTROL Traits]. Además, el destino ya debe existir.

### [!UICONTROL Destination Mappings] herramientas de búsqueda

El panel **[!UICONTROL Destination Mappings]** contiene herramientas de búsqueda como se describe en la tabla siguiente.

| Tipo de búsqueda | Descripción |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Le permite buscar un(a) [!UICONTROL destination] específico(a) por nombre. Para buscar, empiece a escribir. El campo se completará automáticamente en función de los términos de búsqueda. Haga clic en **[!UICONTROL Add Destination]** cuando termine. |
| **[!UICONTROL Browse All Destinations]** | Examine una lista de *todos* los [!UICONTROL destinations] disponibles para usted. Seleccione y agregue [!UICONTROL destinations] a su [!UICONTROL segment] desde la lista emergente. |

## Campos en las ventanas emergentes [!UICONTROL Destination Mappings] {#fields-in-dest-mappings}

En [!UICONTROL Segment Builder], el cuadro de diálogo [!UICONTROL Add Destination] aparece después de seleccionar [!UICONTROL destination]. Esta ventana muestra información estática sobre [!UICONTROL destination] y campos que varían según el tipo [!UICONTROL destination]. Proporcione la información requerida en los campos vacíos para configurar un(a) [!UICONTROL destination mapping].

>[!NOTE]
>
>Las fechas de publicación son opcionales. Cuando está en blanco, el destino se activa y nunca caduca.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] campos

En los campos [!UICONTROL Destination Mapping], especifique los pares clave-valor utilizados para enviar datos a [!UICONTROL destination]. Introduzca la clave en el primer campo y los valores en el segundo. Su elemento emergente [!UICONTROL cookie destination] podría tener un aspecto similar al siguiente:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] campos

En los campos [!UICONTROL URL] y [!UICONTROL Secure URL], especifique la dirección estándar o segura completa utilizada para enviar datos a [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] campos

En el campo [!UICONTROL Destination Value] especifique el valor (parte de un par clave-valor) utilizado para enviar datos a [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Crear un destino de cookie](../../features/destinations/create-cookie-destination.md)
>* [Crear un destino de URL](../../features/destinations/create-url-destination.md)
