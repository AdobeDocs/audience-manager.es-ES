---
description: Este procedimiento lo lleva a través de los pasos necesarios para crear, editar o eliminar un grupo de prueba en Audience Lab
seo-description: Este procedimiento lo lleva a través de los pasos necesarios para crear, editar o eliminar un grupo de prueba en Audience Lab
seo-title: Administrar grupos de prueba
solution: Audience Manager
title: Administrar grupos de prueba
uuid: 2 fadddeb -7574-4853-8 c 52-c 58456582 c 62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Test Groups {#manage-test-groups}

This procedure walks you through the steps needed to create, edit, or delete a test group in [!UICONTROL Audience Lab].

## Create Segment Test Groups {#create-test-groups}

### Requisitos previos

<!-- create-test-group.xml -->

* You need to have at least one **conversion trait** set up. You can set up conversion traits in the [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md), by selecting **conversion** as the event type. For more information on what conversion traits are and how to set them up, we prepared a [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) for you.

   >[!IMPORTANT]
   >
   >[Las características](../../features/traits/about-folder-traits.md) de carpeta **no son compatibles** [!UICONTROL Audience Lab]con. Setting the [Event Type](../../features/traits/create-onboarded-rule-based-traits.md) of a folder trait to **conversion** will not generate any data in [!UICONTROL Audience Lab] for that specific folder trait.

* For companies using [Role-Based Access Control](../../features/administration/administration-overview.md): Assign the [!UICONTROL Audience Lab] [wildcard permission](../../features/administration/administration-overview.md#wild-card-permissions) to **[!UICONTROL User Groups]** to provide access. Este permiso permite al usuario crear y ver los resultados de una prueba. A user will only be able to use segments from a data source they have **read** and **map to destination** privileges for. The user will only be able to use conversion traits from a data source for which they have **&quot;read&quot;** permissions. Un usuario solo podrá ver destinos a los que tengan acceso. So, before adding the [!DNL Audience Lab] wildcard permission to a group, make sure the group has:
   * access to read relevant conversion traits;
   * acceso para leer y asignar segmentos relevantes para pruebas;
   * acceso a destinos relevantes.

To create a new [!UICONTROL Segment Test Group]:

1. Select **[!UICONTROL Create New Test Group]** in the [!UICONTROL Audience Lab] dashboard to start the wizard.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Fill in a **[!UICONTROL Test Group Name]** and a **[!UICONTROL Description]**.
   * Choose the **[!UICONTROL Base Segment]** either by navigating in the file browser or by typing in the search bar, confirm by pressing **[!UICONTROL Choose Segment.]**
   * Puede guardar el grupo de prueba como borrador y reanudarlo más tarde.
   * Se mostrará una alerta en caso de que el segmento base seleccionado ya esté utilizado en otros grupos de prueba. El uso simultáneo del segmento base puede distorsionar los resultados de conversión de ambas pruebas.

1. **[!UICONTROL Allocate Test Segments]**

   * You can create **up to 15 test segments** and divide the percentage of devices as you wish.
   * Para editar el nombre de los segmentos de prueba, haga clic en ellos.
   * Los porcentajes se dividen automáticamente en 100% cuando se asignan nuevos segmentos de prueba. Luego puede editar manualmente los porcentajes. Haga clic en la casilla después de editar los porcentajes y asegúrese de que suman el 100%. De lo contrario, no podrá continuar con el paso siguiente.

1. **[!UICONTROL Set a Control Segment]**

   * Seleccione un segmento de control si desea apartar una parte determinada del segmento para que se utilice como grupo de control. Los grupos de control permiten ver el impacto de los segmentos de prueba que ha creado en comparación con un punto de referencia.
   * You can select a test segment as control segment in the drop-down list, or you can choose **[!UICONTROL None]** for no control.
   * Click **[!UICONTROL Next]** when you&#39;re done.

1. **[!UICONTROL Select Conversion Traits]**

   * Agregue características de conversión escribiendo en la ventana de características de conversión. This is a **mandatory** step and you cannot proceed to the next step unless you add at least one conversion trait.
   * Si lo desea, puede agregar hasta 5 características de conversión.
   * Se mostrará una alerta en caso de que seleccione una característica de conversión ya utilizada para otros grupos de prueba.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Escriba los destinos deseados en el campo de búsqueda o utilice la flecha desplegable. [!UICONTROL Audience Lab] los segmentos de prueba se pueden enviar a URL, cookies o destinos de servidor a servidor.
   * Arrastre y suelte segmentos en destinos.
   * After dropping a segment in a destination, fill in the **[!UICONTROL Destination Mapping Value]** in the blind.
   * Puede enviar el mismo segmento de prueba a varios destinos y agregar varios segmentos de prueba a un solo destino.
   * Destinations are grayed out if they are not available for a certain test segment based on [Data Export Controls](../../features/data-export-controls.md).
   * Users will only see the destinations they have access to based on the [RBAC User Group](../../features/administration/administration-overview.md) they belong to.
   * Finalmente, debe seleccionar una fecha de inicio para el grupo de prueba. Esta fecha marca el comienzo del período en el que el grupo de prueba se publicará en destinos. Select **No End Date** for an indefinite comparison of the test segments.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] con un perfil autenticado solo se admite en destinos en tiempo real. Si un segmento de prueba con una regla de combinación de perfiles de dicha configuración se envía a un destino servidor a servidor basado en archivos, es posible que las audiencias no se rellenen.

   Click **[!UICONTROL Next]** to review and finalize your test group.

1. **[!UICONTROL Summary & Finalize]**

   * Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.
   * Recuerde que una vez que finalice un grupo de prueba, se puede duplicar o eliminar, pero no se edita.
   >[!NOTE]
   >* Puede guardar los grupos de prueba en cualquier momento del proceso de creación y regresar al asistente más tarde. The test group status will be **[!UICONTROL Draft]** and the test group will not send any data to destinations until you finalize the segment test group.
   >* For draft tests, you can go back and edit the test groups by clicking **[!UICONTROL Edit]** in the test group card in the main [!UICONTROL Audience Lab] view.


## Edit Segment Test Groups {#edit-test-groups}

In [!UICONTROL Audience Lab], you are only able to edit draft test groups. In the [!UICONTROL Create Segment Test Group] wizard, you can save your test group as a draft and resume working on it later.

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Search for your draft test groups and select the **[!UICONTROL Edit]** control in the test group card.
1. Resume the [Create Segment Test Group](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) wizard and select **[!UICONTROL Finalize Group]** when you&#39;re done.

## Delete Segment Test Groups {#delete-test-groups}

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Busque el grupo de prueba que desee eliminar. Puede realizar una de las acciones siguientes:

   * press the **[!UICONTROL Delete]** control in the test group card, or
   * press the test group title in the test group card to go to the [Test Group Information](../../features/audience-lab/audience-lab-information-view.md) view and press the **[!UICONTROL Delete]** control in the title bar.

1. For [completed test segments](../../features/audience-lab/audience-lab.md#status), an alert will prompt you to download the CSV file to save the reporting if you wish.
