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
source-wordcount: '1602'
ht-degree: 0%

---

# Explicación de [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Buscar nuevos usuarios con [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] le ayuda a descubrir nuevas audiencias únicas mediante el análisis automatizado de datos. El proceso se inicia al seleccionar [!UICONTROL trait] o [!UICONTROL segment], un intervalo de tiempo y [!UICONTROL data sources] de origen y de terceros. Las opciones proporcionan las entradas para el modelo algorítmico. Cuando se ejecuta el proceso de análisis, busca usuarios aptos en función de las características compartidas de la población seleccionada. Una vez completados, estos datos están disponibles en [Generador de rasgos](../../features/traits/about-trait-builder.md), donde puede utilizarlos para crear rasgos basados en la [precisión y el alcance](../../features/traits/trait-accuracy-reach.md). Además, puede generar segmentos que combinen características algorítmicas con [!UICONTROL rules-based traits] y agregar otros requisitos de calificación con expresiones [!DNL Boolean] y operadores de comparación. [!UICONTROL Look-Alike Modeling] le ofrece una forma dinámica de extraer valor de todos sus datos de rasgos disponibles.

## Ventajas {#advantages}

Las principales ventajas de usar [!UICONTROL Look-Alike Modeling] son las siguientes:

* **Precisión de los datos:** El algoritmo se ejecuta con regularidad, lo que ayuda a mantener los resultados actualizados y relevantes.
* **Automatización:** No tiene que administrar un gran conjunto de reglas estáticas. El algoritmo encuentra las audiencias que necesita.
* **Ahorre tiempo y reduzca el esfuerzo:** Con nuestro proceso de modelado no tiene que adivinar lo que [!UICONTROL traits]/[!UICONTROL segments] puede funcionar o gastar tiempo en recursos en campañas para descubrir nuevas audiencias. El modelo puede hacer esto por usted.
* **Fiabilidad:** el modelado funciona con procesos de calificación y detección del lado del servidor que evalúan sus propios datos y los datos de terceros seleccionados a los que tiene acceso. Esto significa que no tiene que ver los visitantes del sitio para clasificarlos para un rasgo.

## Flujo de trabajo {#workflow}

Usted administra los modelos en **[!UICONTROL Audience Data > Models]**. En un nivel superior, el proceso de flujo de trabajo implica lo siguiente:

* Seleccione los datos de línea de base que desea que evalúe el algoritmo. Esto incluye [!UICONTROL trait] o [!UICONTROL segment], un intervalo de tiempo y [!UICONTROL data sources] (sus propios datos y los de terceros a los que ya tiene acceso a través de [!DNL Audience Manager]). En el flujo de trabajo de creación del modelo, puede excluir [!UICONTROL traits] que no desee que interfiera con el modelo.
* Guarde el modelo. Una vez guardado, el proceso de evaluación algorítmica se ejecuta automáticamente. Sin embargo, tenga en cuenta que este proceso puede tardar hasta siete días en completarse. [!DNL Audience Manager] le envía un correo electrónico cuando el algoritmo ha finalizado y los resultados están disponibles para la creación de [!UICONTROL trait].
* Generar algoritmo [!UICONTROL traits] en [!UICONTROL Trait Builder].
* Combinar [!UICONTROL traits] en [!UICONTROL segments] en [!UICONTROL Segment Builder].
* Crear y enviar datos de [!UICONTROL segment] a [!UICONTROL destination].

## Resolución de problemas {#troubleshooting}

Desactivamos cualquier [!UICONTROL Look-Alike Model] que no genere datos durante tres ejecuciones consecutivas. Tenga en cuenta que no puede volver a establecer el estado del modelo como activo posteriormente. Para garantizar que los modelos generen datos, le recomendamos que genere modelos a partir de fuentes de datos con [!UICONTROL traits] suficientes para acumular datos de.

## Explicación de [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] es un algoritmo propietario diseñado para detectar [!UICONTROL traits] nuevos automáticamente. Compara los datos de [!UICONTROL trait] de sus [!UICONTROL traits] y [!UICONTROL segments] actuales con el resto de los datos de origen y de terceros a los que tiene acceso a través de [!DNL Audience Manager]. Consulte esta sección para obtener una descripción del proceso de detección mediante algoritmos de [!UICONTROL TraitWeight].

![](assets/algo_model.png)

Los pasos siguientes describen el proceso de evaluación de [!UICONTROL TraitWeight].

### Paso 1: Generar una línea de base para la comparación de [!UICONTROL Trait]

Para generar una línea de base, [!UICONTROL TraitWeight] mide todos los [!UICONTROL traits] asociados con una audiencia para un intervalo de 30, 60 o 90 días. A continuación, clasifica [!UICONTROL traits] según su frecuencia y correlación. El recuento de frecuencia mide la uniformidad. La correlación mide la probabilidad de que [!UICONTROL trait] esté presente solamente en la audiencia de línea de base. Se dice que las [!UICONTROL Traits] que aparecen con frecuencia tienen una alta similitud, una característica importante que se usa para establecer una puntuación ponderada cuando se combina con [!UICONTROL traits] que se descubrió en la [!UICONTROL data sources] que seleccionó.

### Paso 2: buscar lo mismo [!UICONTROL Traits] en [!UICONTROL Data Source]

Después de crear una línea de base para la comparación, el algoritmo busca [!UICONTROL traits] idénticos en el [!UICONTROL data sources] seleccionado. En este paso, [!UICONTROL TraitWeight] realiza un recuento de frecuencia de todos los [!UICONTROL traits] detectados y los compara con la línea de base. Sin embargo, a diferencia de la línea de base, las [!UICONTROL traits] poco comunes se clasifican más alto que las que aparecen con más frecuencia. Se dice que las [!UICONTROL traits] raras muestran un alto grado de especificidad. [!UICONTROL TraitWeight] considera que las combinaciones de línea de base común [!UICONTROL traits] y poco común (altamente específico) [!UICONTROL data source] [!UICONTROL traits] son más influyentes o deseables que [!UICONTROL traits] comunes a ambos conjuntos de datos. De hecho, nuestro modelo reconoce estos grandes conjuntos de datos comunes [!UICONTROL traits] y no asigna prioridad excesiva a los conjuntos de datos con correlaciones altas. Los(as) [!UICONTROL traits] raros(as) obtienen mayor prioridad porque es más probable que representen a usuarios nuevos y únicos que [!UICONTROL traits] con una alta comunidad en todos los tableros.

### Paso 3: Asignar Peso

En este paso, [!UICONTROL TraitWeight] clasifica a [!UICONTROL traits] recién descubierto en orden de influencia o conveniencia. La escala de peso es un porcentaje que va del 0 % al 100 %. [!UICONTROL Traits] se clasificó cerca del 100%, lo que significa que se parecen más a la audiencia en la población de línea de base. Además, los [!UICONTROL traits] de alto peso son útiles porque representan a usuarios nuevos y únicos que pueden comportarse de manera similar a la audiencia de línea de base establecida. Recuerde, [!UICONTROL TraitWeight] considera que [!UICONTROL traits] con alta similitud en la línea de base y alta especificidad en las fuentes de datos comparadas es más valioso que [!UICONTROL traits] común en cada conjunto de datos.

### Paso 4: Puntuación de usuarios

A cada usuario del [!UICONTROL data sources] seleccionado se le asigna una puntuación que es igual a la suma de todas las ponderaciones del [!UICONTROL traits] influyente en el perfil de ese usuario. Las puntuaciones del usuario se normalizan entre 0 y 100 %.

### Paso 5: Mostrar y trabajar con resultados

[!DNL Audience Manager] muestra los resultados del modelo ponderado en [!UICONTROL Trait Builder]. Si desea generar un [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] le permite crear [!UICONTROL traits] basándose en la puntuación ponderada generada por el algoritmo durante una ejecución de datos. Puede elegir una precisión mayor para clasificar solo a los usuarios que tienen puntuaciones de usuario muy altas y, por lo tanto, son muy similares a la audiencia de línea de base, en lugar de al resto de la audiencia. Si desea llegar a una audiencia mayor (alcance), puede reducir la precisión.

### Paso 6: Volver a evaluar la relevancia de un(a) [!UICONTROL Trait] en todos los ciclos de procesamiento

Periódicamente, [!UICONTROL TraitWeight] vuelve a evaluar la importancia de un(a) [!UICONTROL trait] en función del tamaño y el cambio en la población de ese(a) [!UICONTROL trait]. Esto sucede a medida que el número de usuarios calificados para ese(a) [!UICONTROL trait] aumenta o disminuye con el tiempo. Este comportamiento se ve más claramente en rasgos que se vuelven muy grandes. Por ejemplo, suponga que el algoritmo utiliza [!UICONTROL trait A] para el modelado. A medida que aumenta la población de [!UICONTROL trait A], [!UICONTROL TraitWeight] vuelve a evaluar la importancia de ese(a) [!UICONTROL trait] y puede asignar una puntuación más baja o ignorarla. En este caso, [!UICONTROL trait A] es demasiado común o grande como para decir algo significativo acerca de su población. Después de que [!UICONTROL TraitWeight] reduzca el valor de [!UICONTROL trait A] (o lo ignore en el modelo), la población del rasgo algorítmico disminuye. La lista de [!UICONTROL traits] influyentes refleja la evolución de la población de línea de base. Use la lista de los [!UICONTROL traits] más influyentes para comprender por qué se producen estos cambios.

Enlaces relacionados:

* [Generador de modelos](../../features/algorithmic-models/create-model.md)
* [Precisión y alcance](../../features/traits/trait-accuracy-reach.md)

## Programación de actualizaciones para [!UICONTROL Look-Alike Models] y [!UICONTROL Traits] {#update-schedule}

Programaciones de creación y actualización para [!UICONTROL algorithmic models] y [!UICONTROL traits] nuevos o existentes.

### Programación de creación y actualización de [!UICONTROL Look-Alike Model]

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
   <td colname="col2"> <p>Para [!UICONTROL Look-Alike Models] nuevos o clonados, el proceso de creación se ejecuta una vez al día a las: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17:00 EST (de noviembre a marzo) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18:00 EDT (de marzo a noviembre) </li> 
     </ul> </p> <p>Los modelos creados o clonados después de la fecha límite de creación se procesan al día siguiente. </p> <p>Si la primera ejecución de un modelo no genera datos, se ejecutará una segunda vez, al día siguiente. Si el segundo intento tampoco genera datos, habrá un tercer intento, al día siguiente. El modelo dejará de ejecutarse si el tercer intento tampoco genera datos. En este caso, desactivaremos el modelo. Ver más en <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> resolución de problemas de modelos similares</a>. </p> </td>
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

### Programación de creación y actualización de [!UICONTROL Look-Alike Trait]

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

La página de lista [!UICONTROL Models] contiene características y herramientas que le ayudarán a:

* Cree nuevos modelos.
* Administrar modelos existentes (editar, pausar, eliminar o clonar).
* Buscar modelos por nombre.
* Crear [!UICONTROL algorithmic traits] con un modelo determinado.

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
   <td colname="col1"> <p> <span class="wintitle"> información básica</span> </p> </td>
   <td colname="col2"> <p>Incluye información básica sobre el modelo, como su nombre y cuándo se ejecutó por última vez. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> Alcance y precisión del modelo <span class="wintitle"></span> </p> </td> 
   <td colname="col2"> <p>Muestra la precisión de <a href="../../features/traits/trait-accuracy-reach.md"> y alcanza </a> datos para la última ejecución del modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> historial de procesamiento de modelo</span> </p> </td> 
   <td colname="col2"> <p>Muestra la fecha y hora de procesamiento de las últimas 10 ejecuciones y si se generaron datos en esas ejecuciones. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> rasgos influyentes</span> </p> </td> 
   <td colname="col2"> <p>La tabla <span class="wintitle"> rasgos influyentes </span>: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Enumera los 50 rasgos influyentes principales que se representan mejor en la población de línea de base del modelo. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Clasifica cada rasgo en orden de su <span class="wintitle"> peso relativo</span> rango. El <span class="wintitle"> peso relativo</span> ordena los rasgos descubiertos recientemente en orden de influencia o conveniencia. La escala de peso es un porcentaje que va del 0 % al 100 %. Las características clasificadas cerca del 100 % significan que se parecen más a la audiencia en la población de línea de base. Consulte <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Explicación de TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Muestra los valores exclusivos de 30 días y la población total de rasgos para cada rasgo. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> rasgos que usan el modelo </span> </p> </td>
   <td colname="col2"> <p>Muestra una lista de los rasgos algorítmicos en función del modelo seleccionado. Haga clic en un nombre o ID de rasgo para obtener más información sobre el rasgo. Seleccione <b><span class="uicontrol"> Crear nuevo rasgo con modelo</span></b> para ir al proceso de creación de rasgos algorítmicos. </p> <p>La etiqueta de sección cambia según el nombre del modelo. Por ejemplo, supongamos que crea un modelo y le asigna el nombre Modelo A. Al cargar la página de resumen, el nombre de esta sección cambia a <span class="wintitle"> rasgos mediante el modelo A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinos](../../features/destinations/destinations.md)
>* [Características](../../features/traits/trait-details-page.md)
>* [Segmentos](../../features/segments/segments-purpose.md)
