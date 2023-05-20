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
source-git-commit: 6ec76227dd8c7581550c3d95e24fc5b6a4b01093
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 2%

---

# Administrar [!UICONTROL Data Sources] {#manage-data-sources}

## Cree un [!UICONTROL Data Source] {#create-data-source}

Para crear un nuevo [!UICONTROL data source], vaya a **[!UICONTROL Audience Data > Data Sources > Add New]** y complete los pasos para cada sección descrita aquí. Se requieren permisos de administrador para crear una [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Consulte [Configuración de fuentes de datos y opciones de menú](../features/datasources-list-and-settings.md#settings-menu-options) para obtener descripciones de estos controles diferentes.

## [!UICONTROL Data Source] Detalles {#details}

Para completar la [!UICONTROL Data Source Details] sección:

1. Asigne un nombre al [!UICONTROL data source].
1. *(Opcional)* Describa el [!UICONTROL data source]. Una descripción concisa le ayuda a definir la función o el propósito del [!UICONTROL data source].
1. Proporcione un [!UICONTROL integration code]. Generalmente, [!UICONTROL integration codes] son opcionales. Son necesarios cuando desea:

   * [Creación de una fuente de datos entre dispositivos](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Utilice el [Servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Uso de [Reglas de combinación de perfiles](../features/profile-merge-rules/merge-rules-start.md).

1. Elija una **[!UICONTROL ID Type]**. [!UICONTROL ID Type] las opciones incluyen:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Necesario para crear una [!UICONTROL Profile Merge Rule]). Tenga en cuenta que, para algunos clientes, esta selección expone el **[!UICONTROL ID Definition]** opciones.

   >[!NOTE]
   >
   >Para cada organización aprovisionada para Audience Manager y Experience Platform, aunque no tenga configurado el uso compartido de segmentos entre las dos aplicaciones, al crear una fuente de datos entre dispositivos, se debe usar un [área de nombres de identidad](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) se crea en Experience Platform.

1. Elija una **[!UICONTROL ID Definition]** opción. Las opciones incluyen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Controles de exportación de datos](../features/data-export-controls.md) son reglas de clasificación opcionales que puede aplicar a un [!UICONTROL data source] y [!UICONTROL destination]. Evitan que usted envíe datos a un [!UICONTROL destination] cuando esa acción infrinja un acuerdo de uso o privacidad de datos. Omita esta sección si no utiliza [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Configuración {#settings}

Esta configuración determina cómo [!UICONTROL data source] se identifica, utiliza y comparte. También puede habilitar los informes de errores para archivos de datos de entrada. Para completar la [!UICONTROL Data Source Settings] sección:

1. Seleccione una [!UICONTROL Data Source Setting] casilla de verificación para aplicar una opción a su [!UICONTROL data source].
2. Haga clic **[!UICONTROL Save]**.

## Eliminar una fuente de datos {#delete-data-source}

<!-- t_datasource_delete.xml -->

Eliminar un [!UICONTROL data source] que ya no necesita.

>[!NOTE]
>
>Tenga en cuenta las siguientes restricciones:
>
>* No puede eliminar un [Característica sincronizada de audiencia activa o fuente de datos](../features/traits/client-activity-synced-audience-traits.md).
>* Para clientes que utilizan Adobe Analytics: Audience Manager no permite eliminar fuentes de datos creadas automáticamente a partir de [!DNL Analytics] grupos de informes. Utilice el [Servicio principal](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) para desasignar estas fuentes de datos.


1. Haga clic **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Seleccione la casilla de verificación situada junto a uno o varios orígenes de datos.
Puede usar el complemento [!UICONTROL Search] para localizar las fuentes de datos que desee si la lista es larga.
1. Clic  ![](assets/icon_trash.png), luego confirme la eliminación.


>[!MORELIKETHIS]
>
>* [Configuración de fuentes de datos y opciones de menú](../features/datasources-list-and-settings.md#settings-menu-options)

