---
description: Devuelve datos sobre la cantidad de usuarios únicos compartidos entre todas las características de origen y de terceros.
seo-description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-title: Trait-to-Trait Overlap Report
solution: Audience Manager
title: Informe de solapamiento entre rasgos
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
source-git-commit: 6cc1351c3a84d4d2219f33ef6175f182b9641377
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 7%

---

# Informe de solapamiento entre rasgos{#trait-to-trait-overlap-report}

Devuelve datos sobre la cantidad de usuarios únicos compartidos entre todas las características de origen y de terceros.

>[!NOTE]
>
>Los informes de superposición de Audience Manager se adhieren a los principios de RBAC. Solo puede ver características de fuentes de datos a las que tiene acceso en función de la variable [Grupo de usuarios RBAC](/help/using/features/administration/administration-overview.md) a la que pertenece.

<!-- 

c_overlap_reports.xml

 -->

## Información general

El [!UICONTROL Trait-to-Trait Overlap] devuelve datos sobre el % de usuarios únicos compartidos entre todas las características propias y las de terceros. Como herramienta de optimización, este informe le ayuda a lo siguiente:

* Cree segmentos con una superposición alta o baja, según sus necesidades. Las características con una alta superposición le proporcionan una audiencia segmentada, pero menos visitantes únicos. Las características con poca superposición pueden resultar útiles para llegar a un conjunto de visitantes único y más grande.
* Validar datos de rasgos de terceros: La fuerte superposición entre rasgos de origen y de terceros similares sugiere que el rasgo de su socio de datos es preciso y fiable. Por el contrario, una superposición baja puede indicar que un rasgo de terceros puede no contener realmente la misma información que su propio rasgo de origen similar.
* Encuentre superposición inesperada entre características y utilice esa información para crear segmentos innovadores.

## Informe de muestra

La siguiente ilustración proporciona información general de alto nivel sobre los elementos de la variable [!UICONTROL Trait-to-Trait Overlap] informe.

>[!NOTE]
>
>El [!UICONTROL Trait-to-Trait Overlap] El informe devuelve un campo vacío cuando compara el mismo rasgo consigo mismo.

>[!NOTE]
>
>Las características de carpeta no están disponibles para la comparación en los informes de superposición de características. Si crea un segmento utilizando una característica de carpeta concreta, puede realizar el análisis mediante las variables [informe de superposición de segmento a característica](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md).

![](assets/trait-to-trait-overlap.png)

## Profundizar en puntos de datos individuales

Seleccione un punto individual para ver los detalles de los datos en una ventana emergente. Las acciones de clic actualizan automáticamente los datos mostrados en el informe.

## Campos emergentes de datos de superposición de características definidos {#field-definitions}

Describe las métricas que se muestran en la ventana emergente al hacer clic en un punto de datos individual.

<!-- 

r_t2t_data_pop.xml

 -->

La ventana emergente del [!UICONTROL Trait-to-Trait Overlap] El informe contiene las métricas siguientes. Tenga en cuenta que la métrica exclusivos de la tabla representa su *usuarios en tiempo real*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Superposición %</span></b> </td> 
   <td colname="col2"> Muestra el % de superposición única entre rasgos comparados (superposición de rasgos únicos/rasgos únicos). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo de fuente de datos</span></b> </td> 
   <td colname="col2">Define el tipo de origen de datos al que pertenece un rasgo. Puede ser: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Origen (su propio rasgo). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terceros (de un socio o proveedor de datos externo). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de rasgo superpuesto</span></b> </td> 
   <td colname="col2"> ID numérico único para el rasgo superpuesto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nombre de rasgo superpuesto</span></b> </td> 
   <td colname="col2"> Nombre del rasgo superpuesto. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de rasgo 2</span></b> </td> 
   <td colname="col2"> ID numérico único para el rasgo en la fuente de datos base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nombre de rasgo 2</span></b> </td> 
   <td colname="col2"> Nombre de la característica en la fuente de datos base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Únicos de superposición</span></b> </td> 
   <td colname="col2"> <p>Para obtener el porcentaje de superposición, Audience Manager utiliza la siguiente fórmula:</p> <p>Uniques superpuestos / (Uniques de rasgos base + Uniques de rasgos superpuestos - Uniques superpuestos)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Únicos de rasgos superpuestos</span></b> </td> 
   <td colname="col2"> El número de visitantes únicos del rasgo superpuesto. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Únicos rasgos base</span></b> </td> 
   <td colname="col2"> El número de visitantes únicos desde el rasgo base. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrar los resultados del informe con las barras de desplazamiento de datos](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, colores y tamaños utilizados en los informes dinámicos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Iconos y herramientas de informes explicados](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes de superposición: actualizar programación y tamaño mínimo del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestreo de datos y tasas de error en los informes de Audience Manager seleccionado...](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)

