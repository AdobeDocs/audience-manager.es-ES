---
description: Devuelve datos sobre el número de usuarios únicos compartidos entre un rasgo concreto y un segmento completo.
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

Devuelve datos sobre el número de usuarios únicos compartidos entre un rasgo concreto y un segmento completo.

>[!NOTE]
>
>Los informes de superposición de Audience Manager se adhieren a los principios de RBAC. Solo puede ver segmentos y características de orígenes de datos a los que tiene acceso en función del grupo[ de usuarios de ](/help/using/features/administration/administration-overview.md)RBAC al que pertenece.

<!-- 

c_segment_trait_overlap.xml

 -->

## Información general

Como herramienta de optimización, los [!UICONTROL Segment to Trait Overlap] informes ayudan a versión segmentos muy enfocados o a ampliar segmento alcance. Por ejemplo, puede crear segmentos enfocados y características con una superposición alta para alcanzar un audiencia en particular. Sin embargo, mucha superposición puede significar menos usuarios únicos (menos alcance). Ejecutar este informe para ayudar a ampliar el alcance eliminando características con mucha superposición de segmento y reemplazándolas con características que tengan menos superposición.

### Informe de muestra

La ilustración siguiente proporciona información general de alto nivel sobre el [!UICONTROL Segment-to-Trait Overlap] informe.

![](assets/segment-to-trait-overlap.png)

### Profundizar en datos individuales Puntos

Seleccione un punto individual para vista detalles de los datos en una ventana emergente. Las acciones de clic actualizan automáticamente los datos que se muestran en el informe.

## Comparación de segmentos con características {#comparing-segments-to-traits}

Describe cómo comparar segmentos y características para obtener información significativa de los resultados.

<!-- 

c_compare_s2t.xml

 -->

### Comparación de rasgos y segmentos únicos: un ejemplo

A primera vista, puede parecer ilógico comparar segmentos con rasgos e intentar sacar conclusiones de los resultados. Después de todo, los segmentos y las características son diferentes, así que ¿cómo pueden tener significado los datos derivados de elementos dispares? Sin embargo, en este caso, no estamos comparando características y segmentos, sino la cantidad de visitantes únicos compartidos entre ellos. El recuento de visitante único compartidos proporciona el valor común que hace posible una comparación de segmento a rasgos.

En el diagrama siguiente se ilustra la relación entre un rasgo y el segmento al que pertenece. En este caso, tenemos un rasgo con 10 visitantes y un segmento con 1000 visitantes. Comparten 3 visitantes únicos en común.

![](assets/s2t.png)

El recuento de visitante único es el valor común y constante compartido entre estas diferentes clases de objetos. Como resultado, puede determinar la relación visitante único entre ellos de la siguiente manera:

* El rasgo comparte el 30% de sus visitantes únicos con el segmento (3/10 = 0,30).
* El segmento comparte el 0,3% de sus visitantes únicos con el rasgo (3/1.000 = 0,003)

### Comparaciones de Valor en segmentos y características

Observar la superposición entre rasgos y segmentos puede ayudarle a estimar el total disponible visitante grupo (previsión) o encontrar segmentos ineficientes con demasiada superposición.

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
   <td colname="col2"> <p>Para determinar el grupo de visitante disponibles, sume la diferencia entre el total de características (menos superposición) y el total segmento (menos superposición). </p> <p>Esta combinación de segmento y rasgos podría alcanzar hasta 1004 nuevos usuarios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Encuentre segmentos ineficientes</b> </td> 
   <td colname="col2"> <p>Si un rasgo forma parte de un <span class="wintitle"> grupo Y</span> en una definición de segmento, los visitantes únicos que tienen ese rasgo ya están en el segmento y no están disponibles para agregar al segmento. Puede utilizar este informe para encontrar características relevantes con poca superposición y agregarlas a la definición de segmento, aumentando así el alcance de esa segmento audiencia grupo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Explicación de los filtros de datos en el informe de solapamiento entre segmento y característica {#data-filters-s2t-report}

Describe cómo funcionan los deslizadores % de superposición única y segmento rasgo.

<!-- 

r_s2t_sliders.xml

 -->

El [!UICONTROL Segment-to-Trait overlap] informe permite utilizar dos controles deslizantes para filtrar los datos por porcentaje de superposición por característica o segmento.

* **[!UICONTROL Filter Trait Uniques %:]** Filtra los datos por el % de visitantes únicos compartidos entre el rasgo y el segmento.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtra los datos por el % de visitantes únicos que comparten entre el segmento y el rasgo.

### Ejemplo

En el diagrama siguiente se ilustra la diferencia entre el % de características únicas y el segmento % de valores únicos. En este caso, el rasgo y el segmento comparten 3 visitantes únicos. Como proporciones:

* El rasgo comparte el 30% de sus visitantes únicos con el segmento (3/10 = 0,30).
* El segmento comparte el 0,3% de sus visitantes únicos con el rasgo (3/1.000 = 0,003)

![](assets/s2t.png)

## Definición de los campos POP de datos de segmento a característica {#fields-defined}

Describe las métricas que se muestran en la ventana emergente al hacer clic en un punto de datos individual.

<!-- 

r_s2t_data_pop.xml

 -->

La ventana emergente del [!UICONTROL Segment-to-Trait Overlap] informe contiene las métricas a continuación. Tenga en cuenta que los Métrica únicos de la tabla representan a los *usuarios* en tiempo real.

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID del segmento</span></b> </td> 
   <td colname="col2"> ID de numérica único para el segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Origen de datos de características </span></b> </td> 
   <td colname="col2"> Nombre del propietario de rasgos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo de Origen datos</span></b> </td> 
   <td colname="col2">Define el tipo de proveedor al que pertenece un rasgo. Puede ser: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Primera parte (su propio rasgo). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">De terceros (de un socio/proveedor de datos externo). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de rasgo</span></b> </td> 
   <td colname="col2"> ID de numérica única para el rasgo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nombre del rasgo</span></b> </td> 
   <td colname="col2"> Nombre del rasgo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Superposición de características únicas %</span></b> </td> 
   <td colname="col2"> % de visitantes únicos que un rasgo comparte con el segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Porcentaje de solapamiento de segmentos únicos</span></b> </td> 
   <td colname="col2"> % de visitantes únicos que una segmento comparte con un rasgo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Solapamiento de elementos únicos</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos compartidos entre el segmento y el rasgo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segmentos únicos</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos en el segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Características únicas</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos en la característica. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrar los resultados del informe con las barras de desplazamiento de datos](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, colores y tamaños utilizados en interactivo informes](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explicación de los iconos y Herramientas del informe](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes de superposición: actualizar programación y tamaño mínimo del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestreo de datos y tasas de Error en informes Audience Manager seleccionados...](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)
