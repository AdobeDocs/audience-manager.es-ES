---
description: Exclusión de características proporciona controles adicionales en el flujo de trabajo de modelado, lo que le permite agregar los carriles de protección necesarios al modelo, en función de su experiencia en el dominio y los requisitos regulatorios. Utilice la opción Exclusions para seleccionar qué características se deben ignorar al crear modelos a partir de una o varias fuentes de datos.
seo-description: Exclusión de características proporciona controles adicionales en el flujo de trabajo de modelado, lo que le permite agregar los carriles de protección necesarios al modelo, en función de su experiencia en el dominio y los requisitos regulatorios. Utilice la opción Exclusions para seleccionar qué características se deben ignorar al crear modelos a partir de una o varias fuentes de datos.
seo-title: Exclusión de características de modelos algorítmicos
title: Exclusión de características de modelos algorítmicos
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Modelos algorítmicos
exl-id: 7e2df04d-7e07-408d-b82a-9571b5839ff4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# Modelos de similitud: exclusión de rasgos {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] proporciona controles adicionales en el flujo de trabajo de modelado, lo que le permite añadir los carriles de protección necesarios al modelo, según la experiencia de su dominio y los requisitos reglamentarios. Utilice la opción [!UICONTROL Exclusions] para seleccionar qué características se deben ignorar al crear modelos a partir de una o más fuentes de datos.

## Casos de uso {#use-cases}

Estos son algunos casos de uso que puede abordar con [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] permite excluir ciertos rasgos generales, como los rasgos de visitante del sitio, para que no se sesgue el modelo y se obtengan resultados planos.
* Puede eliminar características que no conozca o en las que no confíe desde una fuente de datos para comprender mejor las características influyentes.
* Puede excluir ciertos rasgos, como los demográficos, para ayudar con las obligaciones de cumplimiento que pueda tener.

>[!IMPORTANT]
>
>Una nota importante sobre el tercer caso de uso. Si el proveedor de datos de terceros agrega un nuevo rasgo demográfico a la fuente de datos *después de crear el modelo*, el modelo lo recoge automáticamente. Los rasgos no se pueden excluir del modelado después de crear el modelo. Consulte [Aspectos y limitaciones importantes](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Tenga cuidado al utilizar esta función y trabaje con el proveedor de datos para asegurarse de que está informado de cualquier cambio en la estructura de la fuente.

![](assets/lam_exclude_traits.png)

## Cómo usar las exclusiones de rasgos {#how-to-use}

Utilice el flujo de trabajo [Build a model](../../features/algorithmic-models/create-model.md#build-model) para crear nuevos modelos algorítmicos.

1. La selección [!UICONTROL Exclusions] aparece atenuada hasta que se seleccionan una o más fuentes de datos para el modelado.
2. Después de seleccionar una o más fuentes de datos para modelado, presione **[!UICONTROL Browse All Traits]**.
3. En la ventana **[!UICONTROL Select Traits to Exclude]** puede ver todos los rasgos asociados con los orígenes de datos seleccionados previamente. Seleccione los rasgos que desee excluir.
4. Puede filtrar los rasgos por tipo de rasgo, por tipo de población de rasgos ([ID de dispositivo](../../reference/ids-in-aam.md) y [ID de varios dispositivos](../../reference/ids-in-aam.md)) o puede examinar las carpetas de rasgos. Tenga en cuenta que las carpetas de rasgos solo muestran los rasgos asociados a las fuentes de datos seleccionadas.
5. Pulse **[!UICONTROL Exclude Selected Traits]**.

![trait-exclusions](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>Puede excluir carpetas enteras excluyendo el rasgo de carpeta en lugar de excluir los rasgos de la carpeta, uno por uno. Por ejemplo, en una carpeta con 20 características, solo debería excluir la característica de carpeta en lugar de excluir todos los rasgos uno a uno.

Si prefiere tutoriales en vídeo, vea nuestra demostración en vídeo sobre la exclusión de características:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

Además, vea el siguiente vídeo para obtener una vista detallada del funcionamiento de las métricas entre dispositivos.

>[!VIDEO](https://video.tv.adobe.com/v/33445/?quality=12)

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
   <td colname="col1"> <p>Características excluidas en la vista Resumen de modelos </p> </td>
   <td colname="col2"> <p>Los rasgos excluidos <i>no aparecen</i> en la vista Resumen de modelos. Solo se pueden ver los rasgos excluidos en el flujo de trabajo <b><span class="uicontrol"> Editar modelo</span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Controles de acceso basados en roles (RBAC) </p> </td>
   <td colname="col2"> <p>Tenga en cuenta las siguientes limitaciones para las empresas que utilizan <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Si no tiene acceso para ver un rasgo, <i>no puede</i> seleccionar ese rasgo para excluirlo del modelo. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Si no tiene acceso para ver un rasgo, <i>no puede</i> verlo en la lista de rasgos excluidos. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificar características excluidas después de guardar el modelo </p> </td>
   <td colname="col2"> <p>No se pueden modificar los rasgos excluidos después de crear y guardar un modelo. Si desea modificar los resultados, puede clonar el modelo y cambiar los rasgos excluidos. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Número máximo de características que se pueden excluir </p> </td>
   <td colname="col2"> <p>El número máximo de características que se pueden excluir de un modelo es 500. Utilice características de carpeta para maximizar las exclusiones. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Excluir rasgo de línea de base </p> </td>
   <td colname="col2"> <p>El rasgo de línea de base se excluye de forma predeterminada, por lo que no aparece en la lista <b><span class="uicontrol"> Exclusiones</span></b> al crear el modelo. </p> </td>
  </tr>
 </tbody>
</table>

Vea el siguiente vídeo para aprender cómo y por qué excluir características específicas de un [!UICONTROL Look-Alike Model].

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## Vínculos relacionados

* [Acerca de los rasgos algorítmicos](/help/using/features/algorithmic-models/understanding-models.md)
* [Exclusión de características: tutorial](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
