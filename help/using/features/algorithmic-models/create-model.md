---
description: Describe los pasos opcionales y requeridos que permiten crear un modelo algorítmico en el Generador de modelos.
keywords: cómo funciona
seo-description: Describe los pasos opcionales y requeridos que permiten crear un modelo algorítmico en el Generador de modelos.
seo-title: Creación de un modelo algorítmico
solution: Audience Manager
title: Creación de un modelo algorítmico
topic: DIL API
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

---


# Creación de un modelo algorítmico {#create-an-algorithmic-model}

Describe los pasos opcionales y requeridos en los que puede crear un modelo algorítmico en [!UICONTROL Model Builder].

## Generar un modelo {#build-model}

<!-- t_model_build.xml -->

### Sección Generador de modelos

[!UICONTROL Model Builder] consta de las secciones [!UICONTROL Basic Information] y [!UICONTROL Configuration] . Para crear un modelo, complete los campos obligatorios de estas dos secciones. Save your model to start the algorithm. [!DNL Audience Manager] sends you an automated notification after the first data run completes. Después de recibir el correo electrónico, puede ir al Generador de [características](../../features/traits/about-trait-builder.md) y crear características algorítmicas.

>[!NOTE]
>
>* The modeling process runs only once if you create a model and do not build any traits with it.
>* Build models from data sources that contain a meaningful amount of information. Se ejecutarán modelos con datos insuficientes, pero no se obtendrán resultados.
>* *Do not create models with other algorithmic traits or segments.*
>* The automated email notification is sent one time only (after the first data run).


### Build the Model

To build a model, go to the  section and click  and follow the steps below:[!UICONTROL Models]**[!UICONTROL Add New]**

1. In the Basic Information section[](../../features/algorithmic-models/create-model.md#basic-information)
   * Name the model.
   * *(Optional)* Provide a brief description about the model.
   * Set the status for the model to  or . **[!UICONTROL Active]****[!UICONTROL Inactive]** Inactive models will not run and will not produce any data.
1. In the Configuration section:[](../../features/algorithmic-models/create-model.md#configuration)
   * Haga clic **[!UICONTROL Browse All Traits]** o **[!UICONTROL Browse All Segments]** para seleccionar un rasgo o segmento con el que desee modelar. Select an onboarded trait, a rule-based trait, or a segment as baseline. De lo contrario, los modelos no se ejecutarán.
   * Elija un período retrospectivo de 30, 60 o 90 días. Esto establece un intervalo de tiempo para el modelo.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Seleccione un origen de datos en la [!UICONTROL Available Data] lista.
   * Click **[!UICONTROL Save]** when done.

## Información básica para modelos algorítmicos {#basic-information}

<!-- r_model_basic.xml -->

En [!UICONTROL Model Builder], la [!UICONTROL Basic Information] configuración permite crear o editar modelos existentes. Para crear un nuevo modelo, proporcione un nombre y continúe con la [!UICONTROL Configuration] configuración. El campo de descripción es opcional.

| Campo | Descripción |
|---|---|
| **[!UICONTROL Name]** | Asigne a su modelo un nombre corto y lógico que describa su función o propósito. Evite abreviaciones, caracteres especiales y marcas de acento. |
| **[!UICONTROL Description]** | Campo para obtener información descriptiva adicional sobre el modelo. |
| **[!UICONTROL Status]** | Activa o desactiva el modelo (activo de forma predeterminada). |

## Configuración {#configuration}

En [!UICONTROL Model Builder], la [!UICONTROL Configuration] sección permite agregar características o segmentos al modelo. En esta sección, seleccione un rasgo o segmento de línea de base, un período de retrospectiva y datos de las fuentes de datos de origen y de terceros.

<!-- r_model_configuration.xml -->

### Requisitos previos

Complete primero los campos obligatorios de la [!UICONTROL Basic Information] sección.

![](assets/lam_exclude_traits_numbered.png)

<table id="table_7A6BE5E5498D4776A30323B743954150"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Seleccionar una característica o segmento de línea de base (1)</b> </p> </td> 
   <td colname="col2"> <p>Haga clic en el botón de características o segmentos para ver una lista de todas sus características o segmentos. El segmento o rasgo seleccionado se convierte en la línea de base que utilizan los algoritmos del sistema para el modelado. </p> <p> <p><b>Nota</b>:Seleccione una característica integrada, una característica basada en reglas o un segmento como base. De lo contrario, los modelos no se ejecutarán. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Seleccionar período retroactivo (2)</b> </p> </td> 
   <td colname="col2"> <p>Establece un intervalo de tiempo para el modelo. Según su selección, el algoritmo incluye y evalúa datos de los 30, 60 o 90 días anteriores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Seleccionar algoritmo (3)</b> </p> </td> 
   <td colname="col2"> <p>En este momento, el Generador de modelos solo funciona con nuestro algoritmo propietario <span class="keyword"> de peso</span> de rasgo. <span class="keyword"> Audience Manager</span> puede agregar otras funciones algorítmicas en versiones posteriores. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Select Model Data from Data Source (4)</b> </p> </td> 
   <td colname="col2"> <p>Permite seleccionar las fuentes de datos de origen y de terceros que desee utilizar en el modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusions (5)</b> </p> </td> 
   <td colname="col2"> <p>Puede excluir características de las fuentes de datos seleccionadas para el modelado. Use the  Exclusions list and read  Algorithmic Models: Trait Exclusion to learn more.<span class="wintitle"></span><a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"></a> </p> </td>
  </tr> 
 </tbody>
</table>

Watch the video below to learn how to create a first party look-alike model, so that you can find more of your own visitors who look like your converters.

[!VIDEO](https://video.tv.adobe.com/v/23504/?captions=spa)

>[!MORE_LIKE_THIS]
>
>* [Understanding TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

