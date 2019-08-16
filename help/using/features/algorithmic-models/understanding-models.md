---
description: Cree y administre las características o segmentos utilizados en el modelado algorítmico, también denominado modelado similar. Las funciones del modelo se encuentran en Datos de audiencia > Modelos.
keywords: peso relativo, lookequal
seo-description: Cree y administre las características o segmentos utilizados en el modelado algorítmico, también denominado modelado similar. Las funciones del modelo se encuentran en Datos de audiencia > Modelos.
seo-title: Acerca de modelos algorítmicos
solution: Audience Manager
title: Acerca de modelos algorítmicos
topic: API DIL
uuid: 39441 e 72-5316-453 d -9 aff -0 e 0 b 633 aabcd
translation-type: tm+mt
source-git-commit: 73d670225fb4170d02428a1dd163f442540e3415

---


# Acerca de modelos algorítmicos {#about-algorithmic-models}

Cree y administre las características o segmentos utilizados en el modelado algorítmico, también denominado modelado similar. Las funciones modelo se encuentran en **[!UICONTROL Audience Data > Models]**.

<!-- c_models.xml -->

## Explicación de modelos algorítmicos {#understanding-models}

Las secciones siguientes representan una revisión del modelado algorítmico en [!DNL Audience Manager]. Describen cómo funciona el modelado, los beneficios y el flujo de trabajo.

<!-- understanding-models.xml -->

## Buscar nuevos usuarios con modelado algorítmico {#find-new-users}

El modelado algorítmico ayuda a descubrir audiencias únicas y únicas a través del análisis automatizado de datos. El proceso comienza cuando se selecciona un rasgo o segmento, un intervalo de tiempo y fuentes de datos individuales y de terceros. Las opciones proporcionan las entradas para el modelo algorítmico. Cuando se ejecuta el proceso de análisis, busca usuarios elegibles en función de características compartidas de la población seleccionada. Una vez completado, estos datos están disponibles en [el Generador](../../features/traits/about-trait-builder.md) de rasgos, donde puede utilizarlos para crear características basadas en [la precisión y el alcance](../../features/traits/trait-accuracy-reach.md). Además, puede crear segmentos que combinen características algorítmicas con características basadas en reglas y agregue otros requisitos de cualificación con expresiones booleanas y operadores de comparación. El modelado algorítmico proporciona una forma dinámica de extraer valor de todos los datos de características disponibles.

## Ventajas {#advantages}

Los principales beneficios de utilizar [!DNL Audience Manager] modelado son:

* **Precisión de los datos:** El algoritmo se ejecuta regularmente, lo que ayuda a mantener los resultados actuales y relevantes.
* **Automatización:** No es necesario gestionar un gran conjunto de reglas estáticas. El algoritmo buscará audiencias para usted.
* **Ahorre tiempo y reduzca el esfuerzo:** Con nuestro proceso de modelado no tiene que adivinar qué características o segmentos pueden funcionar o gastar recursos en campañas para descubrir nuevas audiencias. El modelo puede hacer esto por usted.
* **Confiabilidad:** El modelado funciona con procesos de identificación y detección del lado del servidor que evalúan sus propios datos y datos de terceros seleccionados a los que usted tiene acceso. Esto significa que no tiene que ver a los visitantes del sitio para que los califique para un rasgo.

## Flujo de trabajo {#workflow}

Los modelos se administran **[!UICONTROL Audience Data > Models]**. En un nivel alto, el proceso de flujo de trabajo implica lo siguiente:

* Seleccione los datos de línea de base que desee que evalúen el algoritmo. Esto incluye un rasgo o un segmento, un intervalo de tiempo y fuentes de datos (sus propios datos y datos de terceros a los que [!DNL Audience Manager]ya tiene acceso). En el flujo de trabajo de creación del modelo, puede excluir las características que no desee interferir con el modelo.
* Guarde el modelo. Una vez guardada, el proceso de evaluación algorítmico se ejecuta automáticamente. No obstante, tenga en cuenta que este proceso puede tardar hasta 7 días en completarse. [!DNL Audience Manager] le envía un mensaje de correo electrónico cuando ha finalizado el algoritmo y los resultados están disponibles para la creación de características.
* Cree características algorítmicas en [!UICONTROL Trait Builder].
* Combine características en segmentos.[!UICONTROL Segment Builder]
* Cree y envíe datos de segmentos a un destino.

## Resolución de problemas {#troubleshooting}

Desactivamos cualquier modelo algorítmico que no genere datos para tres ejecuciones consecutivas. Tenga en cuenta que no puede volver a establecer el estado del modelo en activo después. Para asegurarse de que los modelos generan datos, le recomendamos que genere modelos a partir de fuentes de datos con características suficientes para acumular datos.

>[!MORE_ LIKE_ THIS]
>
>* [Destinos](../../features/destinations/destinations.md)
>* [Características](../../features/traits/trait-details-page.md)
>* [Segmentos](../../features/segments/segments-purpose.md)


## Explicación de traitweight {#understanding-traitweight}

[!UICONTROL TraitWeight] es un algoritmo propietario diseñado para descubrir nuevas características automáticamente. Compara los datos de características de sus características y segmentos actuales con los demás datos de origen y terceros a los que [!DNL Audience Manager]tiene acceso. Consulte esta sección para ver una descripción del proceso de detección [!UICONTROL TraitWeight] algorítmica.

<!-- traitweight.xml -->

![](assets/algo_model.png)

Los pasos siguientes describen el proceso [!UICONTROL TraitWeight] de evaluación.

### Paso 1: Generar una línea base para comparación de características

Para generar una línea base [!UICONTROL TraitWeight] , mide todas las características asociadas a una audiencia para un intervalo de 30, 60 o 90 días. A continuación, clasifica las características según su frecuencia y su correlación. El recuento de frecuencia mide la naturaleza común. La correlación mide la probabilidad de que un rasgo esté presente solo en la audiencia de línea de base. Las características que aparecen con frecuencia muestran un alto nivel común, una característica importante utilizada para configurar una puntuación ponderada cuando se combina con características detectadas en las fuentes de datos seleccionadas.

### Paso 2: Buscar las mismas características en la fuente de datos

Después de crear una línea de base para la comparación, el algoritmo busca características idénticas en las fuentes de datos seleccionadas. En este paso [!UICONTROL TraitWeight] , realiza un recuento de frecuencia de todas las características detectadas y las compara con la línea base. Sin embargo, a diferencia de la línea base, las características poco comunes se clasifican más arriba que las que aparecen con más frecuencia. Se dice que las características raras muestran un alto grado de especificidad. [!UICONTROL TraitWeight] evalúa las combinaciones de características de base comunes y características poco comunes (muy específicas) como características más influyentes u deseables que las características comunes de ambos conjuntos de datos. De hecho, nuestro modelo reconoce estas características comunes grandes y no asigna prioridad excesiva a los conjuntos de datos con correlaciones altas. Las características raras reciben mayor prioridad porque es más probable que representen a usuarios únicos nuevos y únicos que características con alta uniformidad en el tablero.

### Paso 3: Asignar grosor

En este paso [!UICONTROL TraitWeight] , clasifica las características recién detectadas en orden de influencia o conveniencia. La escala de ponderación es un porcentaje que se ejecuta entre 0% y 100%. Las características clasificadas más cerca del 100% suponen que son más parecidas a las de la población de línea de base. Además, las características ponderadas son valiosas porque representan usuarios únicos nuevos y únicos que pueden comportarse de manera similar a la audiencia de línea base establecida. Recuerde, [!UICONTROL TraitWeight] considera que las características con un alto nivel común en la línea de base y la mayor especificidad en las fuentes de datos comparadas son más valiosas que las características comunes de cada conjunto de datos.

### Paso 4: Puntuación de usuarios

A cada usuario de las fuentes de datos seleccionadas se le asigna una puntuación de usuario que equivale a la suma de todas las ponderaciones de las características influyentes del perfil del usuario. Las puntuaciones de usuario se normalizan entre 0 y 100%.

### Paso 5: Mostrar y trabajar con resultados

Audience Manager muestra los resultados del modelo ponderado. [!UICONTROL Trait Builder] Cuando desee crear un rasgo algorítmico, [!UICONTROL Trait Builder] le permite crear características basadas en la puntuación ponderada generada por el algoritmo durante una ejecución de datos. Puede elegir una precisión mayor para calificar únicamente a los usuarios que tienen puntuaciones de usuario muy altas y, por lo tanto, son muy similares a la audiencia de línea de base, en lugar del resto de la audiencia. Si desea llegar a una audiencia más grande (alcance), puede reducir la precisión.

### Paso 6: Reevaluar el significado de una característica en los ciclos de procesamiento

Periódicamente [!UICONTROL TraitWeight] , vuelve a evaluar la importancia de un rasgo según el tamaño y el cambio de la población de dicha característica. Esto sucede como el número de usuarios cualificados para esa característica que aumentan o disminuye con el tiempo. Este comportamiento se ve con mayor claridad en características muy grandes. Por ejemplo, supongamos que el algoritmo usa características A para modelado. A medida que aumenta la población de características A, [!UICONTROL TraitWeight] vuelva a evaluar la importancia de esa característica y puede asignar una puntuación inferior o ignorarla. En este caso, la característica A es demasiado común o grande para decir algo significativo sobre su población. Después [!UICONTROL TraitWeight] de reducir el valor de Rasit A (o se lo omite en el modelo), la población del atributo algorítmico disminuye. La lista de características influyentes refleja la evolución de la población de línea de base. Utilice la lista de características influyentes para comprender por qué se están produciendo estos cambios.

Vínculos relacionados:

* [Generador de modelos](../../features/algorithmic-models/create-model.md)
* [Precisión y alcance](../../features/traits/trait-accuracy-reach.md)

## Actualizar programación para modelos algorítmicos y características {#update-schedule}

Creación y actualización programados para modelos algorítmicos nuevos o existentes.

<!-- c_model_update_schedule.xml -->

### Programación de creación y actualización del modelo algorítmico

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
   <td colname="col2"> <p>Para modelos algorítmicos nuevos o clonados, el proceso de creación se ejecuta una vez al día en: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (de noviembre a marzo) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 6 PM EDT (de marzo a noviembre) </li> 
     </ul> </p> <p>Los modelos creados o clonados después de la fecha de creación se procesan al día siguiente. </p> <p>Si la primera ejecución de un modelo no genera datos, se ejecutará por segunda vez al día siguiente. Si el segundo intento no genera ningún dato, habrá un tercer intento, el día siguiente. El modelo dejará de ejecutarse si el tercer intento tampoco genera datos. En este caso, desactivaremos el modelo. Consulte Más en <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Resolución de problemas algorítmicos</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Actualizar un modelo</b> </td> 
   <td colname="col2"> <p>En condiciones ideales, los modelos existentes se ejecutan en días de semana, al menos una vez cada 7 días. Por ejemplo, si crea un modelo (por fecha de vencimiento) el lunes, se actualiza el siguiente lunes a la última. </p> <p>Un modelo se volverá a ejecutar si cumple cualquiera de las condiciones siguientes: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">La última ejecución no se realizó correctamente. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Se ejecutó correctamente antes de AND y no se ha ejecutado en los últimos 7 días Y el modelo tiene al menos una característica activa adjunta. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Programación de actualización y creación de rasgos algorítmicos

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
   <td colname="col2"> <p>El proceso de creación de características se ejecuta todos los días, de lunes a viernes. Por lo general, las nuevas características algorítmicas aparecen en la interfaz de usuario en un plazo de 48 horas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Actualizar un rasgo</b> </td> 
   <td colname="col2"> <p>Las características existentes se actualizan al menos una vez cada 7 días y siguen la programación de actualizaciones del modelo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vista de lista de modelos {#models-list-view}

La vista de lista es un espacio de trabajo central que ayuda a crear, revisar y administrar modelos.

<!-- c_models_list_view.xml -->

La página de lista Modelos contiene funciones y herramientas que le ayudan a:

* Cree nuevos modelos.
* Administrar modelos existentes (editar, pausar, eliminar o clonar).
* Busque modelos por nombre.
* Crear características algorítmicas con cualquier modelo dado.

## Vista de resumen de modelos {#models-summary-view}

La página de resumen muestra detalles del modelo como nombre, alcance/precisión, historial de procesamiento y características creadas a partir del modelo. La página también incluye ajustes que permiten crear y administrar modelos. Haga clic en un nombre de modelo de la lista de resumen para ver sus detalles.

<!-- c_models_summary.xml -->

La página de resumen del modelo incluye las secciones siguientes.

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
   <td colname="col2"> <p>Incluye información básica sobre el modelo, como su nombre y la última ejecución. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Precisión y alcance del modelo</span> </p> </td> 
   <td colname="col2"> <p>Muestra <a href="../../features/traits/trait-accuracy-reach.md"> la precisión y los</a> datos de alcance del último modelo ejecutado. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Historial de procesamiento modelo</span> </p> </td> 
   <td colname="col2"> <p>Muestra la fecha y hora de procesamiento de las últimas 10 ejecuciones y si se generaron datos en esas ejecuciones. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características influyentes</span> </p> </td> 
   <td colname="col2"> <p>La tabla <span class="wintitle"> Características</span> influyentes: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Enumera las 50 características influyentes más importantes que se representan mejor en la población de línea de base del modelo. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Clasifica cada característica en orden de <span class="wintitle"> su clasificación de Peso</span> relativo. El grosor <span class="wintitle"> Relativo</span> ordena los rasgos recién encontrados en orden de influencia o conveniencia. La escala de ponderación es un porcentaje que se ejecuta entre 0% y 100%. Las características clasificadas más cerca del 100% suponen que son más parecidas a las de la población de línea de base. Consulte <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Explicación de traitweight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Muestra los únicos únicos de 30 días y la población de rasgos total para cada característica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características con modelo</span> </p> </td>
   <td colname="col2"> <p>Muestra una lista de las características algorítmicas basadas en el modelo seleccionado. Haga clic en un nombre de característica o ID de rasgo para obtener más información sobre la característica. Seleccione <b><span class="uicontrol"> Crear nueva característica con modelo</span></b> para ir al proceso de creación de rasgos algorítmicos. </p> <p>La etiqueta de sección cambia según el nombre del modelo. Por ejemplo, supongamos que crea un modelo y lo asigna al Modelo A. Cuando carga la página de resumen, el nombre de esta sección cambia a <span class="wintitle"> Características usando el modelo A</span>. </p> </td>
  </tr>
 </tbody>
</table>