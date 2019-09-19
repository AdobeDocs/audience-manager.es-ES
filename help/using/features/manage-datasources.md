---
description: Para crear una nueva fuente de datos, vaya a Datos de audiencia > Fuentes de datos > Agregar nuevo y complete los pasos para cada sección que se describe aquí. Se necesitan permisos de administrador para crear una fuente de datos.
keywords: cdf;fuente de datos personalizada
seo-description: Para crear una nueva fuente de datos, vaya a Datos de audiencia > Fuentes de datos > Agregar nuevo y complete los pasos para cada sección que se describe aquí. Se necesitan permisos de administrador para crear una fuente de datos.
seo-title: Crear una fuente de datos
solution: Audience Manager
title: Crear una fuente de datos
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

Para crear una nueva fuente de datos, vaya a **[!UICONTROL Audience Data > Data Sources > Add New]** y complete los pasos para cada sección que se describe aquí. Se necesitan permisos de administrador para crear una fuente de datos.

<!-- create-datasource.xml -->

>[!TIP]
>
>Consulte Configuración [de fuente de datos y Opciones](../features/datasources-list-and-settings.md#settings-menu-options) de menú para obtener descripciones de estos diferentes controles.

## Detalles de la fuente de datos {#details}

Para completar la [!UICONTROL Data Source Details] sección:

1. Asigne un nombre al origen de datos.
1. *(Opcional)* Describa la fuente de datos. Una descripción concisa le ayuda a definir la función o el propósito del origen de datos.
1. Proporcione un código de integración. Generalmente, los códigos de integración son opcionales. Son obligatorios cuando desea:

   * [Cree una fuente](../features/profile-merge-rules/merge-rules-start.md#create-data-source)de datos entre dispositivos.
   * Utilice el servicio [de ID de](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud.
   * Trabajar con reglas [de combinación de perfiles](../features/profile-merge-rules/merge-rules-start.md).

1. Elija una **[!UICONTROL ID Type]**. Las opciones de tipo de ID incluyen:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Necesario para crear un [!UICONTROL Profile Merge Rule]). Tenga en cuenta que para algunos clientes, esta selección expone las **[!UICONTROL ID Definition]** opciones.

1. Choose an **[!UICONTROL ID Definition]** option. Las opciones incluyen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Controles de exportación de datos {#export-controls}

[Los controles](../features/data-export-controls.md) de exportación de datos son reglas de clasificación opcionales que se pueden aplicar a un origen y destino de datos. Le impiden enviar datos a un destino cuando dicha acción infringe una privacidad de datos o un acuerdo de uso. Omita esta sección si no utiliza [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

Esta configuración determina cómo se identifica, utiliza y comparte una fuente de datos. También puede habilitar los informes de errores para archivos de datos de entrada. Para completar la [!UICONTROL Data Source Settings] sección:

1. Seleccione una [!UICONTROL Data Source Setting] casilla de verificación para aplicar una opción al origen de datos.
2. Haga clic en **[!UICONTROL Save]**.

>[!MORE_LIKE_THIS]
>
>* [Configuración y opciones de menú de la fuente de datos](../features/datasources-list-and-settings.md#settings-menu-options)


## Eliminar una fuente de datos {#delete-data-source}

<!-- t_datasource_delete.xml -->

Elimine una fuente de datos que ya no necesite.

>[!NOTE]
>
>Tenga en cuenta las siguientes restricciones:
>
>* No puede eliminar una audiencia [activa o una característica](../features/traits/client-activity-synced-audience-traits.md)sincronizada de fuente de datos.
>* Para clientes que utilizan Adobe Analytics: Audience Manager no permite eliminar las fuentes de datos creadas automáticamente desde los grupos [!DNL Analytics] de informes. Utilice el servicio [principal](https://marketing.adobe.com/resources/help/en_US/mcloud/) para desasignar estas fuentes de datos.


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. Active la casilla de verificación situada junto a uno o varios orígenes de datos.
Puede utilizar el [!UICONTROL Search] cuadro para localizar las fuentes de datos deseadas si tiene una lista larga.
1. Haga clic en ![](assets/icon_trash.png)y confirme la eliminación.