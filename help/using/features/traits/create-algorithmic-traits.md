---
description: Describe los pasos y las características exclusivas del proceso de creación de rasgos algorítmicos.
seo-description: Describe los pasos y las características exclusivas del proceso de creación de rasgos algorítmicos.
seo-title: Crear características algorítmicas
solution: Audience Manager
title: Crear características algorítmicas
uuid: 50 c 2 d 2 d 1-f 412-479 b-bb 70-4 f 139429 c 388
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create Algorithmic Traits {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

To create an algorithmic trait, go to [!UICONTROL Traits] and follow the steps below:

1. Click **[!UICONTROL Create New Trait]** and select **[!UICONTROL Algorithmic]** from the drop down menu.
1. In the [Basic Information](../../features/traits/create-onboarded-rule-based-traits.md) section
   * Asigne un nombre a la característica.
   * Seleccione un origen de datos.
   * Elija una carpeta de almacenamiento.
1. Expand the [!UICONTROL Configuration] pane and click **[!UICONTROL Browse All Models]**.
Esto abre una ventana nueva que permite seleccionar el modelo que desee utilizar con la característica.
1. Select a model and click **[!UICONTROL Add Selected Model to Trait]**.
Al agregar el modelo, se exponen los ajustes de alcance y precisión.
1. Seleccione el alcance o la precisión como objetivo y elija un valor de los menús desplegables correspondientes. Click **[!UICONTROL Save]** when done.

>[!MORE_ LIKE_ THIS]
>
>* [Precisión y alcance](../../features/traits/trait-accuracy-reach.md)


## Configuration Settings for Algorithmic Traits {#configure-settings}

In [!UICONTROL Trait Builder], the [!UICONTROL Configuration] section lets you associate an algorithmic model to a trait. Para completar el proceso de creación de rasgos algorítmicos, seleccione un modelo y elija un objetivo de alcance o precisión.

### Requisitos previos

<!-- r_algo_trait_config_section.xml -->

* [Cree un modelo algorítmico](../../features/algorithmic-models/create-model.md#build-model).
* Espere el correo electrónico de notificación que le permite saber que ha finalizado la ejecución de los datos del modelo.
* Complete the required fields in the [Basic Information](../../features/traits/create-onboarded-rule-based-traits.md) section.

### Campos y configuración de configuración

| Elemento Interfaz | Explicación |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Click the **[!UICONTROL Update]** button to open the models window. Desde la ventana, seleccione el modelo algorítmico que desee utilizar para crear la característica. |
| **[!UICONTROL Select Goal Accuracy]** | Seleccione esta opción para crear una característica basada en la precisión. La precisión es un valor puntuado que indica la proximidad de los usuarios potenciales a la línea base. La escala de precisión va desde 0 (menos precisión) a 1 (más precisa). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | En la derecha, esta sección muestra hasta 21 filas de datos numéricos que muestran los valores de precisión y alcance del modelo. |
| **[!UICONTROL Reach and Accuracy Slider]** | El deslizador, situado en la parte inferior del gráfico, le permite establecer un valor numérico para los objetivos de alcance o precisión. Puede definir el control deslizante y, a continuación, elegir el botón de objetivo de alcance o precisión para crear un rasgo. |

>[!MORE_ LIKE_ THIS]
>
>* [Precisión y alcance](../../features/traits/trait-accuracy-reach.md)