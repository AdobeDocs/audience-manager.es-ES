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
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Creación de un modelo algorítmico {#create-an-algorithmic-model}

Describe los pasos opcionales y requeridos en los que puede crear un modelo algorítmico en [!UICONTROL Model Builder].

## Generar un modelo {#build-model}

<!-- t_model_build.xml -->

### Sección Generador de modelos

[!UICONTROL Model Builder] consta de las secciones [!UICONTROL Basic Information] y [!UICONTROL Configuration] . Para crear un modelo, complete los campos obligatorios de estas dos secciones. Guarde el modelo para iniciar el algoritmo. [!DNL Audience Manager] le envía una notificación automatizada una vez que se completa la primera ejecución de datos. Después de recibir el correo electrónico, puede ir al Generador de [características](../../features/traits/about-trait-builder.md) y crear características algorítmicas.

>[!NOTE]
>
>* El proceso de modelado se ejecuta una sola vez si se crea un modelo y no se genera ninguna característica con él.
>* Cree modelos a partir de fuentes de datos que contengan una cantidad significativa de información. Se ejecutarán modelos con datos insuficientes, pero no se obtendrán resultados.
>* *No cree* modelos con otras características algorítmicas o segmentos.
>* La notificación de correo electrónico automatizada se envía una sola vez (después de la primera ejecución de datos).


### Generar el modelo

Para crear un modelo, vaya a la [!UICONTROL Models] sección y haga clic en **[!UICONTROL Add New]** y siga los pasos a continuación:

1. En la sección Información [](../../features/algorithmic-models/create-model.md#basic-information) básica
   * Asigne un nombre al modelo.
   * *(Opcional)* Proporcione una breve descripción del modelo.
   * Establezca el estado del modelo en **[!UICONTROL Active]** o **[!UICONTROL Inactive]**. Los modelos inactivos no se ejecutarán y no producirán datos.
1. En la sección [Configuración](../../features/algorithmic-models/create-model.md#configuration) :
   * Haga clic **[!UICONTROL Browse All Traits]** o **[!UICONTROL Browse All Segments]** para seleccionar un rasgo o segmento con el que desee modelar. Seleccione una característica integrada, una característica basada en reglas o un segmento como base. De lo contrario, los modelos no se ejecutarán.
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
   <td colname="col1"> <p><b>Seleccionar datos de modelo de la fuente de datos (4)</b> </p> </td> 
   <td colname="col2"> <p>Permite seleccionar las fuentes de datos de origen y de terceros que desee utilizar en el modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusiones (5)</b> </p> </td> 
   <td colname="col2"> <p>Puede excluir características de las fuentes de datos seleccionadas para el modelado. Utilice la lista <span class="wintitle"> Exclusiones</span> y lea Modelos <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algoritmos: Exclusión</a> de características para obtener más información. </p> </td>
  </tr> 
 </tbody>
</table>

Vea el siguiente vídeo para aprender a crear un modelo parecido al de origen, de modo que pueda encontrar más visitantes que se parezcan a los convertidores.

>[!VIDEO](https://video.tv.adobe.com/v/23504/?captions=spa)

>[!MORELIKETHIS]
>
>* [Explicación de TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

