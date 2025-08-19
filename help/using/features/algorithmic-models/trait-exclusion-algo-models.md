---
description: La exclusión de características proporciona controles adicionales en su flujo de trabajo de modelado, lo que le permite agregar las barandillas necesarias al modelo, en función de su experiencia en el dominio y los requisitos reglamentarios. Utilice la opción Exclusiones para seleccionar qué características ignorar al crear modelos a partir de uno o varios orígenes de datos.
seo-description: Trait Exclusion provides additional controls in your modeling workflow, allowing you to add the necessary guard rails to the model, based on your domain expertise and regulatory requirements. Use the Exclusions option to select which traits to ignore when creating models from one or more data sources.
seo-title: Algorithmic Models  Trait Exclusion
title: Modelos algorítmicos Exclusión de rasgos
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Algorithmic Models
exl-id: 7e2df04d-7e07-408d-b82a-9571b5839ff4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# Modelado Look similares: exclusión de rasgos {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] Proporciona controles adicionales en su flujo de trabajo de modelado, lo que le permite agregar las barandillas necesarias al modelo, en función de su experiencia en el dominio y los requisitos reglamentarios. Utilice la [!UICONTROL Exclusions] opción para seleccionar qué características ignorar al crear modelos a partir de uno o varios orígenes de datos.

## Casos de uso {#use-cases}

Estos son algunos casos de uso que puede abordar con [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] le permite excluir ciertos rasgos generales, como visitante del sitio rasgos, para no sesgar el modelo, lo que lleva a resultados planos.
* Puede eliminar los rasgos que no conoce o en los que no confía de una fuente de datos, para comprender mejor los rasgos influyentes.
* Puede excluir ciertos rasgos, como los rasgos demográficos, para ayudar con cualquier obligación de cumplimiento que pueda tener.

>[!IMPORTANT]
>
>Una nota importante sobre el tercer caso de uso. Si el proveedor de datos terceros agrega un nuevo rasgo demográfico al fuente de datos *después de haber creado el modelo*, el modelo recoge automáticamente el rasgo. No puede excluir características del modelado después de crearlo. Ver [Aspectos Importantes y Limitaciones](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Tenga cuidado al utilizar esta función y trabaje con el proveedor de datos para asegurarse de que está informado de cualquier cambio en la estructura fuente.

![](assets/lam_exclude_traits.png)

## Cómo utilizar las exclusiones de características {#how-to-use}

Utilice la [flujo de trabajo Generar un modelo](../../features/algorithmic-models/create-model.md#build-model) para versión nuevos modelos algorítmicos.

1. La [!UICONTROL Exclusions] selección aparece atenuada hasta que seleccione una o más fuentes de datos para el modelado.
2. Después de seleccionar uno o más orígenes de datos para el modelado, pulse **[!UICONTROL Browse All Traits]**.
3. En la **[!UICONTROL Select Traits to Exclude]** ventana, puede ver todas las características asociadas con las fuentes de datos que seleccionó anteriormente. Seleccione las características que desea excluir.
4. Puede filtrar las características por tipo de rasgo, tipo de población de características ([ID](../../reference/ids-in-aam.md) de dispositivo e [ID](../../reference/ids-in-aam.md) entre dispositivos) o puede examinar las carpetas de características. Tenga en cuenta que las carpetas de rasgos solo muestran las características asociadas con las fuentes de datos seleccionadas.
5. Pulse **[!UICONTROL Exclude Selected Traits]**.

![exclusiones de características](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>Puede excluir carpetas enteras excluyendo la característica de carpeta en lugar de excluir las características de la carpeta, una por una. Por ejemplo, en una carpeta con 20 características, solo sería necesario excluir la característica de carpeta en lugar de excluir todas las características una por una.

Si prefiere los tutoriales en vídeo, vea nuestra demostración en vídeo sobre la exclusión de rasgos:

>[!VIDEO](https://video.tv.adobe.com/v/38135/?quality=12&captions=spa)

Además, vea el vídeo siguiente para obtener una visión detallada del funcionamiento de las métricas entre dispositivos.

>[!VIDEO](https://video.tv.adobe.com/v/36789/?quality=12&captions=spa)

## Aspectos importantes y limitaciones {#important-aspects-and-limitations}

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
   <td colname="col1"> <p>Características excluidas en el resumen de modelos Ver </p> </td>
   <td colname="col2"> <p>Las características <i>excluidas no aparecen</i> en el vista de resumen de modelos. Las características excluidas solo se pueden ver en el <b><span class="uicontrol"> modelo</span></b> Editar flujo de trabajo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Controles de acceso basados en roles (RBAC) </p> </td>
   <td colname="col2"> <p>Tenga en cuenta las siguientes limitaciones para las empresas que utilizan <a href="../../features/administration/administration-overview.md#administration"> RBAC:</a> </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Si no tiene acceso a vista un rasgo, <i>no puede</i> seleccionar ese rasgo que excluir del modelo. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Si no tiene acceso a vista un rasgo, <i>no puede</i> vista ese rasgo en el lista de rasgos excluidos. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificar características excluidas después de guardar el modelo </p> </td>
   <td colname="col2"> <p>No se pueden modificar las características excluidas después de crear y guardar un modelo. Si desea modificar los resultados, puede clonar el modelo y cambiar las características excluidas. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Número máximo de características que se pueden excluir </p> </td>
   <td colname="col2"> <p>El número máximo de características que puede excluir de un modelo es 500. Utilice las características de carpeta para maximizar las exclusiones. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Excluir rasgo de línea de base </p> </td>
   <td colname="col2"> <p>La característica de línea de base se excluye de forma predeterminada, por lo que no aparece en el <b><span class="uicontrol"> lista de exclusiones</span></b> al crear el modelo. </p> </td>
  </tr>
 </tbody>
</table>

Vea el vídeo siguiente para saber cómo y por qué excluir características específicas de un [!UICONTROL Look-Alike Model]archivo .

>[!VIDEO](https://video.tv.adobe.com/v/38135?captions=spa)

## Enlaces relacionados

* [Acerca de los rasgos algorítmicos](/help/using/features/algorithmic-models/understanding-models.md)
* [Exclusión de características - Tutorial](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
