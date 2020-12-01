---
description: Un destino de cookie devuelve y escribe datos en una cookie en el explorador del usuario. La cookie contiene datos que pueden leer otras plataformas que tienen acceso a la página. Siga estas instrucciones para crear un destino de cookie con [!UICONTROL Destination Builder].
seo-description: Un destino de cookie devuelve y escribe datos en una cookie en el explorador del usuario. La cookie contiene datos que pueden leer otras plataformas que tienen acceso a la página. Siga estas instrucciones para crear un destino de cookie con [!UICONTROL Destination Builder].
seo-title: Configurar un destino de cookie
solution: Audience Manager
title: Configurar un destino de cookie
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 3%

---


# Configurar un destino de cookie {#create-cookie-destination}

Un destino de cookie devuelve y escribe datos en una cookie en el explorador del usuario. La cookie contiene datos que pueden leer otras plataformas que tienen acceso a la página. Siga estas instrucciones para crear un destino de cookie con [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Para crear un nuevo destino de cookie, vaya a **[!UICONTROL Audience Data > Destinations > Create New Destination]** y complete las secciones como se describe a continuación.

## Información básica {#basic-information}

Esta sección contiene campos y opciones que inicio el proceso de creación de la cookie de destino. Para completar esta sección:

1. Haga clic en **[!UICONTROL Basic Information]** para exponer los controles.
2. Asigne un nombre al destino. Evite abreviaciones y caracteres especiales.
3. *(Opcional)* Describa el destino. Una descripción concisa es una forma eficaz de definir o proporcionar más información sobre un destino.
4. En la lista **[!UICONTROL Category]**, elija **[!UICONTROL Custom]**.
5. En la lista **[!UICONTROL Environment]**, seleccione **[!UICONTROL Browser]**. No puede configurar destinos de cookies para entornos móviles nativos, como aplicaciones de Android o iOS.
6. En la lista **[!UICONTROL Type]**, haga clic en **[!UICONTROL Cookie]**.
7. *(Opcional)* Seleccione un  **[!UICONTROL Auto-fill Destination Mapping]**. Las opciones incluyen:
   * **[!UICONTROL Segment ID]**:: Agrega y envía automáticamente el ID de segmento al destino.
   * **[!UICONTROL Integration Code Value]**:: Agrega y envía automáticamente el código de integración de segmentos a la asignación de destino. El código de integración es un identificador único creado y utilizado por el cliente. Está limitada a 255 caracteres como máximo.
8. Haga clic en **[!UICONTROL Next]** para ir a la configuración [!UICONTROL Configuration] o haga clic en **[!UICONTROL Data Export Labels]** para aplicar controles de exportación al destino.

## Etiquetas de exportación de datos {#data-export-labels-cookies}

Esta sección contiene opciones que aplican [controles de exportación de datos](../../features/data-export-controls.md) a un destino de cookie. Omita este paso si no utiliza controles de exportación de datos. Para completar esta sección:

1. Haga clic en **[!UICONTROL Data Export Labels]** para exponer los controles.
2. Seleccione una etiqueta que corresponda al control de exportación de datos aplicado al destino (consulte [Añadir etiquetas de exportación a un destino](/help/using/features/destinations/add-data-export-labels.md) para obtener más información).
3. Haga clic **[!UICONTROL Save]**.

## Configuración {#configuration}

Esta sección contiene campos y opciones que le permiten configurar la cookie para su destino.

>[!NOTE]
>
>[!DNL Audience Manager] codifica los datos escritos en la cookie de destino. Por ejemplo, los espacios se codifican como `%20` y los puntos y comas como `%3B`.

Para completar esta sección:

1. Haga clic **[!UICONTROL Configuration]** para exponer los controles
1. Asigne un nombre a la cookie. Evite abreviaciones y caracteres especiales.
1. Elija una opción de formato de datos. Estas opciones permiten elegir los delimitadores y separadores para los pares de clave-valor que envían datos de segmentos a un destino. Las opciones de formato incluyen:
   * **Clave única:** permite definir la clave en un par de clave-valor. Establecerá el valor después de seleccionar un segmento en la sección [!UICONTROL Segment Mappings] a continuación.
   * **Tecla múltiple:** permite definir la clave y el valor de un par clave-valor. Creará el par clave-valor después de seleccionar un segmento en la sección Asignaciones de segmentos a continuación.
Consulte [Pares de clave-valor estándar y serie](../../features/destinations/key-value-pairs.md) para obtener más información sobre estos elementos de datos.
1. Haga clic **[!UICONTROL Save]**.

El resto de la configuración es opcional. Para obtener más información sobre la configuración **[!UICONTROL Cookie Domain]** y **[!UICONTROL Publish data to]**, consulte [Configuración opcional para destinos de cookies](/help/using/features/destinations/cookie-destination-options.md).

## Asignaciones de segmentos {#segments-mapping}

Esta sección le permite buscar y agregar segmentos a su destino. Para completar esta sección:

1. Haga clic en **[!UICONTROL Segment Mappings]** para exponer los controles.
1. En el cuadro **[!UICONTROL Search and Add Segments]**, escriba el nombre de un segmento en el inicio o haga clic en **[!UICONTROL Browse All Segments]** para examinar una lista de segmentos disponibles.
1. Haga clic **[!UICONTROL Add Selected Segments]** cuando encuentre el segmento que desee utilizar. Al añadir un segmento se abre la ventana [!UICONTROL Edit Mapping].
1. En el cuadro de diálogo [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mapping]** le permite establecer un valor para la clave especificada en la sección Configuración anterior.
   * **[!UICONTROL Publish from]** le permite establecer la fecha de inicio y de finalización para el destino. Si la fecha de finalización está en blanco, el destino nunca caduca.
1. Haga clic **[!UICONTROL Save]**.
1. Haga clic **[!UICONTROL Done]**.