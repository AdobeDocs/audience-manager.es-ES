---
description: Un destino de URL realiza llamadas en píxeles desde una página al destino. Siga estas instrucciones para crear un destino de URL con Destination Builder.
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: Configurar un destino de dirección URL
feature: Destination Basics
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 3%

---

# Configurar un [!DNL URL Destination] {#configure-url-destination}

A [!DNL URL destination] realiza llamadas en píxeles desde una página a su [!DNL destination]. Siga estas instrucciones para crear un [!DNL URL] [!DNL destination] con [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Para crear un nuevo [!DNL URL] [!DNL destination], vaya a **[!UICONTROL Audience Data > Destinations > Create New Destination]** y complete las secciones como se describe a continuación.

## Información básica {#basic-info}

Esta sección contiene campos y opciones que inician el [!DNL URL destination] proceso de creación. Para completar esta sección:

1. Clic **[!UICONTROL Basic Information]** para exponer los controles.
2. Asigne un nombre al [!DNL destination]. Evite las abreviaciones y los caracteres especiales.
3. *(Opcional)* Describa el [!DNL destination]. Una descripción concisa es una forma eficaz de definir o proporcionar más información acerca de una [!DNL destination].
4. En el **[!UICONTROL Category]** lista, elija **[!UICONTROL Custom]**.
5. En el **[!UICONTROL Environment]** , seleccione el entorno en el que desea almacenar en déclencheur la variable [!DNL URL destination].
6. En el **[!UICONTROL Type]** , haga clic en **[!UICONTROL URL]**.
7. *(Opcional)* Seleccione un **[!UICONTROL Auto-fill Destination Mapping]**. Las opciones incluyen:
   * **[!UICONTROL Segment ID]**: Añade y envía automáticamente el ID de segmento a [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Añade y envía automáticamente el código de integración de segmentos a la asignación de destino. El código de integración es un identificador único creado y utilizado por el cliente. Está limitado a 255 caracteres como máximo.
8. Clic **[!UICONTROL Next]** para ir a [!UICONTROL Configuration] configuración o haga clic en **[!UICONTROL Data Export Labels]** para aplicar controles de exportación a [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Esta sección contiene las opciones aplicables [controles de exportación de datos](../../features/data-export-controls.md) a un [!DNL URL] destino. Omita este paso si no utiliza controles de exportación de datos. Para completar esta sección:

1. Clic **[!UICONTROL Data Export Labels]** para exponer los controles.
2. Seleccione una etiqueta que corresponda al control de exportación de datos aplicado al destino (consulte [Añadir etiquetas de exportación a un destino](/help/using/features/destinations/add-data-export-labels.md) para obtener más información).
3. Haga clic **[!UICONTROL Save]**.

## Configuración {#configure-base-data}

Esta sección contiene opciones que le permiten establecer una base [!DNL URL] y los delimitadores de datos pasados por el [!DNL URL] cadena. Esta sección es opcional. Para completar esta sección:

1. Clic **[!UICONTROL Configuration]** para exponer los controles.
1. *(Opcional)* Seleccione el **[!UICONTROL Serialize]** casilla de verificación.
Esto permite enviar segmentos a un [!DNL destination] secuencialmente, en lugar de realizar llamadas independientes para cada segmento. La serialización ayuda a que las transferencias de datos sean eficientes. Al seleccionar esta casilla de verificación, se exponen los campos URL y delimitador. Para obtener más información, consulte [Pares de clave-valor estándar y serie](../../features/destinations/key-value-pairs.md).
1. Si selecciona **[!UICONTROL Serialize]**, también debe configurar los campos URL y delimitador que se describen a continuación.

| Campo | Descripción |
|--- |--- |
| [!UICONTROL Base URL] | La parte básica de un estándar `HTTP` [!DNL URL] que no cambia. Además, debe colocar el `%ALIAS%`  [macro de marcador](../../features/destinations/destination-macros.md#destination-macros-defined) en la dirección URL base. Ejemplo: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | La parte base de un elemento seguro `HTTPS` [!DNL URL] que no cambia. Además, debe colocar el `%ALIAS%`   [macro de marcador](../../features/destinations/destination-macros.md#destination-macros-defined) en la dirección URL base. Ejemplo: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | El símbolo que separa las variables de segmento en la variable [!DNL URL] cadena. Esto suele ser una coma o un punto y coma. Obtenga esta información de su socio de destino. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Esta sección le permite buscar y agregar segmentos a su [!UICONTROL destination]. Para completar esta sección:

1. Clic **[!UICONTROL Segment Mappings]** para exponer los controles.
1. En el **[!UICONTROL Search and Add Segments]** , empiece a escribir el nombre de un segmento o haga clic en **[!UICONTROL Browse All Segments]** examine una lista de segmentos disponibles.
1. Clic **[!UICONTROL Add Selected Segments]** cuando encuentre el segmento que desea utilizar. Añadir un segmento abre el [!UICONTROL Edit Mapping] ventana.
1. En [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Proporcione los pares clave-valor utilizados por el segmento.
   * **[!UICONTROL Start Date]** y **[!UICONTROL End Date]**: elija una fecha de inicio y de finalización para la [!DNL destination]. Si la fecha de finalización está en blanco, la variable [!DNL destination] nunca caduca.
1. Haga clic **[!UICONTROL Done]**.
