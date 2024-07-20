---
description: Los controles de exportación de datos impiden el envío de datos a destinos cuando esta acción infringe los acuerdos de privacidad o uso de datos.
seo-description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-title: Data Export Controls
solution: Audience Manager
title: Controles de exportación de datos
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: 26aa0a210a045b40b2329844324315a092947188
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 1%

---

# Controles de exportación de datos {#data-export-controls}

[!UICONTROL Data Export Controls] le impide enviar datos a destinos cuando esta acción infringe los acuerdos de privacidad o uso de datos.

## Información general {#overview}

[!UICONTROL Data Export Controls] le permite clasificar [orígenes de datos](../features/datasources-list-and-settings.md#data-sources-list-and-settings) y [destinos](../features/destinations/destinations.md). Las clasificaciones que aplique determinan cuándo se pueden exportar o no los datos a un destino. Esta función consta de:

* **[!UICONTROL Data Export Controls]**: puede establecer controles de exportación de datos en *orígenes de datos*. Cuando se establecen en un origen de datos, estos controles restringen la forma en que se pueden utilizar ese origen de datos y sus características.
* **[!UICONTROL Data Export Labels]**: puede establecer etiquetas de exportación de datos en *destinos*. Cuando se establecen en un destino, estas etiquetas identifican cómo utiliza el destino los datos. Consulte [Agregar etiquetas de exportación de datos a un destino](/help/using/features/destinations/add-data-export-labels.md) para obtener información sobre cómo agregar etiquetas de exportación a un destino.

En función de las clasificaciones aplicadas a un origen y destino de datos, los controles de exportación le impiden lo siguiente:

* Agregar un rasgo a un segmento cuando el rasgo pertenece a una fuente de datos que tiene un control de exportación de datos que es incompatible con una etiqueta de exportación de datos en uno o más de los destinos a los que está asignado el segmento.
Por ejemplo, supongamos que un segmento está asignado a un destino con la etiqueta de exportación **[!DNL This destination may enable a combination with personally identifiable information (PII)]**. Los controles de exportación impiden agregar una característica a ese segmento si el origen de datos al que pertenece la característica tiene un control de exportación de datos que dice **[!DNL Cannot be tied to personally identifiable information (PII)]**.
* El envío de datos a un destino que tenga una etiqueta de exportación de datos bloqueada por un control de exportación de datos en cualquiera de los siguientes casos:
   * La fuente de datos de un rasgo incluido.
   * La fuente de datos de un rasgo que se utiliza en un segmento incluido;
   * La regla de combinación de perfiles aprovechada por un segmento incluido;
   * Cualquiera de las fuentes de datos que utiliza la regla de combinación de perfiles de un segmento incluido.

[!UICONTROL Data Export Controls] están disponibles automáticamente para todos los clientes de Audience Manager. Sin embargo, necesita permisos de administrador para agregar controles de exportación a un origen de datos. Para agregar etiquetas de exportación a un destino se requieren permisos de administrador *o* que tengan privilegios suficientes para crear o editar un destino.

## Controles y etiquetas definidos {#controls-labels}

[!UICONTROL Data Export Controls] proporciona los siguientes controles para ayudarle a clasificar orígenes y destinos de datos.

Para bloquear la entrega de datos, debe clasificar un origen de datos con un control de exportación y agregar una etiqueta de exportación a un destino. Si aplica controles de exportación únicamente a un origen o destino de datos, esta función no restringe la entrega de datos. Cuando se establece tanto en el origen de datos *como en el destino*, los controles de exportación limitan los rasgos que se pueden agregar a un segmento e impiden que se envíen los miembros del segmento a un destino.

Además, al menos una etiqueta de exportación debe coincidir con un control de exportación para que las restricciones de entrega de datos surtan efecto. Por ejemplo, supongamos que agrega el control de exportación [!UICONTROL PII] a un origen de datos. A continuación, agregue la etiqueta de segmentación en el sitio a un destino. En este caso, los controles de exportación no limitan la entrega de datos porque la configuración no coincide. Sin embargo, si agrega la etiqueta de exportación [!UICONTROL PII] al destino, los controles de exportación bloquearán la exportación.

>[!IMPORTANT]
>
>No puede bloquear la exportación de un segmento colocando un control de exportación de datos en el origen de datos del segmento. Debe establecer el control en cualquiera de las siguientes ubicaciones:
> * Las fuentes de datos de los rasgos utilizados en el segmento;
> * La regla de combinación de perfiles aprovechada por el segmento;
> * Cualquiera de las fuentes de datos que utiliza la regla de combinación de perfiles del segmento.

<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Controles de exportación de datos para una Source de datos </th> 
   <th colname="col2" class="entry"> Etiquetas de exportación de datos para un destino </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Sin restricciones</span></b> </td> 
   <td colname="col2"> n.d. </td> 
   <td colname="col3"> De forma predeterminada, las restricciones de exportación no se establecen en nuevas fuentes de datos y destinos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> no puede estar vinculado a información de identificación personal</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> Este destino puede habilitar una combinación con información de identificación personal (PII)</span></b> </td> 
   <td colname="col3">Al seleccionarlo, no puede: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Añada características a los segmentos asignados a destinos que utilizan PII. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Asigne segmentos creados con un rasgo de la fuente de datos a destinos que utilicen PII. </li> 
    </ul> <p>Esto suele ser necesario para los proveedores de datos de terceros y cuando se utilizan fuentes de datos que contienen información de seguimiento de anuncios/medios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> No se puede usar para la segmentación de anuncios en el sitio </span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Este destino se puede usar para la segmentación de anuncios en el sitio</span></b> </td> 
   <td colname="col3">Al seleccionarlo, no puede: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Añada características a los segmentos asignados a destinos que personalizan la publicación de anuncios en función del historial de navegación web de un visitante. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Asigne segmentos creados con un rasgo de la fuente de datos a destinos que personalicen la publicación de anuncios en función del historial de navegación web de un visitante. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> No se puede usar para la segmentación de anuncios externos</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Este destino se puede usar para la segmentación de anuncios externos</span></b> </td> 
   <td colname="col3">Al seleccionarlo, no puede: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Agregar características a segmentos asignados a destinos que vuelven a dirigirse a usuarios de otros sitios. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Asigne segmentos creados con un rasgo de la fuente de datos a destinos que vuelvan a segmentar usuarios en otros sitios. </li> 
    </ul> <p>A menudo es necesario cuando se trabaja con datos de plataformas de medios sociales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> no se puede usar para la personalización en el sitio</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Este destino se puede usar para la personalización de anuncios en el sitio</span></b> </td> 
   <td colname="col3">Al seleccionarlo, no puede: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Añada características a los segmentos asignados a destinos que personalizan el contenido en función de los intereses del usuario o del historial de navegación web. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Asigne segmentos creados con un rasgo de la fuente de datos a destinos que personalicen el contenido en función de los intereses del usuario o del historial de navegación web. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Flujo de trabajo {#workflow}

Para empezar, revise la documentación de origen de datos y destino. En estos artículos se proporcionan instrucciones sobre cómo agregar controles de exportación y etiquetas a los orígenes de datos y destinos.

* [Crear una fuente de datos](../features/manage-datasources.md#create-data-source)
* [Añadir etiquetas de exportación de datos a un destino](../features/destinations/add-data-export-labels.md)
