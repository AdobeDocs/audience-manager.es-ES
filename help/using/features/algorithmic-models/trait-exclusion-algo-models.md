---
description: La exclusión de características proporciona controles adicionales en el flujo de trabajo de modelado, permitiéndole agregar los carriles necesarios al modelo, en función de los conocimientos de dominio y los requisitos regulatorios. Utilice la opción Exclusiones para seleccionar qué características se deben ignorar al crear modelos a partir de una o varias fuentes de datos.
seo-description: La exclusión de características proporciona controles adicionales en el flujo de trabajo de modelado, permitiéndole agregar los carriles necesarios al modelo, en función de los conocimientos de dominio y los requisitos regulatorios. Utilice la opción Exclusiones para seleccionar qué características se deben ignorar al crear modelos a partir de una o varias fuentes de datos.
seo-title: Exclusión de rasgos algorítmicos
title: Exclusión de rasgos algorítmicos
uuid: 1359800 b -6 e 6 c -41 e 1-88 b 4-23 d 31952 abb 3
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# Algorithmic Models: Trait Exclusion {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] proporciona controles adicionales en el flujo de trabajo de modelado, permitiéndole agregar los carriles necesarios al modelo, en función de los conocimientos de dominio y los requisitos regulatorios. Use the [!UICONTROL Exclusions] option to select which traits to ignore when creating models from one or more data sources.

## Casos de uso {#use-cases}

Here are some use cases you can address with [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] permite excluir determinadas características de captador, como características del visitante del sitio, por lo que no se diferencia el modelo, lo que lleva a resultados planos.
* Puede eliminar características que no conoce o que no confía en un origen de datos para comprender mejor las características influyentes.
* Puede excluir determinadas características, como características demográficas, para ayudarlo con cualquier obligación de cumplimiento que pueda tener.

>[!IMPORTANT]
>
>Una nota importante sobre el tercer caso de uso. If the third-party data provider adds a new demographic trait to the data feed *after you created the model*, the trait is automatically picked up by the model. No puede excluir características del modelo después de crear el modelo. See [Important Aspects &amp; Limitations](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Tenga cuidado al utilizar esta función y trabajar con el proveedor de datos para asegurarse de que se le informa de cualquier cambio en la estructura de fuentes.

![](assets/lam_exclude_traits.png)

## How to Use Trait Exclusions {#how-to-use}

Use the [Build a model](../../features/algorithmic-models/create-model.md#build-model) workflow to build new algorithmic models.

1. [!UICONTROL Exclusions] La selección aparece atenuada hasta que se seleccionan una o más fuentes de datos para el modelado.
2. After selecting one or more data sources for modeling, press **[!UICONTROL Browse All Traits]**.
3. In the **[!UICONTROL Select Traits to Exclude]** window, you can see all traits associated with the data sources you selected previously. Seleccione las características que desee excluir.
4. Puede filtrar las características por tipo de característica o puede examinar las carpetas de características. Tenga en cuenta que las carpetas de características solo muestran las características asociadas con las fuentes de datos seleccionadas.
5. Press **[!UICONTROL Exclude Selected Traits]**.

>[!TIP]
>
>Puede excluir carpetas enteras excluyendo el rasgo de carpeta en lugar de excluir las características de la carpeta, de una en una. Por ejemplo, en una carpeta con 20 características, solo deberá excluir el rasgo de carpeta en lugar de excluir todas las características uno por uno.

Si prefiere los tutoriales en vídeo, vea nuestra demostración de vídeo para la exclusión de rasgos:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12&captions=spa)

## Important Aspects &amp; Limitations {#important-aspects-and-limitations}

Please take note of the following aspects and limitations related to [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Características excluidas en la vista resumen de modelos </p> </td>
   <td colname="col2"> <p>The excluded traits <i>do not show up</i> in the Models Summary view. You can see the excluded traits only in the <b><span class="uicontrol"> Edit Model</span></b> workflow. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Controles de acceso basados en roles (RBAC) </p> </td>
   <td colname="col2"> <p>Note the following limitations for companies using <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">If you don't have access to view a trait, you <i>cannot</i> select that trait to be excluded from the model. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">If you don't have access to view a trait, you <i>cannot</i> view that trait in the excluded traits list. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificar características excluidas después de guardar el modelo </p> </td>
   <td colname="col2"> <p>No puede modificar las características excluidas después de crear y guardar un modelo. Si desea ajustar los resultados, puede clonar el modelo y cambiar las características excluidas. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Número máximo de características que puede excluir </p> </td>
   <td colname="col2"> <p>El número máximo de características que puede excluir de un modelo es 500. Utilice características de carpeta para maximizar las exclusiones. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Excluir característica de línea base </p> </td>
   <td colname="col2"> <p>The baseline trait is excluded by default, so it does not show up in the <b><span class="uicontrol"> Exclusions</span></b> list, when building the model. </p> </td>
  </tr>
 </tbody>
</table>

## Vínculos relacionados

* [Acerca de las características algorítmicas](/help/using/features/algorithmic-models/understanding-models.md)
* [Exclusión de rasgos: tutorial](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)