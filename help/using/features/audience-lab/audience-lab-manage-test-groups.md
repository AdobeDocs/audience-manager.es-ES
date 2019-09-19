---
description: Este procedimiento le guía por los pasos necesarios para crear, editar o eliminar un grupo de prueba en Audience Lab
seo-description: Este procedimiento le guía por los pasos necesarios para crear, editar o eliminar un grupo de prueba en Audience Lab
seo-title: Administrar grupos de pruebas
solution: Audience Manager
title: Administrar grupos de pruebas
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Administrar grupos de pruebas {#manage-test-groups}

Este procedimiento le guía por los pasos necesarios para crear, editar o eliminar un grupo de prueba en [!UICONTROL Audience Lab].

## Crear grupos de prueba de segmentos {#create-test-groups}

### Requisitos previos

<!-- create-test-group.xml -->

* Debe tener al menos una característica **de conversión** configurada. Puede configurar las características de conversión en el Generador [de](../../features/traits/create-onboarded-rule-based-traits.md)características seleccionando **conversión** como tipo de evento. Para obtener más información sobre las características de conversión y cómo configurarlas, hemos preparado un [vídeo](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) .

   >[!IMPORTANT]
   >
   >[Las características](../../features/traits/about-folder-traits.md) de carpeta **no son compatibles** con [!UICONTROL Audience Lab]. La configuración del tipo [de](../../features/traits/create-onboarded-rule-based-traits.md) evento de una característica de carpeta en **conversión** no generará ningún dato en [!UICONTROL Audience Lab] para esa característica de carpeta específica.

* Para empresas que utilizan el control [de acceso basado en](../../features/administration/administration-overview.md)roles: Asigne el permiso [!UICONTROL Audience Lab] [comodín para](../../features/administration/administration-overview.md#wild-card-permissions) **[!UICONTROL User Groups]** proporcionar acceso. Este permiso permite al usuario crear y ver los resultados de una prueba. Un usuario solo podrá usar segmentos de un origen de datos para el que haya **leído** y **asignado privilegios de destino** . El usuario solo podrá utilizar las características de conversión de una fuente de datos para la que tenga permisos de **"lectura"** . Un usuario solo podrá ver los destinos a los que tenga acceso. Por lo tanto, antes de agregar el permiso de [!DNL Audience Lab] comodín a un grupo, asegúrese de que éste tenga:
   * acceso a la lectura de características de conversión pertinentes;
   * acceso a la lectura y asignación de segmentos pertinentes para las pruebas;
   * acceso a destinos relevantes.

Para crear un nuevo [!UICONTROL Segment Test Group]:

1. Seleccione **[!UICONTROL Create New Test Group]** en el [!UICONTROL Audience Lab] tablero para iniciar el asistente.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Rellene un **[!UICONTROL Test Group Name]** y un **[!UICONTROL Description]**.
   * Elija la opción **[!UICONTROL Base Segment]** navegando en el explorador de archivos o escribiendo en la barra de búsqueda; para confirmarla, pulse **[!UICONTROL Choose Segment.]**
   * Puede guardar el grupo de prueba como borrador y reanudar el trabajo en él posteriormente.
   * Se mostrará una alerta en caso de que el segmento base seleccionado ya se esté utilizando en otros grupos de prueba. El uso del segmento base dos veces puede distorsionar los resultados de conversión para ambas pruebas.

1. **[!UICONTROL Allocate Test Segments]**

   * Puede crear **hasta 15 segmentos** de prueba y dividir el porcentaje de dispositivos como desee.
   * Puede editar el nombre de los segmentos de prueba haciendo clic en ellos.
   * Los porcentajes se dividen automáticamente uniformemente al 100 % cuando se asignan nuevos segmentos de prueba. A continuación, puede editar manualmente los porcentajes. Haga clic en la casilla de verificación después de editar los porcentajes y asegúrese de que suman hasta el 100 %; de lo contrario, no podrá continuar con el paso siguiente.

1. **[!UICONTROL Set a Control Segment]**

   * Seleccione un segmento de control si desea separar una parte determinada del segmento para utilizarlo como grupo de control. Los grupos de control le permiten ver el impacto de los segmentos de prueba que ha creado en comparación con un punto de referencia.
   * Puede seleccionar un segmento de prueba como segmento de control en la lista desplegable o puede elegir **[!UICONTROL None]** sin control.
   * Haga clic **[!UICONTROL Next]** cuando haya terminado.

1. **[!UICONTROL Select Conversion Traits]**

   * Agregue características de conversión escribiendo en la ventana de características de conversión. Este es un paso **obligatorio** y no puede continuar con el siguiente paso a menos que agregue al menos una característica de conversión.
   * Si lo desea, puede agregar hasta 5 características de conversión.
   * Se mostrará una alerta en caso de que seleccione una característica de conversión ya utilizada para otros grupos de prueba.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Escriba los destinos deseados en el campo de búsqueda o utilice la flecha desplegable. [!UICONTROL Audience Lab] los segmentos de prueba se pueden enviar a destinos de URL, cookie o servidor a servidor.
   * Arrastre y suelte segmentos en destinos.
   * Después de soltar un segmento en un destino, rellene el **[!UICONTROL Destination Mapping Value]** elemento ciego.
   * Puede enviar el mismo segmento de prueba a varios destinos y puede agregar varios segmentos de prueba a un único destino.
   * Los destinos aparecen atenuados si no están disponibles para un segmento de prueba determinado según los controles [de exportación de](../../features/data-export-controls.md)datos.
   * Los usuarios solo verán los destinos a los que tienen acceso en función del grupo [de usuarios de](../../features/administration/administration-overview.md) RBAC al que pertenecen.
   * Por último, debe seleccionar una fecha de inicio para el grupo de prueba. Esta fecha marca el inicio del período en el que el grupo de prueba se publicará en los destinos. Seleccione **Sin fecha** de finalización para una comparación indefinida de los segmentos de prueba.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] con un perfil autenticado solo se admiten en destinos en tiempo real. Si un segmento de prueba con una regla de combinación de perfiles de esa configuración se envía a un destino de servidor a servidor basado en archivos, es posible que las audiencias no se rellenen.

   Haga clic en **[!UICONTROL Next]** para revisar y finalizar el grupo de prueba.

1. **[!UICONTROL Summary & Finalize]**

   * Revise la información agregada en los pasos anteriores y seleccione **[!UICONTROL Finalize Group]**.
   * Recuerde que una vez finalizado un grupo de prueba, puede duplicarse o eliminarse, pero no editarse.
   >[!NOTE]
   >* Puede guardar los grupos de prueba en cualquier momento del proceso de creación y volver al asistente más adelante. El estado del grupo de prueba será **[!UICONTROL Draft]** y el grupo de prueba no enviará ningún dato a los destinos hasta que finalice el grupo de prueba del segmento.
   >* Para las pruebas de borrador, puede volver atrás y editar los grupos de prueba haciendo clic **[!UICONTROL Edit]** en la tarjeta del grupo de prueba en la [!UICONTROL Audience Lab] vista principal.


## Editar grupos de prueba de segmentos {#edit-test-groups}

En [!UICONTROL Audience Lab], solo puede editar grupos de prueba de borrador. En el [!UICONTROL Create Segment Test Group] asistente, puede guardar el grupo de prueba como borrador y reanudar el trabajo en él posteriormente.

1. Vaya a la vista [!UICONTROL Audience Lab] principal.
1. Busque los grupos de prueba de borrador y seleccione el **[!UICONTROL Edit]** control en la tarjeta del grupo de prueba.
1. Reanude el asistente [Crear grupo](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) de prueba de segmento y seleccione **[!UICONTROL Finalize Group]** cuando haya terminado.

## Eliminar grupos de prueba de segmentos {#delete-test-groups}

1. Vaya a la vista [!UICONTROL Audience Lab] principal.
1. Busque el grupo de prueba que desee eliminar. Puede:

   * pulse el **[!UICONTROL Delete]** control en la tarjeta del grupo de prueba, o
   * presione el título del grupo de prueba en la tarjeta del grupo de prueba para ir a la vista Información [del grupo de](../../features/audience-lab/audience-lab-information-view.md) pruebas y presione el **[!UICONTROL Delete]** control en la barra de título.

1. Para los segmentos [de prueba](../../features/audience-lab/audience-lab.md#status)completados, una alerta le pedirá que descargue el archivo CSV para guardar el informe si lo desea.
