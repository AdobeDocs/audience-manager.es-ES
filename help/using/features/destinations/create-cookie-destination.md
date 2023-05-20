---
description: Un destino de cookie devuelve y escribe datos en una cookie en el explorador del usuario. La cookie contiene datos que pueden leer otras plataformas que tienen acceso a la página. Siga estas instrucciones para crear un destino de cookie con [!UICONTROL Destination Builder].
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: Configurar un destino de cookie
feature: Destination Basics
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 3%

---

# Configurar un destino de cookie {#create-cookie-destination}

Un destino de cookie devuelve y escribe datos en una cookie en el explorador del usuario. La cookie contiene datos que pueden leer otras plataformas que tienen acceso a la página. Siga estas instrucciones para crear un destino de cookie con [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Para crear un nuevo destino de cookie, vaya a **[!UICONTROL Audience Data > Destinations > Create New Destination]** y complete las secciones como se describe a continuación.

## Información básica {#basic-information}

Esta sección contiene campos y opciones que inician el proceso de creación de destinos de cookies. Para completar esta sección:

1. Clic **[!UICONTROL Basic Information]** para exponer los controles.
2. Nombre el destino. Evite las abreviaciones y los caracteres especiales.
3. *(Opcional)* Describa el destino. Una descripción concisa es una forma eficaz de definir o proporcionar más información sobre un destino.
4. En el **[!UICONTROL Category]** lista, elija **[!UICONTROL Custom]**.
5. En el **[!UICONTROL Environment]** , seleccione **[!UICONTROL Browser]**. No puede configurar destinos de cookies para entornos móviles nativos, como aplicaciones de Android o iOS.
6. En el **[!UICONTROL Type]** , haga clic en **[!UICONTROL Cookie]**.
7. *(Opcional)* Seleccione un **[!UICONTROL Auto-fill Destination Mapping]**. Las opciones incluyen:
   * **[!UICONTROL Segment ID]**: Añade y envía automáticamente el ID de segmento al destino.
   * **[!UICONTROL Integration Code Value]**: Añade y envía automáticamente el código de integración de segmentos a la asignación de destino. El código de integración es un identificador único creado y utilizado por el cliente. Está limitado a 255 caracteres como máximo.
8. Clic **[!UICONTROL Next]** para ir a [!UICONTROL Configuration] configuración o haga clic en **[!UICONTROL Data Export Labels]** para aplicar controles de exportación al destino.

## Etiquetas de exportación de datos {#data-export-labels-cookies}

Esta sección contiene las opciones aplicables [controles de exportación de datos](../../features/data-export-controls.md) a un destino de cookie. Omita este paso si no utiliza controles de exportación de datos. Para completar esta sección:

1. Clic **[!UICONTROL Data Export Labels]** para exponer los controles.
2. Seleccione una etiqueta que corresponda al control de exportación de datos aplicado al destino (consulte [Añadir etiquetas de exportación a un destino](/help/using/features/destinations/add-data-export-labels.md) para obtener más información).
3. Haga clic **[!UICONTROL Save]**.

## Configuración {#configuration}

Esta sección contiene campos y opciones que le permiten configurar la cookie para su destino.

>[!NOTE]
>
>[!DNL Audience Manager] codifica los datos escritos en la cookie de destino. Por ejemplo, los espacios se codifican como `%20` y punto y coma se codifican como `%3B`.

Para completar esta sección:

1. Clic **[!UICONTROL Configuration]** para exponer los controles
1. Asigne un nombre a la cookie. Evite las abreviaciones y los caracteres especiales.
1. Elija una opción de formato de datos. Estas opciones permiten elegir los delimitadores y separadores de los pares clave-valor que envían datos de segmento a un destino. Las opciones de formato incluyen:
   * **Clave única:** Permite establecer la clave en un par clave-valor. Establecerá el valor después de seleccionar un segmento en la [!UICONTROL Segment Mappings] más abajo.
   * **Tecla múltiple:** Permite establecer la clave y el valor de un par clave-valor. Creará el par clave-valor después de seleccionar un segmento en la sección Asignaciones de segmentos a continuación.
Consulte [Pares de clave-valor estándar y serie](../../features/destinations/key-value-pairs.md) para obtener más información sobre estos elementos de datos.
1. Haga clic **[!UICONTROL Save]**.

El resto de configuraciones son opcionales. Para obtener más información sobre **[!UICONTROL Cookie Domain]** y **[!UICONTROL Publish data to]** configuración, consulte [Configuración opcional para destinos de cookies](/help/using/features/destinations/cookie-destination-options.md).

## Asignaciones de segmentos {#segments-mapping}

Esta sección le permite buscar y agregar segmentos a su destino. Para completar esta sección:

1. Clic **[!UICONTROL Segment Mappings]** para exponer los controles.
1. En el **[!UICONTROL Search and Add Segments]** , empiece a escribir el nombre de un segmento o haga clic en **[!UICONTROL Browse All Segments]** para examinar una lista de segmentos disponibles.
1. Clic **[!UICONTROL Add Selected Segments]** cuando encuentre el segmento que desea utilizar. Añadir un segmento abre el [!UICONTROL Edit Mapping] ventana.
1. En el [!UICONTROL Edit Mapping] diálogo:
   * **[!UICONTROL Mapping]** permite establecer un valor para la clave especificada en la sección Configuración anterior.
   * **[!UICONTROL Publish from]** permite establecer las fechas de inicio y finalización del destino. Si la fecha de finalización está en blanco, el destino nunca caduca.
1. Haga clic **[!UICONTROL Save]**.
1. Haga clic **[!UICONTROL Done]**.
