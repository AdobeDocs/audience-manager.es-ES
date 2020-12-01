---
description: Devuelve datos sobre el número de usuarios únicos compartidos entre una característica en particular y un segmento completo.
seo-description: Devuelve datos sobre el número de usuarios únicos compartidos entre una característica en particular y un segmento completo.
seo-title: Informe de solapamiento entre segmento y rasgo
solution: Audience Manager
title: Informe de solapamiento entre segmento y rasgo
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 5%

---


# Informe de solapamiento entre segmento y rasgo{#segment-to-trait-overlap-report}

Devuelve datos sobre el número de usuarios únicos compartidos entre una característica en particular y un segmento completo.

>[!NOTE]
>
>Los informes de superposición en Audience Manager se ajustan a los principios de RBAC. Solo puede ver segmentos y características de fuentes de datos a los que tiene acceso en función del [grupo de usuarios de RBAC](/help/using/features/administration/administration-overview.md) al que pertenece.

<!-- 

c_segment_trait_overlap.xml

 -->

## Información general

Como herramienta de optimización, los informes [!UICONTROL Segment to Trait Overlap] le ayudan a generar segmentos muy enfocados o a expandir el alcance de los segmentos. Por ejemplo, puede crear segmentos y características enfocados con una superposición alta para alcanzar una audiencia determinada. Sin embargo, mucha superposición puede significar menos usuarios únicos (menos alcance). Ejecutar este informe para ayudar a expandir el alcance eliminando características con mucha superposición de segmentos y reemplazándolas con características que tienen menos superposición.

### Informe de muestra

La siguiente ilustración proporciona una visión general de alto nivel del informe [!UICONTROL Segment-to-Trait Overlap].

![](assets/segment-to-trait-overlap.png)

### Explorar en profundidad puntos de datos individuales

Seleccione un punto individual para los detalles de los datos de vista en una ventana emergente. Las acciones de clic actualizan automáticamente los datos mostrados en el informe.

## Comparación de segmentos con características {#comparing-segments-to-traits}

Describe cómo puede comparar segmentos y características para obtener información significativa de los resultados.

<!-- 

c_compare_s2t.xml

 -->

### Comparación de características y únicas de segmento: Un ejemplo

A primera vista, puede parecer ilógico comparar segmentos con características e intentar sacar conclusiones de los resultados. Después de todo, los segmentos y las características son diferentes, así que ¿cómo pueden tener sentido los datos derivados de elementos dispares? Sin embargo, en este caso, no estamos comparando características y segmentos, sino el número de visitantes únicos compartidos entre ellos. El recuento de visitantes únicos compartidos proporciona el valor común que hace posible una comparación de segmentos con características.

El diagrama siguiente ilustra la relación entre una característica y el segmento al que pertenece. En este caso, tenemos una característica con 10 visitantes y un segmento con 1000 visitantes. Comparten 3 visitantes únicos en común.

![](assets/s2t.png)

El recuento de visitantes único es el valor común y constante que se comparte entre estas distintas clases de objetos. Como resultado, puede determinar la relación de visitante única entre ellos de la siguiente manera:

* La característica comparte el 30% de sus visitantes únicos con el segmento (3/10 = 0,30).
* El segmento comparte el 0,3% de sus visitantes únicos con la característica (3/1.000 = 0,003)

### Buscar valores en comparaciones de segmentos con características

El observar la superposición entre características y segmentos puede ayudarle a estimar el conjunto total de visitantes disponibles (previsión) o a encontrar segmentos ineficientes con demasiada superposición.

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
   <td colname="col2"> <p>Para determinar el grupo de visitantes disponible, sume la diferencia entre el total de características (menos superposición) y el total del segmento (menos superposición). </p> <p>Esta combinación de rasgos de segmento podría llegar hasta 1004 usuarios nuevos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Buscar segmentos ineficientes</b> </td> 
   <td colname="col2"> <p>Si una característica forma parte de un grupo <span class="wintitle"> AND</span> en una definición de segmento, los visitantes únicos que tienen esa característica ya están en el segmento y no están disponibles para agregarlos al segmento. Puede utilizar este informe para encontrar características relevantes con baja superposición y agregarlas a la definición del segmento, aumentando así el alcance de ese grupo de audiencias de segmentos. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Explicación de los Filtros de datos en el informe Superposición de segmento a rasgo {#data-filters-s2t-report}

Describe cómo funcionan los controles deslizantes % de solapamiento único de rasgo y segmento.

<!-- 

r_s2t_sliders.xml

 -->

El informe [!UICONTROL Segment-to-Trait overlap] permite utilizar dos controles deslizantes para filtrar los datos por el porcentaje de superposición por características o segmento.

* **[!UICONTROL Filter Trait Uniques %:]** Filtros datos por el % de visitantes únicos compartidos entre la característica y el segmento.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtros los datos según el porcentaje de visitantes únicos compartidos entre el segmento y la característica.

### Ejemplo

El siguiente diagrama ilustra la diferencia entre el % de los únicos rasgos y el % de los únicos de segmento. En este caso, la característica y el segmento comparten 3 visitantes únicos. Como proporciones:

* La característica comparte el 30% de sus visitantes únicos con el segmento (3/10 = 0,30).
* El segmento comparte el 0,3% de sus visitantes únicos con la característica (3/1.000 = 0,003)

![](assets/s2t.png)

## Campos emergentes de datos de segmento a rasgo definidos {#fields-defined}

Describe las métricas que se muestran en la ventana emergente al hacer clic en un punto de datos individual.

<!-- 

r_s2t_data_pop.xml

 -->

La ventana emergente del informe [!UICONTROL Segment-to-Trait Overlap] contiene las métricas siguientes. Tenga en cuenta que la métrica de valores exclusivos de la tabla representa a sus *usuarios en tiempo real*.

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
   <td colname="col2"> ID numérica única para el segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Fuente de datos de características  </span></b> </td> 
   <td colname="col2"> Nombre del propietario de la característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo de fuente de datos</span></b> </td> 
   <td colname="col2">Define el tipo de proveedor al que pertenece una característica. Puede ser: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Origen (propio rasgo). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terceros (de un proveedor o socio de datos externo). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de característica</span></b> </td> 
   <td colname="col2"> ID numérica única para la característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nombre de característica</span></b> </td> 
   <td colname="col2"> Nombre del rasgo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Superposición de características únicas %</span></b> </td> 
   <td colname="col2"> % de visitantes únicos que una característica comparte con el segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Superposición de valores únicos de segmento %</span></b> </td> 
   <td colname="col2"> % de visitantes únicos que un segmento comparte con una característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniones superpuestos</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos compartidos entre el segmento y la característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Únicas de segmentos</span></b> </td> 
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
>* [Formas, colores y tamaños utilizados en informes interactivos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Iconos y herramientas del informe explicados](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes de superposición: actualizar programación y tamaño mínimo del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestreo de datos y tasas de error en los informes de Audience Manager seleccionado...](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)