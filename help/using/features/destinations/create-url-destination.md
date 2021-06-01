---
description: Un destino de URL realiza llamadas en píxeles desde una página hasta su destino. Siga estas instrucciones para crear un destino de URL con el Generador de destinos.
seo-description: Un destino de URL realiza llamadas en píxeles desde una página hasta su destino. Siga estas instrucciones para crear un destino de URL con el Generador de destinos.
seo-title: Configurar un destino de dirección URL
solution: Audience Manager
title: Configurar un destino de dirección URL
feature: Conceptos básicos de destino
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 3%

---

# Configurar un [!DNL URL Destination] {#configure-url-destination}

Un [!DNL URL destination] realiza llamadas en píxeles desde una página a su [!DNL destination]. Siga estas instrucciones para crear un [!DNL URL] [!DNL destination] con [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Para crear un [!DNL URL] [!DNL destination] nuevo, vaya a **[!UICONTROL Audience Data > Destinations > Create New Destination]** y complete las secciones como se describe a continuación.

## Información básica {#basic-info}

Esta sección contiene campos y opciones que inician el proceso de creación de [!DNL URL destination]. Para completar esta sección:

1. Haga clic en **[!UICONTROL Basic Information]** para mostrar los controles.
2. Asigne un nombre a [!DNL destination]. Evite abreviaciones y caracteres especiales.
3. *(Opcional)* Describa el  [!DNL destination]. Una descripción concisa es una forma eficaz de definir o proporcionar más información sobre un [!DNL destination].
4. En la lista **[!UICONTROL Category]**, elija **[!UICONTROL Custom]**.
5. En la lista **[!UICONTROL Environment]**, seleccione el entorno en el que desea almacenar en déclencheur el [!DNL URL destination].
6. En la lista **[!UICONTROL Type]**, haga clic en **[!UICONTROL URL]**.
7. *(Opcional)* Seleccione un  **[!UICONTROL Auto-fill Destination Mapping]**. Las opciones incluyen:
   * **[!UICONTROL Segment ID]**: Agrega y envía automáticamente el ID de segmento al  [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Agrega y envía automáticamente el código de integración de segmentos a la asignación de destino. El código de integración es un identificador único creado y utilizado por el cliente. Está limitada a 255 caracteres como máximo.
8. Haga clic en **[!UICONTROL Next]** para ir a la configuración de [!UICONTROL Configuration] o haga clic en **[!UICONTROL Data Export Labels]** para aplicar controles de exportación a [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Esta sección contiene opciones que aplican [controles de exportación de datos](../../features/data-export-controls.md) a un destino [!DNL URL]. Omita este paso si no utiliza controles de exportación de datos. Para completar esta sección:

1. Haga clic en **[!UICONTROL Data Export Labels]** para mostrar los controles.
2. Seleccione una etiqueta que corresponda al control de exportación de datos aplicado al destino (consulte [Agregar etiquetas de exportación a un destino](/help/using/features/destinations/add-data-export-labels.md) para obtener más información).
3. Haga clic **[!UICONTROL Save]**.

## Configuración {#configure-base-data}

Esta sección contiene opciones que le permiten establecer un [!DNL URL] base y delimitadores de datos pasados por la cadena [!DNL URL]. Esta sección es opcional. Para completar esta sección:

1. Haga clic en **[!UICONTROL Configuration]** para mostrar los controles.
1. *(Opcional)* Seleccione la  **[!UICONTROL Serialize]** casilla de verificación.
Esto le permite enviar segmentos a una [!DNL destination] secuencialmente en lugar de realizar llamadas independientes para cada segmento. La serialización ayuda a hacer que las transferencias de datos sean eficientes. Al seleccionar esta casilla de verificación, se muestran los campos URL y delimitador. Para obtener más información, consulte [Pares de clave-valor estándar y serie](../../features/destinations/key-value-pairs.md).
1. Si selecciona **[!UICONTROL Serialize]**, también debe configurar los campos URL y delimitador que se describen a continuación.

| Campo | Descripción |
|--- |--- |
| [!UICONTROL Base URL] | La parte base de un `HTTP` [!DNL URL] estándar que no cambia. Además, debe colocar el `%ALIAS%` [marcador de posición macro](../../features/destinations/destination-macros.md#destination-macros-defined) en la dirección URL base. Ejemplo: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | La parte base de un `HTTPS` [!DNL URL] seguro que no cambia. Además, debe colocar el `%ALIAS%`   [macro del marcador de posición](../../features/destinations/destination-macros.md#destination-macros-defined) en la dirección URL base. Ejemplo: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Símbolo que separa las variables de segmento en la cadena [!DNL URL]. Normalmente es una coma o punto y coma. Obtenga esta información de su socio de destino. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Esta sección le permite buscar y agregar segmentos a su [!UICONTROL destination]. Para completar esta sección:

1. Haga clic en **[!UICONTROL Segment Mappings]** para mostrar los controles.
1. En el cuadro **[!UICONTROL Search and Add Segments]**, empiece a escribir el nombre de un segmento o haga clic en **[!UICONTROL Browse All Segments]** examinar una lista de segmentos disponibles.
1. Haga clic en **[!UICONTROL Add Selected Segments]** cuando encuentre el segmento que desee utilizar. Al agregar un segmento, se abre la ventana [!UICONTROL Edit Mapping].
1. En [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Proporcione los pares clave-valor utilizados por el segmento.
   * **[!UICONTROL Start Date]** y  **[!UICONTROL End Date]**: Elija una fecha de inicio y de finalización para  [!DNL destination]. Si la fecha de finalización está en blanco, [!DNL destination] nunca caduca.
1. Haga clic **[!UICONTROL Done]**.
