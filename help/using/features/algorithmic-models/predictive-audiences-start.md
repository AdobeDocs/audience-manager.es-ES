---
description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Managing Predictive Audiences
solution: Audience Manager
title: Introducción a Predictive Audiences
feature: Algorithmic Models
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 2%

---

# Introducción a Predictive Audiences {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Este artículo contiene documentación del producto que le guiará a través de la configuración y el uso de esta función. Nada de lo que contiene aquí es asesoramiento legal. Por favor, consulte a su propio asesor legal para obtener orientación legal.

## Creación de un modelo de Predictive Audiences {#create-predictive-audiences}

Antes de crear un modelo [!UICONTROL Predictive Audiences], debe decidir a qué origen de datos de origen desea asignar sus rasgos y segmentos de [!UICONTROL Predictive Audiences]. Puede utilizar una fuente de datos de origen existente o crear una nueva. Consulte [Administrar fuentes de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html) para obtener detalles sobre cómo crear una nueva fuente de datos propia.

Una vez que sepa qué fuente de datos va a utilizar, siga los pasos a continuación.

1. Ir a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. En la sección [!UICONTROL Predictive Audiences], haga clic en **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. A continuación, defina los perfiles por los que desea clasificar la audiencia. Puede hacerlo eligiendo características o segmentos desde los cuales crear personalidades. Utilice las pestañas [!UICONTROL Traits] y [!UICONTROL Segments] en la esquina superior izquierda de la pantalla para cambiar entre el catálogo de rasgos y segmentos. Una vez que haya identificado los rasgos o segmentos que desea usar como personas, haga clic en el icono **[!UICONTROL Add]** correspondiente en la columna [!UICONTROL Action].
   ![smart-persona-select-personalidades](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Debe elegir un mínimo de dos rasgos o dos segmentos para los perfiles de línea de base. No se puede utilizar una combinación de rasgos y segmentos.
1. Haga clic en **[!UICONTROL Next]** después de haber definido las personalidades.
1. A continuación, seleccione la audiencia de origen que desee clasificar eligiendo un rasgo o segmento de origen para esta audiencia. Utilice las pestañas [!UICONTROL Traits] y [!UICONTROL Segments] en la esquina superior izquierda de la pantalla para cambiar entre el catálogo de características y segmentos. Seleccione el rasgo o segmento de origen que desee utilizar como audiencia para agregarlo al modelo.
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. Haga clic en **[!UICONTROL Next]** después de elegir la audiencia.
1. Rellene los detalles del modelo:
   * **[!UICONTROL Model Name]**: escriba un nombre descriptivo para el modelo, que le ayudará a identificarlo más adelante. Los nombres de los segmentos generados por el modelo empezarán por el nombre del modelo.
   * **[!UICONTROL Description]**: escriba una descripción del modelo que le ayudará a identificar su caso de uso.
   * **[!UICONTROL Data Source]**: seleccione el origen de datos de origen al que desea que se asignen los segmentos de [!UICONTROL Predictive Audiences] de este modelo.
   * **[!UICONTROL Profile Merge Rule]**: seleccione [!UICONTROL Profile Merge Rule] que se asignará a todos los objetos predictivos [!UICONTROL segments] creados por este modelo. Si la audiencia de destino seleccionada es un [!UICONTROL segment], se recomienda seleccionar el mismo [!UICONTROL Profile Merge Rule] de la audiencia de destino.
     ![predictive-audiences-save](assets/predictive-audiences-save.png)
1. Haga clic en **[!UICONTROL Save]**.

## Clonación y edición de modelos de Predictive Audience {#clone-predictive-audiences}

Audience Manager no admite la edición de los modelos [!UICONTROL Predictive Audiences] existentes. Para cambiar la configuración de un modelo, puede crear un clon de un modelo existente y editarlo. A continuación se muestra cómo puede hacer esto:

1. Ir a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Haga clic en el nombre del modelo [!UICONTROL Predictive Audiences] que desea clonar.
3. Haga clic en el botón **[!UICONTROL Clone]** en la parte superior izquierda de la pantalla.
   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)
4. Una vez que clone el modelo, se le redirige a la página [!DNL Save & Configure] del modelo clonado. En esta página, puede cambiar [!UICONTROL data source] y el asignado [!UICONTROL Profile Merge Rule] del modelo. Para editar las personalidades y la audiencia de destino del modelo clonado, utilice los botones [!UICONTROL Back] y [!UICONTROL Next] para navegar entre las tres pestañas o haga clic en los tres nombres de pestañas

   ![predictive-audiences-clone-navegar](assets/predictive-audiences-clone-navigate.png)

5. Cuando haya terminado de editar un modelo, haga clic en **[!UICONTROL Save]**.

## Eliminación de Predictive Audiences {#delete-predictive-audiences}

Para eliminar un modelo [!UICONTROL Predictive Audiences], vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, busque el modelo que desea eliminar y haga clic en el icono **[!UICONTROL Delete]**.
