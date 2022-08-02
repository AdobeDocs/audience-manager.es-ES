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

## Crear un rasgo de carpeta {#create-folder-trait}

A [!UICONTROL folder trait] se crea automáticamente al crear una carpeta nueva en la taxonomía.

<!-- create-folder-trait.xml -->

1. Vaya a **[!UICONTROL Audience Data > Traits]** para navegar hasta el **Rasgos** tablero.
1. En el [!UICONTROL Trait Storage] , pase el ratón sobre:

   * Texto &quot;Todas las características&quot; para añadir una nueva carpeta de nivel raíz.
   * Una carpeta principal existente para agregar una nueva carpeta subordinada.

   ![](assets/folder_traits_create.PNG)

1. Haga clic en el icono + para crear la carpeta. Tenga en cuenta que puede crear un máximo de 2000 carpetas en su taxonomía. Consulte la documentación sobre los [límites de uso](../../features/administration/usage-limits.md) para obtener más información.
1. Asigne un nombre a la carpeta y haga clic en **Guardar**. Por ejemplo, una carpeta llamada Electronics tendrá un rasgo de carpeta denominado &quot;Rasgo de carpeta electrónica&quot;. Puede ver y seleccionar el nuevo rasgo de carpeta en el panel de características.
1. El nuevo rasgo de carpeta se asigna automáticamente al [!DNL Audience Manager] fuente de datos generada. Sus usuarios con las [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) pueden cambiar la fuente de datos en el flujo de trabajo de edición de características de carpeta. Consulte [Editar un rasgo de carpeta](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Editar un rasgo de carpeta {#edit-folder-trait}

Describe cómo editar un [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. En el [!UICONTROL Traits] tablero, pase el ratón sobre **[!UICONTROL Actions]** para el rasgo de carpeta que desea editar.
1. Haga clic en el lápiz para editar el rasgo.

   ![](assets/folder_traits_edit_border.png)

1. La variable **[!UICONTROL Edit]** el flujo de trabajo le permite cambiar la fuente de datos para rasgos de carpeta. Seleccione la fuente de datos que desee y haga clic en **[!UICONTROL Save]**. Las fuentes de datos se ordenan numéricamente, por [!DNL DPID], en el cuadro desplegable.

   Si su empresa utiliza [!UICONTROL Role-Based Access Rights (RBAC)], usted o sus usuarios necesitan [permisos de acceso](../../features/traits/about-folder-traits.md#role-based-access-controls) para identificar las fuentes de datos de características.

>[!NOTE]
>
>No se puede cambiar directamente el nombre de un rasgo de carpeta. [Cambiar el nombre de la carpeta de almacenamiento asociada](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) para cambiar el nombre del rasgo de carpeta.

## Eliminar un rasgo de carpeta {#delete-folder-trait}

Elimine un rasgo de carpeta eliminando la carpeta de almacenamiento a la que pertenece el rasgo.

<!-- delete-folder-trait.xml -->

1. **Datos de audiencia > Características** para navegar hasta el **Rasgos** tablero.
1. En el [!UICONTROL Trait Storage] , elimine una carpeta pasando el cursor sobre ella y haciendo clic en el icono X .

   ![Resultado de los pasos](assets/folder_traits_create.PNG)

>[!NOTE]
>
>No puede eliminar un rasgo de carpeta si se utiliza en una expresión de segmento. Vaya a la [vista de características](../../features/traits/trait-details-page.md) para ver qué segmentos utilizan el rasgo de carpeta. A continuación, haga clic en el nombre del segmento para abrir el [vista resumen del segmento](../../features/segments/segment-summary-view.md), que le permite eliminar características de las expresiones de segmento.
