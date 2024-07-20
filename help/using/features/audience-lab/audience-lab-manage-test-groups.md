---
description: Este procedimiento lo acompañará durante los pasos necesarios para crear, editar o eliminar un grupo de prueba en Audience Lab
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: Administrar grupos de prueba
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 0%

---

# Administrar grupos de prueba {#manage-test-groups}

Este procedimiento lo guiará para crear, editar o eliminar un grupo de prueba en [!UICONTROL Audience Lab].

## Crear grupos de prueba de segmentos {#create-test-groups}

### Requisitos previos

<!-- create-test-group.xml -->

* Debe tener al menos un **rasgo de conversión** configurado. Puede configurar características de conversión en [Generador de características](../../features/traits/create-onboarded-rule-based-traits.md), seleccionando **conversión** como tipo de evento. Para obtener más información sobre los rasgos de conversión y cómo configurarlos, hemos preparado un [vídeo](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) para ti.

  >[!IMPORTANT]
  >
  >[Los rasgos de carpeta](../../features/traits/about-folder-traits.md) son **no compatibles** con [!UICONTROL Audience Lab]. Si se establece el [Tipo de evento](../../features/traits/create-onboarded-rule-based-traits.md) de un rasgo de carpeta en **conversión**, no se generará ningún dato en [!UICONTROL Audience Lab] para ese rasgo de carpeta específico.

* Para empresas que usan [Control de acceso basado en roles](../../features/administration/administration-overview.md): asigne el [!UICONTROL Audience Lab] [permiso comodín](../../features/administration/administration-overview.md#wild-card-permissions) a **[!UICONTROL User Groups]** para proporcionar acceso. Permite al usuario crear y ver los resultados de una prueba. Un usuario solo podrá usar segmentos de una fuente de datos para la que tenga privilegios de **read** y **map to destination**. El usuario solamente podrá usar características de conversión de un origen de datos para el cual tenga permisos de **&quot;leer&quot;**. Un usuario solo podrá ver los destinos a los que tiene acceso. Por lo tanto, antes de agregar el permiso comodín [!DNL Audience Lab] a un grupo, asegúrese de que el grupo tenga:
   * acceso para leer los rasgos de conversión relevantes;
   * acceso para leer y asignar segmentos relevantes para las pruebas;
   * acceso a destinos relevantes.

Para crear un nuevo(a) [!UICONTROL Segment Test Group]:

1. Seleccione **[!UICONTROL Create New Test Group]** en el panel [!UICONTROL Audience Lab] para iniciar el asistente.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Rellene **[!UICONTROL Test Group Name]** y **[!UICONTROL Description]**.
   * Elija **[!UICONTROL Base Segment]** navegando en el explorador de archivos o escribiendo en la barra de búsqueda, confirme pulsando **[!UICONTROL Choose Segment.]**
   * Puede guardar el grupo de prueba como borrador y reanudar el trabajo en él más adelante.
   * Se mostrará una alerta en caso de que el segmento base seleccionado ya se esté utilizando en otros grupos de prueba. El uso del segmento base dos veces puede distorsionar los resultados de conversión de ambas pruebas.

1. **[!UICONTROL Allocate Test Segments]**

   * Puede crear **hasta 15 segmentos de prueba** y dividir el porcentaje de dispositivos como desee.
   * Puede editar el nombre de los segmentos de prueba haciendo clic en ellos.
   * Los porcentajes se dividen automáticamente de forma uniforme al 100 % cuando se asignan nuevos segmentos de prueba. A continuación, puede editar manualmente los porcentajes. Haga clic en la casilla de verificación después de editar los porcentajes y asegúrese de que suman el 100 %; de lo contrario, no podrá continuar con el siguiente paso.

1. **[!UICONTROL Set a Control Segment]**

   * Seleccione un segmento de control si desea reservar una parte determinada del segmento para utilizarla como grupo de control. Los grupos de control le permiten ver el impacto de los segmentos de prueba que ha creado en comparación con un análisis de rendimiento.
   * Puede seleccionar un segmento de prueba como segmento de control en la lista desplegable o puede elegir **[!UICONTROL None]** para que no haya control.
   * Haga clic en **[!UICONTROL Next]** cuando haya terminado.

1. **[!UICONTROL Select Conversion Traits]**

   * Añada características de conversión escribiendo en la ventana de características de conversión. Este es un paso de **obligatorio** y no puede continuar con el siguiente paso a menos que agregue al menos un rasgo de conversión.
   * Si lo desea, puede añadir hasta 5 rasgos de conversión.
   * Se mostrará una alerta en caso de que seleccione un rasgo de conversión ya utilizado para otros grupos de prueba.
   * Tenga en cuenta que Audience Manager no admite el uso de [características de carpeta](/help/using/features/traits/about-folder-traits.md) como características de conversión. Si se selecciona una característica de carpeta como característica de conversión, el resultado es 0 informes de acumulado y de tendencias mostrados dentro de la prueba.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Escriba los destinos deseados en el campo de búsqueda o utilice la flecha desplegable. [!UICONTROL Audience Lab] segmentos de prueba se pueden enviar a destinos de URL, cookie o servidor a servidor.
   * Arrastre y suelte segmentos en destinos.
   * Después de soltar un segmento en un destino, rellene **[!UICONTROL Destination Mapping Value]** en la persiana.
   * Puede enviar el mismo segmento de prueba a varios destinos y agregar varios segmentos de prueba a un único destino.
   * Los destinos aparecen atenuados si no están disponibles para un determinado segmento de prueba basado en [Controles de exportación de datos](../../features/data-export-controls.md).
   * Los usuarios solo verán los destinos a los que tienen acceso según el [grupo de usuarios RBAC](../../features/administration/administration-overview.md) al que pertenezcan.
   * Por último, se le pide que seleccione una fecha de inicio para el grupo de prueba. Esta fecha marca el inicio del periodo en el que se publicará el grupo de prueba en los destinos. Seleccione **Sin fecha de finalización** para realizar una comparación indefinida de los segmentos de prueba.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] con un perfil autenticado solo se admiten en destinos en tiempo real. Si se envía un segmento de prueba con una regla de combinación de perfiles de esa configuración a un destino servidor a servidor basado en archivos, es posible que las audiencias no se rellenen.

   Haga clic **[!UICONTROL Next]** para revisar y finalizar el grupo de prueba.

1. **[!UICONTROL Summary & Finalize]**

   * Revise la información que agregó en los pasos anteriores y seleccione **[!UICONTROL Finalize Group]**.
   * Recuerde que una vez que finalice un grupo de prueba, se puede duplicar o eliminar, pero no editar.

   >[!NOTE]
   >* Puede guardar los grupos de prueba en cualquier momento del proceso de creación y volver al asistente más adelante. El estado del grupo de prueba será **[!UICONTROL Draft]** y el grupo de prueba no enviará datos a los destinos hasta que finalice el grupo de prueba de segmentos.
   >* Para las pruebas de borrador, puede volver atrás y editar los grupos de prueba si hace clic en **[!UICONTROL Edit]** en la tarjeta del grupo de prueba en la vista principal [!UICONTROL Audience Lab].

## Editar grupos de prueba de segmentos {#edit-test-groups}

En [!UICONTROL Audience Lab], solo puede editar grupos de prueba de borrador. En el asistente [!UICONTROL Create Segment Test Group], puede guardar el grupo de prueba como borrador y reanudar el trabajo en él más adelante.

1. Vaya a la vista principal de [!UICONTROL Audience Lab].
1. Busque los grupos de prueba de borrador y seleccione el control **[!UICONTROL Edit]** en la tarjeta del grupo de prueba.
1. Reanude el asistente [Crear grupo de prueba de segmentos](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) y seleccione **[!UICONTROL Finalize Group]** cuando haya terminado.

## Eliminar grupos de prueba de segmentos {#delete-test-groups}

1. Vaya a la vista principal de [!UICONTROL Audience Lab].
1. Busque el grupo de prueba que desea eliminar. Puede hacer lo siguiente:

   * presione el control **[!UICONTROL Delete]** en la tarjeta del grupo de prueba o
   * presione el título del grupo de prueba en la tarjeta del grupo de prueba para ir a la vista [Información del grupo de prueba](../../features/audience-lab/audience-lab-information-view.md) y presione el control **[!UICONTROL Delete]** en la barra de título.

1. Para [segmentos de prueba completados](../../features/audience-lab/audience-lab.md#status), una alerta le pedirá que descargue el archivo CSV para guardar la creación de informes si lo desea.
