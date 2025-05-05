---
description: La exclusión de características proporciona controles adicionales en el flujo de trabajo de modelado, lo que le permite añadir las protecciones necesarias al modelo, en función de su experiencia en el dominio y los requisitos regulatorios. Utilice la opción Exclusiones para seleccionar qué rasgos se deben ignorar al crear modelos a partir de una o varias fuentes de datos.
seo-description: Trait Exclusion provides additional controls in your modeling workflow, allowing you to add the necessary guard rails to the model, based on your domain expertise and regulatory requirements. Use the Exclusions option to select which traits to ignore when creating models from one or more data sources.
seo-title: Algorithmic Models  Trait Exclusion
title: Exclusión de rasgos de modelos algorítmicos
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Algorithmic Models
exl-id: 7e2df04d-7e07-408d-b82a-9571b5839ff4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# Modelos de similitud: exclusión de rasgos {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] proporciona controles adicionales en su flujo de trabajo de modelado, lo que le permite agregar las protecciones necesarias al modelo, en función de su experiencia de dominio y de los requisitos regulatorios. Utilice la opción [!UICONTROL Exclusions] para seleccionar qué características se deben ignorar al crear modelos a partir de uno o más orígenes de datos.

## Casos de uso {#use-cases}

Estos son algunos casos de uso que puede tratar con [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] le permite excluir ciertos rasgos generales, como los rasgos de visitante del sitio, para que no distorsione el modelo y obtenga resultados planos.
* Puede eliminar rasgos que no conozca o en los que no confíe de una fuente de datos para comprender mejor los rasgos influyentes.
* Puede excluir ciertos rasgos, como los rasgos demográficos, para ayudar con las obligaciones de cumplimiento que pueda tener.

>[!IMPORTANT]
>
>Una nota importante sobre el tercer caso de uso. Si el proveedor de datos de terceros agrega un nuevo rasgo demográfico a la fuente de datos *después de crear el modelo*, el modelo lo recoge automáticamente. No se pueden excluir rasgos del modelado después de crearlo. Consulte [Aspectos y limitaciones importantes](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Tenga cuidado al utilizar esta función y trabaje con el proveedor de datos para asegurarse de que está informado de cualquier cambio en la estructura de la fuente.

![](assets/lam_exclude_traits.png)

## Cómo utilizar las exclusiones de características {#how-to-use}

Use el flujo de trabajo [Generar un modelo](../../features/algorithmic-models/create-model.md#build-model) para generar nuevos modelos algorítmicos.

1. La selección [!UICONTROL Exclusions] aparece atenuada hasta que seleccione uno o más orígenes de datos para el modelado.
2. Después de seleccionar uno o más orígenes de datos para el modelado, presione **[!UICONTROL Browse All Traits]**.
3. En la ventana **[!UICONTROL Select Traits to Exclude]**, puede ver todos los rasgos asociados con los orígenes de datos que seleccionó anteriormente. Seleccione los rasgos que desee excluir.
4. Puede filtrar los rasgos por tipo de rasgo, tipo de población de rasgos ([ID de dispositivo](../../reference/ids-in-aam.md) e [ID entre dispositivos](../../reference/ids-in-aam.md)), o puede examinar las carpetas de rasgos. Tenga en cuenta que las carpetas de rasgos solo muestran los rasgos asociados con las fuentes de datos seleccionadas.
5. Presione **[!UICONTROL Exclude Selected Traits]**.

![exclusiones de rasgos](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>Puede excluir carpetas completas excluyendo la característica de carpeta en lugar de excluir las características de la carpeta, una por una. Por ejemplo, en una carpeta con 20 características, solo tendría que excluir la característica de carpeta en lugar de excluir todas las características una por una.

Si prefiere tutoriales en vídeo, vea nuestra demostración en vídeo de Exclusión de características:

>[!VIDEO](https://video.tv.adobe.com/v/38135/?quality=12&captions=spa)

Además, vea el siguiente vídeo para obtener una visión detallada de cómo funcionan las métricas entre dispositivos.

>[!VIDEO](https://video.tv.adobe.com/v/36789/?quality=12&captions=spa)

## Aspectos y limitaciones importantes {#important-aspects-and-limitations}

Tome nota de los siguientes aspectos y limitaciones relacionados con [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Características excluidas en la vista de resumen de modelos </p> </td>
   <td colname="col2"> <p>Los rasgos excluidos <i>no aparecen</i> en la vista Resumen de modelos. Solo puede ver los rasgos excluidos en el flujo de trabajo <b><span class="uicontrol"> Editar modelo</span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Controles de acceso basados en roles (RBAC) </p> </td>
   <td colname="col2"> <p>Tenga en cuenta las siguientes limitaciones para compañías que utilizan <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Si no cuenta con acceso para ver un rasgo, <i>no puede</i> seleccionar ese rasgo para excluirlo del modelo. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Si no cuenta con acceso para ver un rasgo, <i>no puede</i> verlo en la lista de rasgos excluidos. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificar rasgos excluidos después de guardar el modelo </p> </td>
   <td colname="col2"> <p>No se pueden modificar los rasgos excluidos después de crear y guardar un modelo. Si desea modificar los resultados, puede clonar el modelo y cambiar los rasgos excluidos. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Número máximo de rasgos que puede excluir </p> </td>
   <td colname="col2"> <p>El número máximo de rasgos que puede excluir de un modelo es de 500. Utilice características de carpeta para maximizar las exclusiones. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Excluir rasgo de línea base </p> </td>
   <td colname="col2"> <p>El rasgo de línea de base se excluye de forma predeterminada, por lo que no aparece en la lista <b><span class="uicontrol"> Exclusiones</span></b> al crear el modelo. </p> </td>
  </tr>
 </tbody>
</table>

Vea el siguiente vídeo para aprender cómo y por qué excluir características específicas de un(a) [!UICONTROL Look-Alike Model].

>[!VIDEO](https://video.tv.adobe.com/v/38135?captions=spa)

## Vínculos relacionados

* [Acerca de los rasgos algorítmicos](/help/using/features/algorithmic-models/understanding-models.md)
* [Exclusión de características - Tutorial](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
