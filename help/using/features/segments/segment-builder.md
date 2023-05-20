---
description: Describe cómo crear segmentos con el generador de segmentos.
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: Generador de segmentos
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 2%

---

# [!UICONTROL Segment Builder] {#segment-builder}

Describe los pasos opcionales y requeridos en [!UICONTROL Segment Builder] los que se crea un segmento.

## Demostración de Vídeo

Comience por ver la [Creación de segmentos en vídeo de Audience Manager](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). El vídeo le guía a través del proceso de creación de segmento. Lea las secciones siguientes para obtener más información.

## Cree un [!UICONTROL Segment] {#create-segment}

### Sección del generador de segmentos

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] consta de 3 secciones separadas: [!UICONTROL Basic Information] , [!UICONTROL Traits] , y [!UICONTROL Destinations Mapping] . Para crear un [!UICONTROL segment] , complete los campos requeridos en las [!UICONTROL Basic Information] secciones y [!UICONTROL Traits] . [!UICONTROL Destinations Mapping] La configuración de es opcional. Consulte las instrucciones siguientes para obtener ayuda adicional.

1. En el [Información básica](../../features/segments/segment-builder.md#segment-builder-controls-basics) sección:

   ![create-segment](assets/create-segment.png)

   * Asigne un nombre al [!UICONTROL segment]. La longitud máxima de un [!UICONTROL segment] el nombre tiene 255 caracteres.
   * Configure las variables [!UICONTROL segment] estado (activo de forma predeterminada).
   * Elija un [!UICONTROL data source] . Utilice el primer menú desplegable para filtrar entre Audience Manager [!UICONTROL data sources], grupos de informes de Adobe Analytics o ambos. A continuación, utilice el segundo menú desplegable para elegir su [!UICONTROL data source]. Si no utiliza grupos de informes de Adobe Analytics, la variable [!UICONTROL data source] el selector de tipo está desactivado y solo se usan de forma predeterminada fuentes de datos de Audience Manager.
   * Seleccione una [!UICONTROL profile merge rule] para usar en [!UICONTROL segment] calificación.
   * Asigne el [!UICONTROL segment] a una carpeta de almacenamiento.

1. En el [Características](../../features/segments/segment-builder.md#segment-builder-controls-traits) sección:
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Busque la variable [!UICONTROL trait] desea añadir a un segmento y haga clic en **[!UICONTROL Add Trait]**. Añadir otro [!UICONTROL trait] para crear un [!UICONTROL trait] grupo.
   * Traiga el [!UICONTROL Advanced Search] modal haciendo clic en **[!UICONTROL Browse All Traits]**. Buscar por [!UICONTROL traits] por nombre, ID, descripción o [!UICONTROL data source]. Haga clic en una carpeta mientras busca para limitar los resultados a esa carpeta y sus subcarpetas. También puede filtrar [!UICONTROL traits] por [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded], y [!UICONTROL Algorithmic]) o tipo de población ([ID de dispositivo](../../reference/ids-in-aam.md) y [ID entre dispositivos](../../reference/ids-in-aam.md)).
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Activar [recomendaciones de rasgos](trait-recommendations.md) a medida que crea su [!UICONTROL segment].
   * Haga clic y arrastre [!UICONTROL traits] para crear grupos separados.
   * Pase el ratón entre grupos para establecer relaciones con Boolean [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] valores.
   * Pase el ratón sobre el icono del reloj para añadir [actualización y frecuencia](../../features/segments/recency-and-frequency.md) reglas para [!UICONTROL trait].
   * Ver datos de población de segmentos a medida que agrega o elimina [!UICONTROL traits]. Clic **[!UICONTROL Calculate Estimates]** para ver (o actualizar) los números de población estimados. Más información sobre [datos de población de segmentos](../../features/segments/segment-builder-data.md#segment-populations) en el [!UICONTROL Segment Builder].
   * Clic **[!UICONTROL Save]** cuando termine.

1. *(Opcional)* Asignar a [!UICONTROL segment] a un [!UICONTROL destination] en el [Asignación de destino](../../features/segments/segment-builder.md#segment-builder-controls-destinations) sección:
   * Busque la variable [!UICONTROL destination] y haga clic en **[!UICONTROL Add Destination]**. Tenga en cuenta que [!UICONTROL destination] ya debe existir antes de poder agregarlo a un [!UICONTROL segment].
   * Clic **[!UICONTROL Save]** cuando termine.

Vea el siguiente vídeo para obtener una visión detallada de cómo funcionan las métricas entre dispositivos.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] Controles: [!UICONTROL Basic Information] Sección {#segment-builder-controls-basics}

Entrada [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] La configuración de permite crear rasgos nuevos o editar los existentes. Para crear un nuevo [!UICONTROL segment], proporcione un nombre, un [!UICONTROL data source]y seleccione una carpeta de almacenamiento. El resto de campos son opcionales. Continúe con el [!UICONTROL Traits] cuando haya terminado.

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
| **[!UICONTROL Name]** | Dé a la segmento un nombre corto, lógico que describe su función o propósito. Evite abreviaciones y caracteres especiales. La longitud máxima de un nombre de segmento es de 255 caracteres. |
| **[!UICONTROL Description]** | Un campo para obtener información descriptiva adicional sobre la segmento. |
| **[!UICONTROL Integration Code]** | Campo para un ID usuario definido u otra información específica de compañía. |
| **[!UICONTROL Data Source]** | Asocia el segmento con un proveedor de datos específico. <br> Utilice el primer menú desplegable para filtrar entre fuentes de datos del Audience Manager, grupos de informes de Adobe Analytics o ambos. A continuación, utilice el segundo menú desplegable para elegir la fuente de datos. <br> Si no utiliza grupos de informes de Adobe Analytics, el selector de tipo de fuente de datos está desactivado y solo tiene valores predeterminados de fuentes de datos de Audience Manager. |
| **[!UICONTROL Profile Merge Rule]** | Selecciona la regla de combinación de perfiles que se utilizará para la calificación de segmentos. |
| **[!UICONTROL Status]** | Activa o desactiva el segmento (activo de forma predeterminada). |
| **Almacenamiento de carpetas** | Determina a qué carpeta de almacenamiento pertenece el segmento. |

## [!UICONTROL Segment Builder] Controles: [!UICONTROL Traits] Sección {#segment-builder-controls-traits}

Entrada [!UICONTROL Segment Builder], el [!UICONTROL Traits] le permite administrar [!UICONTROL traits] en un [!UICONTROL segment], crear [!UICONTROL trait] grupos y establezca criterios de cualificación. Para agregar un [!UICONTROL trait] a un [!UICONTROL segment], escriba el [!UICONTROL trait] en el campo de búsqueda y haga clic en [!UICONTROL Add Trait]. Guarde el [!UICONTROL trait] (si ha finalizado) o continúe con [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Requisitos previos:** Rellene los campos obligatorios en la [!UICONTROL Basic Information] sección.

| Campo | Descripción |
|--- |--- |
| **[!UICONTROL Basic View]** | Esta sección proporciona controles visuales que permiten: <ul><li>Crear nuevos y administrar existentes [!UICONTROL segments] .</li><li>Quitar [!UICONTROL traits] de a [!UICONTROL segment] .</li><li>Añadir hasta 50 (máximo) [!UICONTROL traits] a [!UICONTROL segment] .</li><li>Arrastre y suelte [!UICONTROL traits] para crear nuevos grupos.</li><li>Ver [!UICONTROL traits] y [!UICONTROL trait] grupos en un [!UICONTROL segment] .</li><li>Establezca criterios de calificación con Expresiones booleanas, operadores de comparación y ajustes de actualización/Frecuencia.</li></ul> |
| **[!UICONTROL Code View]** | Abre una entorno de desarrollo que permite crear y administrar [!UICONTROL traits] , grupos y calificar requisitos con código en lugar de la interfaz visual. El código vista es útil si [!UICONTROL segments] : <ul><li>Contiene más de 50 [!UICONTROL traits] en un individuo [!UICONTROL segment] . Nota: [!UICONTROL Segments] está limitado a 5000 [!UICONTROL traits] (máximo).</li><li>Contiene muchos [!UICONTROL trait] grupos.</li><li>Tiene requisitos de cualificación complejos.</li></ul> |
| Buscar | Ayuda a encontrar [!UICONTROL traits] para agregar a [!UICONTROL segment]. |
| Las actividades de | Obtener recomendaciones en directo para productos similares [!UICONTROL traits], desde su origen [!UICONTROL traits] y [!UICONTROL Audience Marketplace] fuentes de datos a las que está suscrito. Añada estas recomendaciones a [!UICONTROL segment] para ampliar la audiencia. Más información en [Recommendations de rasgos](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Obtener recomendaciones en directo para productos similares [!UICONTROL traits], desde [!UICONTROL Audience Marketplace] fuentes de datos a las que no está suscrito. Más información en [Recommendations de rasgos](trait-recommendations.md). |
| Real y Estimado [!UICONTROL Segment] Datos de tamaño | Consulte [Datos de tamaño de segmentos y rasgos en el Generador de segmentos](segment-builder-data.md) |

## Eliminar [!UICONTROL Traits] de a [!UICONTROL Segment] {#remove-traits}

Administración de [!UICONTROL traits] en su [!UICONTROL segments] es una parte importante de mantener [!UICONTROL segments] viable. Siga estos pasos si necesita eliminar [!UICONTROL traits] de a [!UICONTROL segment].

Para eliminar [!UICONTROL traits] de a [!UICONTROL segment]:

1. Ir a **[!UICONTROL Audience Data > Segments]**. Desplácese por la lista o utilice la función de búsqueda para encontrar el [!UICONTROL segment] desea trabajar con.
2. Haga clic en [!UICONTROL segment] nombre para abrir [!UICONTROL segment] pantalla de detalles.
3. Clic **Editar** para abrir [!UICONTROL Segment Builder] y luego haga clic en **Características** para abrir [!UICONTROL traits] panel.
4. Pase el ratón sobre [!UICONTROL trait] desea eliminar y, a continuación, haga clic en la X. Esta acción elimina inmediatamente el [!UICONTROL trait] de su [!UICONTROL segment].

## [!UICONTROL Segment Builder] Controles: [!UICONTROL Destinations Mappings] Sección {#segment-builder-controls-destinations}

Entrada [!UICONTROL Segment Builder], el opcional [!UICONTROL Destinations Mapping] La sección le permite enviar [!UICONTROL segment] datos a un tercero [!DNL cookie], [!DNL URL], o [!UICONTROL server-to-server destination]. Para agregar un [!UICONTROL destination], busque (o examine) un [!UICONTROL destination], proporcionar [!UICONTROL destination] información específica y haga clic en **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Requisitos previos

Rellene los campos obligatorios en la [!UICONTROL Basic Information] y [!UICONTROL Traits] secciones. Además, el destino ya debe existir.

### [!UICONTROL Destination Mappings] Herramientas de búsqueda

El **[!UICONTROL Destination Mappings]** El panel contiene herramientas de búsqueda como se describe en la tabla siguiente.

| Tipo de búsqueda | Descripción |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Le permite buscar un elemento específico [!UICONTROL destination] por nombre. Para buscar, empiece a escribir. El campo se completará automáticamente en función de los términos de búsqueda. Clic **[!UICONTROL Add Destination]** cuando termine. |
| **[!UICONTROL Browse All Destinations]** | Examen de una lista de *todo* [!UICONTROL destinations] disponible para usted. Seleccionar y añadir [!UICONTROL destinations] a su [!UICONTROL segment] de la lista emergente. |

## Campos en la [!UICONTROL Destination Mappings] Ventanas emergentes {#fields-in-dest-mappings}

Entrada [!UICONTROL Segment Builder], el [!UICONTROL Add Destination] El cuadro de diálogo aparece después de seleccionar una [!UICONTROL destination]. Esta ventana muestra información estática sobre el [!UICONTROL destination] y campos que varían según la variable [!UICONTROL destination] escriba. Proporcione la información necesaria en los campos vacíos para configurar una [!UICONTROL destination mapping].

>[!NOTE]
>
>Las fechas de publicación son opcionales. Cuando está en blanco, el destino se activa y nunca caduca.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Campos

En el [!UICONTROL Destination Mapping] campos, especifique los pares de clave-valor utilizados para enviar datos al [!UICONTROL destination]. Introduzca la clave en el primer campo y los valores en el segundo. Su [!UICONTROL cookie destination] pop podría tener un aspecto similar al siguiente:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Campos

En el [!UICONTROL URL] y [!UICONTROL Secure URL] campos, especifique la dirección estándar o segura completa utilizada para enviar datos al [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Campos

En el [!UICONTROL Destination Value] especifique el valor (parte de un par clave-valor) utilizado para enviar datos al [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Crear un destino de cookie](../../features/destinations/create-cookie-destination.md)
>* [Crear un destino de URL](../../features/destinations/create-url-destination.md)

