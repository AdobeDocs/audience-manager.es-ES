---
description: Un destino URL realiza llamadas de píxeles desde una Página al destino. Siga estas instrucciones para crear un destino URL con el Generador de destinos.
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: Configurar un destino de URL
feature: Destination Basics
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 1%

---

# Configure un [!DNL URL Destination] {#configure-url-destination}

A [!DNL URL destination] realiza llamadas de píxeles desde un Página a su [!DNL destination]. Siga estas instrucciones para crear un [!DNL URL] [!DNL destination] con [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Para crear una nueva [!DNL URL] [!DNL destination], vaya a **[!UICONTROL Audience Data > Destinations > Create New Destination]** las secciones y complételas como se describe a continuación.

## Información básica {#basic-info}

Esta sección contiene campos y opciones que inicio el proceso de [!DNL URL destination] creación. Para completar esta sección:

1. Haga clic **[!UICONTROL Basic Information]** para exponer los controles.
2. Asigne el siguiente nombre al [!DNL destination]archivo . Evite abreviaturas y caracteres especiales.
3. *(Opcional)* Describa el [!DNL destination]archivo . Una descripción concisa es una forma eficaz de definir o proporcionar más información sobre un [!DNL destination]archivo .
4. En la lista **[!UICONTROL Category]**, elija **[!UICONTROL Custom]**.
5. En la lista **[!UICONTROL Environment]**, seleccione el entorno en el que desea almacenar en déclencheur a [!DNL URL destination].
6. En la lista **[!UICONTROL Type]**, haga clic en **[!UICONTROL URL]**.
7. *(Opcional)* Seleccione un **[!UICONTROL Auto-fill Destination Mapping]** archivo . Las opciones incluyen:
   * **[!UICONTROL Segment ID]**: agrega y envía automáticamente el ID de segmento al [!DNL destination]archivo .
   * **[!UICONTROL Integration Code Value]**: agrega y envía automáticamente el código de integración segmento a la asignación de destino. El código de integración es un identificador único creado y utilizado por el cliente. Está limitada a 255 caracteres como máximo.
8. Haga clic **[!UICONTROL Next]** para ir a la [!UICONTROL Configuration] configuración o haga clic **[!UICONTROL Data Export Labels]** para aplicar controles de [!DNL destination]exportación al .

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Esta sección contiene opciones que aplican [controles](../../features/data-export-controls.md) de exportación de datos a un [!DNL URL] destino. Omita este paso si no utiliza controles de exportación de datos. Para completar esta sección:

1. Haga clic **[!UICONTROL Data Export Labels]** para exponer los controles.
2. Seleccione una etiqueta que corresponda al control de exportación de datos aplicado al destino (consulte [añadir Exportar etiquetas a un destino](/help/using/features/destinations/add-data-export-labels.md) para obtener más información).
3. Haga clic en **[!UICONTROL Save]**.

## Configuración {#configure-base-data}

Esta sección contiene opciones que le permiten establecer una base [!DNL URL] y delimitadores de datos pasados por la [!DNL URL] cadena. Esta sección es opcional. Para completar esta sección:

1. Haga clic **[!UICONTROL Configuration]** para exponer los controles.
1. *(Opcional)* Seleccione la casilla de **[!UICONTROL Serialize]** verificación.
Esto permite enviar segmentos de forma [!DNL destination] secuencial en lugar de realizar llamadas independientes para cada segmento. La serialización ayuda a que las transferencias de datos sean eficientes. Al seleccionar esta casilla de verificación, se exponen los campos URL y delimitador. Para obtener más información, consulte [Par](../../features/destinations/key-value-pairs.md) de clave Valor serie y estándar.
1. Si selecciona **[!UICONTROL Serialize]**, también deberá configurar los campos de URL y delimitador que se describen a continuación.

| Campo | Descripción |
|--- |--- |
| [!UICONTROL Base URL] | La parte base de un(a) `HTTP` [!DNL URL] estándar que no cambia. Además, debe colocar la `%ALIAS%` [macro de marcador de posición](../../features/destinations/destination-macros.md#destination-macros-defined) en la dirección URL base. Ejemplo: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | La parte base de una caja fuerte `HTTPS` [!DNL URL] que no cambia. Además, debe colocar la macro`%ALIAS%` de marcador de [](../../features/destinations/destination-macros.md#destination-macros-defined)posición en la URL base.   Ejemplo: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Símbolo que separa las variables de segmento de la [!DNL URL] cadena. Por lo general, es una coma o un punto y coma. Obtenga esta información de su socio de destino. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Esta sección le permite búsqueda y agregar segmentos a su [!UICONTROL destination]. Para completar esta sección:

1. Haga clic **[!UICONTROL Segment Mappings]** para exponer los controles.
1. En el **[!UICONTROL Search and Add Segments]** cuadro, inicio escribiendo el nombre de una segmento o haga clic en **[!UICONTROL Browse All Segments]** examinar una lista de segmentos disponibles.
1. Haga clic **[!UICONTROL Add Selected Segments]** cuando encuentre la segmento que desea utilizar. Al agregar una segmento se abre la [!UICONTROL Edit Mapping] ventana.
1. En [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: proporcionan los pares clave-valor utilizados por el segmento.
   * **[!UICONTROL Start Date]** y **[!UICONTROL End Date]**: elija una fecha inicio y una fecha de finalización para el [!DNL destination]. Si la fecha de finalización está en blanco, [!DNL destination] nunca caducará.
1. Haga clic en **[!UICONTROL Done]**.
