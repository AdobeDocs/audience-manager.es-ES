---
description: Un destino de cookie devuelve y escribe datos en una cookie en el navegador del usuario. La cookie contiene datos que pueden ser leídos por otras plataformas que tengan acceso a la página. Siga estas instrucciones para crear un destino de cookie con [! UICONTROL Destination Builder].
seo-description: Un destino de cookie devuelve y escribe datos en una cookie en el navegador del usuario. La cookie contiene datos que pueden ser leídos por otras plataformas que tengan acceso a la página. Siga estas instrucciones para crear un destino de cookie con [! UICONTROL Destination Builder].
seo-title: Configurar un destino de cookie
solution: Audience Manager
title: Configurar un destino de cookie
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Configurar un destino de cookie {#create-cookie-destination}

Un destino de cookie devuelve y escribe datos en una cookie en el navegador del usuario. La cookie contiene datos que pueden ser leídos por otras plataformas que tengan acceso a la página. Siga estas instrucciones para crear un destino de cookie con [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Para crear un nuevo destino de cookie, diríjase **[!UICONTROL Audience Data > Destinations > Create New Destination]** y complete las secciones como se describe a continuación.

## Información básica {#basic-information}

Esta sección contiene campos y opciones que inician el proceso de creación de destinos de cookies. Para completar esta sección:

1. Haga clic para **[!UICONTROL Basic Information]** exponer los controles.
2. Asigne un nombre al destino. Evite abreviaciones y caracteres especiales.
3. *(Opcional)* Describa el destino. Una descripción concisa es una manera eficaz de definir o proporcionar más información sobre un destino.
4. En la **[!UICONTROL Category]** lista, elija **[!UICONTROL Custom]**.
5. En la **[!UICONTROL Environment]** lista, seleccione **[!UICONTROL Browser]**. No se pueden configurar destinos de cookies para entornos móviles nativos, como las aplicaciones de Android o iOS.
6. En la **[!UICONTROL Type]** lista, haga clic **[!UICONTROL Cookie]** en.
7. *(Opcional)* Seleccione un **[!UICONTROL Auto-fill Destination Mapping]**. Las opciones incluyen:
   * **[!UICONTROL Segment ID]**: Agrega automáticamente y envía el ID de segmento al destino.
   * **[!UICONTROL Integration Code Value]**: Agrega y envía automáticamente el código de integración de segmentos a la asignación de destino. El código de integración es un identificador único creado y utilizado por el cliente. Tiene un límite de 255 caracteres, máximo.
8. Haga clic para **[!UICONTROL Next]** ir a [!UICONTROL Configuration] la configuración o haga clic **[!UICONTROL Data Export Labels]** para aplicar los controles de exportación al destino.

## Etiquetas de exportación de datos {#data-export-labels-cookies}

Esta sección contiene opciones que aplican [controles de exportación de datos](../../features/data-export-controls.md) a un destino de cookie. Omita este paso si no utiliza los controles de exportación de datos. Para completar esta sección:

1. Haga clic para **[!UICONTROL Data Export Labels]** exponer los controles.
2. Seleccione una etiqueta que corresponda al control de exportación de datos aplicado al destino (consulte [Agregar etiquetas de exportación a un destino](/help/using/features/destinations/add-data-export-labels.md) para obtener detalles).
3. Haga clic en **[!UICONTROL Save]**.

## Configuración {#configuration}

Esta sección contiene campos y opciones que permiten configurar la cookie para el destino.

>[!NOTE]
>
>[!DNL Audience Manager] codifica los datos escritos en la cookie de destino. Por ejemplo, los espacios se codifican como `%20` y los puntos y comas se codifican como `%3B`.

Para completar esta sección:

1. Haga clic para **[!UICONTROL Configuration]** exponer los controles
1. Asigne un nombre a la cookie. Evite abreviaciones y caracteres especiales.
1. Elija una opción de formato de datos. Estas opciones permiten elegir los delimitadores y separadores para los pares de clave-valor que envían datos de segmentos a un destino. Las opciones de formato son:
   * **Clave única:** Permite definir la clave en un par clave-valor. Debe establecer el valor después de seleccionar un segmento en la [!UICONTROL Segment Mappings] sección siguiente.
   * **Clave múltiple:** Permite definir la clave y el valor de un par clave-valor. Creará el par clave-valor después de seleccionar un segmento en la sección Asignaciones de segmentos a continuación.
Consulte [Pares de clave-valor estándar y de valor de serie](../../features/destinations/key-value-pairs.md) para obtener más información sobre estos elementos de datos.
1. Haga clic en **[!UICONTROL Save]**.

Todos los demás ajustes son opcionales. Para obtener más información sobre la **[!UICONTROL Cookie Domain]** configuración y **[!UICONTROL Publish data to]** la configuración, consulte [Configuración opcional para destinos de cookies](/help/using/features/destinations/cookie-destination-options.md).

## Asignaciones de segmentos {#segments-mapping}

Esta sección permite buscar y agregar segmentos al destino. Para completar esta sección:

1. Haga clic para **[!UICONTROL Segment Mappings]** exponer los controles.
1. En **[!UICONTROL Search and Add Segments]** el cuadro, empiece a escribir el nombre de un segmento o haga clic **[!UICONTROL Browse All Segments]** para examinar una lista de segmentos disponibles.
1. Haga clic **[!UICONTROL Add Selected Segments]** en cuando encuentre el segmento que desee utilizar. Al agregar un segmento, se abre [!UICONTROL Edit Mapping] la ventana.
1. En el cuadro de [!UICONTROL Edit Mapping] diálogo:
   * **[!UICONTROL Mapping]** permite establecer un valor para la clave especificada en la sección Configuración anterior.
   * **[!UICONTROL Publish from]** permite definir la fecha de inicio y finalización del destino. Si la fecha de finalización está en blanco, el destino nunca caduca.
1. Haga clic en **[!UICONTROL Save]**.
1. Haga clic en **[!UICONTROL Done]**.