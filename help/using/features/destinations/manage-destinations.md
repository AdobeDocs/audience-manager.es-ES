---
description: La página de aterrizaje Destino muestra todos los destinos de URL, cookie y servidor a servidor. Proporciona funciones que permiten crear, editar, buscar e informar sobre destinos. La página de aterrizaje se encuentra en Datos de audiencia > Destinos.
seo-description: La página de aterrizaje Destino muestra todos los destinos de URL, cookie y servidor a servidor. Proporciona funciones que permiten crear, editar, buscar e informar sobre destinos. La página de aterrizaje se encuentra en Datos de audiencia > Destinos.
seo-title: Administrar destinos
solution: Audience Manager
title: Administrar destinos
uuid: 6 b 66 ff 42-0075-49 a 7-a 58 f -7 f 8 ea 2295 fdc
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Administrar destinos {#manage-destinations}

La página [!UICONTROL Destination] de aterrizaje muestra todos [!DNL URL]los destinos de servidor a servidor, cookie y servidor. Proporciona funciones que permiten crear, editar, buscar e informar sobre destinos. La página de aterrizaje se encuentra en **[!UICONTROL Audience Data > Destinations]**.

## Página de aterrizaje predeterminada {#default-landing-page}

<!-- destinations-home.xml -->

La página de aterrizaje predeterminada enumera los destinos según el tipo. Puede filtrar los destinos utilizando las cuatro fichas disponibles:

* **Todos**: muestra todos los tipos de destinos.
* **Adobe Experience Cloud**: muestra destinos que envían datos a otras soluciones de Adobe Experience Cloud. Actualmente, la única opción compatible es Adobe Analytics. See [Configure an Analytics Destination](/help/using/features/destinations/create-analytics-destination.md).
* **Plataformas integradas**: muestra destinos basados en las personas y en los dispositivos (también denominados destinos servidor a servidor). Tenga en cuenta que los destinos basados en personas actualmente son una función beta que solo está disponible para clientes seleccionados.
* **Personalizado**: muestra destinos de URL y cookie.


![](assets/destinations-landing.png)

## Página de aterrizaje de audiencias objetivo {#audiences-landing-page}

Para ver los datos de audiencia y las tasas de coincidencia del destino servidor a servidor, seleccione **[!UICONTROL Integrated Platforms > Device-Based]**.

Para obtener más información sobre la información mostrada, consulte [Interfaz de audiencias abordables](/help/using/features/addressable-audiences.md#addressable-audience-interface).

![](/help/using/features/assets/addressable-audiences-landing.png)

## Configurar un destino de URL {#configure-url-destination}

[!DNL URL] Un destino realiza llamadas de píxeles desde una página a su destino. Siga estas instrucciones para crear [!DNL URL] un destino con [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Para crear [!DNL URL] un nuevo destino, vaya **[!UICONTROL Audience Data > Destinations > Create New Destination]** y complete las secciones como se describe a continuación.

### Información básica {#basic-info}

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

### Etiquetas de exportación de datos {#data-export-labels-dest}

Esta sección contiene opciones que aplican [controles de exportación de datos](../../features/data-export-controls.md) a [!DNL URL] un destino. Omita este paso si no utiliza los controles de exportación de datos. Para completar esta sección:

1. Haga clic para **[!UICONTROL Data Export Labels]** exponer los controles.
2. Seleccione una etiqueta que corresponda al control de exportación de datos aplicado al destino (consulte [Agregar etiquetas de exportación a un destino](../../features/destinations/manage-destinations.md#add-data-export-labels) para obtener detalles).
3. Haga clic en **[!UICONTROL Save]**.

### Configuración {#configure-base-data}

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

### Asignaciones de segmentos {#segment-mappings}

Esta sección permite buscar y agregar segmentos al destino. Para completar esta sección:

1. Haga clic para **[!UICONTROL Segment Mappings]** exponer los controles.
1. En **[!UICONTROL Search and Add Segments]** el cuadro, empiece a escribir el nombre de un segmento o haga clic **[!UICONTROL Browse All Segments]** en Examinar una lista de segmentos disponibles.
1. Haga clic **[!UICONTROL Add Selected Segments]** en cuando encuentre el segmento que desee utilizar. Al agregar un segmento, se abre [!UICONTROL Edit Mapping] la ventana.
1. En [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Proporcione los pares de clave-valor que utiliza el segmento.
   * **[!UICONTROL Start Date]** y **[!UICONTROL End Date]**: Elija una fecha de inicio y de finalización para el destino. Si la fecha de finalización está en blanco, el destino nunca caduca.
1. Haga clic en **[!UICONTROL Done]**.

## Agregar o editar segmentos para destinos de servidor a servidor {#add-edit-segments}

Solo se pueden agregar o editar segmentos para un destino servidor a servidor ([!DNL S2S]). No puede crear [!DNL S2S] destinos con [!UICONTROL Destination Builder]. Póngase en contacto con su asesor para configurar [!DNL S2S] destinos. Siga estas instrucciones para agregar o editar segmentos para un [!DNL S2S] destino.

<!-- destination-s2s-edit.xml -->

Para agregar o editar asignaciones de segmentos para un [!DNL S2S] destino:

1. Vaya **[!UICONTROL Audience Data > Destinations]** a. Seleccione **Plataformas integradas &gt; Basadas en dispositivo** y busque [!DNL S2S] el destino con el que desea trabajar.
2. En [!UICONTROL Action] la columna, haga clic en el icono de lápiz para editar el destino.
   * En **[!UICONTROL Search and Add Segments]** el cuadro, empiece a escribir el nombre de un segmento o haga clic **[!UICONTROL Browse All Segments]** en Examinar una lista de segmentos disponibles.
   * Haga clic **[!UICONTROL Add Selected Segments]** en cuando encuentre el segmento que desee utilizar. Al agregar un segmento, se abre [!UICONTROL Edit Mapping] la ventana.
   * En [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Defina un valor para el par [clave-valor](../../features/destinations/key-value-pairs.md) utilizado por este destino.
      * **[!UICONTROL Start Date]** y **[!UICONTROL End Date]**: Elija una fecha de inicio y de finalización para el destino. Si la fecha de finalización está en blanco, el destino nunca caduca.
3. Haga clic en **[!UICONTROL Save]** y, a continuación, haga clic **[!UICONTROL Done]** en.

## Agregar etiquetas de exportación de datos a un destino {#add-data-export-labels}

[!DNL Data Export Labels] trabaje con [!DNL Export Controls] el que establezca en un origen de datos. [!DNL Data Export Labels] impedir que agregue características restringidas a un segmento y envíe datos de segmentos a un destino. Puede configurar varias etiquetas de exportación a un nuevo o existente [!DNL cookie][!DNL URL] destino.

>[!NOTE]
>
>Para agregar una etiqueta de exportación, necesita permisos *de administrador o* suficientes privilegios para crear o editar un destino.

<!-- t_export_labels.xml -->

Para agregar etiquetas de exportación a un destino:

1. Haga clic en **[!UICONTROL Audience Data]**:
   * Para nuevos destinos: Haga clic **[!UICONTROL Create New Destination]** en. Complete [!UICONTROL Basic Information] la sección antes de seleccionar una etiqueta de exportación de datos. Consulte [Creación de un destino de cookie](../../features/destinations/manage-destinations.md#create-cookie-destination) o [Creación de un destino de URL para](../../features/destinations/manage-destinations.md#configure-url-destination) obtener información.
   * Para destinos existentes: Utilice [!DNL Search] el cuadro para encontrar el destino o desplazarse por la lista y hacer clic en el nombre de destino para abrirlo.
1. Seleccione una [!DNL Data Export Label]. Deje las casillas de verificación en blanco si no desea establecer restricciones de exportación. Las etiquetas de exportación incluyen las siguientes opciones:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Las restricciones de exportación no funcionarán a menos que establezca un [control de exportación coincidente](../../features/data-export-controls.md) en un origen de datos.
1. Haga clic en **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Crear una fuente de datos](../../features/manage-datasources.md#create-data-source)

