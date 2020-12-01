---
description: Para crear una nueva fuente de datos, vaya a Datos de Audiencia > Fuentes de datos > Añadir nueva y complete los pasos para cada sección que se describe aquí. Se necesitan permisos de administrador para crear una fuente de datos.
keywords: data sources;manage data source;audience manager data source
seo-description: Para crear una nueva fuente de datos, vaya a Datos de Audiencia > Fuentes de datos > Añadir nueva y complete los pasos para cada sección que se describe aquí. Se necesitan permisos de administrador para crear una fuente de datos.
seo-title: Crear una fuente de datos
solution: Audience Manager
title: Administrar fuentes de datos
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 5%

---


# Administrar [!UICONTROL Data Sources] {#manage-data-sources}

## Cree un [!UICONTROL Data Source] {#create-data-source}

Para crear un [!UICONTROL data source] nuevo, vaya a **[!UICONTROL Audience Data > Data Sources > Add New]** y complete los pasos para cada sección que se describe aquí. Se requieren permisos de administrador para crear un [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Consulte [Configuración de fuente de datos y Opciones de menú](../features/datasources-list-and-settings.md#settings-menu-options) para obtener descripciones de estos diferentes controles.

## [!UICONTROL Data Source] Detalles {#details}

Para completar la sección [!UICONTROL Data Source Details]:

1. Asigne un nombre a [!UICONTROL data source].
1. *(Opcional)* Describa el  [!UICONTROL data source]. Una descripción concisa le ayuda a definir la función o el propósito del [!UICONTROL data source].
1. Proporcione un [!UICONTROL integration code]. Generalmente, [!UICONTROL integration codes] son opcionales. Son obligatorios cuando desea:

   * [Cree una fuente](../features/profile-merge-rules/merge-rules-start.md#create-data-source) de datos entre dispositivos.
   * Utilice el [servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html).
   * Trabaje con [Reglas de combinación de Perfiles](../features/profile-merge-rules/merge-rules-start.md).

1. Elija un **[!UICONTROL ID Type]**. [!UICONTROL ID Type] las opciones incluyen:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Necesario para crear un  [!UICONTROL Profile Merge Rule]). Tenga en cuenta que para algunos clientes, esta selección expone las opciones **[!UICONTROL ID Definition]**.

1. Elija una opción **[!UICONTROL ID Definition]**. Las opciones incluyen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Los ](../features/data-export-controls.md) controles de exportación de datos son reglas de clasificación opcionales que se pueden aplicar a  [!UICONTROL data source] y  [!UICONTROL destination]. Le impiden enviar datos a [!UICONTROL destination] cuando dicha acción infringe una privacidad de datos o un acuerdo de uso. Omita esta sección si no utiliza [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Configuración {#settings}

Esta configuración determina cómo se identifica, utiliza y comparte un [!UICONTROL data source]. También puede activar el sistema de informes de errores para archivos de datos de entrada. Para completar la sección [!UICONTROL Data Source Settings]:

1. Seleccione una casilla de verificación [!UICONTROL Data Source Setting] para aplicar una opción a su [!UICONTROL data source].
2. Haga clic **[!UICONTROL Save]**.

## Eliminar una fuente de datos {#delete-data-source}

<!-- t_datasource_delete.xml -->

Elimine un [!UICONTROL data source] que ya no necesite.

>[!NOTE]
>
>Tenga en cuenta las siguientes restricciones:
>
>* No puede eliminar una [Audiencia activa o característica sincronizada con la fuente de datos](../features/traits/client-activity-synced-audience-traits.md).
>* Para clientes que utilizan Adobe Analytics: Audience Manager no permite eliminar las fuentes de datos creadas automáticamente desde los grupos de informes [!DNL Analytics]. Utilice el [Servicio principal](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) para desasignar estas fuentes de datos.


1. Haga clic **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Active la casilla de verificación situada junto a uno o varios orígenes de datos.
Puede utilizar el cuadro [!UICONTROL Search] para localizar las fuentes de datos deseadas si tiene una lista larga.
1. Haga clic en ![](assets/icon_trash.png) y confirme la eliminación.


>[!MORELIKETHIS]
>
>* [Configuración y opciones de menú de la fuente de datos](../features/datasources-list-and-settings.md#settings-menu-options)