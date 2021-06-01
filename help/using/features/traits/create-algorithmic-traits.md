---
description: Describe los pasos y las funciones de configuración exclusivos del proceso de creación de características algorítmicas.
seo-description: Describe los pasos y las funciones de configuración exclusivos del proceso de creación de características algorítmicas.
seo-title: Crear rasgos algorítmicos
solution: Audience Manager
title: Crear rasgos algorítmicos
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: 'Rasgos '
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 5%

---

# Crear rasgos algorítmicos {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Para crear un rasgo algorítmico, vaya a [!UICONTROL Traits] y siga los pasos a continuación:

1. Haga clic en **[!UICONTROL Create New Trait]** y seleccione **[!UICONTROL Algorithmic]** en el menú desplegable.
1. En la sección [Información básica](../../features/traits/create-onboarded-rule-based-traits.md)
   * Asigne un nombre al rasgo.
   * Seleccione una fuente de datos.
   * Elija una carpeta de almacenamiento.
1. Expanda el panel [!UICONTROL Configuration] y haga clic en **[!UICONTROL Browse All Models]**.
Esto abre una nueva ventana que permite seleccionar el modelo que desea utilizar con el rasgo.
1. Seleccione un modelo y haga clic en **[!UICONTROL Add Selected Model to Trait]**.
Al agregar el modelo, se expone la configuración de alcance y precisión.
1. Seleccione alcance o precisión como objetivo y elija un valor en los menús desplegables respectivos. Haga clic en **[!UICONTROL Save]** cuando termine.

## Ajustes de configuración para rasgos algorítmicos {#configure-settings}

En [!UICONTROL Trait Builder], la sección [!UICONTROL Configuration] permite asociar un modelo algorítmico a un rasgo. Para completar el proceso de creación de características algorítmicas, seleccione un modelo y elija un objetivo de alcance o precisión.

### Requisitos previos

<!-- r_algo_trait_config_section.xml -->

* [Creación de un modelo de similitud](../../features/algorithmic-models/create-model.md).
* Espere el correo electrónico de notificación que le permite saber que la ejecución de datos del modelo ha finalizado.
* Rellene los campos obligatorios de la sección [Información básica](../../features/traits/create-onboarded-rule-based-traits.md) .

### Campos y configuración

| Elemento Interfaz | Explicación |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Haga clic en el botón **[!UICONTROL Update]** para abrir la ventana de modelos. En la ventana , seleccione el modelo algorítmico que desee utilizar para crear el rasgo. |
| **[!UICONTROL Select Goal Accuracy]** | Seleccione esta opción para crear un rasgo basado en la precisión. La precisión es un valor punteado que indica la proximidad de los usuarios potenciales a la línea base. La escala de precisión va de 0 (menos precisa) a 1 (más precisa). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Situada a la derecha, esta sección muestra hasta 21 filas de datos numéricos que muestran los valores de precisión y alcance del modelo. |
| **[!UICONTROL Reach and Accuracy Slider]** | Situado en la parte inferior del gráfico, el control deslizante le permite establecer un valor numérico para sus objetivos de alcance o precisión. Puede definir el control deslizante y, a continuación, elegir el botón de objetivo de alcance o precisión para crear un rasgo. |

>[!MORELIKETHIS]
>
>* [Precisión y alcance](../../features/traits/trait-accuracy-reach.md)

