---
description: Un destino de URL realiza llamadas de píxeles desde una página a su destino. Siga estas instrucciones para crear un destino URL con el Generador de destino.
seo-description: Un destino de URL realiza llamadas de píxeles desde una página a su destino. Siga estas instrucciones para crear un destino URL con el Generador de destino.
seo-title: Configurar un destino de URL
solution: Audience Manager
title: Configurar un destino de URL
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# Configurar un destino de URL {#configure-url-destination}

[!DNL URL] Un destino realiza llamadas de píxeles desde una página a su destino. Siga estas instrucciones para crear [!DNL URL] un destino con [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Para crear [!DNL URL] un nuevo destino, vaya **[!UICONTROL Audience Data > Destinations > Create New Destination]** y complete las secciones como se describe a continuación.

## Información básica {#basic-info}

Esta sección contiene campos y opciones que inician el proceso de creación de destinos de URL. Para completar esta sección:

1. Haga clic para **[!UICONTROL Basic Information]** exponer los controles.
2. Asigne un nombre al destino. Evite abreviaciones y caracteres especiales.
3. *(Opcional)* Describa el destino. Una descripción concisa es una manera eficaz de definir o proporcionar más información sobre un destino.
4. En la **[!UICONTROL Category]** lista, elija **[!UICONTROL Custom]**.
5. En **[!UICONTROL Environment]** la lista, seleccione el entorno en el que se activará el destino de la URL.
6. En la **[!UICONTROL Type]** lista, haga clic **[!UICONTROL URL]** en.
7. *(Opcional)* Seleccione un **[!UICONTROL Auto-fill Destination Mapping]**. Las opciones incluyen:
   * **[!UICONTROL Segment ID]**: Agrega automáticamente y envía el ID de segmento al destino.
   * **[!UICONTROL Integration Code Value]**: Agrega y envía automáticamente el código de integración de segmentos a la asignación de destino. El código de integración es un identificador único creado y utilizado por el cliente. Tiene un límite de 255 caracteres, máximo.
8. Haga clic para **[!UICONTROL Next]** ir a [!UICONTROL Configuration] la configuración o haga clic **[!UICONTROL Data Export Labels]** para aplicar los controles de exportación al destino.

## Etiquetas de exportación de datos {#data-export-labels-dest}

Esta sección contiene opciones que aplican [controles de exportación de datos](../../features/data-export-controls.md) a [!DNL URL] un destino. Omita este paso si no utiliza los controles de exportación de datos. Para completar esta sección:

1. Haga clic para **[!UICONTROL Data Export Labels]** exponer los controles.
2. Seleccione una etiqueta que corresponda al control de exportación de datos aplicado al destino (consulte [Agregar etiquetas de exportación a un destino](/help/using/features/destinations/add-data-export-labels.md) para obtener detalles).
3. Haga clic en **[!UICONTROL Save]**.

## Configuración {#configure-base-data}

Esta sección contiene opciones que permiten establecer un base [!DNL URL] y delimitadores de datos pasados por [!DNL URL] la cadena. Esta sección es opcional. Para completar esta sección:

1. Haga clic para **[!UICONTROL Configuration]** exponer los controles.
1. *(Opcional)* Seleccione la casilla de **[!UICONTROL Serialize]** verificación.
Esto permite enviar segmentos a un destino secuencialmente en lugar de realizar llamadas independientes para cada segmento. La serialización ayuda a hacer eficientes las transferencias de datos. Al seleccionar esta casilla de verificación, se exponen los campos URL y delimitador. Para obtener más información, consulte [Pares de clave-valor estándar y valor de serie](../../features/destinations/key-value-pairs.md).
1. Si selecciona **[!UICONTROL Serialize]**, también debe configurar los campos URL y delimitadores que se describen a continuación.

| Campo | Descripción |
|--- |--- |
| Dirección URL base | Parte base de un estándar `HTTP`[!DNL URL] que no cambia. Además, debe colocar la macro `%ALIAS%`[de marcador de posición](../../features/destinations/destination-macros.md#destination-macros-defined) en la dirección URL base. Ejemplo: `https://www.myCompany.com/%alias%...` |
| URL segura | Parte base de un seguro `HTTPS`[!DNL URL] que no cambia. Además, debe colocar la macro `%ALIAS%`[de marcador de posición](../../features/destinations/destination-macros.md#destination-macros-defined) en la dirección URL base. Ejemplo: `https://www.myCompany.com/%alias%...` |
| Delimitador | Símbolo que separa las variables de segmentos en la [!DNL URL] cadena. Normalmente es una coma o punto y coma. Obtenga esta información de su socio de destino. |

## Asignaciones de segmentos {#segment-mappings}

Esta sección permite buscar y agregar segmentos al destino. Para completar esta sección:

1. Haga clic para **[!UICONTROL Segment Mappings]** exponer los controles.
1. En **[!UICONTROL Search and Add Segments]** el cuadro, empiece a escribir el nombre de un segmento o haga clic **[!UICONTROL Browse All Segments]** en Examinar una lista de segmentos disponibles.
1. Haga clic **[!UICONTROL Add Selected Segments]** en cuando encuentre el segmento que desee utilizar. Al agregar un segmento, se abre [!UICONTROL Edit Mapping] la ventana.
1. En [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Proporcione los pares de clave-valor que utiliza el segmento.
   * **[!UICONTROL Start Date]** y **[!UICONTROL End Date]**: Elija una fecha de inicio y de finalización para el destino. Si la fecha de finalización está en blanco, el destino nunca caduca.
1. Haga clic en **[!UICONTROL Done]**.