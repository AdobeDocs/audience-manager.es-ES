---
description: Describe los pasos opcionales y requeridos que permiten crear un modelo algorítmico en el Generador de modelos.
keywords: algo de cómo funciona
seo-description: Describe los pasos opcionales y requeridos que permiten crear un modelo algorítmico en el Generador de modelos.
seo-title: Crear un modelo algorítmico
solution: Audience Manager
title: Crear un modelo algorítmico
topic: API DIL
uuid: ccf 4 fc 4 e-cf 92-445 f-b 2 d 9-71 c 3 ca 624 e 26
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create an Algorithmic Model {#create-an-algorithmic-model}

Describes the required and optional steps that let you create an algorithmic model in [!UICONTROL Model Builder].

## Build a Model {#build-model}

<!-- t_model_build.xml -->

### Sección del Generador de modelos

[!UICONTROL Model Builder] consiste en las secciones [!UICONTROL Basic Information] y [!UICONTROL Configuration] los elementos. Para crear un modelo, complete los campos obligatorios de estas dos secciones. Guarde el modelo para iniciar el algoritmo. [!DNL Audience Manager] le envía una notificación automatizada después de que se completen los primeros datos. After you receive the email, you can go to [Trait Builder](../../features/traits/about-trait-builder.md) and create algorithmic traits.

>[!NOTE]
>
>* El proceso de modelado se ejecuta una sola vez si crea un modelo y no genera características con él.
>* Genere modelos a partir de fuentes de datos que contengan una cantidad de información significativa. Se ejecutarán modelos con datos insuficientes, pero no devolverán resultados.
>* *No* cree modelos con otras características o segmentos algorítmicos.
>* La notificación de correo electrónico automatizada se envía una sola vez (después de ejecutar los primeros datos).


### Generar el modelo

To build a model, go to the [!UICONTROL Models] section and click **[!UICONTROL Add New]** and follow the steps below:

1. In the [Basic Information](../../features/algorithmic-models/create-model.md#basic-information) section
   * Asigne un nombre al modelo.
   * *(Opcional)* Proporcione una breve descripción sobre el modelo.
   * Set the status for the model to **[!UICONTROL Active]** or **[!UICONTROL Inactive]**. Los modelos inactivos no se ejecutarán y no producirán ningún dato.
1. In the [Configuration](../../features/algorithmic-models/create-model.md#configuration) section:
   * Click **[!UICONTROL Browse All Traits]** or **[!UICONTROL Browse All Segments]** to select a trait or segment you want to model against. Seleccione un rasgo integrado, un rasgo basado en reglas o un segmento como línea de base. De lo contrario, los modelos no se ejecutarán.
   * Elija un período de retroceso de 30, 60 o 90 días. Esto establece un intervalo de tiempo para el modelo.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Select a data source from the [!UICONTROL Available Data] list.
   * Click **[!UICONTROL Save]** when done.

## Basic Information for Algorithmic Models {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder], the [!UICONTROL Basic Information] settings let you create new or edit existing models. To create a new model, provide a name and move on to the [!UICONTROL Configuration] settings. El campo description es opcional.

| Campo | Descripción |
|---|---|
| **[!UICONTROL Name]** | Asigne un nombre lógico a su modelo que describa su función u objetivo. Evite abreviaciones, caracteres especiales y signos de acento. |
| **[!UICONTROL Description]** | Campo para obtener información descriptiva adicional sobre el modelo. |
| **[!UICONTROL Status]** | Activa o desactiva el modelo (activo de forma predeterminada). |

## Configuración {#configuration}

In [!UICONTROL Model Builder], the [!UICONTROL Configuration] section lets you add traits or segments to the model. En esta sección, seleccione un rasgo o segmento básico, un período de retroceso y datos de las fuentes de datos individuales y de terceros.

<!-- r_model_configuration.xml -->

### Requisitos previos

Complete the required fields in the [!UICONTROL Basic Information] section first.

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
   <td colname="col1"> <p><b>Seleccionar un rasgo o segmento de línea base (1)</b> </p> </td> 
   <td colname="col2"> <p>Haga clic en el botón de características o segmentos para ver una lista de todas sus características o segmentos. El segmento o rasgo seleccionado se convierte en la línea de base que utilizan los algoritmos del sistema para el modelado. </p> <p> <p><b>Nota</b>: Seleccione un rasgo integrado, un rasgo basado en reglas o un segmento como línea de base. De lo contrario, los modelos no se ejecutarán. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Seleccionar período atrás (2)</b> </p> </td> 
   <td colname="col2"> <p>Define un intervalo de tiempo para el modelo. En función de su selección, el algoritmo incluye y evalúa datos de los 30, 60 o 90 días anteriores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Seleccionar algoritmo (3)</b> </p> </td> 
   <td colname="col2"> <p>At this time, Model Builder works with our proprietary <span class="keyword"> Trait Weight</span> algorithm only. <span class="keyword"> Audience Manager</span> puede agregar otras funciones algorítmicas en versiones posteriores. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Seleccionar datos modelo de fuente de datos (4)</b> </p> </td> 
   <td colname="col2"> <p>Permite seleccionar las fuentes de datos individuales y de terceros que desee utilizar en el modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusiones (5)</b> </p> </td> 
   <td colname="col2"> <p>Puede excluir características de las fuentes de datos seleccionadas para el modelado. Use the <span class="wintitle"> Exclusions</span> list and read <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algorithmic Models: Trait Exclusion</a> to learn more. </p> </td>
  </tr> 
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Explicación de traitweight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

