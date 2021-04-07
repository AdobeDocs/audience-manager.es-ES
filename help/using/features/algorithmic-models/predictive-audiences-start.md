---
description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-title: Administración de Predictive Audiences
solution: Audience Manager
title: Introducción a las Predictive Audiences
feature: Modelos algorítmicos
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
translation-type: tm+mt
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 7%

---

# Introducción a las Predictive Audiences {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Este artículo contiene documentación del producto pensada para guiarle en la configuración y uso de esta función. Nada de lo contenido en este documento es asesoramiento jurídico. Consulte a su propio asesor jurídico para obtener asesoramiento jurídico.

## Crear un modelo de audiencias predictivas {#create-predictive-audiences}

Antes de crear un modelo [!UICONTROL Predictive Audiences], debe decidir a qué fuente de datos de origen desea asignar sus rasgos y segmentos [!UICONTROL Predictive Audiences]. Puede usar una fuente de datos de origen existente o crear una nueva. Consulte [Administrar fuentes de datos](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) para obtener más información sobre cómo crear una nueva fuente de datos de origen.

Una vez que sepa qué fuente de datos va a utilizar, siga los pasos a continuación.

1. Vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. En la sección [!UICONTROL Predictive Audiences], haga clic en **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. A continuación, defina las personas por las que desea clasificar la audiencia. Para ello, puede elegir rasgos o segmentos a partir de los cuales crear personalidades. Utilice las pestañas [!UICONTROL Traits] y [!UICONTROL Segments] en la esquina superior izquierda de la pantalla para cambiar entre el catálogo de rasgos y segmentos. Una vez identificados los rasgos o segmentos que desea utilizar como personalidades, haga clic en el icono **[!UICONTROL Add]** correspondiente de la columna [!UICONTROL Action].
   ![smart-persona-select-persons](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Debe elegir un mínimo de dos características o dos segmentos para las personas de línea de base. No puede utilizar una combinación de características y segmentos.
1. Haga clic en **[!UICONTROL Next]** después de definir las personas.
1. A continuación, seleccione la audiencia de origen que desea clasificar eligiendo un rasgo o segmento de origen para esta audiencia. Utilice las pestañas [!UICONTROL Traits] y [!UICONTROL Segments] de la esquina superior izquierda de la pantalla para cambiar entre el catálogo de características y segmentos. Seleccione el rasgo o segmento de origen que desee usar como audiencia para agregarlo al modelo.
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. Haga clic en **[!UICONTROL Next]** después de elegir la audiencia.
1. Rellene los detalles del modelo:
   * **[!UICONTROL Model Name]**: Introduzca un nombre descriptivo para el modelo, que le ayudará a identificarlo más adelante. Los nombres de los segmentos generados por el modelo empezarán con el nombre del modelo.
   * **[!UICONTROL Description]**: Introduzca una descripción del modelo que le ayudará a identificar su caso de uso.
   * **[!UICONTROL Data Source]**: Seleccione la fuente de datos de origen a la que desea asignar los  [!UICONTROL Predictive Audiences] segmentos de este modelo.
   * **[!UICONTROL Profile Merge Rule]**: Seleccione el  [!UICONTROL Profile Merge Rule] que desea asignar para todos los predictivos  [!UICONTROL segments] creados por este modelo. Si la audiencia de destino seleccionada es [!UICONTROL segment], se recomienda seleccionar la misma [!UICONTROL Profile Merge Rule] audiencia de destino.
      ![predictive-audiences-save](assets/predictive-audiences-save.png)
1. Haga clic **[!UICONTROL Save]**.

## Clonación y edición de modelos de Audiencia predictivos {#clone-predictive-audiences}

El Audience Manager no admite la edición de modelos [!UICONTROL Predictive Audiences] existentes. Para cambiar la configuración de un modelo, puede crear un clon de un modelo existente y editarlo. Así puede hacer esto:

1. Vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Haga clic en el nombre del modelo [!UICONTROL Predictive Audiences] que desea clonar.
3. Haga clic en el botón **[!UICONTROL Clone]** en la parte superior izquierda de la pantalla.
   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)
4. Una vez que clona el modelo, se le redirige a la página [!DNL Save & Configure] del modelo clonado. En esta página, puede cambiar el [!UICONTROL data source] y el[!UICONTROL Profile Merge Rule] asignado del modelo. Para editar las personas y la audiencia de destino del modelo clonado, utilice los botones [!UICONTROL Back] y [!UICONTROL Next] para desplazarse entre las tres pestañas o haga clic en los tres nombres de ficha

   ![predictive-audiences-clone-navegar](assets/predictive-audiences-clone-navigate.png)

5. Cuando haya terminado de editar un modelo, haga clic en **[!UICONTROL Save]**.

## Eliminación de Predictive Audiences {#delete-predictive-audiences}

Para eliminar un modelo [!UICONTROL Predictive Audiences], vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, busque el modelo que desea eliminar y haga clic en el icono **[!UICONTROL Delete]**.
