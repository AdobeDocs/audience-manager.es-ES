---
description: Este procedimiento lo acompaña durante los pasos necesarios para crear, editar o eliminar un grupo de prueba en el Audience Lab
seo-description: Este procedimiento lo acompaña durante los pasos necesarios para crear, editar o eliminar un grupo de prueba en el Audience Lab
seo-title: Administrar grupos de pruebas
solution: Audience Manager
title: Administrar grupos de pruebas
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: 'Audience Lab '
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 1%

---

# Administrar grupos de pruebas {#manage-test-groups}

Este procedimiento lo acompaña durante los pasos necesarios para crear, editar o eliminar un grupo de prueba en [!UICONTROL Audience Lab].

## Crear grupos de prueba de segmentos {#create-test-groups}

### Requisitos previos

<!-- create-test-group.xml -->

* Debe tener al menos un **rasgo de conversión** configurado. Puede configurar características de conversión en el [Generador de características](../../features/traits/create-onboarded-rule-based-traits.md) seleccionando **conversión** como tipo de evento. Para obtener más información sobre cuáles son los rasgos de conversión y cómo configurarlos, preparamos un [vídeo](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) para usted.

   >[!IMPORTANT]
   >
   >[Los ](../../features/traits/about-folder-traits.md) rasgos de carpeta  **no son** compatibles con  [!UICONTROL Audience Lab]. Si se establece el [Tipo de evento](../../features/traits/create-onboarded-rule-based-traits.md) de un rasgo de carpeta en **conversión** no se generará ningún dato en [!UICONTROL Audience Lab] para ese rasgo de carpeta específico.

* Para empresas que utilizan [Control de acceso basado en roles](../../features/administration/administration-overview.md): Asigne el [!UICONTROL Audience Lab] [permiso comodín](../../features/administration/administration-overview.md#wild-card-permissions) a **[!UICONTROL User Groups]** para proporcionar acceso. Este permiso permite al usuario crear y ver los resultados de una prueba. Un usuario solo podrá utilizar segmentos de una fuente de datos para la que tenga **read** y **map to destination** privilegios. El usuario solo podrá utilizar características de conversión de una fuente de datos para la que tenga permisos de **&quot;read&quot;**. Un usuario solo podrá ver los destinos a los que tenga acceso. Por lo tanto, antes de añadir el permiso comodín [!DNL Audience Lab] a un grupo, asegúrese de que este tenga:
   * acceso a la lectura de características de conversión relevantes;
   * acceso a la lectura y asignación de segmentos relevantes para las pruebas;
   * acceso a destinos relevantes.

Para crear un nuevo [!UICONTROL Segment Test Group]:

1. Seleccione **[!UICONTROL Create New Test Group]** en el panel [!UICONTROL Audience Lab] para iniciar el asistente.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Rellene un **[!UICONTROL Test Group Name]** y un **[!UICONTROL Description]**.
   * Elija el **[!UICONTROL Base Segment]** navegando por el explorador de archivos o escribiendo en la barra de búsqueda, confirme pulsando **[!UICONTROL Choose Segment.]**
   * Puede guardar el grupo de prueba como borrador y continuar trabajando en él más adelante.
   * Se mostrará una alerta en caso de que el segmento base seleccionado ya se haya utilizado en otros grupos de prueba. El uso del segmento base dos veces puede distorsionar los resultados de conversión para ambas pruebas.

1. **[!UICONTROL Allocate Test Segments]**

   * Puede crear **hasta 15 segmentos de prueba** y dividir el porcentaje de dispositivos como desee.
   * Puede editar el nombre de los segmentos de prueba haciendo clic en ellos.
   * Los porcentajes se dividen automáticamente uniformemente al 100 % cuando se asignan nuevos segmentos de prueba. A continuación, puede editar manualmente los porcentajes. Haga clic en la casilla de verificación después de editar los porcentajes y asegúrese de que suman hasta el 100 %; de lo contrario, no podrá continuar con el paso siguiente.

1. **[!UICONTROL Set a Control Segment]**

   * Seleccione un segmento de control si desea apartar una parte determinada del segmento para utilizarla como grupo de control. Los grupos de control le permiten ver el impacto de los segmentos de prueba que ha creado en comparación con un punto de referencia.
   * Puede seleccionar un segmento de prueba como segmento de control en la lista desplegable o elegir **[!UICONTROL None]** sin control.
   * Haga clic en **[!UICONTROL Next]** cuando haya terminado.

1. **[!UICONTROL Select Conversion Traits]**

   * Para agregar características de conversión, escriba en la ventana de características de conversión. Este es un paso **obligatorio** y no puede continuar con el siguiente paso a menos que agregue al menos un rasgo de conversión.
   * Si lo desea, puede agregar hasta 5 características de conversión.
   * Se mostrará una alerta en caso de que seleccione un rasgo de conversión que ya se haya utilizado en otros grupos de prueba.
   * Tenga en cuenta que el Audience Manager no admite el uso de [características de carpeta](/help/using/features/traits/about-folder-traits.md) como características de conversión. Si se selecciona un rasgo de carpeta como rasgo de conversión, los informes de acumulados y tendencias se muestran en la prueba.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Escriba los destinos deseados en el campo de búsqueda o utilice la flecha desplegable. [!UICONTROL Audience Lab] los segmentos de prueba se pueden enviar a destinos de URL, cookies o servidor a servidor.
   * Arrastre y suelte los segmentos en los destinos.
   * Después de soltar un segmento en un destino, rellene la **[!UICONTROL Destination Mapping Value]** en la ciega.
   * Puede enviar el mismo segmento de prueba a varios destinos y puede agregar varios segmentos de prueba a un único destino.
   * Los destinos aparecen atenuados si no están disponibles para un determinado segmento de prueba basado en [Controles de exportación de datos](../../features/data-export-controls.md).
   * Los usuarios solo verán los destinos a los que tienen acceso en función del [grupo de usuarios de RBAC](../../features/administration/administration-overview.md) al que pertenecen.
   * Por último, es necesario seleccionar una fecha de inicio para el grupo de prueba. Esta fecha marca el inicio del periodo en el que el grupo de prueba se publicará en los destinos. Seleccione **Sin fecha de finalización** para una comparación indefinida de los segmentos de prueba.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] con un perfil autenticado solo se admiten en destinos en tiempo real. Si un segmento de prueba con una regla de combinación de perfiles de esa configuración se envía a un destino de servidor a servidor basado en archivos, es posible que las audiencias no se rellenen.

   Haga clic en **[!UICONTROL Next]** para revisar y finalizar el grupo de prueba.

1. **[!UICONTROL Summary & Finalize]**

   * Revise la información añadida en los pasos anteriores y seleccione **[!UICONTROL Finalize Group]**.
   * Recuerde que una vez finalizado un grupo de prueba, puede duplicarse o eliminarse, pero no editarse.

   >[!NOTE]
   >* Puede guardar los grupos de prueba en cualquier punto del proceso de creación y volver al asistente más adelante. El estado del grupo de prueba será **[!UICONTROL Draft]** y el grupo de prueba no enviará ningún dato a los destinos hasta que finalice el grupo de prueba de segmento.
   >* Para las pruebas de borrador, puede volver atrás y editar los grupos de prueba haciendo clic en **[!UICONTROL Edit]** en la tarjeta del grupo de prueba en la vista principal [!UICONTROL Audience Lab].


## Editar grupos de prueba de segmentos {#edit-test-groups}

En [!UICONTROL Audience Lab], solo puede editar los grupos de prueba de borrador. En el asistente [!UICONTROL Create Segment Test Group], puede guardar el grupo de prueba como borrador y continuar trabajando en él más adelante.

1. Vaya a la vista principal [!UICONTROL Audience Lab].
1. Busque los grupos de prueba de borrador y seleccione el control **[!UICONTROL Edit]** en la tarjeta del grupo de prueba.
1. Reanude el asistente [Crear grupo de prueba de segmentos](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) y seleccione **[!UICONTROL Finalize Group]** cuando haya terminado.

## Eliminar grupos de prueba de segmentos {#delete-test-groups}

1. Vaya a la vista principal [!UICONTROL Audience Lab].
1. Busque el grupo de prueba que desea eliminar. Puede:

   * pulse el control **[!UICONTROL Delete]** en la tarjeta del grupo de prueba, o
   * pulse el título del grupo de prueba en la tarjeta del grupo de prueba para ir a la vista [Información del grupo de prueba](../../features/audience-lab/audience-lab-information-view.md) y pulse el control **[!UICONTROL Delete]** en la barra de título.

1. Para [segmentos de prueba completados](../../features/audience-lab/audience-lab.md#status), una alerta le pedirá que descargue el archivo CSV para guardar el informe si lo desea.
