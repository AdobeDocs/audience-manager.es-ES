---
description: Un destino URL realiza llamadas en píxeles desde una página hasta el destino. Siga estas instrucciones para crear un destino de URL con el Generador de destinos.
seo-description: Un destino URL realiza llamadas en píxeles desde una página hasta el destino. Siga estas instrucciones para crear un destino de URL con el Generador de destinos.
seo-title: Configurar un destino de dirección URL
solution: Audience Manager
title: Configurar un destino de dirección URL
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# Configurar un destino de dirección URL {#configure-url-destination}

Un [!DNL URL] destino realiza llamadas en píxeles desde una página hasta el destino. Siga estas instrucciones para crear un [!DNL URL] destino con [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Para crear un nuevo [!DNL URL] destino, vaya a **[!UICONTROL Audience Data > Destinations > Create New Destination]** y complete las secciones como se describe a continuación.

## Información básica {#basic-info}

Esta sección contiene los campos y las opciones que inician el proceso de creación del destino de URL. Para completar esta sección:

1. Haga clic **[!UICONTROL Basic Information]** para mostrar los controles.
2. Asigne un nombre al destino. Evite abreviaciones y caracteres especiales.
3. *(Opcional)* Describa el destino. Una descripción concisa es una forma eficaz de definir o proporcionar más información sobre un destino.
4. En la **[!UICONTROL Category]** lista, elija **[!UICONTROL Custom]**.
5. En la **[!UICONTROL Environment]** lista, seleccione el entorno en el que se activará el destino de la dirección URL.
6. En la **[!UICONTROL Type]** lista, haga clic en **[!UICONTROL URL]**.
7. *(Opcional)* Seleccione un **[!UICONTROL Auto-fill Destination Mapping]**. Las opciones incluyen:
   * **[!UICONTROL Segment ID]**:: Agrega y envía automáticamente el ID de segmento al destino.
   * **[!UICONTROL Integration Code Value]**:: Agrega y envía automáticamente el código de integración de segmentos a la asignación de destino. El código de integración es un identificador único creado y utilizado por el cliente. Está limitada a 255 caracteres como máximo.
8. Haga clic en **[!UICONTROL Next]** para ir a la [!UICONTROL Configuration] configuración o haga clic en **[!UICONTROL Data Export Labels]** para aplicar controles de exportación al destino.

## Etiquetas de exportación de datos {#data-export-labels-dest}

Esta sección contiene opciones que aplican controles [de exportación de](../../features/data-export-controls.md) datos a un [!DNL URL] destino. Omita este paso si no utiliza controles de exportación de datos. Para completar esta sección:

1. Haga clic **[!UICONTROL Data Export Labels]** para mostrar los controles.
2. Seleccione una etiqueta que corresponda al control de exportación de datos aplicado al destino (consulte [Agregar etiquetas de exportación a un destino](/help/using/features/destinations/add-data-export-labels.md) para obtener más información).
3. Haga clic en **[!UICONTROL Save]**.

## Configuración {#configure-base-data}

Esta sección contiene opciones que le permiten establecer un delimitador de base [!DNL URL] y de datos pasados por la [!DNL URL] cadena. Esta sección es opcional. Para completar esta sección:

1. Haga clic **[!UICONTROL Configuration]** para mostrar los controles.
1. *(Opcional)* Seleccione la **[!UICONTROL Serialize]** casilla de verificación.
Esto le permite enviar segmentos a un destino secuencialmente en lugar de realizar llamadas independientes para cada segmento. La serialización ayuda a hacer que las transferencias de datos sean eficientes. Al seleccionar esta casilla de verificación se exponen los campos de delimitador y URL. Para obtener más información, consulte [Estándar y Par](../../features/destinations/key-value-pairs.md)de clave-valor serie.
1. Si selecciona **[!UICONTROL Serialize]**, también debe configurar la dirección URL y los campos delimitadores que se describen a continuación.

| Campo | Descripción |
|--- |--- |
| Dirección URL base | Parte base de un estándar `HTTP` que no [!DNL URL] cambia. Además, debe colocar la macro `%ALIAS%` de [](../../features/destinations/destination-macros.md#destination-macros-defined) marcador de posición en la URL base. Ejemplo: `https://www.myCompany.com/%alias%...` |
| URL segura | Parte base de una seguridad `HTTPS` que no [!DNL URL] cambia. Además, debe colocar la macro `%ALIAS%` de [](../../features/destinations/destination-macros.md#destination-macros-defined) marcador de posición en la URL base. Ejemplo: `https://www.myCompany.com/%alias%...` |
| Delimitador | Símbolo que separa las variables de segmento en la [!DNL URL] cadena. Generalmente es una coma o punto y coma. Obtenga esta información de su socio de destino. |

## Asignaciones de segmentos {#segment-mappings}

Esta sección le permite buscar y agregar segmentos a su destino. Para completar esta sección:

1. Haga clic **[!UICONTROL Segment Mappings]** para mostrar los controles.
1. En el **[!UICONTROL Search and Add Segments]** cuadro, empiece a escribir el nombre de un segmento o haga clic en **[!UICONTROL Browse All Segments]** examinar una lista de segmentos disponibles.
1. Haga clic **[!UICONTROL Add Selected Segments]** cuando encuentre el segmento que desee utilizar. Al agregar un segmento se abre la [!UICONTROL Edit Mapping] ventana.
1. En [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**:: Proporcione los pares clave-valor utilizados por el segmento.
   * **[!UICONTROL Start Date]** y **[!UICONTROL End Date]**: Elija una fecha de inicio y de finalización para el destino. Si la fecha de finalización está en blanco, el destino nunca caduca.
1. Haga clic en **[!UICONTROL Done]**.