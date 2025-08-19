---
description: Un destino cookie devuelve y escribe datos en un cookie del explorador del usuario. El cookie contiene datos que pueden ser leídos por otras plataformas que tengan acceso al Página. Siga estas instrucciones para crear un destino cookie con [!UICONTROL Destination Builder].
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: Configuración de un destino de cookies
feature: Destination Basics
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 1%

---

# Configuración de un destino de cookies {#create-cookie-destination}

Un destino cookie devuelve y escribe datos en un cookie del explorador del usuario. El cookie contiene datos que pueden ser leídos por otras plataformas que tengan acceso al Página. Siga estas instrucciones para crear un destino cookie con [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Para crear un nuevo destino de cookie, vaya a **[!UICONTROL Audience Data > Destinations > Create New Destination]** las secciones y complételas como se describe a continuación.

## Información básica {#basic-information}

Esta sección contiene campos y opciones que inicio el proceso de creación de cookie destino. Para completar esta sección:

1. Haga clic **[!UICONTROL Basic Information]** para exponer los controles.
2. Asigne un nombre al destino. Evite abreviaturas y caracteres especiales.
3. *(Opcional)* Describa el destino. Una descripción concisa es una forma eficaz de definir o proporcionar más información sobre un destino.
4. En el **[!UICONTROL Category]** lista, elija **[!UICONTROL Custom]**.
5. En la **[!UICONTROL Environment]** lista, seleccione **[!UICONTROL Browser]**. No puede configurar destinos cookie para entornos móviles nativa, como aplicaciones Android o iOS.
6. En la **[!UICONTROL Type]** lista, haga clic en **[!UICONTROL Cookie]**.
7. *(Opcional)* Seleccione un **[!UICONTROL Auto-fill Destination Mapping]** archivo . Las opciones incluyen:
   * **[!UICONTROL Segment ID]**: agrega y envía automáticamente el ID de segmento al destino.
   * **[!UICONTROL Integration Code Value]**: agrega y envía automáticamente el código de integración segmento a la asignación de destino. El código de integración es un identificador único creado y utilizado por el cliente. Está limitada a 255 caracteres como máximo.
8. Haga clic **[!UICONTROL Next]** para ir a la [!UICONTROL Configuration] configuración o haga clic **[!UICONTROL Data Export Labels]** para aplicar controles de exportación al destino.

## Etiquetas de exportación de datos {#data-export-labels-cookies}

Esta sección contiene opciones que aplican [controles](../../features/data-export-controls.md) de exportación de datos a un destino cookie. Omita este paso si no utiliza controles de exportación de datos. Para completar esta sección:

1. Haga clic **[!UICONTROL Data Export Labels]** para exponer los controles.
2. Seleccione una etiqueta que corresponda al control de exportación de datos aplicado al destino (consulte [añadir Exportar etiquetas a un destino](/help/using/features/destinations/add-data-export-labels.md) para obtener más información).
3. Haga clic en **[!UICONTROL Save]**.

## Configuración {#configuration}

Esta sección contiene campos y opciones que le permiten configurar el cookie para su destino.

>[!NOTE]
>
>[!DNL Audience Manager] Codifica los datos escritos en el cookie de destino. Por ejemplo, los espacios se codifican como `%20` y los puntos y comas se codifican como `%3B`.

Para completar esta sección:

1. Haga clic **[!UICONTROL Configuration]** para exponer los controles
1. Asigne un nombre al cookie. Evite abreviaturas y caracteres especiales.
1. Elija una opción formato datos. Estas opciones le permiten elegir los delimitadores y separadores para los pares clave-valor que envían segmento datos a un destino. Las opciones de formato incluyen:
   * **Clave única:** le permite establecer la clave en un par de clave-valor. Definirá el valor después de seleccionar un segmento en la [!UICONTROL Segment Mappings] sección siguiente.
   * **Clave múltiple:** Permite definir la clave y el valor de un par clave-valor. Se creará el par clave-valor después de seleccionar un segmento en la sección Asignaciones de segmentos a continuación.
Consulte [Pares](../../features/destinations/key-value-pairs.md) Valor clave estándar y serie para obtener más información sobre estos elementos de datos.
1. Haga clic en **[!UICONTROL Save]**.

Todos los demás ajustes son opcionales. Para obtener más información acerca de la configuración AND **[!UICONTROL Cookie Domain]**, consulte **[!UICONTROL Publish data to]** Configuración opcional para destinos[ de ](/help/using/features/destinations/cookie-destination-options.md) cookies.

## Asignaciones de segmentos {#segments-mapping}

Esta sección le permite búsqueda y agregar segmentos a su destino. Para completar esta sección:

1. Haga clic **[!UICONTROL Segment Mappings]** para exponer los controles.
1. En el **[!UICONTROL Search and Add Segments]** cuadro, inicio escribiendo el nombre de una segmento o haga clic **[!UICONTROL Browse All Segments]** para examinar una lista de segmentos disponibles.
1. Haga clic **[!UICONTROL Add Selected Segments]** cuando encuentre la segmento que desea utilizar. Al agregar una segmento se abre la [!UICONTROL Edit Mapping] ventana.
1. En el cuadro de [!UICONTROL Edit Mapping] diálogo:
   * **[!UICONTROL Mapping]** le permite establecer un valor para la clave especificada en la sección Configuración anterior.
   * **[!UICONTROL Publish from]** Permite establecer la fecha inicio y la de finalización del destino. Si la fecha de finalización está en blanco, el destino no caduca nunca.
1. Haga clic en **[!UICONTROL Save]**.
1. Haga clic en **[!UICONTROL Done]**.
