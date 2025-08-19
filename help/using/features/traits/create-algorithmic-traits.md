---
description: Describe los pasos de configuración y las funciones exclusivas del proceso de creación de rasgos algorítmicos.
seo-description: Describes set up steps and features unique to the algorithmic trait creation process.
seo-title: Create Algorithmic Traits
solution: Audience Manager
title: Crear Características algorítmicas
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# Crear Características algorítmicas {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Para crear un rasgo algorítmico, siga y [!UICONTROL Traits] seguir los pasos siguientes:

1. Haga clic **[!UICONTROL Create New Trait]** y seleccione **[!UICONTROL Algorithmic]** en el menú desplegable.
1. En la [sección Información](../../features/traits/create-onboarded-rule-based-traits.md) básica
   * Asigne un nombre al rasgo.
   * Seleccione una fuente de datos.
   * Elija una carpeta almacenamiento.
1. Expanda el [!UICONTROL Configuration] panel y haga clic en **[!UICONTROL Browse All Models]**.
Se abre una nueva ventana que le permite seleccionar el modelo que desea utilizar con la característica.
1. Seleccione un modelo y haga clic en **[!UICONTROL Add Selected Model to Trait]**.
Al agregar el modelo se exponen los ajustes de alcance y precisión.
1. Seleccione el alcance o la precisión como su objetivo y elija un valor de los menús desplegables respectivos. Haga clic **[!UICONTROL Save]** cuando termine.

## Configuración de configuración para rasgos algorítmicos {#configure-settings}

En [!UICONTROL Trait Builder], la [!UICONTROL Configuration] sección permite asociar un modelo algorítmico a un rasgo. Para completar el proceso de creación de rasgos algorítmicos, seleccione un modelo y elija un objetivo de alcance o precisión.

### Requisitos previos

<!-- r_algo_trait_config_section.xml -->

* [Crear un modelo](../../features/algorithmic-models/create-model.md) Look similar.
* Espere a la correo electrónico notificación que le permita saber que la ejecución de los datos del modelo ha finalizado.
* Todas las aplicaciones los campos obligatorios en la [sección Información](../../features/traits/create-onboarded-rule-based-traits.md) básica.

### Campos de configuración y Configuración

| Elemento Interfaz | Explicación |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Haga clic en el **[!UICONTROL Update]** botón para abrir la ventana de modelos. Desde la ventana, seleccione el modelo algorítmico que desea utilizar para crear el rasgo. |
| **[!UICONTROL Select Goal Accuracy]** | Seleccione esta opción para crear un rasgo basado en la precisión. La precisión es un valor puntuado que indica la proximidad de los usuarios potenciales a la línea base. La escala de precisión va de 0 (menos precisa) a 1 (más precisa). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Ubicada a la derecha, esta sección muestra hasta 21 filas de datos numérica que muestran la precisión y los valores de alcance para su modelo. |
| **[!UICONTROL Reach and Accuracy Slider]** | Ubicada en la parte inferior del gráfico, la regulador le permite establecer un valor numérica para sus objetivos de alcance o precisión. Puede establecer el regulador y luego elegir el objetivo de alcance o precisión botón para crear un rasgo. |

>[!MORELIKETHIS]
>
>* [Precisión y alcance](../../features/traits/trait-accuracy-reach.md)
