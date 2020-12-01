---
description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-title: Administración de Audiencias predictivas
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 48bf17a2899fd06c525ba6b4fddb9ec805efb5c3
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 7%

---


# Introducción a las Predictive Audiences {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

## Crear un modelo de Audiencias predictivas {#create-predictive-audiences}

Antes de crear un modelo [!UICONTROL Predictive Audiences], debe decidir a qué origen de datos de origen desea asignar sus características y segmentos [!UICONTROL Predictive Audiences]. Puede utilizar una fuente de datos de origen existente o crear una nueva. Consulte [Administrar fuentes de datos](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) para obtener más información sobre cómo crear una nueva fuente de datos de origen.

Una vez que sepa qué fuente de datos va a utilizar, siga los pasos a continuación.

1. Vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. En la sección [!UICONTROL Predictive Audiences], haga clic en **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. A continuación, defina las personas por las que desea clasificar la audiencia. Puede hacerlo eligiendo características o segmentos de los que generar personalidades. Utilice las fichas [!UICONTROL Traits] y [!UICONTROL Segments] de la esquina superior izquierda de la pantalla para cambiar entre el catálogo de características y segmentos. Una vez que haya identificado las características o segmentos que desea utilizar como personas, haga clic en el icono **[!UICONTROL Add]** correspondiente en la columna [!UICONTROL Action].
   ![inteligente-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Debe elegir un mínimo de dos características o dos segmentos para las personas de línea base. No puede utilizar una combinación de características y segmentos.
1. Haga clic **[!UICONTROL Next]** después de haber definido las personas.
1. A continuación, seleccione la audiencia de origen que desea clasificar eligiendo una característica de origen o un segmento para esta audiencia. Utilice las fichas [!UICONTROL Traits] y [!UICONTROL Segments] de la esquina superior izquierda de la pantalla para cambiar entre el catálogo de características y segmentos. Seleccione el rasgo o segmento de origen que desee utilizar como audiencia para agregarlo al modelo.
   ![smart-persona-select-audiencia](assets/predictive-audiences-audience.png)
1. Haga clic **[!UICONTROL Next]** después de elegir la audiencia.
1. Rellene los detalles del modelo:
   * **[!UICONTROL Model Name]**:: Introduzca un nombre descriptivo para el modelo, que le ayudará a identificarlo más adelante. Los nombres de los segmentos generados por el modelo tendrán inicios con el nombre del modelo.
   * **[!UICONTROL Description]**:: Introduzca una descripción del modelo que le ayudará a identificar su caso de uso.
   * **[!UICONTROL Data Source]**:: Seleccione el origen de datos de origen al que desea asignar los  [!UICONTROL Predictive Audiences] segmentos de este modelo.
   * **[!UICONTROL Profile Merge Rule]**:: Seleccione el  [!UICONTROL Profile Merge Rule] que se va a asignar para todos los predictivos  [!UICONTROL segments] creados por este modelo. Si la audiencia de destinatario seleccionada es [!UICONTROL segment], le recomendamos que seleccione la misma [!UICONTROL Profile Merge Rule] de la audiencia de destinatario.
      ![predictive-audiencias-save](assets/predictive-audiences-save.png)
1. Haga clic **[!UICONTROL Save]**.

## Clonación y edición de modelos de Audiencia predictivos {#clone-predictive-audiences}

El Audience Manager no admite la edición de modelos [!UICONTROL Predictive Audiences] existentes. Para cambiar la configuración de un modelo, puede crear un clon de un modelo existente y editarlo. Así es como puede hacer esto:

1. Vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Haga clic en el nombre del modelo [!UICONTROL Predictive Audiences] que desea clonar.
3. Haga clic en el botón **[!UICONTROL Clone]** en la parte superior izquierda de la pantalla.
   ![predictive-audiencias-clone](assets/predictive-audiences-clone.png)
4. Una vez que clona el modelo, se le redirige a la página [!DNL Save & Configure] del modelo clonado. En esta página, puede cambiar el [!UICONTROL data source] y el[!UICONTROL Profile Merge Rule] asignado del modelo. Para editar las personas y la audiencia de destinatario del modelo clonado, utilice los botones [!UICONTROL Back] y [!UICONTROL Next] para navegar entre las tres fichas o haga clic en los tres nombres de fichas

   ![predictive-audiencias-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. Cuando haya terminado de editar un modelo, haga clic en **[!UICONTROL Save]**.

## Eliminación de Audiencias predictivas {#delete-predictive-audiences}

Para eliminar un modelo [!UICONTROL Predictive Audiences], vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, busque el modelo que desea eliminar y haga clic en el icono **[!UICONTROL Delete]**.
