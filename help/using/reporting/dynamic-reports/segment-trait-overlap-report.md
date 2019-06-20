---
description: Devuelve datos sobre el número de usuarios únicos compartidos entre un rasgo concreto y un segmento completo.
seo-description: Devuelve datos sobre el número de usuarios únicos compartidos entre un rasgo concreto y un segmento completo.
seo-title: Informe de solapamiento entre segmento y característica
solution: Audience Manager
title: Informe de solapamiento entre segmento y característica
uuid: a 6 b 3 dd 21-332 e -449 f-aa 01-2 beb 47 f 1794 e
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# Informe de solapamiento entre segmento y característica{#segment-to-trait-overlap-report}

Devuelve datos sobre el número de usuarios únicos compartidos entre un rasgo concreto y un segmento completo.

>[!NOTE]
>
>Los informes Superponer de Audience Manager respetan los principios RBAC. You can only see segments and traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_segment_trait_overlap.xml

 -->

## Información general

As an optimization tool, the [!UICONTROL Segment to Trait Overlap] reports helps you build highly focused segments or expand segment reach. Por ejemplo, puede crear segmentos y características centrados con superposición alta para llegar a una audiencia concreta. Sin embargo, una gran cantidad de superposición puede significar menos usuarios únicos (menos alcance). Si ejecuta este informe para ayudar a ampliar el alcance eliminando características con un gran segmento de superposición y reemplazándolas por características que tengan menos solapamiento.

### Informe de muestra

The following illustration provides a high-level overview of the [!UICONTROL Segment-to-Trait Overlap] report.

![](assets/segment-to-trait-overlap.png)

### Explorar en profundidad puntos de datos individuales

Seleccione un punto individual para ver los detalles de los datos en una ventana emergente. Las acciones de clic actualizan automáticamente los datos mostrados en el informe.

## Comparing Segments to Traits {#comparing-segments-to-traits}

Describe cómo puede comparar segmentos y características para obtener información significativa de los resultados.

<!-- 

c_compare_s2t.xml

 -->

### Comparación de únicos de características y segmentos: Ejemplo

A primera vista, puede parecer ilógico comparar segmentos con características e intentar sacar conclusiones de los resultados. Después de todo, los segmentos y las características son diferentes, por lo que¿cómo pueden derivarse los datos a partir de elementos dispares? Sin embargo, en este caso no se comparan características ni segmentos, sino la cantidad de visitantes únicos compartidos entre ellos. El recuento de visitantes únicos compartidos proporciona el valor común que hace posible la comparación de segmentos.

El siguiente diagrama ilustra la relación entre un rasgo y el segmento al que pertenece. En este caso, tenemos un rasgo con 10 visitantes y un segmento con 1000 visitantes. Comparten 3 visitantes únicos en común.

![](assets/s2t.png)

El recuento de visitantes únicos es el valor común y constante compartido entre estas clases diferentes de objetos. Como resultado, puede determinar la relación de visitante único entre ellos de la siguiente manera:

* El rasgo comparte el 30% de sus visitantes únicos con el segmento (3/10 = 0,30).
* El segmento comparte el 0,3% de sus visitantes únicos con el rasgo (3/1 000 = 0,003)

### Buscar valor en el segmento en comparaciones de características

Mirar la superposición entre características y segmentos puede ayudarle a calcular el grupo de visitantes total disponible (pronosticando) o encontrar segmentos ineficientes con demasiadas superposiciones.

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
   <td colname="col2"> <p>Para determinar el grupo de visitantes disponible, suma la diferencia entre el total de características (menos solapamiento) y el total del segmento (menos solapamiento). </p> <p>Esta combinación de segmentos puede alcanzar hasta 1004 usuarios nuevos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Buscar segmentos ineficientes</b> </td> 
   <td colname="col2"> <p>If a trait is part of an <span class="wintitle"> AND</span> group in a segment definition, the unique visitors who have that trait are already in the segment and not available for adding to the segment. Puede utilizar este informe para encontrar características relevantes con superposición baja y agregarlas a la definición del segmento, aumentando así el alcance del grupo de audiencias de segmentos. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Understanding the Data Filters in the Segment-to-Trait Overlap Report {#data-filters-s2t-report}

Describe cómo funcionan las características deslizantes % de rasgo y de segmento.

<!-- 

r_s2t_sliders.xml

 -->

[!UICONTROL Segment-to-Trait overlap] El informe permite utilizar dos controles deslizantes para filtrar los datos según el porcentaje de superposición por características o segmentos.

* **[!UICONTROL Filter Trait Uniques %:]** Filtra los datos por el % de visitantes únicos compartidos entre el rasgo y el segmento.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Los datos de filtros por el porcentaje de visitantes únicos comparten entre el segmento y el rasgo.

### Ejemplo

El siguiente diagrama ilustra la diferencia entre los únicos únicos de características % y los únicos del segmento. En este caso, el atributo y el segmento comparten 3 visitantes únicos. Como proporciones:

* El rasgo comparte el 30% de sus visitantes únicos con el segmento (3/10 = 0,30).
* El segmento comparte el 0,3% de sus visitantes únicos con el rasgo (3/1 000 = 0,003)

![](assets/s2t.png)

## Segment-to-Trait Data Pop Fields Defined {#fields-defined}

Describe las métricas mostradas en la ventana emergente al hacer clic en un punto de datos individual.

<!-- 

r_s2t_data_pop.xml

 -->

The popup for the [!UICONTROL Segment-to-Trait Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.

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
   <td colname="col1"><b><span class="wintitle"> Nombre del proveedor de datos</span></b> </td> 
   <td colname="col2"> Nombre del propietario del segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo de proveedor de datos</span></b> </td> 
   <td colname="col2">Define el tipo de proveedor al que pertenece. Puede ser: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Origen (su propio rasgo). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terceros (de un socio o proveedor externo de datos). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> SID</span></b> </td> 
   <td colname="col2"> ID numérico único para el segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nombre del SID</span></b> </td> 
   <td colname="col2"> Nombre del segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Características únicas de características superpuestas</span></b> </td> 
   <td colname="col2"> % de visitantes únicos una característica compartida con el segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Superposición de segmentos únicos %</span></b> </td> 
   <td colname="col2"> % de visitantes únicos que comparten segmentos con un rasgo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Superposición de únicos</span></b> </td> 
   <td colname="col2"> Cantidad de visitantes únicos compartidos entre el segmento y el rasgo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Únicos de segmentos</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos en el segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Únicos únicos</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos en la característica. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Filtrar resultados del informe con los controles deslizantes de datos](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, colores y tamaños utilizados en informes interactivos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explicación de los iconos y las herramientas del informe](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes superpuestos: Actualizar programación y tamaño mínimo de segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestras de datos y tasas de error en informes de Audience Manager seleccionados…](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)