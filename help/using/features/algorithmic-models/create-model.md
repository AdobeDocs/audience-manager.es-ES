---
description: Describe los pasos opcionales y requeridos que permiten crear un modelo algorítmico en el Generador de modelos.
keywords: cómo funciona
seo-description: Describe los pasos opcionales y requeridos que permiten crear un modelo algorítmico en el Generador de modelos.
seo-title: Crear un modelo algorítmico
solution: Audience Manager
title: Crear un modelo algorítmico
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: Modelos algorítmicos
exl-id: 8b7c4f57-f2c8-46f1-8924-5513fd6ede04
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---

# Creación de un modelo de similitud {#create-an-algorithmic-model}

Describe los pasos opcionales y requeridos que le permiten crear un [!UICONTROL Look-Alike Model].

## Sección Generador de modelos

[!UICONTROL Model Builder] consta de  [!UICONTROL Basic Information] las  [!UICONTROL Configuration] secciones y . Para crear un modelo, complete los campos obligatorios de estas dos secciones. Guarde el modelo para iniciar el algoritmo. [!DNL Audience Manager] envía una notificación automatizada una vez finalizada la primera ejecución de datos. Después de recibir el correo electrónico, puede ir a [Generador de rasgos](../../features/traits/about-trait-builder.md) y crear rasgos algorítmicos.

>[!NOTE]
>
>* El proceso de modelado se ejecuta una sola vez si se crea un modelo y no se genera ningún rasgo con él.
>* Cree modelos a partir de fuentes de datos que contengan una cantidad significativa de información. Los modelos con datos insuficientes se ejecutarán, pero no devolverán resultados.
>* *No* cree modelos con otros rasgos o segmentos algorítmicos.
>* La notificación de correo electrónico automatizada se envía una sola vez (después de la primera ejecución de los datos).


## Creación del modelo

Siga los pasos a continuación para crear un [!UICONTROL Look-Alike Model]:

1. Vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** y haga clic **[!UICONTROL Add New]** en la sección [!UICONTROL Look-Alike Modeling].
   ![look-like-add](assets/look-alike-add.png)
1. En la sección [Información básica](../../features/algorithmic-models/create-model.md#basic-information)
   * Asigne un nombre al modelo.
   * *(Opcional)* Proporcione una breve descripción del modelo.
   * Establezca el estado del modelo en **[!UICONTROL Active]** o **[!UICONTROL Inactive]**. Los modelos inactivos no se ejecutarán y no producirán datos.
      ![similitud-básico](assets/look-alike-basic.png)
1. En la sección [Configuration](../../features/algorithmic-models/create-model.md#configuration):
   * Haga clic en **[!UICONTROL Browse All Traits]** o **[!UICONTROL Browse All Segments]** para seleccionar un rasgo o segmento con el que desee modelar. Busque características por nombre, ID, descripción o fuente de datos. Haga clic en una carpeta mientras busca para limitar los resultados a esa carpeta y sus subcarpetas. También puede filtrar los rasgos por tipo de rasgo ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] y [!UICONTROL Algorithmic]) o por tipo de población ([ID del dispositivo](../../reference/ids-in-aam.md) y [ID entre dispositivos](../../reference/ids-in-aam.md)).
      ![características del explorador](assets/browse-traits.png)
   * Elija un período retrospectivo de 30, 60 o 90 días. Esto establece un intervalo de tiempo para el modelo.
   * El algoritmo [!UICONTROL TraitWeight] está seleccionado de forma predeterminada.
   * Seleccione una fuente de datos en la lista [!UICONTROL Available Data].
   * Haga clic en **[!UICONTROL Save]** cuando termine.
      ![configuración de similitud](assets/look-alike-configuration.png)

Vea el siguiente vídeo para obtener una vista detallada del funcionamiento de las métricas entre dispositivos.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Información básica para modelos algorítmicos {#basic-information}

<!-- r_model_basic.xml -->

En [!UICONTROL Model Builder], la configuración [!UICONTROL Basic Information] permite crear o editar modelos existentes. Para crear un nuevo modelo, proporcione un nombre y continúe con la configuración de [!UICONTROL Configuration] . El campo de descripción es opcional.

| Campo | Descripción |
|---|---|
| **[!UICONTROL Name]** | Asigne a su modelo un nombre corto y lógico que describa su función o propósito. Evite abreviaciones, caracteres especiales y marcas de acento. |
| **[!UICONTROL Description]** | Campo para obtener información descriptiva adicional sobre el modelo. |
| **[!UICONTROL Status]** | Activa o desactiva el modelo (activo de forma predeterminada). |

## Configuración {#configuration}

En [!UICONTROL Model Builder], la sección [!UICONTROL Configuration] permite agregar características o segmentos al modelo. En esta sección, seleccione un rasgo o segmento de línea de base, un período retrospectivo y datos de sus fuentes de datos de origen y de terceros.

<!-- r_model_configuration.xml -->

### Requisitos previos

Rellene primero los campos obligatorios de la sección [!UICONTROL Basic Information] .

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
   <td colname="col1"> <p><b>Seleccionar un rasgo o segmento de línea de base (1)</b> </p> </td> 
   <td colname="col2"> <p>Haga clic en el botón rasgo o segmento para ver una lista de todos sus rasgos o segmentos. El segmento o rasgo seleccionado se convierte en la línea de base que los algoritmos del sistema utilizan para el modelado. </p> <p> <p><b>Nota</b>: Seleccione un rasgo incorporado, un rasgo basado en reglas o un segmento como línea de base. De lo contrario, los modelos no se ejecutarán. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Seleccionar período retrospectivo (2)</b> </p> </td> 
   <td colname="col2"> <p>Establece un intervalo de tiempo para el modelo. Según su selección, el algoritmo incluye y evalúa los datos de los 30, 60 o 90 días anteriores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Seleccionar algoritmo (3)</b> </p> </td> 
   <td colname="col2"> <p>En este momento, el Generador de modelos funciona únicamente con nuestro algoritmo <span class="keyword"> Trait Weight</span> propietario. <span class="keyword"> Audience </span> Manager puede añadir otras funciones algorítmicas en versiones posteriores. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Seleccionar datos de modelo de fuente de datos (4)</b> </p> </td> 
   <td colname="col2"> <p>Permite seleccionar las fuentes de datos de origen y de terceros que desee utilizar en el modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusiones (5)</b> </p> </td> 
   <td colname="col2"> <p>Puede excluir características de las fuentes de datos seleccionadas para el modelado. Utilice la lista <span class="wintitle"> Exclusiones</span> y lea <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Modelos algorítmicos: Exclusión de características</a> para obtener más información. </p> </td>
  </tr> 
 </tbody>
</table>

Vea el siguiente vídeo para aprender a crear un modelo de similitud de origen, de modo que pueda encontrar más visitantes que se parezcan a sus convertidores.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [Explicación de TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

