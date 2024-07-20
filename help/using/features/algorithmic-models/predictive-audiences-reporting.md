---
description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Reporting
solution: Audience Manager
title: Informes de Predictive Audiences
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 2%

---

# Informes de Predictive Audiences

Después de guardar un modelo [!UICONTROL Predictive Audiences], el Audience Manager comienza a entrenarlo. En un par de horas, el modelo calculado empezará a analizar audiencias en los [servidores de recopilación de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs). Los informes estarán disponibles al día siguiente.

Para ver los resultados de la clasificación [!UICONTROL Predictive Audiences], vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** y haga clic en el modelo en la lista.

Utilice las opciones de filtrado de la izquierda para buscar el nombre del modelo o filtrar los resultados según el tipo de modelo.

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

La tabla de modelos muestra la siguiente información:

* **[!UICONTROL ID]**: el ID de modelo identifica de forma exclusiva cada modelo de su cuenta de Audience Manager;
* **[!UICONTROL Name]**: el nombre proporcionado en el paso de creación del modelo;
* **[!UICONTROL Description]**: la descripción proporcionada en el paso de creación del modelo;
* **[!UICONTROL Model Type]**: el tipo de cada modelo ([!UICONTROL Look-Alike Modeling] o [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: el estado de cada modelo:
   * **[!UICONTROL Pending]**: el modelo se está inicializando y empezará a producir resultados en breve;
   * **[!UICONTROL Active]**: el modelo se está ejecutando correctamente y produce resultados;
   * **[!UICONTROL Warning]**: el modelo no produjo resultados debido a datos insuficientes (es decir, población de líneas de base baja, los perfiles de usuario no son enriquecidos);
   * **[!UICONTROL Error]**: no se pudo ejecutar el modelo. Debe ponerse en contacto con el representante del Adobe.

## Informe general de modelo{#model-report}

Una vez que elija un modelo, se cargará su página de informes. En la parte superior de la página puede ver los 5 segmentos predictivos más grandes, basados en la comprensión en tiempo real de 1 día, por los que el modelo ha clasificado la audiencia objetivo. La categoría **[!UICONTROL Other]** incluye el resto de las personalidades, que no se incluyeron entre los 5 segmentos predictivos más grandes.

El Audience Manager muestra un gráfico circular con códigos de color y un gráfico de escala de tiempo para su [!UICONTROL Predictive Audiences].

Al hacer clic en las pestañas de perfiles en la parte superior de la página, se añaden o eliminan del gráfico y del gráfico.

El gráfico de anillo muestra un desglose basado en personas de la audiencia de destino, mientras que el gráfico muestra la tendencia de la población en tiempo real de 1 día de los segmentos predictivos durante los últimos 6 días.

Si el estado del modelo es [!UICONTROL Pending], [!UICONTROL Warning] o [!UICONTROL Error], se muestra el estado del modelo en lugar de los gráficos.

![informe-persona-inteligente](assets/predictive-audiences-report.png)

La tabla del informe muestra la siguiente información para cada segmento [!UICONTROL Predictive Audiences].

1. **[!UICONTROL SEGMENT ID]**: el ID de segmento del segmento creado automáticamente y asociado a cada persona;
1. **[!UICONTROL NAME]**: el nombre de la persona;
1. **[!UICONTROL STATUS]**: el estado del segmento [!UICONTROL Predictive Audiences]:
   * **[!UICONTROL Succeeded]**: los usuarios se están clasificando en este segmento;
   * **[!UICONTROL Pending]**: el segmento aún se está inicializando;
   * **[!UICONTROL Insufficient Training Data]**: los usuarios no se están clasificando en este segmento debido a la falta de datos. La población de línea de base total es demasiado baja y no proporciona datos suficientes para aprender de ella.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: número de realizaciones de segmento de cada persona en las últimas 24 horas.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: porcentaje de realizaciones de segmentos de cada persona en las últimas 24 horas sobre la población total de modelos.

## Rasgos influyentes{#influential-traits}

[!UICONTROL Influential Traits] son características que el algoritmo [!UICONTROL Predictive Audiences] ha descubierto que son los predictores más sólidos para determinar la clasificación personal de un visitante.

Su signo indica si la presencia del rasgo aumenta (+) o disminuye (-) la probabilidad de que el usuario pertenezca al personaje seleccionado.

Para ver los rasgos influyentes de todas las personalidades, haga clic en [!UICONTROL View All Influential Traits].

La ventana [!UICONTROL Influential Traits] muestra la siguiente información para cada perfil del modelo seleccionado:

![rasgos influyentes](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: el ID de rasgo de cada rasgo influyente del personaje seleccionado;
1. **[!UICONTROL NAME]**: nombre de cada rasgo influyente del personaje seleccionado;
1. **[!UICONTROL DESCRIPTION]**: la descripción de cada rasgo influyente del personaje seleccionado;
1. **[!UICONTROL WEIGHT]**: el peso de cada rasgo influyente del personaje seleccionado. [!UICONTROL Influential Traits] se ordenan de manera predeterminada por grosor, en orden descendente.  El valor de los pesos indica su poder predictivo. El signo indica si la presencia del rasgo aumenta (+) o disminuye (-) la probabilidad de pertenecer a una persona.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: número de realizaciones de rasgos únicos para cada rasgo influyente de la persona seleccionada en los últimos 30 días.
