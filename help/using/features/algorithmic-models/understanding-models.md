---
description: Cree y administre las características o segmentos utilizados en el modelado similar.
keywords: relative weight, lookalike
seo-description: Cree y administre las características o segmentos utilizados en el modelado similar.
seo-title: Acerca del modelado similar a la apariencia
solution: Audience Manager
title: Acerca del modelado similar a la apariencia
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1590'
ht-degree: 1%

---


# Explicación [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Buscar nuevos usuarios con [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] ayuda a descubrir nuevas audiencias únicas mediante la análisis automatizada de datos. El proceso inicio cuando se selecciona un [!UICONTROL trait] o, un intervalo de tiempo, y un intervalo de tiempo, y de origen y de terceros [!UICONTROL segment][!UICONTROL data sources]. Las opciones proporcionan las entradas para el modelo algorítmico. Cuando se ejecuta el proceso de análisis, busca usuarios elegibles en función de las características compartidas de la población seleccionada. Una vez finalizados, estos datos están disponibles en el [generador](../../features/traits/about-trait-builder.md) de rasgos, donde puede utilizarlos para crear características basadas en la [precisión y el alcance](../../features/traits/trait-accuracy-reach.md). Además, puede crear segmentos que combinen características algorítmicas con [!UICONTROL rules-based traits] y agregar otros requisitos de cualificación con [!DNL Boolean] expresiones y operadores de comparación. [!UICONTROL Look-Alike Modeling] proporciona una forma dinámica de extraer valor de todos los datos de características disponibles.

## Ventajas {#advantages}

Los principales beneficios de usar [!UICONTROL Look-Alike Modeling] incluyen:

* **Precisión de los datos:** El algoritmo se ejecuta regularmente, lo que ayuda a mantener los resultados actualizados y relevantes.
* **Automatización:** No es necesario administrar un gran conjunto de reglas estáticas. El algoritmo encontrará audiencias para usted.
* **Ahorre tiempo y reduzca el esfuerzo:** Con nuestro proceso de modelado no tienes que adivinar qué [!UICONTROL traits]/[!UICONTROL segments] puede funcionar o dedicar recursos de tiempo a campañas para descubrir nuevas audiencias. El modelo puede hacer esto por usted.
* **Fiabilidad:** El modelado funciona con procesos de detección y calificación del lado del servidor que evalúan sus propios datos y los datos de terceros seleccionados a los que tiene acceso. Esto significa que no tiene que ver los visitantes en su sitio para calificarlos para una característica.

## Flujo de trabajo {#workflow}

Los modelos se administran en **[!UICONTROL Audience Data > Models]**. En un nivel superior, el proceso de flujo de trabajo incluye lo siguiente:

* Seleccione los datos de línea de base que desee que evalúe el algoritmo. Esto incluye un intervalo de tiempo [!UICONTROL trait] o [!UICONTROL segment], y [!UICONTROL data sources] (sus propios datos y datos de terceros a los que ya tiene acceso mediante [!DNL Audience Manager]). En el flujo de trabajo de creación de modelos, puede excluir el [!UICONTROL traits] que no desee que interfiera con el modelo.
* Guarde el modelo. Una vez guardado, el proceso de evaluación algorítmica se ejecuta automáticamente. Sin embargo, tenga en cuenta que este proceso puede tardar hasta 7 días en completarse. [!DNL Audience Manager] le envía un mensaje de correo electrónico cuando el algoritmo ha finalizado y los resultados están disponibles para [!UICONTROL trait] su creación.
* Genere algoritmos [!UICONTROL traits] en [!UICONTROL Trait Builder].
* Combinar [!UICONTROL traits] en [!UICONTROL segments] en [!UICONTROL Segment Builder].
* Cree y envíe [!UICONTROL segment] datos a un [!UICONTROL destination].

## Resolución de problemas {#troubleshooting}

Desactivamos cualquier [!UICONTROL Look-Alike Model] que no pueda generar datos para tres ejecuciones consecutivas. Tenga en cuenta que no puede volver a activar el estado del modelo posteriormente. Para garantizar que los modelos generen datos, le recomendamos que cree modelos a partir de fuentes de datos con suficiente [!UICONTROL traits] para acumular datos.

## Explicación [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] es un algoritmo propietario diseñado para descubrir nuevos [!UICONTROL traits] automáticamente. Compara [!UICONTROL trait] los datos actuales [!UICONTROL traits] y [!UICONTROL segments] con todos los demás datos de origen y de terceros a los que tiene acceso [!DNL Audience Manager]. Consulte esta sección para ver una descripción del proceso de detección [!UICONTROL TraitWeight] algorítmica.

![](assets/algo_model.png)

Los pasos siguientes describen el proceso de [!UICONTROL TraitWeight] evaluación.

### Paso 1: Generar una línea de base para la [!UICONTROL Trait] comparación

Para generar una línea base, [!UICONTROL TraitWeight] mide toda la [!UICONTROL traits] asociada con una audiencia para un intervalo de 30, 60 ó 90 días. Luego, se clasifica [!UICONTROL traits] según su frecuencia y correlación. El recuento de frecuencias mide la comunidad. La correlación mide la probabilidad de [!UICONTROL trait] estar presente únicamente en la audiencia de base. [!UICONTROL Traits] que aparecen a menudo se dice que exhiben una alta generalidad, una característica importante utilizada para establecer una puntuación ponderada cuando se combina con [!UICONTROL traits] descubierta en la [!UICONTROL data sources].

### Paso 2: Buscar lo mismo [!UICONTROL Traits] en la [!UICONTROL Data Source]

Después de crear una línea de base para la comparación, el algoritmo busca lo mismo [!UICONTROL traits] en la [!UICONTROL data sources]. En este paso, [!UICONTROL TraitWeight] realiza un recuento de frecuencia de todos los detectados [!UICONTROL traits] y los compara con la línea base. Sin embargo, a diferencia de la línea base, las poco comunes [!UICONTROL traits] se clasifican más que las que aparecen con más frecuencia. Se dice que [!UICONTROL traits] son raras las que muestran un alto grado de especificidad. [!UICONTROL TraitWeight] evalúa las combinaciones de línea base común [!UICONTROL traits] y poco frecuentes (altamente específicas) [!UICONTROL data source][!UICONTROL traits] como más influyentes o deseables que [!UICONTROL traits] comunes a ambos conjuntos de datos. De hecho, nuestro modelo reconoce estas grandes características comunes [!UICONTROL traits] y no asigna prioridad excesiva a los conjuntos de datos con correlaciones altas. Raros [!UICONTROL traits] obtienen una prioridad mayor porque tienen más probabilidades de representar a usuarios nuevos y únicos que [!UICONTROL traits] con una gran cantidad de elementos comunes en todos los ámbitos.

### Paso 3: Asignar Peso

En este paso, [!UICONTROL TraitWeight] clasificaciones recién descubiertas [!UICONTROL traits] en orden de influencia o deseabilidad. La escala de pesos es un porcentaje que va del 0 % al 100 %. [!UICONTROL Traits] clasificado cerca del 100% significa que son más como la audiencia en la población basal. Además, [!UICONTROL traits] son valiosos porque representan usuarios nuevos y únicos que pueden comportarse de manera similar a la audiencia de línea de base establecida. Recuerde, [!UICONTROL TraitWeight] considera que [!UICONTROL traits] la gran cantidad de elementos comunes en la base de referencia y la alta especificidad en las fuentes de datos comparadas son más valiosas que [!UICONTROL traits] comunes en cada conjunto de datos.

### Paso 4: Usuarios con puntuación

A cada usuario seleccionado [!UICONTROL data sources] se le asigna una puntuación de usuario que es igual a la suma de todos los pesos del influyente [!UICONTROL traits] en el perfil de ese usuario. Las puntuaciones del usuario se normalizan entre 0 y 100%.

### Paso 5: Mostrar y trabajar con resultados

[!DNL Audience Manager] muestra los resultados del modelo ponderado en [!UICONTROL Trait Builder]. Cuando desee crear un [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] le permite crear [!UICONTROL traits] basándose en la puntuación ponderada generada por el algoritmo durante una ejecución de datos. Puede elegir una precisión mayor para calificar solo a los usuarios con puntuaciones de usuario muy altas y, por lo tanto, son muy similares a la audiencia de línea de base, en lugar de al resto de la audiencia. Si desea alcanzar una audiencia mayor (alcance), puede reducir la precisión.

### Paso 6: Volver a evaluar la importancia de un [!UICONTROL Trait] ciclo de procesamiento

Periódicamente, [!UICONTROL TraitWeight] reevalúa la importancia de un [!UICONTROL trait] producto basado en el tamaño y el cambio de la población de ese [!UICONTROL trait]. Esto sucede a medida que el número de usuarios cualificados para ello [!UICONTROL trait] aumenta o disminuye con el tiempo. Este comportamiento se ve más claramente en rasgos que se vuelven muy grandes. Por ejemplo, supongamos que el algoritmo utiliza [!UICONTROL trait A] para modelar. A medida que la población de [!UICONTROL trait A] aumenta, [!UICONTROL TraitWeight] vuelve a evaluar la importancia de eso [!UICONTROL trait] y puede asignar una puntuación más baja o ignorarla. En este caso, [!UICONTROL trait A] es demasiado común o grande para decir algo significativo sobre su población. Después de [!UICONTROL TraitWeight] reducir el valor de [!UICONTROL trait A] (o ignorarlo en el modelo), la población de la característica algorítmica disminuye. La lista de factores influyentes [!UICONTROL traits] refleja la evolución de la población de referencia. Utilice la lista del influyente [!UICONTROL traits] para comprender por qué se producen estos cambios.

Vínculos relacionados:

* [Generador de modelos](../../features/algorithmic-models/create-model.md)
* [Precisión y alcance](../../features/traits/trait-accuracy-reach.md)

## Actualizar programación para [!UICONTROL Look-Alike Models] y [!UICONTROL Traits] {#update-schedule}

Creación y actualización de programas para nuevos [!UICONTROL algorithmic models] y existentes y [!UICONTROL traits].

### [!UICONTROL Look-Alike Model] Programa de creación y actualización

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
   <td colname="col2"> <p>Para los [!Modelos con apariencia similar de UICONTROL] nuevos o clonados, el proceso de creación se ejecuta una vez al día en: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (noviembre - marzo) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 6 PM EDT (marzo - noviembre) </li> 
     </ul> </p> <p>Los modelos creados o clonados después de la fecha límite de creación se procesan al día siguiente. </p> <p>Si la primera ejecución de un modelo no genera datos, se ejecutará por segunda vez, al día siguiente. Si el segundo intento tampoco genera datos, habrá un tercer intento, al día siguiente. El modelo dejará de ejecutarse si el tercer intento tampoco genera datos. En este caso, desactivaremos el modelo. Consulte más información en <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Resolución de problemas de modelos</a>similares. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Actualizar un modelo</b> </td> 
   <td colname="col2"> <p>En condiciones ideales, los modelos existentes se ejecutan en días de semana, al menos una vez cada 7 días. Por ejemplo, si crea un modelo (antes de la fecha límite) el lunes, se actualizará el lunes siguiente a más tardar. </p> <p>Un modelo se volverá a ejecutar si cumple cualquiera de las siguientes condiciones: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Su última ejecución no tuvo éxito. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Se ha ejecutado correctamente antes Y no se ha ejecutado en absoluto en los últimos 7 días Y el modelo tiene al menos una característica activa conectada a él. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] Programa de creación y actualización

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

## Vista de Lista de modelos {#models-list-view}

La vista de lista es un espacio de trabajo central que le ayuda a crear, revisar y administrar modelos.

La página [!UICONTROL Models] lista contiene funciones y herramientas que le ayudan a:

* Cree nuevos modelos.
* Administre modelos existentes (editar, pausar, eliminar o clonar).
* Busque modelos por nombre.
* Crear [!UICONTROL algorithmic traits] con cualquier modelo determinado.

## Vista de resumen de modelos {#models-summary-view}

La página de resumen muestra los detalles del modelo, tales como nombre, alcance/precisión, historial de procesamiento y [!UICONTROL traits] creados a partir del modelo. La página también incluye opciones que le permiten crear y administrar modelos. Haga clic en un nombre de modelo de la lista de resumen para ver sus detalles.

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
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Lista los 50 rasgos influyentes principales que mejor se representan en la población base del modelo. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Clasifica cada característica en orden de su <span class="wintitle"> clasificación de Peso</span> Relativo. El <span class="wintitle"> Peso</span> Relativo ordena los rasgos recién descubiertos en orden de influencia o deseabilidad. La escala de pesos es un porcentaje que va del 0 % al 100 %. Las características clasificadas cerca del 100% significan que son más como la audiencia en la población basal. Consulte <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Explicación de TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Muestra los únicos de 30 días y la población total de características de cada característica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Características con modelo</span> </p> </td>
   <td colname="col2"> <p>Muestra una lista de las características algorítmicas en función del modelo seleccionado. Haga clic en un nombre de característica o en un ID de característica para obtener más información sobre la característica. Seleccione <b><span class="uicontrol"> Crear nueva característica con modelo</span></b> para ir al proceso de creación de características algorítmicas. </p> <p>La etiqueta de sección cambia según el nombre del modelo. Por ejemplo, supongamos que crea un modelo y lo denomina Modelo A. Al cargar la página de resumen, el nombre de esta sección se cambia a <span class="wintitle"> Características con el modelo A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinos ](../../features/destinations/destinations.md)
>* [Rasgos ](../../features/traits/trait-details-page.md)
>* [Segmentos ](../../features/segments/segments-purpose.md)

