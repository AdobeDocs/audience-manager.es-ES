---
description: Describe cómo crear segmentos con el Generador de segmentos.
seo-description: Describe cómo crear segmentos con el Generador de segmentos.
seo-title: Generador de segmentos
solution: Audience Manager
title: Generador de segmentos
uuid: 5 ca 924 a 5-2 b 29-4802-ab 02-e 292 d 77 a 0 aae
translation-type: tm+mt
source-git-commit: b346dbe500f1e662c7b121a18c6cc0704ef3cfac

---


# Generador de segmentos {#segment-builder}

Describes the required and optional steps that create a segment in [!UICONTROL Segment Builder].

## Creación de segmentos {#create-segment}

### Sección Generador de segmentos

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] consiste en 3 secciones separadas: [!UICONTROL Basic Information], [!UICONTROL Traits]y [!UICONTROL Destinations Mapping]. To create a segment, complete the required fields in the [!UICONTROL Basic Information] and [!UICONTROL Traits] sections. [!UICONTROL Destinations Mapping] los ajustes son opcionales. Consulte las instrucciones siguientes para obtener más ayuda.

1. In the [Basic Information](../../features/segments/segment-builder.md#segment-builder-controls-basics) section:
   * Asigne un nombre al segmento. La longitud máxima de un nombre de segmento es de 255 caracteres.
   * Establezca el estado del segmento (activo es predeterminado).
   * Elija un origen de datos.
   * Seleccione una regla de combinación de perfiles para utilizarla para la cualificación de segmentos.
   * Asigne el segmento a una carpeta de almacenamiento.
1. In the [Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits) section:
   * Search for the trait you want to add to a segment and click **[!UICONTROL Add Trait]**. Agregue otro atributo para crear un grupo de características.
   * Bring up the Advanced Search modal by clicking **[!UICONTROL Browse All Traits]**. Busque características por nombre, ID, descripción o fuente de datos. Haga clic en una carpeta mientras intenta limitar los resultados a esa carpeta y sus subcarpetas. También puede filtrar características por tipo de característica.
   * Get live [trait recommendations](trait-recommendations.md) as you build your segment.
   * Haga clic y arrastre características para crear grupos separados.
   * Hover between groups to set relationships with Boolean [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] values.
   * Hover over the clock icon to add [recency and frequency](../../features/segments/recency-and-frequency.md) rules to the trait.
   * Vea los datos de población de segmentos al agregar o eliminar características. Click **[!UICONTROL Calculate Estimates]** to see (or refresh) the estimated population numbers. Read more about [segment population data](../../features/segments/segment-builder-data.md#segment-populations) in the Segment Builder.
   * Click **[!UICONTROL Save]** when done.
1. *(Opcional)* Asigne un segmento a un destino en la [sección Asignación](../../features/segments/segment-builder.md#segment-builder-controls-destinations) de destino:
   * Search for the destination and click **[!UICONTROL Add Destination]**. Tenga en cuenta que el destino ya debe existir antes de agregarlo a un segmento.
   * Click **[!UICONTROL Save]** when done.

## Segment Builder Controls: Basic Information Section {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] settings let you create new, or edit existing traits. Para crear un nuevo segmento, proporcione un nombre, un origen de datos y seleccione una carpeta de almacenamiento. El resto de campos son opcionales. Move on to the [!UICONTROL Traits] section when done.

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
   <td colname="col2"> <p>Asigne un nombre lógico a un segmento que describa su función u objetivo. Evite abreviaciones y caracteres especiales. La longitud máxima de un nombre de segmento es de 255 caracteres. </p> </td> 
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
   <td colname="col2"> <p>Asocia el segmento con un proveedor de datos específico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Regla de combinación de perfiles</b> </td> 
   <td colname="col2"> <p>Selecciona la regla de combinación de perfiles para utilizarla para la cualificación de segmentos. </p> </td> 
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

## Segment Builder Controls: Traits Section {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], the [!UICONTROL Traits] section lets you manage traits in a segment, create trait groups, and set qualification criteria. To add a trait to a segment, type the trait name in the search field and click [!UICONTROL Add Trait]. Save the trait (if finished) or move on to [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**Requisitos previos:** Complete los campos obligatorios de [!UICONTROL Basic Information] la sección.

| Campo | Descripción |
|--- |--- |
| Vista básica | Esta sección proporciona controles visuales que le permiten: <ul><li>Cree nuevos segmentos y administre los existentes.</li><li>Eliminar características de un segmento.</li><li>Añada hasta 50 características (máximo) a un segmento.</li><li>Arrastre y suelte características para crear nuevos grupos.</li><li>Ver características y grupos de rasgos en un segmento.</li><li>Establezca criterios de cualificación con expresiones booleanas, operadores de comparación y ajustes de actualización/frecuencia.</li></ul> |
| Vista de código | Abre un entorno de desarrollo que permite crear y administrar características, grupos y requisitos de cualificación con código en lugar de la interfaz visual. La vista de código es útil si sus segmentos: <ul><li>Contiene más de 50 características en un segmento individual. Nota: Los segmentos están limitados a 5000 características (máximo).</li><li>Contiene muchos grupos de características.</li><li>Tienen requisitos de cualificación complejos.</li></ul> |
| Buscar | Ayuda a encontrar características que agregar a un segmento. |
| Las actividades de | Obtener recomendaciones activas para características similares que se agregarán a la regla de segmentos. Read more in [Trait Recommendations](trait-recommendations.md). |
| Datos de tamaño de segmento real y estimado | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Remove Traits from a Segment {#remove-traits}

La administración de características en los segmentos es una parte importante para mantener segmentos viables. Siga estos pasos si necesita eliminar características de un segmento.

Para eliminar características de un segmento:

1. Go to **Audience Data &gt; Segments**. Desplácese por la lista o utilice la función de búsqueda para encontrar el segmento con el que desea trabajar.
2. Haga clic en el nombre del segmento para abrir la pantalla de detalles del segmento.
3. Click **Edit** to open Segment Builder and then click **Traits** to open the traits panel.
4. Pase el ratón sobre la característica que desee eliminar y, a continuación, haga clic en la X. Esta acción elimina inmediatamente la característica del segmento.

## Segment Builder Controls: Destinations Mappings Section {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], the optional [!UICONTROL Destinations Mapping] section lets you send segment data to a third-party [!DNL cookie], [!DNL URL], or server-to-server destination. To add a destination, search (or browse) for a destination, provide destination specific information, and click **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Requisitos previos

Complete the required fields in the [!UICONTROL Basic Information] and [!UICONTROL Traits] sections. Asimismo, el destino ya debe existir.

### Herramientas de búsqueda de asignaciones de destino

**[!UICONTROL Destination Mappings]** El panel contiene herramientas de búsqueda como se describe en la siguiente tabla.

| Tipo de búsqueda | Descripción |
|---|---|
| **Buscar por nombre de destino** | Permite buscar un destino específico por nombre. Para buscar, empiece a escribir. El campo se completará automáticamente según los términos de búsqueda. Click **[!UICONTROL Add Destination]** when done. |
| **Examinar todos los destinos** | Browse a list of *all* destinations available to you. Seleccione y agregue destinos al segmento desde la lista emergente. |

## Fields in the Destination Mappings Pop-up Windows {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], the [!UICONTROL Add Destination] dialog appears after you select a destination. Esta ventana muestra información estática sobre el destino y los campos que varían según el tipo de destino. Proporcione la información requerida en los campos vacíos para configurar una asignación de destino.

>[!NOTE]
>
>Las fechas de publicación son opcionales. Cuando está en blanco, el destino se activa y nunca caduca.

<!-- r_add_mappings_pop.xml -->

### Campos de destino de cookies

In the [!UICONTROL Destination Mapping] fields, specify the key-value pairs used to send data to the destination. Introduzca la clave del primer campo y los valores del segundo. El pop de destino de cookie podría tener un aspecto similar al siguiente:

![](assets/cookie_modal.PNG)

### Campos de destino de URL

In the [!UICONTROL URL] and [!UICONTROL Secure URL] fields, specify the complete standard or secure address used to send data to the destination.

![](assets/url_modal.PNG)

### Campos de destino de servidor a servidor

In the [!UICONTROL Destination Value] field specify the value (part of a key-value pair) used to send data to the destination.

![](assets/s2s_modal.PNG)

>[!MORE_ LIKE_ THIS]
>
>* [Crear un destino de cookie](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [Crear un destino de URL](../../features/destinations/manage-destinations.md#configure-url-destination)

