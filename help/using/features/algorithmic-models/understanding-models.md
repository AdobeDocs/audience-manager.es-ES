---
description: Cree y administre los rasgos o segmentos utilizados en el modelado de similitudes.
keywords: peso relativo, similitud
seo-description: Build and manage the traits or segments used in look-alike modeling.
seo-title: About Look-Alike Modeling
solution: Audience Manager
title: Acerca de los modelos de similitud
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1576'
ht-degree: 1%

---

# Comprensión [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Buscar nuevos usuarios con [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] le ayuda a descubrir nuevas audiencias únicas mediante el análisis automatizado de datos. El proceso se inicia al seleccionar un [!UICONTROL trait] o [!UICONTROL segment], un intervalo de tiempo, y origen y terceros [!UICONTROL data sources]. Las opciones proporcionan las entradas para el modelo algorítmico. Cuando se ejecuta el proceso de análisis, busca usuarios aptos en función de las características compartidas de la población seleccionada. Una vez finalizados, estos datos están disponibles en [Generador de rasgos](../../features/traits/about-trait-builder.md) donde se puede utilizar para crear rasgos basados en [precisión y alcance](../../features/traits/trait-accuracy-reach.md). Además, puede generar segmentos que combinen características algorítmicas con [!UICONTROL rules-based traits] y agregue otros requisitos de cualificación con [!DNL Boolean] expresiones y operadores de comparación. [!UICONTROL Look-Alike Modeling] le ofrece una forma dinámica de extraer valor de todos los datos de rasgos disponibles.

## Ventajas {#advantages}

Las principales ventajas de utilizar [!UICONTROL Look-Alike Modeling] incluir:

* **Precisión de los datos:** El algoritmo se ejecuta regularmente, lo que ayuda a mantener los resultados actualizados y relevantes.
* **Automatización:** No es necesario que administre un gran conjunto de reglas estáticas. El algoritmo encuentra las audiencias que necesita.
* **Ahorre tiempo y reduzca el esfuerzo:** Con nuestro proceso de modelado no tienes que adivinar qué [!UICONTROL traits]/[!UICONTROL segments] puede trabajar o dedicar tiempo a recursos en campañas para descubrir nuevas audiencias. El modelo puede hacer esto por usted.
* **Fiabilidad:** El modelado funciona con procesos de detección y calificación del lado del servidor que evalúan sus propios datos y los datos de terceros seleccionados a los que tiene acceso. Esto significa que no tiene que ver los visitantes del sitio para clasificarlos para un rasgo.

## Flujo de trabajo {#workflow}

Los modelos se administran en **[!UICONTROL Audience Data > Models]**. En un nivel superior, el proceso de flujo de trabajo implica lo siguiente:

* Seleccione los datos de línea de base que desea que evalúe el algoritmo. Esto incluye un [!UICONTROL trait] o [!UICONTROL segment], intervalo de tiempo y [!UICONTROL data sources] (sus propios datos y los datos de terceros a los que ya tiene acceso a través de [!DNL Audience Manager]). En el flujo de trabajo de creación de modelos, puede excluir la variable [!UICONTROL traits] que no quieres interferir con tu modelo.
* Guarde el modelo. Una vez guardado, el proceso de evaluación algorítmica se ejecuta automáticamente. Sin embargo, tenga en cuenta que este proceso puede tardar hasta siete días en completarse. [!DNL Audience Manager] le envía un correo electrónico cuando el algoritmo ha finalizado y los resultados están disponibles para [!UICONTROL trait] creación.
* Generar algorítmico [!UICONTROL traits] in [!UICONTROL Trait Builder].
* Combinar [!UICONTROL traits] en [!UICONTROL segments] in [!UICONTROL Segment Builder].
* Crear y enviar [!UICONTROL segment] datos a un [!UICONTROL destination].

## Resolución de problemas {#troubleshooting}

Desactivamos cualquier [!UICONTROL Look-Alike Model] que no genera datos para tres ejecuciones consecutivas. Tenga en cuenta que no puede volver a establecer el estado del modelo como activo posteriormente. Para garantizar que los modelos generen datos, le recomendamos que cree modelos a partir de fuentes de datos con [!UICONTROL traits] para acumular datos de.

## Comprensión [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] es un algoritmo propietario diseñado para descubrir nuevos [!UICONTROL traits] automáticamente. Se compara con [!UICONTROL trait] datos de su [!UICONTROL traits] y [!UICONTROL segments] frente a todos los demás datos de origen y de terceros a los que tenga acceso a través de [!DNL Audience Manager]. Consulte esta sección para obtener una descripción de la [!UICONTROL TraitWeight] proceso de detección algorítmica.

![](assets/algo_model.png)

Los pasos siguientes describen la [!UICONTROL TraitWeight] proceso de evaluación.

### Paso 1: Crear una línea de base para [!UICONTROL Trait] Comparación

Para crear una línea de base, [!UICONTROL TraitWeight] mide todos los [!UICONTROL traits] asociadas a una audiencia para un intervalo de 30, 60 o 90 días. A continuación, clasifica [!UICONTROL traits] según su frecuencia y correlación. El recuento de frecuencia mide la uniformidad. La correlación mide la probabilidad de una [!UICONTROL trait] estar presente solo en la audiencia de línea de base. [!UICONTROL Traits] que aparecen a menudo se dice que tienen una alta comunalidad, una característica importante utilizada para establecer una puntuación ponderada cuando se combina con [!UICONTROL traits] descubierto en su seleccionado [!UICONTROL data sources].

### Paso 2: Buscar lo mismo [!UICONTROL Traits] en el [!UICONTROL Data Source]

Después de crear una línea de base para la comparación, el algoritmo busca lo mismo [!UICONTROL traits] en el seleccionado [!UICONTROL data sources]. En este paso, [!UICONTROL TraitWeight] realiza un recuento de frecuencia de todos los elementos detectados [!UICONTROL traits] y los compara con la línea de base. Sin embargo, a diferencia del valor basal, poco frecuente [!UICONTROL traits] se clasifican más arriba que las que aparecen con más frecuencia. Raro [!UICONTROL traits] se dice que presentan un alto grado de especificidad. [!UICONTROL TraitWeight] evalúa combinaciones de línea base común [!UICONTROL traits] y poco frecuentes (altamente específicas) [!UICONTROL data source] [!UICONTROL traits] más influyentes o deseables que [!UICONTROL traits] común a ambos conjuntos de datos. De hecho, nuestro modelo reconoce estos grandes, comunes [!UICONTROL traits] y no asigna una prioridad excesiva a los conjuntos de datos con correlaciones elevadas. Raro [!UICONTROL traits] obtener una prioridad mayor porque es más probable que representen a usuarios nuevos y únicos que [!UICONTROL traits] con una alta comunalidad en todos los ámbitos.

### Paso 3: Asignar Peso

En este paso, [!UICONTROL TraitWeight] rangos recientemente descubiertos [!UICONTROL traits] en orden de influencia o conveniencia. La escala de peso es un porcentaje que va del 0 % al 100 %. [!UICONTROL Traits] una clasificación más cercana al 100 % significa que se parecen más a la audiencia en la población de línea de base. Además, muy ponderado [!UICONTROL traits] son útiles porque representan a usuarios nuevos y únicos que pueden comportarse de manera similar a la audiencia de línea de base establecida. Recuerde, [!UICONTROL TraitWeight] considera [!UICONTROL traits] con una alta similitud en la línea de base y una alta especificidad en las fuentes de datos comparadas para ser más valiosos que [!UICONTROL traits] común en cada conjunto de datos.

### Paso 4: Puntuación de usuarios

Cada usuario del seleccionado [!UICONTROL data sources] recibe una puntuación del usuario igual a la suma de todas las ponderaciones del influyente [!UICONTROL traits] en el perfil de ese usuario. Las puntuaciones del usuario se normalizan entre 0 y 100 %.

### Paso 5: Mostrar y trabajar con resultados

[!DNL Audience Manager] muestra los resultados del modelo ponderado en [!UICONTROL Trait Builder]. Cuando desee crear una [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] permite crear [!UICONTROL traits] en función de la puntuación ponderada generada por el algoritmo durante una ejecución de datos. Puede elegir una precisión mayor para clasificar solo a los usuarios que tienen puntuaciones de usuario muy altas y, por lo tanto, son muy similares a la audiencia de línea de base, en lugar de al resto de la audiencia. Si desea llegar a una audiencia mayor (alcance), puede reducir la precisión.

### Paso 6: Volver a evaluar la relevancia de un [!UICONTROL Trait] Entre ciclos de procesamiento

Periódicamente, [!UICONTROL TraitWeight] reevalúa la importancia de un [!UICONTROL trait] basado en el tamaño y el cambio en la población de ese [!UICONTROL trait]. Esto sucede cuando el número de usuarios cumple los requisitos para eso [!UICONTROL trait] aumenta o disminuye con el tiempo. Este comportamiento se ve más claramente en rasgos que se vuelven muy grandes. Por ejemplo, supongamos que el algoritmo utiliza [!UICONTROL trait A] para el modelado. Como población de [!UICONTROL trait A] aumenta, [!UICONTROL TraitWeight] reevalúa la importancia de eso [!UICONTROL trait] y pueden asignar una puntuación más baja o ignorarla. En este caso, [!UICONTROL trait A] es demasiado común o grande como para decir algo significativo sobre su población. Después [!UICONTROL TraitWeight] reduce el valor de [!UICONTROL trait A] (o lo ignora en el modelo), la población del rasgo algorítmico disminuye. La lista de influyentes [!UICONTROL traits] refleja la evolución de la población de referencia. Utilice la lista de los influyentes [!UICONTROL traits] para comprender por qué se están produciendo estos cambios.

Enlaces relacionados:

* [Generador de modelos](../../features/algorithmic-models/create-model.md)
* [Precisión y alcance](../../features/traits/trait-accuracy-reach.md)

## Programación de actualizaciones para [!UICONTROL Look-Alike Models] y [!UICONTROL Traits] {#update-schedule}

Programaciones de creación y actualización para nuevas o existentes [!UICONTROL algorithmic models] y [!UICONTROL traits].

### [!UICONTROL Look-Alike Model] Programación de creación y actualización

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> Tipo de actividad </th>
   <th colname="col2" class="entry"> Descripción </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>Crear o clonar un modelo</b> </td>
   <td colname="col2"> <p>Para nuevos o clonados [!UICONTROL Look-Alike Models], el proceso de creación se ejecuta una vez al día en: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17:00 EST (de noviembre a marzo) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18:00 EDT (de marzo a noviembre) </li> 
     </ul> </p> <p>Los modelos creados o clonados después de la fecha límite de creación se procesan al día siguiente. </p> <p>Si la primera ejecución de un modelo no genera datos, se ejecutará una segunda vez, al día siguiente. Si el segundo intento tampoco genera datos, habrá un tercer intento, al día siguiente. El modelo dejará de ejecutarse si el tercer intento tampoco genera datos. En este caso, desactivaremos el modelo. Ver más en <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Solución de problemas de modelos de similitud</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Actualizar un modelo</b> </td> 
   <td colname="col2"> <p>En condiciones ideales, los modelos existentes se ejecutan entre semana, al menos una vez cada 7 días. Por ejemplo, si crea un modelo (dentro del plazo) el lunes, se actualizará el lunes siguiente como máximo. </p> <p>Un modelo se volverá a ejecutar si cumple cualquiera de las siguientes condiciones: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Su última ejecución no se realizó correctamente. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Se ha ejecutado correctamente antes de y no se ha ejecutado en absoluto en los últimos 7 días Y el modelo tiene al menos un rasgo activo adjunto. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] Programación de creación y actualización

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de actividad </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Crear un rasgo</b> </td> 
   <td colname="col2"> <p>El proceso de creación de rasgos se ejecuta todos los días, de lunes a viernes. Por lo general, los nuevos rasgos algorítmicos aparecen en la interfaz de usuario en un plazo de 48 horas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Actualizar un rasgo</b> </td> 
   <td colname="col2"> <p>Las características existentes se actualizan al menos una vez cada 7 días y siguen la programación de actualizaciones de modelos. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vista de lista de modelos {#models-list-view}

La vista de lista es un espacio de trabajo central que le ayuda a crear, revisar y administrar modelos.

El [!UICONTROL Models] Esta página de lista contiene funciones y herramientas que le ayudan a lo siguiente:

* Cree nuevos modelos.
* Administrar modelos existentes (editar, pausar, eliminar o clonar).
* Buscar modelos por nombre.
* Crear [!UICONTROL algorithmic traits] utilizando cualquier modelo determinado.

## Vista de resumen de modelos {#models-summary-view}

La página Resumen muestra detalles del modelo, como nombre, alcance/precisión, historial de procesamiento y [!UICONTROL traits] creado a partir del modelo. La página también incluye configuraciones que le permiten crear y administrar modelos. Haga clic en el nombre de un modelo en la lista de resumen para ver sus detalles.

La página de resumen del modelo incluye las siguientes secciones.

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sección </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> Información básica</span> </p> </td>
   <td colname="col2"> <p>Incluye información básica sobre el modelo, como su nombre y cuándo se ejecutó por última vez. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Alcance y precisión del modelo</span> </p> </td> 
   <td colname="col2"> <p>Muestra <a href="../../features/traits/trait-accuracy-reach.md"> precisión y alcance</a> datos de la última ejecución del modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Historial de procesamiento del modelo</span> </p> </td> 
   <td colname="col2"> <p>Muestra la fecha y hora de procesamiento de las últimas 10 ejecuciones y si se generaron datos en esas ejecuciones. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Rasgos influyentes</span> </p> </td> 
   <td colname="col2"> <p>El <span class="wintitle"> Rasgos influyentes</span> tabla: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Enumera los 50 rasgos influyentes principales que se representan mejor en la población de línea de base del modelo. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Clasifica cada rasgo en orden de importancia <span class="wintitle"> Peso relativo</span> rango. El <span class="wintitle"> Peso relativo</span> ordena los rasgos recién descubiertos en orden de influencia o deseabilidad. La escala de peso es un porcentaje que va del 0 % al 100 %. Las características clasificadas cerca del 100 % significan que se parecen más a la audiencia en la población de línea de base. Consulte <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Explicación de TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Muestra los valores exclusivos de 30 días y la población total de rasgos para cada rasgo. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características que utilizan el modelo</span> </p> </td>
   <td colname="col2"> <p>Muestra una lista de los rasgos algorítmicos en función del modelo seleccionado. Haga clic en un nombre o ID de rasgo para obtener más información sobre el rasgo. Seleccionar <b><span class="uicontrol"> Crear nueva característica con el modelo</span></b> para ir al proceso de creación de rasgos algorítmicos. </p> <p>La etiqueta de sección cambia según el nombre del modelo. Por ejemplo, supongamos que crea un modelo y le asigna el nombre Modelo A. Al cargar la página de resumen, el nombre de esta sección cambia a <span class="wintitle"> Rasgos que utilizan el modelo A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinos ](../../features/destinations/destinations.md)
>* [Rasgos ](../../features/traits/trait-details-page.md)
>* [Segmentos ](../../features/segments/segments-purpose.md)

