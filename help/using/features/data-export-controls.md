---
description: Los controles de exportación de datos impiden enviar datos a destinos cuando esta acción infringe los acuerdos de privacidad de datos o uso de datos.
seo-description: Los controles de exportación de datos impiden enviar datos a destinos cuando esta acción infringe los acuerdos de privacidad de datos o uso de datos.
seo-title: Controles de exportación de datos
solution: Audience Manager
title: Controles de exportación de datos
uuid: de 7 f 3608-c 0 cb -4049-973 a -8 be 54525 c 600
translation-type: tm+mt
source-git-commit: 302670f294574c3b56ccd16aeca8ebab8f4e8ce9

---


# Controles de exportación de datos {#data-export-controls}

[!UICONTROL Data Export Controls] impedir que envíe datos a destinos cuando esta acción infringe los acuerdos de privacidad de datos o uso de datos.

## Información general {#overview}

[!UICONTROL Data Export Controls] permiten clasificar [fuentes](../features/datasources-list-and-settings.md#data-sources-list-and-settings) y [destinos de datos](../features/destinations/destinations.md). Las clasificaciones que aplique determinan cuándo pueden exportarse o no los datos a un destino. Esta función consta de:

* **[!UICONTROL Data Export Controls]**: Puede definir Controles de exportación de datos en *fuentes de datos*. Cuando se configura en un origen de datos, estos controles restringen el uso de la fuente de datos y sus características.
* **[!UICONTROL Data Export Labels]**: Puede configurar Etiquetas de exportación de datos en *destinos*. Cuando se configura en un destino, estas etiquetas identifican cómo utiliza los datos el destino. See [Add Data Export Labels to a Destination](/help/using/features/destinations/manage-destinations.md#add-data-export-labels) to learn how to add export labels to a destination.

En función de las clasificaciones aplicadas a un origen de datos y a un destino, los controles de exportación se detienen de:

* Adición de un rasgo a un segmento cuando pertenece a un origen de datos que tiene un control de exportación de datos incompatible con una etiqueta de exportación de datos en uno o más de los destinos a los que se asigna el segmento.
For example, say a segment is mapped to a destination with the export label **[UICONTROL! This destination may enable a combination with personally identifiable information (PII)]**. Export controls stop you from adding a trait to that segment if the data source that the trait belongs to has a data export control that says **[UICONTROL! Cannot be tied to personally identifiable information (PII)]**.
* Enviar cualquier dato a un destino de destino tiene una etiqueta de exportación de datos bloqueada por un control de exportación de datos en cualquiera de los siguientes casos:
   * La fuente de datos de un rasgo incluido;
   * La fuente de datos de una característica que se utiliza en un segmento incluido;
   * La regla de combinación de perfiles aprovechada por un segmento incluido;
   * Cualquiera de las fuentes de datos que utiliza una regla de combinación de perfiles del segmento incluido.

[!UICONTROL Data Export Controls] están disponibles automáticamente para todos los clientes de Audience Manager. Sin embargo, necesita permisos de administrador para agregar controles de exportación a un origen de datos. Adding export labels to a destination requires administrator permissions *or* sufficient privileges to create or edit a destination.

## Controls and labels defined {#controls-labels}

[!UICONTROL Data Export Controls] proporcione los controles siguientes para ayudarle a clasificar las fuentes de datos y los destinos.

Para bloquear la entrega de datos, debe clasificar una fuente de datos con un control de exportación y agregar una etiqueta de exportación a un destino. Si aplica controles de exportación solo a un origen de datos o a un destino, esta función no restringirá la entrega de datos. When set on both the data source *and* destination, the export controls will limit the traits you can add to a segment and prevent sending the segment members to a destination.

Además, al menos una etiqueta de exportación debe coincidir con un control de exportación antes de que se apliquen las restricciones de entrega de datos. For example, say you add the [!UICONTROL PII] export control to a data source. A continuación, agregue la etiqueta de targeting in situ a un destino. En este caso, los controles de exportación no limitarán la entrega de datos porque la configuración no coincide. However, if you add the [!UICONTROL PII] export label to the destination, the export controls will block the export.

>[!IMPORTANT]
>
>[No se puede bloquear la exportación de un segmento colocando un control de exportación de datos en la fuente de datos del segmento, debe definir el control en cualquiera de las siguientes opciones:
> * Fuentes de datos de las características utilizadas en el segmento;
> * La regla de combinación de perfiles aprovechada por el segmento;
> * Cualquiera de las fuentes de datos que utiliza la regla de combinación de perfiles del segmento.


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Controles de exportación de datos para una fuente de datos </th> 
   <th colname="col2" class="entry"> Etiquetas de exportación de datos para un destino </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Sin restricción</span></b> </td> 
   <td colname="col2"> n.d. </td> 
   <td colname="col3"> De forma predeterminada, las restricciones de exportación no se establecen en fuentes de datos y destinos nuevos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> No se puede asociar a información de identificación personal</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> Este destino puede permitir una combinación con información personal (PII)</span></b> </td> 
   <td colname="col3">Cuando se selecciona, no puede: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Agregue características a segmentos asignados a destinos que utilicen PII. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Asigne segmentos creados con una característica del origen de datos a destinos que utilicen PII. </li> 
    </ul> <p>Esto suele ser necesario para proveedores de datos de terceros y al usar fuentes de datos que contienen información de seguimiento de anuncios o medios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> No se puede utilizar para objetivos publicitarios en el sitio</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Este destino puede utilizarse para objetivos publicitarios en el sitio</span></b> </td> 
   <td colname="col3">Cuando se selecciona, no puede: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Agregue características a segmentos asignados a destinos que personalicen la entrega de publicidad en función del historial de navegación web de un visitante. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Asigne segmentos creados con una característica del origen de datos a destinos que personalizan la entrega de publicidad en función del historial de navegación web de un visitante. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> No se puede utilizar para la segmentación fuera del sitio</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Este destino se puede utilizar para la segmentación fuera del sitio</span></b> </td> 
   <td colname="col3">Estas restricciones se utilizan generalmente con una opción Cuando se selecciona, no puede: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Agregue características a segmentos asignados a destinos que vuelvan a dirigirse a usuarios en otros sitios. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Asigne segmentos creados con una característica del origen de datos a destinos que redireccionan usuarios en otros sitios. </li> 
    </ul> <p>A menudo se requiere cuando se trabaja con datos de plataformas de medios sociales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> No se puede utilizar para personalización in situ</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Este destino puede utilizarse para personalización publicitaria en el sitio</span></b> </td> 
   <td colname="col3">Cuando se selecciona, no puede: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Agregue características a segmentos asignados a destinos que personalicen el contenido según los intereses del usuario o el historial de navegación Web. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Asigne segmentos creados con una característica del origen de datos a destinos que personalicen el contenido en función de los intereses del usuario o del historial de navegación web. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Flujo de trabajo {#workflow}

Para comenzar, revise la documentación de origen y fuente de datos. Estos artículos proporcionan instrucciones sobre cómo agregar controles y etiquetas de exportación a sus fuentes de datos y destinos.

* [Crear una fuente de datos](../features/manage-datasources.md#create-data-source)
* [Agregar etiquetas de exportación de datos a un destino](../features/destinations/manage-destinations.md#add-data-export-labels)