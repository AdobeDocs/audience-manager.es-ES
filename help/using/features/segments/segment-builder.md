---
description: Describe cómo crear segmentos con el Generador de segmentos.
seo-description: Describe cómo crear segmentos con el Generador de segmentos.
seo-title: Generador de segmentos
solution: Audience Manager
title: Generador de segmentos
uuid: 5 ca 924 a 5-2 b 29-4802-ab 02-e 292 d 77 a 0 aae
translation-type: tm+mt
source-git-commit: 2733080505760bbcf39737f0ad0d2d7605d1f477

---


# Generador de segmentos {#segment-builder}

Describe los pasos opcionales y requeridos que crean un segmento.[!UICONTROL Segment Builder]

## Demostración de vídeo

El siguiente vídeo lo lleva a través del proceso de creación de segmentos. Lea las secciones siguientes para obtener más información.

>[!VIDEO](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)

## Creación de segmentos {#create-segment}

### Sección Generador de segmentos

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] consiste en 3 secciones separadas: [!UICONTROL Basic Information], [!UICONTROL Traits]y [!UICONTROL Destinations Mapping]. Para crear un segmento, complete los campos obligatorios de [!UICONTROL Basic Information] las [!UICONTROL Traits] secciones y. [!UICONTROL Destinations Mapping] los ajustes son opcionales. Consulte las instrucciones siguientes para obtener más ayuda.

1. En [la sección Información](../../features/segments/segment-builder.md#segment-builder-controls-basics) básica:
   * Asigne un nombre al segmento. La longitud máxima de un nombre de segmento es de 255 caracteres.
   * Establezca el estado del segmento (activo es predeterminado).
   * Elija un origen de datos.
   * Seleccione una regla de combinación de perfiles para utilizarla para la cualificación de segmentos.
   * Asigne el segmento a una carpeta de almacenamiento.
1. En la sección [Características](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   * Busque la característica que desee agregar a un segmento y haga clic **[!UICONTROL Add Trait]** en. Agregue otro atributo para crear un grupo de características.
   * Haga clic en **[!UICONTROL Browse All Traits]** el modal de Búsqueda avanzada. Busque características por nombre, ID, descripción o fuente de datos. Haga clic en una carpeta mientras intenta limitar los resultados a esa carpeta y sus subcarpetas. También puede filtrar características por tipo de característica.
   * Obtenga recomendaciones [de rasgos en directo](trait-recommendations.md) a medida que crea su segmento.
   * Haga clic y arrastre características para crear grupos separados.
   * Pase el ratón entre grupos para establecer relaciones con booleano [!UICONTROL AND], [!UICONTROL OR][!UICONTROL AND NOT] valores.
   * Pase el ratón sobre el icono del reloj para agregar [reglas de actualización y](../../features/segments/recency-and-frequency.md) frecuencia a la característica.
   * Vea los datos de población de segmentos al agregar o eliminar características. Haga clic en **[!UICONTROL Calculate Estimates]** para ver (o actualizar) los números de población estimados. Obtenga más información sobre [los datos de población de segmentos](../../features/segments/segment-builder-data.md#segment-populations) en el Generador de segmentos.
   * Click **[!UICONTROL Save]** when done.
1. *(Opcional)* Asigne un segmento a un destino en la [sección Asignación](../../features/segments/segment-builder.md#segment-builder-controls-destinations) de destino:
   * Busque el destino y haga clic **[!UICONTROL Add Destination]** en. Tenga en cuenta que el destino ya debe existir antes de agregarlo a un segmento.
   * Click **[!UICONTROL Save]** when done.

## Controles del Generador de segmentos: Sección Información básica {#segment-builder-controls-basics}

En [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] la configuración permite crear nuevas características o editarlas. Para crear un nuevo segmento, proporcione un nombre, un origen de datos y seleccione una carpeta de almacenamiento. El resto de campos son opcionales. Se mueve a [!UICONTROL Traits] la sección cuando termine.

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

## Controles del Generador de segmentos: Sección Características {#segment-builder-controls-traits}

En [!UICONTROL Segment Builder]la, [!UICONTROL Traits] la sección le permite administrar características en un segmento, crear grupos de características y definir criterios de cualificación. Para agregar un rasgo a un segmento, escriba el nombre de característica en el campo de búsqueda y haga clic [!UICONTROL Add Trait]en. Guarde el rasgo (si se ha terminado) o desplácese hasta [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**Requisitos previos:** Complete los campos obligatorios de [!UICONTROL Basic Information] la sección.

| Campo | Descripción |
|--- |--- |
| Vista básica | Esta sección proporciona controles visuales que le permiten: <ul><li>Cree nuevos segmentos y administre los existentes.</li><li>Eliminar características de un segmento.</li><li>Añada hasta 50 características (máximo) a un segmento.</li><li>Arrastre y suelte características para crear nuevos grupos.</li><li>Ver características y grupos de rasgos en un segmento.</li><li>Establezca criterios de cualificación con expresiones booleanas, operadores de comparación y ajustes de actualización/frecuencia.</li></ul> |
| Vista de código | Abre un entorno de desarrollo que permite crear y administrar características, grupos y requisitos de cualificación con código en lugar de la interfaz visual. La vista de código es útil si sus segmentos: <ul><li>Contiene más de 50 características en un segmento individual. Nota: Los segmentos están limitados a 5000 características (máximo).</li><li>Contiene muchos grupos de características.</li><li>Tienen requisitos de cualificación complejos.</li></ul> |
| Buscar | Ayuda a encontrar características que agregar a un segmento. |
| Las actividades de | Obtener recomendaciones activas para características similares que se agregarán a la regla de segmentos. Obtenga más información en [Recomendaciones de características](trait-recommendations.md). |
| Datos de tamaño de segmento real y estimado | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Eliminar características de un segmento {#remove-traits}

La administración de características en los segmentos es una parte importante para mantener segmentos viables. Siga estos pasos si necesita eliminar características de un segmento.

Para eliminar características de un segmento:

1. Vaya a **Datos de audiencia &gt; Segmentos**. Desplácese por la lista o utilice la función de búsqueda para encontrar el segmento con el que desea trabajar.
2. Haga clic en el nombre del segmento para abrir la pantalla de detalles del segmento.
3. Haga clic **en Editar** para abrir el Generador de segmentos y, a continuación, haga clic **en Características** para abrir el panel de características.
4. Pase el ratón sobre la característica que desee eliminar y, a continuación, haga clic en la X. Esta acción elimina inmediatamente la característica del segmento.

## Controles del Generador de segmentos: Sección Asignaciones de destinos {#segment-builder-controls-destinations}

En [!UICONTROL Segment Builder], la sección opcional [!UICONTROL Destinations Mapping] permite enviar datos de segmentos a un destino [!DNL cookie][!DNL URL]de servidor a servidor o de servidor. Para agregar un destino, busque (o busque) un destino, proporcione información específica de destino y haga clic **[!UICONTROL Add Destination]** en.

<!-- r_segment_destinations_map.xml -->

### Requisitos previos

Complete los campos obligatorios de [!UICONTROL Basic Information] las [!UICONTROL Traits] secciones y. Asimismo, el destino ya debe existir.

### Herramientas de búsqueda de asignaciones de destino

**[!UICONTROL Destination Mappings]** El panel contiene herramientas de búsqueda como se describe en la siguiente tabla.

| Tipo de búsqueda | Descripción |
|---|---|
| **Buscar por nombre de destino** | Permite buscar un destino específico por nombre. Para buscar, empiece a escribir. El campo se completará automáticamente según los términos de búsqueda. Click **[!UICONTROL Add Destination]** when done. |
| **Examinar todos los destinos** | Busque una lista de *todos* los destinos disponibles. Seleccione y agregue destinos al segmento desde la lista emergente. |

## Campos en Ventanas emergentes de asignaciones de destino {#fields-in-dest-mappings}

En [!UICONTROL Segment Builder], el [!UICONTROL Add Destination] cuadro de diálogo aparece después de seleccionar un destino. Esta ventana muestra información estática sobre el destino y los campos que varían según el tipo de destino. Proporcione la información requerida en los campos vacíos para configurar una asignación de destino.

>[!NOTE]
>
>Las fechas de publicación son opcionales. Cuando está en blanco, el destino se activa y nunca caduca.

<!-- r_add_mappings_pop.xml -->

### Campos de destino de cookies

En [!UICONTROL Destination Mapping] los campos, especifique los pares de clave-valor utilizados para enviar datos al destino. Introduzca la clave del primer campo y los valores del segundo. El pop de destino de cookie podría tener un aspecto similar al siguiente:

![](assets/cookie_modal.PNG)

### Campos de destino de URL

En los campos [!UICONTROL URL] y [!UICONTROL Secure URL] los campos, especifique la dirección estándar completa o la dirección segura utilizada para enviar datos al destino.

![](assets/url_modal.PNG)

### Campos de destino de servidor a servidor

En [!UICONTROL Destination Value] el campo, especifique el valor (parte de un par de valor clave) utilizado para enviar datos al destino.

![](assets/s2s_modal.PNG)

>[!MORE_ LIKE_ THIS]
>
>* [Crear un destino de cookie](../../features/destinations/create-cookie-destination.md)
>* [Crear un destino de URL](../../features/destinations/create-url-destination.md)

