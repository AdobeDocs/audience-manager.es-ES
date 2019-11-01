---
description: Describe los pasos y las funciones de configuración exclusivos del proceso de creación de características algorítmicas.
seo-description: Describe los pasos y las funciones de configuración exclusivos del proceso de creación de características algorítmicas.
seo-title: Crear características algorítmicas
solution: Audience Manager
title: Crear características algorítmicas
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Crear características algorítmicas {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Para crear una característica algorítmica, vaya a [!UICONTROL Traits] y siga los pasos a continuación:

1. Haga clic **[!UICONTROL Create New Trait]** y seleccione **[!UICONTROL Algorithmic]** en el menú desplegable.
1. En la sección Información [](../../features/traits/create-onboarded-rule-based-traits.md) básica
   * Asigne un nombre a la característica.
   * Seleccione un origen de datos.
   * Elija una carpeta de almacenamiento.
1. Expanda el [!UICONTROL Configuration] panel y haga clic en **[!UICONTROL Browse All Models]**.
Se abre una nueva ventana que permite seleccionar el modelo que desea utilizar con la característica.
1. Seleccione un modelo y haga clic en **[!UICONTROL Add Selected Model to Trait]**.
Al agregar el modelo se exponen los valores de alcance y precisión.
1. Seleccione el alcance o la precisión como objetivo y elija un valor en los menús desplegables correspondientes. Click **[!UICONTROL Save]** when done.

## Configuración de características algorítmicas {#configure-settings}

En [!UICONTROL Trait Builder], la [!UICONTROL Configuration] sección permite asociar un modelo algorítmico a una característica. Para completar el proceso de creación de características algorítmicas, seleccione un modelo y elija un objetivo de alcance o precisión.

### Requisitos previos

<!-- r_algo_trait_config_section.xml -->

* [Cree un modelo](../../features/algorithmic-models/create-model.md#build-model)algorítmico.
* Espere el correo electrónico de notificación que le permite saber que la ejecución de datos del modelo ha finalizado.
* Complete los campos requeridos en la sección Información [](../../features/traits/create-onboarded-rule-based-traits.md) básica.

### Campos y configuración

| Elemento Interfaz | Explicación |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Haga clic en el **[!UICONTROL Update]** botón para abrir la ventana de modelos. En la ventana, seleccione el modelo algorítmico que desee utilizar para crear la característica. |
| **[!UICONTROL Select Goal Accuracy]** | Seleccione esta opción para crear una característica basada en la precisión. Precisión es un valor de puntuación que indica la proximidad de los usuarios potenciales a la línea base. La escala de precisión va de 0 (menos precisa) a 1 (más precisa). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Situada a la derecha, esta sección muestra hasta 21 filas de datos numéricos que muestran los valores de precisión y alcance del modelo. |
| **[!UICONTROL Reach and Accuracy Slider]** | Ubicado en la parte inferior del gráfico, el control deslizante permite establecer un valor numérico para los objetivos de alcance o precisión. Puede definir el control deslizante y, a continuación, seleccionar el botón de objetivo de alcance o precisión para crear una característica. |

>[!MORELIKETHIS]
>
>* [Precisión y alcance](../../features/traits/trait-accuracy-reach.md)

