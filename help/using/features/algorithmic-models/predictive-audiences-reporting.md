---
description: Las Audiencias predictivas ayudan a clasificar audiencias desconocidas en personalidades distintas en tiempo real, mediante el uso de la ciencia de datos.
seo-description: Las Audiencias predictivas ayudan a clasificar audiencias desconocidas en personalidades distintas en tiempo real, mediante el uso de la ciencia de datos.
seo-title: Sistema de informes de Audiencias predictivas
solution: Audience Manager
title: Audiencias predictivas del Administrador de Audiencias
translation-type: tm+mt
source-git-commit: 8259f07c91efa0efd88e8f7c87cb1829ffadd77d

---


# Sistema de informes de Audiencias predictivas

Después de guardar un [!UICONTROL Predictive Audiences] modelo, el Administrador de Audiencias inicio formarlo. En un par de horas, el modelo calculado analizará en inicio las audiencias en los servidores [de recopilación de](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)datos. El Sistema de informes estará disponible al día siguiente.

Para ver los resultados de la [!UICONTROL Predictive Audiences] clasificación, vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** y haga clic en el modelo en la lista.

Utilice las opciones de filtrado del lado izquierdo para buscar el nombre del modelo o filtrar los resultados según el tipo de modelo.

![predictive-audiencias-filter](assets/predictive-audiences-filter-models.png)

La tabla de modelos muestra la siguiente información:

* **[!UICONTROL ID]**:: el ID de modelo identifica de forma exclusiva cada modelo de la cuenta del Administrador de Audiencias;
* **[!UICONTROL Name]**:: el nombre proporcionado en el paso de creación del modelo;
* **[!UICONTROL Description]**:: la descripción proporcionada en el paso de creación del modelo;
* **[!UICONTROL Model Type]**:: el tipo de cada modelo ([!UICONTROL Look-Alike Modeling] o [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**:: el estado de cada modelo:
   * **[!UICONTROL Pending]**:: el modelo se está inicializando y dará inicios para producir resultados en breve;
   * **[!UICONTROL Active]**:: el modelo se ejecuta correctamente y produce resultados;
   * **[!UICONTROL Warning]**:: el modelo no produjo resultados debido a la insuficiencia de datos (es decir, una población de bases de referencia bajas, los perfiles de los usuarios no son ricos);
   * **[!UICONTROL Error]**:: no se pudo ejecutar el modelo. Debe ponerse en contacto con su representante de Adobe.

## Informe Información general de modelo{#model-report}

Una vez que elija un modelo, se cargará su página de sistema de informes. En la parte superior de la página puede ver los 5 segmentos predictivos más grandes, basados en la realización en tiempo real de 1 día, por los que el modelo ha clasificado la audiencia de destinatarios. La **[!UICONTROL Other]** categoría incluye al resto de personas, que no se incluyeron en los cinco segmentos predictivos más grandes.

El Administrador de Audiencias muestra un gráfico circular con códigos de color y un gráfico de línea de tiempo para su [!UICONTROL Predictive Audiences].

Al hacer clic en las fichas Personas en la parte superior de la página, éstas se agregan o eliminan del gráfico y el gráfico.

El gráfico circular muestra un desglose por persona de la audiencia de destinatario, mientras que el gráfico muestra la tendencia de población en tiempo real de 1 día de los segmentos predictivos en los últimos 6 días.

Si el estado del modelo es [!UICONTROL Pending], [!UICONTROL Warning]o [!UICONTROL Error], se muestra el estado del modelo en lugar de los gráficos.

![smart-persona-report](assets/predictive-audiences-report.png)

La tabla del informe muestra la siguiente información para cada [!UICONTROL Predictive Audiences] segmento.

1. **[!UICONTROL SEGMENT ID]**:: el ID de segmento del segmento creado automáticamente asociado a cada persona;
1. **[!UICONTROL NAME]**:: el nombre de la persona;
1. **[!UICONTROL STATUS]**:: estado del [!UICONTROL Predictive Audiences] segmento:
   * **[!UICONTROL Succeeded]**:: los usuarios se clasifican en este segmento;
   * **[!UICONTROL Pending]**:: el segmento aún se está inicializando;
   * **[!UICONTROL Insufficient Training Data]**:: los usuarios no se clasifican en este segmento debido a la falta de datos. La población basal total es demasiado baja y no proporciona datos suficientes para aprender.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**:: Número de realizaciones de segmentos para cada persona, en las últimas 24 horas.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**:: El porcentaje de realización de segmentos para cada persona, en las últimas 24 horas, de la población total de modelos.

## Características influyentes{#influential-traits}

[!UICONTROL Influential Traits] Son características que el algoritmo descubrió que son los predictores más sólidos para determinar la clasificación personal de un visitante. [!UICONTROL Predictive Audiences]

Su signo indica si la presencia de la característica aumenta (+) o disminuye(-) la probabilidad del usuario que pertenece a la persona seleccionada.

Para vista de las características influyentes de todas las personas, haga clic en [!UICONTROL View All Influential Traits].

La [!UICONTROL Influential Traits] ventana muestra la siguiente información para cada persona del modelo seleccionado:

![características influyentes](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**:: la ID de característica de cada característica influyente de la persona seleccionada;
1. **[!UICONTROL NAME]**:: el nombre de cada característica influyente de la persona seleccionada;
1. **[!UICONTROL DESCRIPTION]**:: la descripción de cada característica influyente de la persona seleccionada;
1. **[!UICONTROL WEIGHT]**:: el peso de cada característica influyente para la persona seleccionada. [!UICONTROL Influential Traits] se ordenan de forma predeterminada por pesos, en orden descendente.  El valor de los pesos indica su poder predictivo. El signo indica si la presencia de la característica aumenta (+) o disminuye(-) la probabilidad de pertenecer a una persona.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**:: el número de realizaciones de características únicas para cada característica influyente de la persona seleccionada, en los últimos 30 días.