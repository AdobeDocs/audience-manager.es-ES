---
description: Para crear una fuente de datos nueva, vaya a Datos de audiencia > Fuentes de datos > Añadir nuevo y complete los pasos para cada sección que se describe aquí. Se requieren permisos de administrador para crear una fuente de datos.
keywords: fuentes de datos;administrar fuente de datos;fuente de datos de audience manager
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: Administrar fuentes de datos
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: e41dddd022b6fa02cab3e16bd21536d41584975f
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# Administrar [!UICONTROL Data Sources] {#manage-data-sources}

## Crear un(a) [!UICONTROL Data Source] {#create-data-source}

Para crear un(a) nuevo(a) [!UICONTROL data source], vaya a **[!UICONTROL Audience Data > Data Sources > Add New]** y complete los pasos para cada sección que se describe aquí. Se requieren permisos de administrador para crear [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Consulte [Configuración de Data Source y Opciones de menú](../features/datasources-list-and-settings.md#settings-menu-options) para obtener descripciones de estos controles diferentes.

## Detalles de [!UICONTROL Data Source] {#details}

Para completar la sección [!UICONTROL Data Source Details]:

1. Asigne un nombre a [!UICONTROL data source].
1. *(Opcional)* Describa a [!UICONTROL data source]. Una descripción concisa le ayudará a definir la función o el propósito de [!UICONTROL data source].
1. Proporcione un [!UICONTROL integration code]. Por lo general, [!UICONTROL integration codes] son opcionales. Son necesarios cuando desea:

   * [Crear una fuente de datos entre dispositivos](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Usar [servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Trabajar con [reglas de combinación de perfiles](../features/profile-merge-rules/merge-rules-start.md).

1. Elija un **[!UICONTROL ID Type]**. [!UICONTROL ID Type] opciones incluyen:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (necesario para crear un [!UICONTROL Profile Merge Rule]). Tenga en cuenta que, para algunos clientes, esta selección expone las opciones de **[!UICONTROL ID Definition]**.

   >[!NOTE]
   >
   >Para cada organización aprovisionada para Audience Manager y Experience Platform, incluso si no tiene configurado el uso compartido de segmentos entre las dos aplicaciones, al crear una fuente de datos entre dispositivos, se crea un [área de nombres de identidad](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) correspondiente en el Experience Platform.

1. Elija una opción **[!UICONTROL ID Definition]**. Las opciones incluyen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Los controles de exportación de datos](../features/data-export-controls.md) son reglas de clasificación opcionales que puede aplicar a [!UICONTROL data source] y a [!UICONTROL destination]. Impiden que se envíen datos a [!UICONTROL destination] cuando esa acción infringe un acuerdo de uso o privacidad de datos. Omita esta sección si no usa [!UICONTROL Data Export Controls].

## Configuración de [!UICONTROL Data Source] {#settings}

Esta configuración determina cómo se identifica, usa y comparte un(a) [!UICONTROL data source]. También puede habilitar los informes de errores para archivos de datos de entrada. Para completar la sección [!UICONTROL Data Source Settings]:

1. Seleccione una casilla de verificación [!UICONTROL Data Source Setting] para aplicar una opción a su [!UICONTROL data source].
2. Haga clic en **[!UICONTROL Save]**.

## Eliminar un Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

Elimine un(a) [!UICONTROL data source] que ya no necesite.

>[!NOTE]
>
>Tenga en cuenta las siguientes restricciones:
>
>* No puede eliminar una [Audiencia activa o un Rasgo sincronizado de Data Source](../features/traits/client-activity-synced-audience-traits.md).
>* Para clientes que utilizan Adobe Analytics: Audience Manager no permite eliminar fuentes de datos creadas automáticamente a partir de los grupos de informes [!DNL Analytics]. Use el [servicio principal](https://experienceleague.adobe.com/en/docs/core-services/interface/services/customer-attributes/attributes) para desasignar estos orígenes de datos.

1. Haga clic en **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Seleccione la casilla de verificación situada junto a uno o varios orígenes de datos.
Puede usar el cuadro [!UICONTROL Search] para buscar los orígenes de datos deseados si tiene una lista larga.
1. Haga clic en ![](assets/icon_trash.png) y confirme la eliminación.


>[!MORELIKETHIS]
>
>* [Configuración de Data Source y opciones de menú](../features/datasources-list-and-settings.md#settings-menu-options)
