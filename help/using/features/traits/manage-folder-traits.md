---
description: Cree, edite y elimine características de carpetas.
keywords: Característica de carpeta; Características de carpeta; características de carpeta; característica de carpeta
seo-description: Cree, edite y elimine características de carpetas.
seo-title: Administrar características de carpeta
solution: Audience Manager
title: Administrar características de carpeta
uuid: 287 ac 280-bd 58-4985-85 bd-b 6501 eb 64 b 7 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Folder Traits {#manage-folder-traits}

Cree, edite y elimine características de carpetas.

## Create a Folder Trait {#create-folder-trait}

A [!UICONTROL folder trait] is created automatically when you create a new folder in your taxonomy.

<!-- create-folder-trait.xml -->

1. Go to **[!UICONTROL Audience Data > Traits]** to navigate to the **Traits** dashboard.
1. In the [!UICONTROL Trait Storage] window, hover over:

   * Texto &quot;Todas las características&quot; para agregar una nueva carpeta de nivel raíz.
   * Una carpeta principal existente para agregar una nueva carpeta subordinada.
   ![](assets/folder_traits_create.PNG)

1. Haga clic en el icono + para crear la carpeta. Tenga en cuenta que puede crear un máximo de 2000 carpetas en su taxonomía. Consulte la documentación sobre los [límites de uso](../../features/administration/usage-limits.md) para obtener más información.
1. Name the folder and click **Save**. Por ejemplo, una carpeta llamada Electrónica tendrá una característica de carpeta denominada «Características de la carpeta electrónica». Puede ver y seleccionar la nueva característica de carpeta en el tablero de características.
1. The new folder trait is automatically assigned to the [!DNL Audience Manager] generated data source. Your users with appropriate [!UICONTROL Role-Based Access Control ([!DNL RBAC])] permissions can change the data source in the edit folder trait workflow. See [Edit a Folder Trait](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Edit a Folder Trait {#edit-folder-trait}

Describes how you can edit a [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the **[!UICONTROL Actions]** column for the folder trait you want to edit.
1. Haga clic en el lápiz para editar la característica.

   ![](assets/folder_traits_edit_border.png)

1. The **[!UICONTROL Edit]** workflow allows you to change the data source for folder traits. Select your desired data source and click **[!UICONTROL Save]**. Data sources are sorted numerically, by [!DNL DPID], in the drop-down box.

   If your company uses [!UICONTROL Role-Based Access Rights (RBAC)], you or your users need [access permissions](../../features/traits/about-folder-traits.md#role-based-access-controls) to traits data sources.

>[!NOTE]
>
>No puede cambiar el nombre directamente de una carpeta. [Cambie el nombre de la carpeta](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) de almacenamiento asociada para cambiar el nombre de la carpeta.

## Delete a Folder Trait {#delete-folder-trait}

Elimine una característica de carpeta eliminando la carpeta de almacenamiento a la que pertenece.

<!-- delete-folder-trait.xml -->

1. **Datos de audiencia &gt; Características** para navegar al tablero **Características** .
1. In the [!UICONTROL Trait Storage] window, delete a folder by hovering over it and clicking the X icon.

   ![Resultado de paso](assets/folder_traits_create.PNG)

>[!NOTE]
>
>No se puede eliminar un rasgo de carpeta, si se utiliza en una expresión de segmento. Navigate to the [trait view](../../features/traits/trait-details-page.md) section to see which segments use the folder trait. Then, click on the segment name to open the [segment summary view](../../features/segments/segment-summary-view.md), which allows you to remove traits from segment expressions.