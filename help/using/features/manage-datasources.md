---
description: Para crear una nueva fuente de datos, vaya a Datos de audiencia > Fuentes de datos > Agregar nuevo y complete los pasos para cada sección descrita aquí. Los permisos de administrador son necesarios para crear una fuente de datos.
keywords: cdf; fuente de datos personalizada
seo-description: Para crear una nueva fuente de datos, vaya a Datos de audiencia > Fuentes de datos > Agregar nuevo y complete los pasos para cada sección descrita aquí. Los permisos de administrador son necesarios para crear una fuente de datos.
seo-title: Crear una fuente de datos
solution: Audience Manager
title: Crear una fuente de datos
uuid: 4 df 65 bcb -9 ad 9-4 b 72-a 71 e -8918 b 43 d 4850
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

To create a new data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. Los permisos de administrador son necesarios para crear una fuente de datos.

<!-- create-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. Asigne un nombre al origen de datos.
1. *(Opcional)* Describa el origen de datos. Una descripción concisa le ayuda a definir la función o el propósito del origen de datos.
1. Proporcione un código de integración. Generalmente, los códigos de integración son opcionales. Son necesarios cuando desee:

   * [Crear una fuente de datos entre dispositivos](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Use the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
   * Work with [Profile Merge Rules](../features/profile-merge-rules/merge-rules-start.md).

1. Choose an **[!UICONTROL ID Type]**. Las opciones de Tipo de ID incluyen:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Necesario para crear una [!UICONTROL Profile Merge Rule]). Note, for some customers, this selection exposes the **[!UICONTROL ID Definition]** options.

1. Choose an **[!UICONTROL ID Definition]** option. Las opciones incluyen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Controles de exportación de datos {#export-controls}

[Los controles de exportación de datos](../features/data-export-controls.md) son reglas opcionales de clasificación que se pueden aplicar a un origen de datos y a un destino. Evita que envíe datos a un destino cuando esa acción infringe una privacidad de datos o utilice un acuerdo. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

Esta configuración determina cómo se identifica, utiliza y comparte un origen de datos. También puede habilitar el informe de errores para archivos de datos entrantes. To complete the [!UICONTROL Data Source Settings] section:

1. Select a [!UICONTROL Data Source Setting] check box to apply an option to your data source.
2. Haga clic en **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Configuración de la fuente de datos y opciones de menú](../features/datasources-list-and-settings.md#settings-menu-options)


## Delete a Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

Elimine un origen de datos que ya no necesite.

>[!NOTE]
>
>Tenga en cuenta las restricciones siguientes:
>
>* You cannot delete an [Active Audience or Data Source Synced Trait](../features/traits/client-activity-synced-audience-traits.md).
>* For customers using Adobe Analytics: Audience Manager does not allow you to delete data sources created automatically from your [!DNL Analytics] report suites. Use the [Core Service](https://marketing.adobe.com/resources/help/en_US/mcloud/) to unmap these data sources.


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. Seleccione la casilla de verificación situada junto a una o varias fuentes de datos.
You can use the [!UICONTROL Search] box to locate the desired data sources if you have a long list.
1. Click  ![](assets/icon_trash.png), then confirm the deletion.