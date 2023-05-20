---
description: Cree, edite y elimine características de carpeta.
keywords: Rasgo de carpeta;Rasgos de carpeta;rasgos de carpeta;rasgo de carpeta
seo-description: Create, edit, and delete folder traits.
seo-title: Manage Folder Traits
solution: Audience Manager
title: Administrar rasgos de carpetas
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
exl-id: fa7a8d2a-dacc-413e-89d6-d3b7ce7bbbe3
source-git-commit: f7a4478589f4af1d467f1045a97dbb7f5cd6f9e5
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 5%

---

# Administrar rasgos de carpetas {#manage-folder-traits}

Cree, edite y elimine características de carpeta.

## Crear una característica de carpeta {#create-folder-trait}

A [!UICONTROL folder trait] se crea automáticamente al crear una carpeta nueva en su taxonomía.

<!-- create-folder-trait.xml -->

1. Ir a **[!UICONTROL Audience Data > Traits]** para ir al **Características** panel.
1. En el [!UICONTROL Trait Storage] ventana, pase el ratón sobre:

   * Texto &quot;Todas las características&quot; para agregar una nueva carpeta de nivel raíz.
   * Carpeta principal existente para agregar una nueva carpeta subordinada.

   ![](assets/folder_traits_create.PNG)

1. Haga clic en el icono + para crear la carpeta. Tenga en cuenta que puede crear un máximo de 2000 carpetas en su taxonomía. Consulte la documentación sobre los [límites de uso](../../features/administration/usage-limits.md) para obtener más información.
1. Asigne un nombre a la carpeta y haga clic en **Guardar**. Por ejemplo, una carpeta denominada Electronics tendrá un rasgo de carpeta denominado &quot;Rasgo de carpeta de Electronics&quot;. Puede ver y seleccionar el nuevo rasgo de carpeta en el panel de rasgos.
1. El nuevo rasgo de carpeta se asigna automáticamente al [!DNL Audience Manager] fuente de datos generada. Sus usuarios con las [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) permisos pueden cambiar la fuente de datos en el flujo de trabajo editar característica de carpeta. Consulte [Editar un rasgo de carpeta](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Editar un rasgo de carpeta {#edit-folder-trait}

Describe cómo se puede editar un [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. En el [!UICONTROL Traits] panel, pase el ratón sobre **[!UICONTROL Actions]** para la característica de carpeta que desea editar.
1. Haga clic en el lápiz para editar la característica.

   ![](assets/folder_traits_edit_border.png)

1. El **[!UICONTROL Edit]** El flujo de trabajo de permite cambiar la fuente de datos de las características de la carpeta. Seleccione la fuente de datos que desee y haga clic en **[!UICONTROL Save]**. Las fuentes de datos se ordenan numéricamente por [!DNL DPID], en el cuadro desplegable.

   Si su empresa utiliza [!UICONTROL Role-Based Access Rights (RBAC)], usted o los usuarios necesitan [permisos de acceso](../../features/traits/about-folder-traits.md#role-based-access-controls) a fuentes de datos de rasgos.

>[!NOTE]
>
>No se puede cambiar directamente el nombre de una característica de carpeta. [Cambiar nombre de la carpeta de almacenamiento asociada](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) para cambiar el nombre de la característica de carpeta.

## Eliminar un rasgo de carpeta {#delete-folder-trait}

Elimine un rasgo de carpeta eliminando la carpeta de almacenamiento a la que pertenece el rasgo.

<!-- delete-folder-trait.xml -->

1. **Datos de audiencia > Rasgos** para ir al **Características** panel.
1. En el [!UICONTROL Trait Storage] , elimine una carpeta pasando el puntero sobre ella y haciendo clic en el icono X.

   ![Resultado del paso](assets/folder_traits_create.PNG)

>[!NOTE]
>
>No puede eliminar una característica de carpeta si se utiliza en una expresión de segmento. Vaya a [vista de rasgos](../../features/traits/trait-details-page.md) para ver qué segmentos utilizan la característica de carpeta. A continuación, haga clic en el nombre del segmento para abrir [vista resumen de segmentos](../../features/segments/segment-summary-view.md), que permite eliminar rasgos de las expresiones de segmentos.
