---
description: La exclusión de características proporciona controles adicionales en el flujo de trabajo de modelado, lo que le permite agregar los carriles de protección necesarios al modelo, en función de la experiencia del dominio y los requisitos normativos. Utilice la opción Exclusiones para seleccionar qué características se deben ignorar al crear modelos a partir de una o varias fuentes de datos.
seo-description: La exclusión de características proporciona controles adicionales en el flujo de trabajo de modelado, lo que le permite agregar los carriles de protección necesarios al modelo, en función de la experiencia del dominio y los requisitos normativos. Utilice la opción Exclusiones para seleccionar qué características se deben ignorar al crear modelos a partir de una o varias fuentes de datos.
seo-title: Exclusión de características de modelos algorítmicos
title: Exclusión de características de modelos algorítmicos
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 56f3b605b434f18c07d36196fd6ae21743401294
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 1%

---


# Modelos de similitud: exclusión de rasgos {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] proporciona controles adicionales en el flujo de trabajo de modelado, lo que le permite agregar los carriles de protección necesarios al modelo, en función de la experiencia del dominio y los requisitos reglamentarios. Utilice la opción [!UICONTROL Exclusions] para seleccionar qué características se deben ignorar al crear modelos a partir de una o varias fuentes de datos.

## Casos de uso {#use-cases}

A continuación se indican algunos casos de uso que puede abordar con [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] permite excluir ciertas características de captación global, como las características de visitante del sitio, para que no se sesgue el modelo, lo que conduce a resultados planos.
* Puede eliminar características que no conoce o en las que no confía de un origen de datos para comprender mejor las características influyentes.
* Puede excluir determinadas características, como las características demográficas, para ayudar con las obligaciones de cumplimiento que pueda tener.

>[!IMPORTANT]
>
>Una nota importante sobre el tercer caso de uso. Si el proveedor de datos de terceros agrega una nueva característica demográfica a la fuente de datos *después de crear el modelo*, el modelo la detecta automáticamente. Después de crear el modelo no se pueden excluir características del modelado. Consulte [Aspectos y limitaciones importantes](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Tenga cuidado al utilizar esta función y trabaje con el proveedor de datos para asegurarse de que está informado de cualquier cambio en la estructura de la fuente.

![](assets/lam_exclude_traits.png)

## Cómo usar las exclusiones de características {#how-to-use}

Utilice el flujo de trabajo [Generar un modelo](../../features/algorithmic-models/create-model.md#build-model) para generar nuevos modelos algorítmicos.

1. La selección [!UICONTROL Exclusions] aparece atenuada hasta que se seleccionan una o varias fuentes de datos para el modelado.
2. Después de seleccionar una o varias fuentes de datos para modelar, presione **[!UICONTROL Browse All Traits]**.
3. En la ventana **[!UICONTROL Select Traits to Exclude]**, puede ver todas las características asociadas con las fuentes de datos seleccionadas anteriormente. Seleccione las características que desee excluir.
4. Puede filtrar las características por tipo de característica, tipo de población de características ([ID del dispositivo](../../reference/ids-in-aam.md) y [ID entre dispositivos](../../reference/ids-in-aam.md)) o puede examinar las carpetas de características. Tenga en cuenta que las carpetas de características solo muestran las características asociadas con las fuentes de datos seleccionadas.
5. Pulse **[!UICONTROL Exclude Selected Traits]**.

![características-exclusiones](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>Puede excluir carpetas enteras excluyendo la característica de carpeta en lugar de excluir las características de la carpeta, una por una. Por ejemplo, en una carpeta con 20 características, solo tendría que excluir la característica de carpeta en lugar de excluir todas las características una por una.

Si prefiere tutoriales en vídeo, vea nuestra demostración en vídeo sobre la exclusión de características:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

Además, vea el siguiente vídeo para ver en detalle cómo funcionan las métricas entre dispositivos.

>[!VIDEO](https://video.tv.adobe.com/v/33445/?quality=12)

## Aspectos y limitaciones importantes {#important-aspects-and-limitations}

Tenga en cuenta los siguientes aspectos y limitaciones relacionados con [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Vista de resumen de características excluidas en modelos </p> </td>
   <td colname="col2"> <p>Las características excluidas <i>no se muestran</i> en la vista Resumen de modelos. Solo se pueden ver las características excluidas en el flujo de trabajo <b><span class="uicontrol"> Editar modelo</span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Controles de acceso basados en roles (RBAC) </p> </td>
   <td colname="col2"> <p>Tenga en cuenta las siguientes limitaciones para compañías que utilizan <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Si no tiene acceso a la vista de un rasgo, <i>no puede</i> seleccionar ese rasgo para excluirlo del modelo. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Si no tiene acceso a la vista de un rasgo, <i>no puede</i> vista que se caracterice en la lista de características excluidas. </li>
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
   <td colname="col1"> <p>Excluir rasgo de línea de base </p> </td>
   <td colname="col2"> <p>La característica de línea de base se excluye de forma predeterminada, por lo que no aparece en la lista <b><span class="uicontrol"> Exclusiones</span></b> al crear el modelo. </p> </td>
  </tr>
 </tbody>
</table>

Vea el siguiente vídeo para saber cómo y por qué excluir características específicas de un [!UICONTROL Look-Alike Model].

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## Vínculos relacionados

* [Acerca de las características algorítmicas](/help/using/features/algorithmic-models/understanding-models.md)
* [Exclusión de características: tutorial](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)