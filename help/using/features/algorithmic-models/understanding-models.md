---
description: Cree y gestione las características o segmentos utilizados en el modelado algorítmico, también denominado modelado similar. Las funciones de modelo se encuentran en Datos de audiencia > Modelos.
keywords: peso relativo, similar
seo-description: Cree y gestione las características o segmentos utilizados en el modelado algorítmico, también denominado modelado similar. Las funciones de modelo se encuentran en Datos de audiencia > Modelos.
seo-title: Acerca de los modelos algorítmicos
solution: Audience Manager
title: Acerca de los modelos algorítmicos
topic: DIL API
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Acerca de los modelos algorítmicos {#about-algorithmic-models}

Cree y gestione las características o segmentos utilizados en el modelado algorítmico, también denominado modelado similar. Las funciones del modelo se encuentran en **[!UICONTROL Audience Data > Models]**.

<!-- c_models.xml -->

## Explicación de los modelos algorítmicos {#understanding-models}

Las secciones siguientes representan una revisión del modelado algorítmico en [!DNL Audience Manager]. Describen cómo funciona el modelado, las ventajas y el flujo de trabajo.

<!-- understanding-models.xml -->

## Buscar nuevos usuarios con modelado algorítmico {#find-new-users}

El modelado algorítmico ayuda a descubrir audiencias nuevas y únicas a través del análisis automatizado de datos. El proceso comienza cuando se selecciona una característica o segmento, un intervalo de tiempo y fuentes de datos de origen y de terceros. Las opciones proporcionan las entradas para el modelo algorítmico. Cuando se ejecuta el proceso de análisis, busca usuarios elegibles en función de las características compartidas de la población seleccionada. Una vez finalizados, estos datos están disponibles en el [generador](../../features/traits/about-trait-builder.md) de rasgos, donde puede utilizarlos para crear características basadas en la [precisión y el alcance](../../features/traits/trait-accuracy-reach.md). Además, puede crear segmentos que combinen características algorítmicas con características basadas en reglas y agregar otros requisitos de cualificación con expresiones booleanas y operadores de comparación. El modelado algorítmico le proporciona una manera dinámica de extraer valor de todos los datos de características disponibles.

## Ventajas {#advantages}

Las principales ventajas de utilizar [!DNL Audience Manager] modelos incluyen:

* **** Precisión de los datos: El algoritmo se ejecuta regularmente, lo que ayuda a mantener los resultados actualizados y relevantes.
* **** Automatización: No es necesario administrar un gran conjunto de reglas estáticas. El algoritmo encontrará audiencias para usted.
* **** Ahorre tiempo y reduzca el esfuerzo: Con nuestro proceso de modelado no tiene que adivinar qué características o segmentos pueden funcionar o dedicar recursos de tiempo a campañas para descubrir nuevas audiencias. El modelo puede hacer esto por usted.
* **** Fiabilidad: El modelado funciona con procesos de detección y calificación del lado del servidor que evalúan sus propios datos y los datos de terceros seleccionados a los que tiene acceso. Esto significa que no tiene que ver a los visitantes del sitio para calificarlos para una característica.

## Flujo de trabajo {#workflow}

Los modelos se administran en **[!UICONTROL Audience Data > Models]**. En un nivel superior, el proceso de flujo de trabajo incluye lo siguiente:

* Seleccione los datos de línea de base que desee que evalúe el algoritmo. Esto incluye una característica o segmento, un intervalo de tiempo y fuentes de datos (sus propios datos y datos de terceros a los que ya tiene acceso a través de [!DNL Audience Manager]). En el flujo de trabajo de creación de modelos, puede excluir las características que no desee que interfieran con el modelo.
* Guarde el modelo. Una vez guardado, el proceso de evaluación algorítmica se ejecuta automáticamente. Sin embargo, tenga en cuenta que este proceso puede tardar hasta 7 días en completarse. [!DNL Audience Manager] le envía un mensaje de correo electrónico cuando el algoritmo ha finalizado y los resultados están disponibles para la creación de características.
* Genere características algorítmicas en [!UICONTROL Trait Builder].
* Combine características en segmentos en [!UICONTROL Segment Builder].
* Cree y envíe datos de segmentos a un destino.

## Resolución de problemas {#troubleshooting}

Desactivamos cualquier modelo algorítmico que no pueda generar datos para tres ejecuciones consecutivas. Tenga en cuenta que no puede volver a activar el estado del modelo posteriormente. Para garantizar que los modelos generen datos, le recomendamos que cree modelos a partir de fuentes de datos con características suficientes para acumular datos.

## Explicación de TraitWeight {#understanding-traitweight}

[!UICONTROL TraitWeight] es un algoritmo propietario diseñado para descubrir automáticamente nuevas características. Compara los datos de características de sus características actuales y los segmentos con todos los demás datos de origen y de terceros a los que tiene acceso a través de [!DNL Audience Manager]. Consulte esta sección para ver una descripción del proceso de detección [!UICONTROL TraitWeight] algorítmica.

<!-- traitweight.xml -->

![](assets/algo_model.png)

Los pasos siguientes describen el proceso de [!UICONTROL TraitWeight] evaluación.

### Paso 1: Generar una línea de base para la comparación de características

Para generar una línea base, mide todas las características asociadas con una audiencia para un intervalo de 30, 60 o 90 días. [!UICONTROL TraitWeight] Luego, clasifica los rasgos según su frecuencia y correlación. El recuento de frecuencias mide la comunidad. La correlación mide la probabilidad de que una característica esté presente solamente en la audiencia de referencia. Se dice que las características que aparecen con frecuencia muestran una gran generalidad, una característica importante utilizada para establecer una puntuación ponderada cuando se combina con características detectadas en las fuentes de datos seleccionadas.

### Paso 2: Buscar las mismas características en la fuente de datos

Después de crear una línea de base para la comparación, el algoritmo busca características idénticas en las fuentes de datos seleccionadas. En este paso, [!UICONTROL TraitWeight] realiza un recuento de frecuencias de todas las características detectadas y las compara con la línea base. Sin embargo, a diferencia de la línea base, las características poco comunes se clasifican más que las que aparecen con más frecuencia. Se dice que las características raras muestran un alto grado de especificidad. [!UICONTROL TraitWeight] evalúa las combinaciones de características básicas comunes y las características poco comunes (muy específicas) de la fuente de datos como más influyentes o deseables que las características comunes a ambos conjuntos de datos. De hecho, nuestro modelo reconoce estas características comunes y grandes y no asigna prioridad excesiva a los conjuntos de datos con correlaciones altas. Las características raras obtienen mayor prioridad porque son más propensas a representar a usuarios nuevos y únicos que a rasgos con una gran comunidad en todos los ámbitos.

### Paso 3: Asignar peso

En este paso, [!UICONTROL TraitWeight] clasifica los rasgos recién descubiertos en orden de influencia o deseabilidad. La escala de peso es un porcentaje que va del 0 % al 100 %. Las características clasificadas más cerca del 100% significan que se parecen más a la audiencia en la población básica. Además, las características con ponderación alta son valiosas porque representan usuarios nuevos y únicos que pueden comportarse de manera similar a la audiencia establecida con base. Recuerde, [!UICONTROL TraitWeight] considera que las características con alta coincidencia en la línea de base y alta especificidad en las fuentes de datos comparadas son más valiosas que las características comunes en cada conjunto de datos.

### Paso 4: Usuarios con puntuación

A cada usuario de las fuentes de datos seleccionadas se le asigna una puntuación de usuario igual a la suma de todas las ponderaciones de las características influyentes en el perfil de ese usuario. Las puntuaciones del usuario se normalizan entre 0 y 100%.

### Paso 5: Mostrar y trabajar con resultados

Audience Manager muestra los resultados del modelo ponderado en [!UICONTROL Trait Builder]. Si desea crear una característica algorítmica, [!UICONTROL Trait Builder] le permite crear características basadas en la puntuación ponderada generada por el algoritmo durante una ejecución de datos. Puede elegir una precisión mayor para clasificar solo a los usuarios que tengan una puntuación de usuario muy alta y que, por tanto, sean muy similares a la audiencia básica, en lugar de al resto de la audiencia. Si desea llegar a una audiencia mayor (alcance), puede reducir la precisión.

### Paso 6: Volver a evaluar la importancia de una característica en los ciclos de procesamiento

Periódicamente, [!UICONTROL TraitWeight] reevalúa la importancia de una característica en función del tamaño y el cambio en la población de esa característica. Esto sucede cuando el número de usuarios cualificados para esa característica aumenta o disminuye con el tiempo. Este comportamiento se ve más claramente en rasgos que se vuelven muy grandes. Por ejemplo, supongamos que el algoritmo utiliza la característica A para el modelado. A medida que aumenta la población de la característica A, [!UICONTROL TraitWeight] vuelve a evaluar la importancia de esa característica y puede asignar una puntuación inferior o ignorarla. En este caso, la característica A es demasiado común o grande para decir algo significativo sobre su población. Después de [!UICONTROL TraitWeight] reducir el valor de la característica A (o ignorarlo en el modelo), la población de la característica algorítmica disminuye. La lista de características influyentes refleja la evolución de la población de referencia. Utilice la lista de características influyentes para comprender por qué se producen estos cambios.

Vínculos relacionados:

* [Generador de modelos](../../features/algorithmic-models/create-model.md)
* [Precisión y alcance](../../features/traits/trait-accuracy-reach.md)

## Actualizar programación para modelos y características algorítmicos {#update-schedule}

Creación y actualización de programas para modelos y características algorítmicos nuevos o existentes.

<!-- c_model_update_schedule.xml -->

### Creación y actualización de modelos algorítmicos

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
   <td colname="col2"> <p>Para modelos algorítmicos nuevos o clonados, el proceso de creación se ejecuta una vez al día a las siguientes horas: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (noviembre - marzo) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 6 PM EDT (marzo - noviembre) </li> 
     </ul> </p> <p>Los modelos creados o clonados después del plazo de creación se procesan al día siguiente. </p> <p>Si la primera ejecución de un modelo no genera datos, se ejecutará por segunda vez, al día siguiente. Si el segundo intento tampoco genera datos, habrá un tercer intento, al día siguiente. El modelo dejará de ejecutarse si el tercer intento tampoco genera datos. En este caso, desactivaremos el modelo. Consulte más información en <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Resolución de problemas de modelos</a>algorítmicos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Actualizar un modelo</b> </td> 
   <td colname="col2"> <p>En condiciones ideales, los modelos existentes se ejecutan en días laborables, al menos una vez cada 7 días. Por ejemplo, si crea un modelo (antes de la fecha límite) el lunes, se actualizará el lunes siguiente a más tardar. </p> <p>Un modelo se volverá a ejecutar si cumple cualquiera de las siguientes condiciones: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Su última ejecución no tuvo éxito. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Se ha ejecutado correctamente antes Y no se ha ejecutado en absoluto en los últimos 7 días Y el modelo tiene al menos una característica activa conectada a él. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Creación y actualización de características algorítmicas

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de actividad </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Crear una característica</b> </td> 
   <td colname="col2"> <p>El proceso de creación de rasgos se ejecuta todos los días, de lunes a viernes. En general, aparecen nuevas características algorítmicas en la interfaz de usuario en un plazo de 48 horas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Actualizar una característica</b> </td> 
   <td colname="col2"> <p>Las características existentes se actualizan al menos una vez cada 7 días y siguen la programación de actualizaciones de modelos. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vista de lista de modelos {#models-list-view}

La vista de lista es un espacio de trabajo central que le ayuda a crear, revisar y administrar modelos.

<!-- c_models_list_view.xml -->

La página de lista Modelos contiene funciones y herramientas que le ayudan a:

* Cree nuevos modelos.
* Administre modelos existentes (editar, pausar, eliminar o clonar).
* Busque modelos por nombre.
* Cree características algorítmicas utilizando cualquier modelo determinado.

## Vista de resumen de modelos {#models-summary-view}

La página de resumen muestra detalles del modelo como nombre, alcance/precisión, historial de procesamiento y características creadas a partir del modelo. La página también incluye opciones que le permiten crear y administrar modelos. Haga clic en un nombre de modelo en la lista de resumen para ver sus detalles.

<!-- c_models_summary.xml -->

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
   <td colname="col2"> <p>Muestra <a href="../../features/traits/trait-accuracy-reach.md"> la precisión y los datos de alcance</a> de la última ejecución del modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Historial de procesamiento del modelo</span> </p> </td> 
   <td colname="col2"> <p>Muestra la fecha y hora de procesamiento de las últimas 10 ejecuciones y si se generaron datos en dichas ejecuciones. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características influyentes</span> </p> </td> 
   <td colname="col2"> <p>Tabla de características <span class="wintitle"> influyentes</span> : </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Enumera las 50 características influyentes principales que se representan mejor en la población base del modelo. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Clasifica cada característica en orden de su <span class="wintitle"> clasificación de peso</span> relativo. El <span class="wintitle"> Peso</span> Relativo ordena los rasgos recién descubiertos en orden de influencia o deseabilidad. La escala de peso es un porcentaje que va del 0 % al 100 %. Las características clasificadas más cerca del 100% significan que se parecen más a la audiencia en la población básica. Consulte <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Explicación de TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Muestra los únicos de 30 días y la población total de características de cada característica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características con modelo</span> </p> </td>
   <td colname="col2"> <p>Muestra una lista de las características algorítmicas basadas en el modelo seleccionado. Haga clic en un nombre de característica o en un ID de característica para obtener más información sobre la característica. Seleccione <b><span class="uicontrol"> Crear nueva característica con modelo</span></b> para ir al proceso de creación de características algorítmicas. </p> <p>La etiqueta de sección cambia según el nombre del modelo. Por ejemplo, supongamos que crea un modelo y lo denomina Modelo A. Al cargar la página de resumen, el nombre de esta sección se cambia a <span class="wintitle"> Características con el modelo A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinos](../../features/destinations/destinations.md)
>* [Características](../../features/traits/trait-details-page.md)
>* [Segmentos](../../features/segments/segments-purpose.md)

