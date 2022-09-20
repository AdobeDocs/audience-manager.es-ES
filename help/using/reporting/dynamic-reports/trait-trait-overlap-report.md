---
description: Devuelve datos sobre el número de usuarios únicos compartidos entre todos los rasgos de origen y de terceros.
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

Devuelve datos sobre el número de usuarios únicos compartidos entre todos los rasgos de origen y de terceros.

>[!NOTE]
>
>Los informes de superposición en el Audience Manager se adhieren a los principios de RBAC. Solo puede ver los rasgos de las fuentes de datos a las que tiene acceso en función de la variable [Grupo de usuarios de RBAC](/help/using/features/administration/administration-overview.md) a la que pertenece.

<!-- 

c_overlap_reports.xml

 -->

## Información general

La variable [!UICONTROL Trait-to-Trait Overlap] devuelve datos sobre el % de usuarios únicos compartidos entre todos sus rasgos y los de terceros. Como herramienta de optimización, este informe le ayuda a:

* Cree segmentos con superposición alta o baja, según sus necesidades. Los rasgos con superposición alta le proporcionan una audiencia segmentada, pero menos visitantes únicos. Los rasgos con baja superposición pueden resultar útiles para alcanzar un conjunto de visitantes único y más grande.
* Validar datos de rasgos de terceros: Una fuerte superposición entre características similares de origen y de terceros sugiere que el rasgo del socio de datos es preciso y fiable. Por el contrario, una superposición baja puede indicar que un rasgo de terceros puede no contener realmente la misma información que su propio rasgo de origen similar.
* Encuentre superposiciones inesperadas entre características y utilice esa información para crear segmentos innovadores.

## Informe de ejemplo

La siguiente ilustración proporciona una descripción general de alto nivel de los elementos del [!UICONTROL Trait-to-Trait Overlap] informe.

>[!NOTE]
>
>La variable [!UICONTROL Trait-to-Trait Overlap] devuelve un campo vacío cuando compara el mismo rasgo con sí mismo.

>[!NOTE]
>
>Los rasgos de carpeta no están disponibles para su comparación en los informes de superposición entre rasgos. Al crear un segmento utilizando un rasgo de carpeta en particular, puede realizar un análisis a través del [informe de superposición de segmento a rasgo](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md).

![](assets/trait-to-trait-overlap.png)

## Explorar en profundidad puntos de datos individuales

Seleccione un punto individual para ver los detalles de los datos en una ventana emergente. Las acciones de clic actualizan automáticamente los datos mostrados en el informe.

## Definición de campos emergentes de datos de solapamiento entre rasgos {#field-definitions}

Describe las métricas mostradas en la ventana emergente cuando se hace clic en un punto de datos individual.

<!-- 

r_t2t_data_pop.xml

 -->

La ventana emergente de la variable [!UICONTROL Trait-to-Trait Overlap] contiene las métricas siguientes. Tenga en cuenta que la métrica Únicos de la tabla representa su *usuarios en tiempo real*.

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
   <td colname="col2"> Muestra el % de superposición única entre características comparadas (superposición de únicos/únicos de características). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo de fuente de datos</span></b> </td> 
   <td colname="col2">Define el tipo de fuente de datos al que pertenece un rasgo. Puede ser: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Origen (su propio rasgo). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terceros (de un socio o proveedor de datos externos). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de rasgo superpuesto</span></b> </td> 
   <td colname="col2"> ID numérica única para el rasgo superpuesto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nombre de rasgo superpuesto</span></b> </td> 
   <td colname="col2"> Nombre del rasgo superpuesto. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de rasgo 2</span></b> </td> 
   <td colname="col2"> ID numérica única para el rasgo en la fuente de datos base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nombre de rasgo 2</span></b> </td> 
   <td colname="col2"> Nombre del rasgo de la fuente de datos base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Superposición de elementos únicos</span></b> </td> 
   <td colname="col2"> <p>Para obtener el porcentaje de superposición, el Audience Manager utiliza la fórmula siguiente:</p> <p>Únicos superpuestos / (Rasgos básicos únicos + Rasgos superpuestos únicos - Únicos superpuestos)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Rasgos únicos superpuestos</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos del rasgo que se superpone. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Rasgos únicos base</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos del rasgo base. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrar los resultados del informe con las barras de desplazamiento de datos](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, colores y tamaños utilizados en informes dinámicos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Iconos de informe y herramientas explicadas](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes de superposición: actualizar programación y tamaño mínimo del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestreo de datos y tasas de error en los informes de Audience Manager seleccionado...](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)

