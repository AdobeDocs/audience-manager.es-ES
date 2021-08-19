---
description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-title: Sistema de informes de Predictive Audiences
solution: Audience Manager
title: Sistema de informes de Predictive Audiences
feature: Modelos algorítmicos
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 6%

---

# Sistema de informes de Predictive Audiences

Después de guardar un modelo [!UICONTROL Predictive Audiences], el Audience Manager comienza a formarlo. En un par de horas, el modelo calculado empezará a analizar las audiencias en los [Servidores de recopilación de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs). Los informes estarán disponibles al día siguiente.

Para ver los resultados de su clasificación [!UICONTROL Predictive Audiences], vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** y haga clic en su modelo en la lista.

Utilice las opciones de filtrado del lado izquierdo para buscar el nombre del modelo o filtrar los resultados según el tipo de modelo.

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

La tabla de modelos muestra la siguiente información:

* **[!UICONTROL ID]**: el ID de modelo identifica de forma exclusiva cada modelo en su cuenta de Audience Manager;
* **[!UICONTROL Name]**: el nombre proporcionado en el paso de creación del modelo;
* **[!UICONTROL Description]**: la descripción proporcionada en el paso de creación del modelo;
* **[!UICONTROL Model Type]**: el tipo de cada modelo ([!UICONTROL Look-Alike Modeling] o  [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: el estado de cada modelo:
   * **[!UICONTROL Pending]**: el modelo se está inicializando y comenzará a producir resultados en breve;
   * **[!UICONTROL Active]**: el modelo se ejecuta correctamente y produce resultados;
   * **[!UICONTROL Warning]**: el modelo no produjo resultados debido a la falta de datos (es decir, la población de líneas de base bajas, los perfiles de usuario no son enriquecidos);
   * **[!UICONTROL Error]**: no se pudo ejecutar el modelo. Debe ponerse en contacto con su representante del Adobe.

## Informe Información general de modelo{#model-report}

Una vez que elija un modelo, se cargará su página de informes. En la parte superior de la página puede ver los 5 segmentos predictivos más grandes, basados en la realización en tiempo real de 1 día, por los que el modelo ha clasificado a la audiencia de destino. La categoría **[!UICONTROL Other]** incluye el resto de las personalidades, que no se incluyeron en los 5 segmentos predictivos más grandes.

El Audience Manager muestra un gráfico circular con códigos de color y un gráfico de cronología para su [!UICONTROL Predictive Audiences].

Al hacer clic en las pestañas personalidades en la parte superior de la página, estas se añaden o eliminan del gráfico y el gráfico.

El gráfico circular muestra un desglose por persona de la audiencia de destino, mientras que el gráfico muestra la tendencia de población en tiempo real de 1 día de los segmentos predictivos durante los últimos 6 días.

Si el estado del modelo es [!UICONTROL Pending], [!UICONTROL Warning] o [!UICONTROL Error], se muestra el estado del modelo en lugar de los gráficos.

![smart-persona-report](assets/predictive-audiences-report.png)

La tabla del informe muestra la siguiente información para cada segmento [!UICONTROL Predictive Audiences].

1. **[!UICONTROL SEGMENT ID]**: el ID de segmento del segmento creado automáticamente asociado a cada personalidad;
1. **[!UICONTROL NAME]**: el nombre de la personalidad;
1. **[!UICONTROL STATUS]**: el estado del  [!UICONTROL Predictive Audiences] segmento:
   * **[!UICONTROL Succeeded]**: los usuarios se clasifican en este segmento;
   * **[!UICONTROL Pending]**: el segmento aún se está inicializando;
   * **[!UICONTROL Insufficient Training Data]**: los usuarios no se clasifican en este segmento debido a que no hay datos suficientes. La población inicial total es demasiado baja y no proporciona datos suficientes para aprender de ella.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: Número de realizaciones de segmentos para cada persona, en las últimas 24 horas.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: El porcentaje de realizaciones de segmentos para cada persona, en las últimas 24 horas, de la población total de modelos.

## Características influyentes{#influential-traits}

[!UICONTROL Influential Traits] son características que el  [!UICONTROL Predictive Audiences] algoritmo descubrió que eran los predictores más potentes para determinar la clasificación de personalidad de un visitante.

Su signo indica si la presencia del rasgo aumenta (+) o disminuye (-) la probabilidad del usuario que pertenece al perfil seleccionado.

Para ver los rasgos influyentes de todas las personalidades, haga clic en [!UICONTROL View All Influential Traits].

La ventana [!UICONTROL Influential Traits] muestra la siguiente información para cada persona del modelo seleccionado:

![rasgos influyentes](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: el ID de rasgo de cada rasgo influyente para la personalidad seleccionada;
1. **[!UICONTROL NAME]**: el nombre de cada rasgo influyente para la personalidad seleccionada;
1. **[!UICONTROL DESCRIPTION]**: la descripción de cada rasgo influyente para la personalidad seleccionada;
1. **[!UICONTROL WEIGHT]**: el peso de cada rasgo influyente para el perfil seleccionado. [!UICONTROL Influential Traits] se ordenan de forma predeterminada por peso, en orden descendente.  El valor de los pesos indica su poder predictivo. El signo indica si la presencia del rasgo aumenta (+) o disminuye (-) la probabilidad de pertenecer a una personalidad.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: el número de realizaciones de características únicas para cada rasgo influyente para la personalidad seleccionada, durante los últimos 30 días.
