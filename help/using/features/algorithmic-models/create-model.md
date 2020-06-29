---
description: Describe los pasos opcionales y requeridos que permiten crear un modelo algorítmico en el Generador de modelos.
keywords: algo how works
seo-description: Describe los pasos opcionales y requeridos que permiten crear un modelo algorítmico en el Generador de modelos.
seo-title: Creación de un modelo algorítmico
solution: Audience Manager
title: Creación de un modelo algorítmico
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---


# Creación de un modelo similar {#create-an-algorithmic-model}

Describe los pasos opcionales y requeridos que le permiten crear un [!UICONTROL Look-Alike Model].

## Sección Generador de modelos

[!UICONTROL Model Builder] consta de las secciones [!UICONTROL Basic Information] y [!UICONTROL Configuration] . Para crear un modelo, complete los campos obligatorios de estas dos secciones. Guarde el modelo para inicio del algoritmo. [!DNL Audience Manager] le envía una notificación automatizada una vez que se completa la primera ejecución de datos. Después de recibir el correo electrónico, puede ir al Generador de [características](../../features/traits/about-trait-builder.md) y crear características algorítmicas.

>[!NOTE]
>
>* El proceso de modelado se ejecuta una sola vez si se crea un modelo y no se genera ninguna característica con él.
>* Cree modelos a partir de fuentes de datos que contengan una cantidad significativa de información. Se ejecutarán modelos con datos insuficientes, pero no se obtendrán resultados.
>* *No cree* modelos con otras características algorítmicas o segmentos.
>* La notificación de correo electrónico automatizada se envía una sola vez (después de la primera ejecución de datos).


## Generar el modelo

Siga los pasos a continuación para crear un [!UICONTROL Look-Alike Model]:

1. Vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** y haga clic **[!UICONTROL Add New]** en la [!UICONTROL Look-Alike Modeling] sección .
   ![look-like-add](assets/look-alike-add.png)
1. En la sección Información [](../../features/algorithmic-models/create-model.md#basic-information) básica
   * Asigne un nombre al modelo.
   * *(Opcional)* Proporcione una breve descripción del modelo.
   * Establezca el estado del modelo en **[!UICONTROL Active]** o **[!UICONTROL Inactive]**. Los modelos inactivos no se ejecutarán y no producirán datos.
      ![similar-básico](assets/look-alike-basic.png)
1. En la sección [Configuración](../../features/algorithmic-models/create-model.md#configuration) :
   * Haga clic **[!UICONTROL Browse All Traits]** o **[!UICONTROL Browse All Segments]** para seleccionar un rasgo o segmento con el que desee modelar. Busque características por nombre, ID, descripción o fuente de datos. Haga clic en una carpeta mientras busca para limitar los resultados a esa carpeta y sus subcarpetas. También puede filtrar características por tipo de característica ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]y [!UICONTROL Algorithmic]) o por tipo de población (ID[](../../reference/ids-in-aam.md) del dispositivo e ID [](../../reference/ids-in-aam.md)cruzado del dispositivo).
      ![características de exploración](assets/browse-traits.png)
   * Elija un período retrospectivo de 30, 60 o 90 días. Esto establece un intervalo de tiempo para el modelo.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Seleccione un origen de datos de la [!UICONTROL Available Data] lista.
   * Haga clic **[!UICONTROL Save]** cuando termine.
      ![configuración similar](assets/look-alike-configuration.png)

Vea el siguiente vídeo para ver en detalle cómo funcionan las métricas entre dispositivos.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Información básica para modelos algorítmicos {#basic-information}

<!-- r_model_basic.xml -->

En [!UICONTROL Model Builder], la [!UICONTROL Basic Information] configuración permite crear o editar modelos existentes. Para crear un nuevo modelo, proporcione un nombre y continúe con la [!UICONTROL Configuration] configuración. El campo de descripción es opcional.

| Campo | Descripción |
|---|---|
| **[!UICONTROL Name]** | Asigne a su modelo un nombre corto y lógico que describa su función o propósito. Evite abreviaciones, caracteres especiales y marcas de acento. |
| **[!UICONTROL Description]** | Campo para obtener información descriptiva adicional sobre el modelo. |
| **[!UICONTROL Status]** | Activa o desactiva el modelo (activo de forma predeterminada). |

## Configuración {#configuration}

En [!UICONTROL Model Builder], la [!UICONTROL Configuration] sección le permite agregar características o segmentos al modelo. En esta sección, seleccione un rasgo o segmento de línea de base, un período de retrospectiva y datos de las fuentes de datos de origen y de terceros.

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
   <td colname="col2"> <p>Haga clic en el botón de características o segmentos para ver una lista de todas sus características o segmentos. El segmento o rasgo seleccionado se convierte en la línea de base que utilizan los algoritmos del sistema para el modelado. </p> <p> <p><b>Nota</b>:  Seleccione una característica integrada, una característica basada en reglas o un segmento como línea de base. De lo contrario, los modelos no se ejecutarán. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Seleccionar período retroactivo (2)</b> </p> </td> 
   <td colname="col2"> <p>Establece un intervalo de tiempo para el modelo. Según su selección, el algoritmo incluye y evalúa datos de los 30, 60 o 90 días anteriores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Seleccionar algoritmo (3)</b> </p> </td> 
   <td colname="col2"> <p>En este momento, el Generador de modelos solo funciona con nuestro algoritmo de Peso <span class="keyword"></span> de características patentado. <span class="keyword"> El Audience Manager</span> puede agregar otras funciones algorítmicas en versiones posteriores. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Seleccionar datos de modelo de la fuente de datos (4)</b> </p> </td> 
   <td colname="col2"> <p>Permite seleccionar las fuentes de datos de origen y de terceros que desee utilizar en el modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusiones (5)</b> </p> </td> 
   <td colname="col2"> <p>Puede excluir características de las fuentes de datos seleccionadas para el modelado. Utilice la lista <span class="wintitle"> Exclusiones</span> y lea Modelos <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algoritmos: Exclusión</a> de características para obtener más información. </p> </td>
  </tr> 
 </tbody>
</table>

Vea el siguiente vídeo para aprender a crear un modelo de origen similar, de modo que pueda encontrar más visitantes que se parezcan a los convertidores.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [Explicación de TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

