---
description: Los controles de exportación de datos impiden que envíe datos a los destinos cuando esta acción infringe acuerdos de privacidad o uso de datos.
seo-description: Los controles de exportación de datos impiden que envíe datos a los destinos cuando esta acción infringe acuerdos de privacidad o uso de datos.
seo-title: Controles de exportación de datos
solution: Audience Manager
title: Controles de exportación de datos
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Controles de exportación de datos
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 2%

---

# Controles de exportación de datos {#data-export-controls}

[!UICONTROL Data Export Controls] impida que envíe datos a destinos cuando esta acción infrinja los acuerdos de privacidad o uso de datos.

## Información general {#overview}

[!UICONTROL Data Export Controls] permite clasificar  [fuentes de ](../features/datasources-list-and-settings.md#data-sources-list-and-settings) datos y  [destinos](../features/destinations/destinations.md). Las clasificaciones que aplique determinan cuándo se pueden exportar o no datos a un destino. Esta función consiste en:

* **[!UICONTROL Data Export Controls]**: Puede establecer controles de exportación de datos en fuentes de  *datos*. Cuando se establece en una fuente de datos, estos controles restringen el modo en que se puede utilizar dicha fuente de datos y sus rasgos.
* **[!UICONTROL Data Export Labels]**: Puede establecer etiquetas de exportación de datos en los  *destinos*. Cuando se configura en un destino, estas etiquetas identifican cómo utiliza los datos el destino. Consulte [Agregar etiquetas de exportación de datos a un destino](/help/using/features/destinations/add-data-export-labels.md) para obtener información sobre cómo agregar etiquetas de exportación a un destino.

En función de las clasificaciones aplicadas a un origen y destino de datos, los controles de exportación le impiden:

* Añadir un rasgo a un segmento cuando el rasgo pertenece a un origen de datos que tiene un control de exportación de datos incompatible con una etiqueta de exportación de datos en uno o varios de los destinos a los que está asignado el segmento.
Por ejemplo, supongamos que un segmento está asignado a un destino con la etiqueta de exportación **[!DNL This destination may enable a combination with personally identifiable information (PII)]**. Los controles de exportación impiden añadir un rasgo a ese segmento si el origen de datos al que pertenece el rasgo tiene un control de exportación de datos que diga **[!DNL Cannot be tied to personally identifiable information (PII)]**.
* El envío de datos a un destino tiene una etiqueta de exportación de datos bloqueada por un control de exportación de datos en cualquiera de los siguientes casos:
   * La fuente de datos de un rasgo incluido;
   * La fuente de datos de un rasgo que se utiliza en un segmento incluido;
   * La regla de combinación de perfiles aprovechada por un segmento incluido;
   * Cualquiera de las fuentes de datos que utiliza una regla de combinación de perfiles de un segmento incluido.

[!UICONTROL Data Export Controls] están disponibles automáticamente para todos los clientes Audience Manager. Sin embargo, se necesitan permisos de administrador para agregar controles de exportación a un origen de datos. La adición de etiquetas de exportación a un destino requiere permisos de administrador *o* suficientes privilegios para crear o editar un destino.

## Controles y etiquetas definidos {#controls-labels}

[!UICONTROL Data Export Controls] proporcione los siguientes controles para ayudarle a clasificar fuentes de datos y destinos.

Para bloquear la entrega de datos, debe clasificar un origen de datos con un control de exportación y añadir una etiqueta de exportación a un destino. Si aplica controles de exportación solo a un origen o destino de datos, esta función no restringirá el envío de datos. Cuando se establecen tanto en el destino de origen de datos *como en*, los controles de exportación limitan las características que puede agregar a un segmento e impiden que los miembros del segmento se envíen a un destino.

Además, al menos una etiqueta de exportación debe coincidir con un control de exportación antes de que se apliquen las restricciones de entrega de datos. Por ejemplo, supongamos que agrega el control de exportación [!UICONTROL PII] a un origen de datos. A continuación, agregue la etiqueta de objetivo en el sitio a un destino. En este caso, los controles de exportación no limitarán la entrega de datos porque la configuración no coincide. Sin embargo, si agrega la etiqueta de exportación [!UICONTROL PII] al destino, los controles de exportación bloquearán la exportación.

>[!IMPORTANT]
>
>No se puede bloquear la exportación de un segmento colocando un control de exportación de datos en el origen de datos del segmento, debe establecer el control en cualquiera de los siguientes elementos:
> * Las fuentes de datos de los rasgos utilizados en el segmento;
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
   <td colname="col3"> De forma predeterminada, las restricciones de exportación no se establecen en nuevos orígenes de datos y destinos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> No se puede asociar a información</span></b>  de identificación personal (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> Este destino puede permitir una combinación con información de identificación personal (PII)</span></b> </td> 
   <td colname="col3">Cuando está seleccionado, no puede: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Añadir características a segmentos asignados a destinos que utilizan PII. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Asigne segmentos creados con un rasgo de la fuente de datos a destinos que utilicen PII. </li> 
    </ul> <p>Esto suele ser necesario para proveedores de datos de terceros y cuando se utilizan fuentes de datos que contienen información de seguimiento de anuncios/medios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> No se puede usar para la segmentación de anuncios en el sitio</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Este destino se puede usar para la segmentación de anuncios en el sitio</span></b> </td> 
   <td colname="col3">Cuando está seleccionado, no puede: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Agregue características a segmentos asignados a destinos que personalicen el envío de publicidad en función del historial de navegación web de un visitante. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Asigne segmentos creados con un rasgo de la fuente de datos a destinos que personalicen el envío de publicidad en función del historial de navegación web de un visitante. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> No se puede usar para la segmentación de anuncios fuera del sitio</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Este destino se puede usar para la segmentación de anuncios fuera del sitio</span></b> </td> 
   <td colname="col3">Estas restricciones se utilizan generalmente con Cuando se selecciona, no puede: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Agregue características a segmentos asignados a destinos que redirijan a usuarios de otros sitios. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Asigne segmentos creados con un rasgo de la fuente de datos a destinos que redirijan a usuarios de otros sitios. </li> 
    </ul> <p>A menudo es necesario cuando se trabaja con datos de plataformas de medios sociales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> No se puede usar para la personalización en el sitio</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Este destino puede utilizarse para la personalización de anuncios en el sitio</span></b> </td> 
   <td colname="col3">Cuando está seleccionado, no puede: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Añada características a segmentos asignados a destinos que personalicen el contenido en función de los intereses del usuario o del historial de navegación web. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Asigne segmentos creados con un rasgo de la fuente de datos a destinos que personalicen el contenido en función de los intereses del usuario o del historial de navegación web. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Flujo de trabajo {#workflow}

Para empezar, consulte la documentación de origen y destino de los datos. En estos artículos se proporcionan instrucciones sobre cómo agregar controles de exportación y etiquetas a sus orígenes y destinos de datos.

* [Crear una fuente de datos](../features/manage-datasources.md#create-data-source)
* [Agregar etiquetas de exportación de datos a un destino](../features/destinations/add-data-export-labels.md)
