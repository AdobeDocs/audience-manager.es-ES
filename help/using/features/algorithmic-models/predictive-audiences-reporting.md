---
description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Reporting
solution: Audience Manager
title: Informes de Audiences predictivos
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 2%

---

# Informes de Audiences predictivos

Después de guardar un [!UICONTROL Predictive Audiences] modelo, Audience Manager comienza aprendizaje él. En un par de horas, el modelo calculado inicio analizar audiencias en los servidores[ de ](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)recopilación de datos. Los informes estarán disponibles al día siguiente.

Para ver los resultados de su [!UICONTROL Predictive Audiences] clasificación, vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** y haga clic en su modelo en el lista.

Utilice las opciones de filtrado del lado izquierdo para búsqueda buscar el nombre del modelo o filtrar los resultados según el tipo de modelo.

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

La tabla de modelos muestra la siguiente información:

* **[!UICONTROL ID]**: el ID del modelo identifica de forma exclusiva cada modelo en su cuenta Audience Manager;
* **[!UICONTROL Name]**: el nombre que proporcionó en el paso de creación del modelo;
* **[!UICONTROL Description]**: la descripción que proporcionó en el paso de creación del modelo;
* **[!UICONTROL Model Type]**: el tipo de cada modelo ([!UICONTROL Look-Alike Modeling] o [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: el estado de cada modelo:
   * **[!UICONTROL Pending]**: el modelo se está inicializando y inicio producirá resultados en breve;
   * **[!UICONTROL Active]**: el modelo se está ejecutando con éxito y produce resultados;
   * **[!UICONTROL Warning]**: el modelo no produjo resultados, debido a datos insuficientes (es decir, población de líneas de base bajas, usuario perfiles no son ricos);
   * **[!UICONTROL Error]**: el modelo no se pudo ejecutar. Debe ponerse en contacto con su representante de Adobe.

## Informe de descripción general de modelo{#model-report}

Una vez que elija un modelo, se cargará su Página sistema de informes. En la parte superior del Página puede ver los 5 segmentos predictivos más grandes, basados en la realización en tiempo real de 1 día, por los que el modelo ha clasificado su audiencia destino. El **[!UICONTROL Other]** categoría incluye el resto de las personas, que no se incluyeron en los 5 segmentos predictivos más grandes.

Audience Manager muestra un gráfico de anillos codificado por colores y un gráfico cronología para su [!UICONTROL Predictive Audiences].

Al hacer clic en las fichas de perfiles en la parte superior del Página, se agregan o eliminan del gráfico y del gráfico.

El gráfico de rosquillas muestra una desglose basada en la persona de su audiencia destino, mientras que el gráfico muestra la tendencia de la población en tiempo real de 1 día de sus segmentos predictivos en los últimos 6 días.

Si el estado del modelo es [!UICONTROL Pending], [!UICONTROL Warning], o [!UICONTROL Error], se muestra el estado del modelo en lugar de en los gráficos.

![informe de persona inteligente](assets/predictive-audiences-report.png)

La tabla del informe muestra la siguiente información para cada [!UICONTROL Predictive Audiences] segmento.

1. **[!UICONTROL SEGMENT ID]**: el ID de segmento del segmento creado automáticamente asociado a cada persona;
1. **[!UICONTROL NAME]**: el nombre de la persona;
1. **[!UICONTROL STATUS]**: el estado del [!UICONTROL Predictive Audiences] segmento:
   * **[!UICONTROL Succeeded]**: los usuarios están siendo clasificados en este segmento;
   * **[!UICONTROL Pending]**: el segmento aún se está inicializando;
   * **[!UICONTROL Insufficient Training Data]**: los usuarios no se clasifican en este segmento debido a que los datos no son suficientes. La población de línea de base total es demasiado baja y no proporciona suficientes datos de los que aprender.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: El número de realizaciones de segmento para cada persona, en las últimas 24 horas.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: El porcentaje de realizaciones de segmento para cada persona, en las últimas 24 horas, de la población modelo total.

## Características influyentes{#influential-traits}

[!UICONTROL Influential Traits] son rasgos que el [!UICONTROL Predictive Audiences] algoritmo descubrió que eran los predictores más fuertes para determinar el clasificación de persona de un visitante.

Su signo indica si la presencia del rasgo aumenta (+) o disminuye (-) la probabilidad de que el usuario pertenezca a la persona seleccionada.

Para vista los rasgos influyentes de todos los usuarios, haz clic en [!UICONTROL View All Influential Traits].

La [!UICONTROL Influential Traits] ventana muestra la siguiente información, para cada persona del modelo seleccionado:

![rasgos influyentes](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: el ID de cada rasgo influyente para la persona seleccionada;
1. **[!UICONTROL NAME]**: el nombre de cada rasgo influyente para la persona seleccionada;
1. **[!UICONTROL DESCRIPTION]**: la descripción de cada rasgo influyente para la persona seleccionada;
1. **[!UICONTROL WEIGHT]**: la peso de cada rasgo influyente para el personaje seleccionado. [!UICONTROL Influential Traits] se ordenan de forma predeterminada por peso, en orden de bajada.  El valor de las ponderaciones indica su poder predictivo. El signo indica si la presencia del rasgo aumenta (+) o disminuye (-) la probabilidad de pertenecer a una persona.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: el número de realizaciones de rasgos únicos para cada rasgo influyente para el personaje seleccionado, durante los últimos 30 días.
