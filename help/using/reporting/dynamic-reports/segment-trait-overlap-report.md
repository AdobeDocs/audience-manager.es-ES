---
description: Devuelve datos sobre el número de usuarios únicos compartidos entre un rasgo en particular y un segmento completo.
seo-description: Devuelve datos sobre el número de usuarios únicos compartidos entre un rasgo en particular y un segmento completo.
seo-title: Informe de solapamiento entre segmento y rasgo
solution: Audience Manager
title: Informe de solapamiento entre segmento y rasgo
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Informes de superposición
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 5%

---

# Informe de solapamiento entre segmento y rasgo{#segment-to-trait-overlap-report}

Devuelve datos sobre el número de usuarios únicos compartidos entre un rasgo en particular y un segmento completo.

>[!NOTE]
>
>Los informes de superposición en el Audience Manager se adhieren a los principios de RBAC. Solo puede ver segmentos y rasgos de orígenes de datos a los que tiene acceso en función del [Grupo de usuarios de RBAC](/help/using/features/administration/administration-overview.md) al que pertenece.

<!-- 

c_segment_trait_overlap.xml

 -->

## Información general

Como herramienta de optimización, los informes [!UICONTROL Segment to Trait Overlap] le ayudan a generar segmentos con un alto enfoque o a expandir el alcance de los segmentos. Por ejemplo, puede crear segmentos y rasgos centrados con una superposición alta para llegar a una audiencia determinada. Sin embargo, muchas superposiciones pueden significar menos usuarios únicos (menos alcance). La ejecución de este informe para ayudar a ampliar el alcance mediante la eliminación de características con mucha superposición de segmentos y su sustitución por características que tienen menos superposición.

### Informe de ejemplo

La siguiente ilustración proporciona información general de alto nivel del informe [!UICONTROL Segment-to-Trait Overlap].

![](assets/segment-to-trait-overlap.png)

### Explorar en profundidad puntos de datos individuales

Seleccione un punto individual para ver los detalles de los datos en una ventana emergente. Las acciones de clic actualizan automáticamente los datos mostrados en el informe.

## Comparación de segmentos con rasgos {#comparing-segments-to-traits}

Describe cómo puede comparar segmentos y características para obtener información relevante de los resultados.

<!-- 

c_compare_s2t.xml

 -->

### Comparación de características y únicas de segmentos: Ejemplo

A primera vista, puede parecer ilógico comparar segmentos con rasgos e intentar sacar conclusiones de los resultados. Después de todo, los segmentos y las características son diferentes, por lo que ¿cómo pueden tener sentido los datos derivados de elementos dispares? Sin embargo, en este caso, no estamos comparando características y segmentos, sino el número de visitantes únicos compartidos entre ellos. El recuento de visitantes únicos compartidos proporciona el valor común que hace posible un segmento para la comparación de características.

El diagrama siguiente ilustra la relación entre un rasgo y el segmento al que pertenece. En este caso, tenemos un rasgo con 10 visitantes y un segmento con 1000 visitantes. Comparten 3 visitantes únicos en común.

![](assets/s2t.png)

El recuento de visitantes únicos es el valor constante común que se comparte entre estas diferentes clases de objetos. Como resultado, puede determinar la relación de visitante único entre ellos de la siguiente manera:

* El rasgo comparte el 30% de sus visitantes únicos con el segmento (3/10 = 0,30).
* El segmento comparte el 0,3% de sus visitantes únicos con el rasgo (3/1.000 = 0,003)

### Buscar valores en comparaciones de segmentos con rasgos

Examinar la superposición entre características y segmentos puede ayudarle a estimar el grupo de visitantes total disponible (previsión) o encontrar segmentos ineficientes con demasiada superposición.

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
   <td colname="col2"> <p>Para determinar el grupo de visitantes disponible, sume la diferencia entre el total de rasgos (menos superposición) y el total del segmento (menos superposición). </p> <p>Esta combinación de rasgos de segmentos podría llegar a 1004 nuevos usuarios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Buscar segmentos ineficientes</b> </td> 
   <td colname="col2"> <p>Si un rasgo es parte de un grupo <span class="wintitle"> AND</span> en una definición de segmento, los visitantes únicos que tienen ese rasgo ya están en el segmento y no están disponibles para agregarlo al segmento. Puede utilizar este informe para encontrar características relevantes con baja superposición y agregarlas a la definición del segmento, aumentando así el alcance de ese grupo de audiencia del segmento. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Explicación de los filtros de datos en el informe de solapamiento entre segmento y característica {#data-filters-s2t-report}

Describe cómo funcionan los controles deslizantes de superposición única de rasgos y segmentos %.

<!-- 

r_s2t_sliders.xml

 -->

El informe [!UICONTROL Segment-to-Trait overlap] permite utilizar dos controles deslizantes para filtrar los datos por el porcentaje de superposición por rasgo o segmento.

* **[!UICONTROL Filter Trait Uniques %:]** Filtra los datos por el % de visitantes únicos compartidos entre el rasgo y el segmento.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtra los datos por el % de visitantes únicos que comparten entre el segmento y la característica.

### Ejemplo

El diagrama siguiente ilustra la diferencia entre los rasgos únicos % y los segmentos únicos %. En este caso, el rasgo y el segmento comparten 3 visitantes únicos. Como proporciones:

* El rasgo comparte el 30% de sus visitantes únicos con el segmento (3/10 = 0,30).
* El segmento comparte el 0,3% de sus visitantes únicos con el rasgo (3/1.000 = 0,003)

![](assets/s2t.png)

## Campos emergentes de datos de segmento a rasgo definidos {#fields-defined}

Describe las métricas mostradas en la ventana emergente cuando se hace clic en un punto de datos individual.

<!-- 

r_s2t_data_pop.xml

 -->

La ventana emergente del informe [!UICONTROL Segment-to-Trait Overlap] contiene las métricas siguientes. Tenga en cuenta que la métrica Únicos de la tabla representa a sus *usuarios en tiempo real*.

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
   <td colname="col2"> ID numérica única para el segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Fuente de datos de características  </span></b> </td> 
   <td colname="col2"> Nombre del propietario del rasgo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo de fuente de datos</span></b> </td> 
   <td colname="col2">Define el tipo de proveedor al que pertenece un rasgo. Puede ser: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Origen (su propio rasgo). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terceros (de un socio o proveedor de datos externos). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de rasgo</span></b> </td> 
   <td colname="col2"> ID numérica única para el rasgo. </td> 
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
   <td colname="col1"><b><span class="wintitle"> Superposición de valores únicos de segmento %</span></b> </td> 
   <td colname="col2"> % de visitantes únicos que un segmento comparte con un rasgo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Superposición de elementos únicos</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos compartidos entre el segmento y la característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Únicos de segmentos</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos en el segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Únicos rasgos</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos en el rasgo. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrar los resultados del informe con las barras de desplazamiento de datos](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, colores y tamaños utilizados en informes interactivos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Iconos de informe y herramientas explicadas](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes de superposición: actualizar programación y tamaño mínimo del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestreo de datos y tasas de error en los informes de Audience Manager seleccionado...](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)

