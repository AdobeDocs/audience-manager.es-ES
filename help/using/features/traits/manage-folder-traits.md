---
description: Cree, edite y elimine características de carpeta.
keywords: Folder Trait;Folder Traits;folder traits;folder trait
seo-description: Cree, edite y elimine características de carpeta.
seo-title: Administrar rasgos de carpetas
solution: Audience Manager
title: Administrar rasgos de carpetas
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
translation-type: tm+mt
source-git-commit: 4ea5ba4ebd8cd4c13c99c8272f4b5733ab5fa125
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 9%

---


# Administrar rasgos de carpetas {#manage-folder-traits}

Cree, edite y elimine características de carpeta.

## Crear una característica de carpeta {#create-folder-trait}

Se crea automáticamente un [!UICONTROL folder trait] al crear una nueva carpeta en la taxonomía.

<!-- create-folder-trait.xml -->

1. Vaya a **[!UICONTROL Audience Data > Traits]** para navegar al panel **Características**.
1. En la ventana [!UICONTROL Trait Storage], pase el ratón por encima:

   * Texto &quot;Todas las características&quot; para agregar una nueva carpeta de nivel raíz.
   * Una carpeta principal existente para agregar una nueva carpeta subordinada.

   ![](assets/folder_traits_create.PNG)

1. Haga clic en el icono + para crear la carpeta. Tenga en cuenta que puede crear un máximo de 2000 carpetas en su taxonomía. Consulte la documentación sobre los [límites de uso](../../features/administration/usage-limits.md) para obtener más información.
1. Asigne un nombre a la carpeta y haga clic en **Guardar**. Por ejemplo, una carpeta llamada Electronics tendrá una característica de carpeta denominada &#39;Características de la carpeta de componentes electrónicos&#39;. Puede vista y seleccionar la nueva característica de carpeta en el panel de características.
1. La nueva característica de carpeta se asigna automáticamente al origen de datos generado por [!DNL Audience Manager]. Los usuarios con los permisos [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) adecuados pueden cambiar el origen de datos en el flujo de trabajo de características de la carpeta de edición. Consulte [Editar una característica de carpeta](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Editar una característica de carpeta {#edit-folder-trait}

Describe cómo se puede editar un [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. En el panel [!UICONTROL Traits], pase el ratón sobre la columna **[!UICONTROL Actions]** de la característica de carpeta que desee editar.
1. Haga clic en el lápiz para editar la característica.

   ![](assets/folder_traits_edit_border.png)

1. El flujo de trabajo **[!UICONTROL Edit]** le permite cambiar el origen de datos para características de carpeta. Seleccione el origen de datos deseado y haga clic en **[!UICONTROL Save]**. Las fuentes de datos se ordenan numéricamente, por [!DNL DPID], en el cuadro desplegable.

   Si su compañía utiliza [!UICONTROL Role-Based Access Rights (RBAC)], usted o sus usuarios necesitan [permisos de acceso](../../features/traits/about-folder-traits.md#role-based-access-controls) para caracterizar las fuentes de datos.

>[!NOTE]
>
>No se puede cambiar directamente el nombre de una característica de carpeta. [Cambie el nombre de la ](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) carpeta de almacenamiento asociada para cambiar el nombre de la característica de carpeta.

## Eliminar una característica de carpeta {#delete-folder-trait}

Elimine una característica de carpeta eliminando la carpeta de almacenamiento a la que pertenece la característica.

<!-- delete-folder-trait.xml -->

1. **Datos de audiencia >** Características para navegar hasta el  **** panel de características.
1. En la ventana [!UICONTROL Trait Storage], elimine una carpeta pasando el ratón sobre ella y haciendo clic en el icono X.

   ![Resultado del paso](assets/folder_traits_create.PNG)

>[!NOTE]
>
>No puede eliminar una característica de carpeta si se utiliza en una expresión de segmento. Vaya a la sección [vista de características](../../features/traits/trait-details-page.md) para ver qué segmentos utilizan la característica de carpeta. A continuación, haga clic en el nombre del segmento para abrir la [vista de resumen del segmento](../../features/segments/segment-summary-view.md), que le permite eliminar características de expresiones de segmentos.
