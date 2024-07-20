---
description: Devuelve datos sobre la cantidad de usuarios únicos compartidos entre una característica en particular y un segmento completo.
seo-description: Returns data on the number of unique users shared between a particular trait and an entire segment.
seo-title: Segment-to-Trait Overlap Report
solution: Audience Manager
title: Informe de solapamiento entre segmento y característica
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Overlap Reports
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%

---

# Informe de solapamiento entre segmento y característica{#segment-to-trait-overlap-report}

Devuelve datos sobre la cantidad de usuarios únicos compartidos entre una característica en particular y un segmento completo.

>[!NOTE]
>
>Los informes de superposición de Audience Manager se adhieren a los principios de RBAC. Solo puede ver segmentos y características de orígenes de datos a los que tenga acceso en función del [grupo de usuarios RBAC](/help/using/features/administration/administration-overview.md) al que pertenezca.

<!-- 

c_segment_trait_overlap.xml

 -->

## Información general

Como herramienta de optimización, los informes de [!UICONTROL Segment to Trait Overlap] le ayudan a generar segmentos muy centrados o a expandir el alcance de los segmentos. Por ejemplo, puede crear segmentos centrados y rasgos con una alta superposición para llegar a una audiencia determinada. Sin embargo, mucha superposición puede significar menos usuarios únicos (menos alcance). Ejecución de este informe para ampliar el alcance eliminando características con mucha superposición de segmentos y reemplazándolas por características con menos superposición.

### Informe de muestra

La siguiente ilustración proporciona información general de alto nivel sobre el informe [!UICONTROL Segment-to-Trait Overlap].

![](assets/segment-to-trait-overlap.png)

### Profundizar en puntos de datos individuales

Seleccione un punto individual para ver los detalles de los datos en una ventana emergente. Las acciones de clic actualizan automáticamente los datos mostrados en el informe.

## Comparación de segmentos con características {#comparing-segments-to-traits}

Describe cómo se pueden comparar segmentos y características para obtener información significativa de los resultados.

<!-- 

c_compare_s2t.xml

 -->

### Comparación de características y exclusiones de segmentos: un ejemplo

A primera vista, puede parecer ilógico comparar segmentos con rasgos e intentar sacar conclusiones de los resultados. Después de todo, los segmentos y los rasgos son diferentes, así que ¿cómo pueden tener significado los datos derivados de elementos dispares? Sin embargo, en este caso, no se comparan características y segmentos, sino la cantidad de visitantes únicos compartidos entre ellos. La cantidad de visitantes únicos compartidos proporciona el valor común que hace posible la comparación de segmentos y características.

El diagrama siguiente ilustra la relación entre un rasgo y el segmento al que pertenece. En este caso, tenemos un rasgo con 10 visitantes y un segmento con 1000 visitantes. Comparten 3 visitantes únicos en común.

![](assets/s2t.png)

La cantidad de visitantes únicos es el valor constante común que comparten estas diferentes clases de objetos. Como resultado, puede determinar la relación de visitante único entre ellos de la siguiente manera:

* El rasgo comparte el 30 % de sus visitantes únicos con el segmento (3/10 = 0,30).
* El segmento comparte el 0,3 % de sus visitantes únicos con el rasgo (3/1000 = 0,003)

### Buscar valor en las comparaciones de segmento a rasgo

Observar la superposición entre características y segmentos puede ayudarle a estimar el conjunto total de visitantes disponible (previsión) o a encontrar segmentos ineficientes con demasiada superposición.

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Previsión</b> </td> 
   <td colname="col2"> <p>Para determinar el grupo de visitantes disponible, sume la diferencia entre el total de rasgos (menos superposición) y el total de segmentos (menos superposición). </p> <p>Esta combinación de segmento y característica podría llegar a 1004 nuevos usuarios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Buscar segmentos ineficientes</b> </td> 
   <td colname="col2"> <p>Si un rasgo forma parte de un grupo <span class="wintitle"> AND</span> en una definición de segmento, los visitantes únicos que tienen ese rasgo ya están en el segmento y no están disponibles para agregarlos al segmento. Puede utilizar este informe para buscar características relevantes con baja superposición y añadirlas a la definición del segmento, aumentando así el alcance de ese grupo de audiencias del segmento. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Explicación de los filtros de datos en el informe de solapamiento entre segmento y característica {#data-filters-s2t-report}

Describe cómo funcionan los deslizadores % de superposición única de rasgos y segmentos.

<!-- 

r_s2t_sliders.xml

 -->

El informe [!UICONTROL Segment-to-Trait overlap] le permite utilizar dos controles deslizantes para filtrar los datos según el porcentaje de superposición por característica o segmento.

* **[!UICONTROL Filter Trait Uniques %:]** filtra los datos por el % de visitantes únicos compartidos entre el rasgo y el segmento.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** filtra los datos por el % de visitantes únicos que comparten entre el segmento y la característica.

### Ejemplo

El diagrama siguiente ilustra la diferencia entre el porcentaje de valores exclusivos de rasgos y el porcentaje de valores exclusivos de segmentos. En este caso, el rasgo y el segmento comparten 3 visitantes únicos. Como proporciones:

* El rasgo comparte el 30 % de sus visitantes únicos con el segmento (3/10 = 0,30).
* El segmento comparte el 0,3 % de sus visitantes únicos con el rasgo (3/1000 = 0,003)

![](assets/s2t.png)

## Campos emergentes de datos de segmento a característica definidos {#fields-defined}

Describe las métricas que se muestran en la ventana emergente al hacer clic en un punto de datos individual.

<!-- 

r_s2t_data_pop.xml

 -->

La ventana emergente del informe [!UICONTROL Segment-to-Trait Overlap] contiene las métricas siguientes. Tenga en cuenta que la métrica exclusivos de la tabla representa a sus *usuarios en tiempo real*.

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de segmento</span></b> </td> 
   <td colname="col2"> ID numérico único para el segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Source de datos de rasgos </span></b> </td> 
   <td colname="col2"> Nombre del propietario del rasgo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> tipo de Source de datos</span></b> </td> 
   <td colname="col2">Define el tipo de proveedor al que pertenece un rasgo. Puede ser: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Origen (su propio rasgo). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terceros (de un socio o proveedor de datos externo). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID. de rasgo </span></b> </td> 
   <td colname="col2"> ID numérico único para el rasgo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nombre de característica</span></b> </td> 
   <td colname="col2"> Nombre de la característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> superposición de valores exclusivos de rasgos %</span></b> </td> 
   <td colname="col2"> % de visitantes únicos un rasgo comparte con el segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> superposición de valores exclusivos de segmento %</span></b> </td> 
   <td colname="col2"> % de visitantes únicos que un segmento comparte con un rasgo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> valores exclusivos de superposición </span></b> </td> 
   <td colname="col2"> Número de visitantes únicos compartidos entre el segmento y la característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> valores exclusivos de segmento</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos en el segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> rasgos únicos</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos en el rasgo. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrar los resultados del informe con las barras de desplazamiento de datos](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, colores y tamaños utilizados en los informes interactivos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Iconos y herramientas de informe explicados](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes de superposición: actualizar programación y tamaño mínimo del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestreo de datos y tasas de error en los informes de Audience Manager seleccionados...](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)
