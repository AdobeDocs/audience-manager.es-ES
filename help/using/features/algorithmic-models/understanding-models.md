---
description: Cree y administre los rasgos o segmentos utilizados en el modelado de similitud.
keywords: peso relativo, parecido
seo-description: Cree y administre los rasgos o segmentos utilizados en el modelado de similitud.
seo-title: Acerca del modelado similar
solution: Audience Manager
title: Acerca del modelado similar
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Modelos algorítmicos
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1595'
ht-degree: 1%

---

# Explicación de [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Buscar nuevos usuarios con [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] ayuda a descubrir audiencias nuevas y únicas mediante el análisis automatizado de datos. El proceso se inicia cuando selecciona [!UICONTROL trait] o [!UICONTROL segment], un intervalo de tiempo y [!UICONTROL data sources] de origen y de terceros. Las opciones proporcionan las entradas para el modelo algorítmico. Cuando se ejecuta el proceso de análisis, busca usuarios elegibles en función de características compartidas de la población seleccionada. Una vez finalizados, estos datos están disponibles en [Generador de rasgos](../../features/traits/about-trait-builder.md), donde puede utilizarlos para crear rasgos basados en la [precisión y el alcance](../../features/traits/trait-accuracy-reach.md). Además, puede generar segmentos que combinen características algorítmicas con [!UICONTROL rules-based traits] y agregar otros requisitos de calificación con expresiones [!DNL Boolean] y operadores de comparación. [!UICONTROL Look-Alike Modeling] le ofrece una forma dinámica de extraer valor de todos los datos de rasgos disponibles.

## Ventajas {#advantages}

Los principales beneficios de utilizar [!UICONTROL Look-Alike Modeling] incluyen:

* **Precisión de los datos:** el algoritmo se ejecuta regularmente, lo que ayuda a mantener los resultados actualizados y relevantes.
* **Automatización:** no es necesario administrar un gran conjunto de reglas estáticas. El algoritmo encontrará audiencias para usted.
* **Ahorre tiempo y reduzca los esfuerzos:** Con nuestro proceso de modelado no tiene que adivinar qué  [!UICONTROL traits]/[!UICONTROL segments] puede funcionar o dedicar recursos de tiempo en campañas para descubrir nuevas audiencias. El modelo puede hacerlo por usted.
* **Fiabilidad:** el modelado funciona con procesos de detección y calificación del lado del servidor que evalúan sus propios datos y los datos de terceros seleccionados a los que tiene acceso. Esto significa que no tiene que ver los visitantes del sitio para calificarlos para un rasgo.

## Flujo de trabajo {#workflow}

Los modelos se administran en **[!UICONTROL Audience Data > Models]**. En un nivel superior, el proceso de flujo de trabajo implica lo siguiente:

* Seleccione los datos de línea de base que desea que evalúe el algoritmo. Esto incluye un [!UICONTROL trait] o [!UICONTROL segment], intervalo de tiempo y [!UICONTROL data sources] (sus propios datos y datos de terceros a los que ya tiene acceso mediante [!DNL Audience Manager]). En el flujo de trabajo de creación de modelos, puede excluir el [!UICONTROL traits] que no desea que interfiera con el modelo.
* Guarde el modelo. Una vez guardado, el proceso de evaluación algorítmica se ejecuta automáticamente. Tenga en cuenta, sin embargo, que este proceso puede tardar hasta 7 días en completarse. [!DNL Audience Manager] le envía un mensaje de correo electrónico cuando el algoritmo ha finalizado y los resultados están disponibles para su  [!UICONTROL trait] creación.
* Generar [!UICONTROL traits] algorítmico en [!UICONTROL Trait Builder].
* Combine [!UICONTROL traits] en [!UICONTROL segments] en [!UICONTROL Segment Builder].
* Cree y envíe datos [!UICONTROL segment] a un [!UICONTROL destination].

## Resolución de problemas {#troubleshooting}

Desactivamos cualquier [!UICONTROL Look-Alike Model] que no genere datos para tres ejecuciones consecutivas. Tenga en cuenta que no puede volver a establecer el estado del modelo en activo posteriormente. Para garantizar que los modelos generen datos, se recomienda crear modelos a partir de fuentes de datos con suficiente [!UICONTROL traits] para acumular datos de.

## Explicación de [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] es un algoritmo propietario diseñado para descubrir nuevas  [!UICONTROL traits] automáticamente. Compara los [!UICONTROL trait] datos de sus [!UICONTROL traits] y [!UICONTROL segments] actuales con los demás datos de origen y de terceros a los que tiene acceso mediante [!DNL Audience Manager]. Consulte esta sección para obtener una descripción del proceso de detección algorítmica [!UICONTROL TraitWeight].

![](assets/algo_model.png)

Los siguientes pasos describen el proceso de evaluación [!UICONTROL TraitWeight].

### Paso 1: Generar una línea de base para la comparación [!UICONTROL Trait]

Para crear una línea de base, [!UICONTROL TraitWeight] mide todos los [!UICONTROL traits] asociados a una audiencia para un intervalo de 30, 60 o 90 días. A continuación, se clasifica [!UICONTROL traits] según su frecuencia y correlación. El recuento de frecuencia mide la cantidad de elementos comunes. La correlación mide la probabilidad de que un [!UICONTROL trait] esté presente solo en la audiencia de línea de base. [!UICONTROL Traits] que aparecen a menudo se dice que exhiben alta generalidad, una característica importante usada para establecer una puntuación ponderada cuando se combina con  [!UICONTROL traits] descubierto en el  [!UICONTROL data sources].

### Paso 2: Busque Same [!UICONTROL Traits] en el [!UICONTROL Data Source]

Después de crear una línea de base para la comparación, el algoritmo busca [!UICONTROL traits] idéntico en el [!UICONTROL data sources] seleccionado. En este paso, [!UICONTROL TraitWeight] realiza un recuento de frecuencia de todos los [!UICONTROL traits] descubiertos y los compara con la línea base. Sin embargo, a diferencia de la línea de base, los poco comunes [!UICONTROL traits] se clasifican más que los que aparecen con más frecuencia. Se dice que [!UICONTROL traits] raros exhiben un alto grado de especificidad. [!UICONTROL TraitWeight] evalúa las combinaciones de línea base común  [!UICONTROL traits] y poco frecuentes (muy específicos)  [!UICONTROL data source] [!UICONTROL traits] como más influyentes o deseables que  [!UICONTROL traits] comunes a ambos conjuntos de datos. De hecho, nuestro modelo reconoce estas [!UICONTROL traits] grandes y comunes y no asigna prioridad excesiva a los conjuntos de datos con correlaciones altas. Las [!UICONTROL traits] raras obtienen mayor prioridad porque es más probable que representen a usuarios nuevos y únicos que [!UICONTROL traits] con una alta frecuencia en todos los ámbitos.

### Paso 3: Asignar peso

En este paso, [!UICONTROL TraitWeight] clasifica los [!UICONTROL traits] recién descubiertos en orden de influencia o conveniencia. La escala de ponderación es un porcentaje que va del 0 % al 100 %. [!UICONTROL Traits] clasificado cerca del 100 % significa que se parecen más a la audiencia en la población de línea de base. Además, los [!UICONTROL traits] ponderados en gran medida son valiosos porque representan usuarios nuevos y únicos que pueden comportarse de manera similar a la audiencia establecida y de línea de base. Recuerde, [!UICONTROL TraitWeight] considera que [!UICONTROL traits] con una alta generalidad en la línea de base y una alta especificidad en las fuentes de datos comparadas es más valiosa que [!UICONTROL traits] común en cada conjunto de datos.

### Paso 4: Usuarios con puntuación

A cada usuario del [!UICONTROL data sources] seleccionado se le asigna una puntuación de usuario igual a la suma de todas las ponderaciones del [!UICONTROL traits] influyente en el perfil de ese usuario. A continuación, las puntuaciones del usuario se normalizan entre el 0 y el 100%.

### Paso 5: Mostrar y trabajar con resultados

[!DNL Audience Manager] muestra los resultados del modelo ponderado en  [!UICONTROL Trait Builder]. Cuando desea generar un [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] permite crear [!UICONTROL traits] en función de la puntuación ponderada generada por el algoritmo durante una ejecución de datos. Puede elegir una precisión mayor para solo calificar a los usuarios que tienen puntuaciones de usuario muy altas y, por lo tanto, son muy similares a la audiencia de línea de base, en lugar de al resto de la audiencia. Si desea alcanzar una audiencia mayor (alcance), puede reducir la precisión.

### Paso 6: Volver a evaluar la relevancia de un [!UICONTROL Trait] en los ciclos de procesamiento

Periódicamente, [!UICONTROL TraitWeight] vuelve a evaluar la importancia de un [!UICONTROL trait] en función del tamaño y el cambio en la población de ese [!UICONTROL trait]. Esto sucede a medida que el número de usuarios clasificados para ese [!UICONTROL trait] aumenta o disminuye con el tiempo. Este comportamiento se ve claramente en rasgos que se vuelven muy grandes. Por ejemplo, supongamos que el algoritmo utiliza [!UICONTROL trait A] para el modelado. A medida que aumenta la población de [!UICONTROL trait A], [!UICONTROL TraitWeight] vuelve a evaluar la importancia de ese [!UICONTROL trait] y puede asignar una puntuación inferior o ignorarla. En este caso, [!UICONTROL trait A] es demasiado común o grande para decir algo significativo sobre su población. Después de que [!UICONTROL TraitWeight] reduzca el valor de [!UICONTROL trait A] (o lo ignore en el modelo), la población del rasgo algorítmico disminuye. La lista de influyentes [!UICONTROL traits] refleja la evolución de la población basal. Utilice la lista de [!UICONTROL traits] influyentes para comprender por qué se producen estos cambios.

Vínculos relacionados:

* [Generador de modelos](../../features/algorithmic-models/create-model.md)
* [Precisión y alcance](../../features/traits/trait-accuracy-reach.md)

## Actualizar programación para [!UICONTROL Look-Alike Models] y [!UICONTROL Traits] {#update-schedule}

Creación y actualización de programas para [!UICONTROL algorithmic models] y [!UICONTROL traits] nuevos o existentes.

### [!UICONTROL Look-Alike Model] Creación y actualización de programación

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
   <td colname="col2"> <p>Para los [!UICONTROL Modelos de similitud] nuevos o clonados, el proceso de creación se ejecuta una vez al día en: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (noviembre a marzo) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 6 PM EDT (marzo - noviembre) </li> 
     </ul> </p> <p>Los modelos creados o clonados después de la fecha límite de creación se procesan al día siguiente. </p> <p>Si la primera ejecución de un modelo no genera datos, se ejecutará por segunda vez al día siguiente. Si el segundo intento tampoco genera datos, habrá un tercer intento, al día siguiente. El modelo dejará de ejecutarse si el tercer intento tampoco genera datos. En este caso, desactivaremos el modelo. Consulte más información en <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Solución de problemas de modelos de similitud</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Actualizar un modelo</b> </td> 
   <td colname="col2"> <p>En condiciones ideales, los modelos existentes se ejecutan entre semana, al menos una vez cada 7 días. Por ejemplo, si crea un modelo (antes de la fecha límite) el lunes, se actualizará el lunes siguiente a más tardar. </p> <p>Un modelo se volverá a ejecutar si cumple cualquiera de las siguientes condiciones: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Su última ejecución no tuvo éxito. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Se ha ejecutado correctamente antes de AND no se ha ejecutado en absoluto en los últimos 7 días Y el modelo tiene al menos un rasgo activo adjunto. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] Creación y actualización de programación

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
   <td colname="col2"> <p>El proceso de creación de características se ejecuta todos los días, de lunes a viernes. Por lo general, aparecen nuevos rasgos algorítmicos en la interfaz de usuario en un plazo de 48 horas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Actualizar un rasgo</b> </td> 
   <td colname="col2"> <p>Los rasgos existentes se actualizan al menos una vez cada 7 días y siguen la programación de las actualizaciones del modelo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vista de lista de modelos {#models-list-view}

La vista de lista es un espacio de trabajo central que le ayuda a crear, revisar y administrar modelos.

La página de lista [!UICONTROL Models] contiene funciones y herramientas que le ayudan a:

* Cree nuevos modelos.
* Administrar modelos existentes (editar, pausar, eliminar o clonar).
* Busque modelos por nombre.
* Cree [!UICONTROL algorithmic traits] utilizando cualquier modelo determinado.

## Vista de resumen de modelos {#models-summary-view}

La página de resumen muestra detalles del modelo como nombre, alcance/precisión, historial de procesamiento y [!UICONTROL traits] creado a partir del modelo. La página también incluye configuraciones que permiten crear y administrar modelos. Haga clic en un nombre de modelo de la lista de resumen para ver sus detalles.

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
   <td colname="col2"> <p>Incluye información básica sobre el modelo, como su nombre y el momento en que se ejecutó por última vez. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Alcance y precisión del modelo</span> </p> </td> 
   <td colname="col2"> <p>Muestra la precisión <a href="../../features/traits/trait-accuracy-reach.md"> y los datos de alcance</a> para la última ejecución del modelo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Historial de procesamiento de modelo</span> </p> </td> 
   <td colname="col2"> <p>Muestra la fecha y hora de procesamiento de las últimas 10 ejecuciones y si se generaron datos sobre ellas. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características influyentes</span> </p> </td> 
   <td colname="col2"> <p>La tabla <span class="wintitle"> Rasgos influyentes</span>: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Enumera las 50 principales características influyentes que se representan mejor en la población de línea de base del modelo. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Clasifica cada rasgo en orden de su <span class="wintitle"> Peso relativo</span> rango. El <span class="wintitle"> Peso relativo</span> clasifica los rasgos recién descubiertos en orden de influencia o conveniencia. La escala de ponderación es un porcentaje que va del 0 % al 100 %. Los rasgos clasificados cerca del 100 % significan que se parecen más a la audiencia en la población de línea de base. Consulte <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Explicación de TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Muestra los únicos de 30 días y la población total de rasgos de cada rasgo. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Rasgos con modelo</span> </p> </td>
   <td colname="col2"> <p>Muestra una lista de los rasgos algorítmicos en función del modelo seleccionado. Haga clic en un nombre o ID de rasgo para obtener más información sobre el rasgo. Seleccione <b><span class="uicontrol"> Crear nuevo rasgo con modelo</span></b> para ir al proceso de creación algorítmica de rasgos. </p> <p>La etiqueta de sección cambia según el nombre del modelo. Por ejemplo, supongamos que crea un modelo y lo denomina Modelo A. Al cargar la página de resumen, el nombre de esta sección cambia a <span class="wintitle"> Rasgos usando el modelo A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinos ](../../features/destinations/destinations.md)
* [Rasgos ](../../features/traits/trait-details-page.md)
* [Segmentos ](../../features/segments/segments-purpose.md)

