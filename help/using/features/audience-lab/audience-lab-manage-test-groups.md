---
description: Este procedimiento le guía por los pasos necesarios para crear, editar o eliminar un grupo de prueba en el laboratorio de Audiencias
seo-description: Este procedimiento le guía por los pasos necesarios para crear, editar o eliminar un grupo de prueba en el laboratorio de Audiencias
seo-title: Administrar grupos de pruebas
solution: Audience Manager
title: Administrar grupos de pruebas
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 0%

---


# Administrar grupos de pruebas {#manage-test-groups}

Este procedimiento le guía por los pasos necesarios para crear, editar o eliminar un grupo de prueba en [!UICONTROL Audience Lab].

## Crear grupos de prueba de segmentos {#create-test-groups}

### Requisitos previos

<!-- create-test-group.xml -->

* Debe tener al menos una **característica de conversión** configurada. Puede configurar las características de conversión en el [Generador de características](../../features/traits/create-onboarded-rule-based-traits.md) seleccionando **conversión** como tipo de evento. Para obtener más información sobre las características de conversión y cómo configurarlas, hemos preparado un [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) para usted.

   >[!IMPORTANT]
   >
   >[Los ](../../features/traits/about-folder-traits.md) atributos de carpeta  **no son** compatibles con  [!UICONTROL Audience Lab]. Al establecer el [Tipo de evento](../../features/traits/create-onboarded-rule-based-traits.md) de una característica de carpeta en **conversión** no se generarán datos en [!UICONTROL Audience Lab] para esa característica de carpeta específica.

* Para compañías que utilizan [Control de acceso basado en roles](../../features/administration/administration-overview.md): Asigne el [!UICONTROL Audience Lab] [permiso comodín](../../features/administration/administration-overview.md#wild-card-permissions) a **[!UICONTROL User Groups]** para proporcionar acceso. Este permiso permite al usuario crear y vista los resultados de una prueba. Un usuario solo podrá usar segmentos de un origen de datos para el que tenga **leer** y **asignar a destino** privilegios. El usuario solo podrá utilizar las características de conversión de un origen de datos para el que tenga permisos **&quot;read&quot;**. Un usuario solo podrá ver los destinos a los que tenga acceso. Por lo tanto, antes de agregar el permiso comodín [!DNL Audience Lab] a un grupo, asegúrese de que el grupo tenga:
   * acceso a la lectura de características de conversión pertinentes;
   * acceso a la lectura y asignación de segmentos pertinentes para las pruebas;
   * acceso a destinos relevantes.

Para crear un nuevo [!UICONTROL Segment Test Group]:

1. Seleccione **[!UICONTROL Create New Test Group]** en el panel [!UICONTROL Audience Lab] para inicio del asistente.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Rellene un **[!UICONTROL Test Group Name]** y un **[!UICONTROL Description]**.
   * Elija el **[!UICONTROL Base Segment]** navegando en el explorador de archivos o escribiendo en la barra de búsqueda, confirme presionando **[!UICONTROL Choose Segment.]**
   * Puede guardar el grupo de prueba como borrador y reanudar el trabajo en él más tarde.
   * Se mostrará una alerta en caso de que el segmento base seleccionado ya se esté utilizando en otros grupos de prueba. El uso del segmento base dos veces puede distorsionar los resultados de conversión para ambas pruebas.

1. **[!UICONTROL Allocate Test Segments]**

   * Puede crear **hasta 15 segmentos de prueba** y dividir el porcentaje de dispositivos como desee.
   * Puede editar el nombre de los segmentos de prueba haciendo clic en ellos.
   * Los porcentajes se dividen automáticamente uniformemente al 100 % cuando se asignan nuevos segmentos de prueba. A continuación, puede editar manualmente los porcentajes. Haga clic en la casilla de verificación después de editar los porcentajes y asegúrese de que suman hasta el 100 %; de lo contrario, no podrá continuar con el paso siguiente.

1. **[!UICONTROL Set a Control Segment]**

   * Seleccione un segmento de control si desea separar una parte determinada del segmento para utilizarlo como grupo de control. Los grupos de control le permiten ver el impacto de los segmentos de prueba que ha creado en comparación con un punto de referencia.
   * Puede seleccionar un segmento de prueba como segmento de control en la lista desplegable o puede elegir **[!UICONTROL None]** sin control.
   * Haga clic **[!UICONTROL Next]** cuando haya terminado.

1. **[!UICONTROL Select Conversion Traits]**

   * Añada las características de conversión escribiendo en la ventana de características de conversión. Este es un paso **obligatorio** y no puede continuar con el paso siguiente a menos que agregue al menos una característica de conversión.
   * Si lo desea, puede agregar hasta 5 características de conversión.
   * Se mostrará una alerta en caso de que seleccione una característica de conversión ya utilizada para otros grupos de prueba.
   * Tenga en cuenta que el Audience Manager no admite el uso de [características de carpeta](/help/using/features/traits/about-folder-traits.md) como características de conversión. Si se selecciona una característica de carpeta como característica de conversión, se muestra 0 sistemas de informes acumulados y de tendencia en la prueba.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Escriba los destinos deseados en el campo de búsqueda o utilice la flecha desplegable. [!UICONTROL Audience Lab] los segmentos de prueba se pueden enviar a destinos de URL, cookie o servidor a servidor.
   * Arrastre y suelte segmentos en destinos.
   * Después de soltar un segmento en un destino, rellene la **[!UICONTROL Destination Mapping Value]** en la ciega.
   * Puede enviar el mismo segmento de prueba a varios destinos y puede agregar varios segmentos de prueba a un único destino.
   * Los destinos aparecen atenuados si no están disponibles para un determinado segmento de prueba basado en [Controles de exportación de datos](../../features/data-export-controls.md).
   * Los usuarios solo verán los destinos a los que tienen acceso en función del [grupo de usuarios de RBAC](../../features/administration/administration-overview.md) al que pertenecen.
   * Por último, debe seleccionar una fecha de inicio para el grupo de prueba. Esta fecha marca el inicio del período en el que se publicará el grupo de prueba en los destinos. Seleccione **Sin fecha de finalización** para una comparación indefinida de los segmentos de prueba.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] con un perfil autenticado solo se admiten en los destinos en tiempo real. Si un segmento de prueba con una regla de combinación de perfiles de esa configuración se envía a un destino de servidor a servidor basado en archivos, es posible que las audiencias no se rellenen.

   Haga clic **[!UICONTROL Next]** para revisar y finalizar el grupo de prueba.

1. **[!UICONTROL Summary & Finalize]**

   * Revise la información agregada en los pasos anteriores y seleccione **[!UICONTROL Finalize Group]**.
   * Recuerde que una vez finalizado un grupo de prueba, puede duplicarse o eliminarse, pero no editarse.

   >[!NOTE]
   >* Puede guardar los grupos de prueba en cualquier momento del proceso de creación y volver al asistente más adelante. El estado del grupo de prueba será **[!UICONTROL Draft]** y el grupo de prueba no enviará ningún dato a los destinos hasta que finalice el grupo de prueba del segmento.
   >* Para las pruebas de borrador, puede volver atrás y editar los grupos de prueba haciendo clic en **[!UICONTROL Edit]** en la tarjeta del grupo de prueba en la vista principal [!UICONTROL Audience Lab].


## Editar grupos de prueba de segmentos {#edit-test-groups}

En [!UICONTROL Audience Lab], solo puede editar los grupos de prueba de borrador. En el asistente [!UICONTROL Create Segment Test Group], puede guardar el grupo de prueba como borrador y reanudar el trabajo en él posteriormente.

1. Vaya a la vista principal [!UICONTROL Audience Lab].
1. Busque los grupos de prueba de borrador y seleccione el control **[!UICONTROL Edit]** en la tarjeta del grupo de prueba.
1. Reanude el asistente [Crear grupo de prueba de segmento](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) y seleccione **[!UICONTROL Finalize Group]** cuando haya terminado.

## Eliminar grupos de prueba de segmentos {#delete-test-groups}

1. Vaya a la vista principal [!UICONTROL Audience Lab].
1. Busque el grupo de prueba que desee eliminar. Puede:

   * pulse el control **[!UICONTROL Delete]** en la tarjeta del grupo de prueba, o
   * presione el título del grupo de prueba en la tarjeta del grupo de prueba para ir a la vista [Información del grupo de prueba](../../features/audience-lab/audience-lab-information-view.md) y presione el control **[!UICONTROL Delete]** en la barra de título.

1. Para [segmentos de prueba completados](../../features/audience-lab/audience-lab.md#status), una alerta le pedirá que descargue el archivo CSV para guardar el sistema de informes si lo desea.
