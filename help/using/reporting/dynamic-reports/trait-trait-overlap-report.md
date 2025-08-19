---
description: Devuelve datos sobre el número de usuarios únicos compartidos entre todas las características de primera y terceros.
seo-description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-title: Trait-to-Trait Overlap Report
solution: Audience Manager
title: Informe de solapamiento entre características
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
source-git-commit: 6cc1351c3a84d4d2219f33ef6175f182b9641377
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# Informe de solapamiento entre características{#trait-to-trait-overlap-report}

Devuelve datos sobre el número de usuarios únicos compartidos entre todas las características de primera y terceros.

>[!NOTE]
>
>Los informes de superposición de Audience Manager se adhieren a los principios de RBAC. Solo puede ver características de orígenes de datos a los que tiene acceso en función del grupo[ de usuarios de ](/help/using/features/administration/administration-overview.md)RBAC al que pertenece.

<!-- 

c_overlap_reports.xml

 -->

## Información general

El [!UICONTROL Trait-to-Trait Overlap] informe devuelve datos sobre el % de usuarios únicos compartidos entre todas sus características y sus terceros características. Como herramienta de optimización, este informe le ayuda a:

* Crear segmentos con una superposición alta o baja, según sus necesidades. Las características con una gran superposición le proporcionan un objetivo audiencia, pero menos visitantes únicos. Las características con poca superposición pueden ser útiles para alcanzar un conjunto visitante único más grande.
* Validar terceros datos de rasgos: la fuerte superposición entre rasgos similares primero y terceros sugiere que el rasgo de su socio de datos es preciso y confiable. Por el contrario, una superposición baja puede indicar que un rasgo terceros puede no contener la misma información que su propio rasgo de origen similar.
* Encuentre una superposición inesperada entre rasgos y utilice esa información para versión segmentos innovadores.

## Informe de muestra

La siguiente ilustración proporciona una descripción general de alto nivel de los elementos del [!UICONTROL Trait-to-Trait Overlap] informe.

>[!NOTE]
>
>El [!UICONTROL Trait-to-Trait Overlap] informe devuelve un campo vacío cuando compara la misma característica consigo mismo.

>[!NOTE]
>
>Carpeta características no están disponibles para la comparación en informes de solapamiento entre características. Al crear una segmento usar una característica de carpeta en particular, puede realizar análisis a través del [informe](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md) de solapamiento de segmento a característica.

![](assets/trait-to-trait-overlap.png)

## Profundizar en datos individuales Puntos

Seleccione un punto individual para vista detalles de los datos en una ventana emergente. Las acciones de clic actualizan automáticamente los datos que se muestran en el informe.

## Datos de solapamiento entre características Definición de campos emergentes {#field-definitions}

Describe las métricas que se muestran en la ventana emergente al hacer clic en un punto de datos individual.

<!-- 

r_t2t_data_pop.xml

 -->

La ventana emergente del [!UICONTROL Trait-to-Trait Overlap] informe contiene las métricas a continuación. Tenga en cuenta que los Métrica únicos de la tabla representan a los *usuarios* en tiempo real.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Solapamiento %</span></b> </td> 
   <td colname="col2"> Muestra el % de superposición única entre rasgos comparados (solapamiento único/rasgos únicos). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo de Origen datos</span></b> </td> 
   <td colname="col2">Define el tipo de fuente de datos al que pertenece un rasgo. Puede ser: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Primera parte (su propio rasgo). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">De terceros (de un socio/proveedor de datos externo). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de rasgo superpuesto</span></b> </td> 
   <td colname="col2"> ID de numérica única para la característica de superposición. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nombre de rasgo superpuesto</span></b> </td> 
   <td colname="col2"> Nombre del rasgo que se superpone. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Id. de rasgo 2</span></b> </td> 
   <td colname="col2"> ID de numérica única para el rasgo en su fuente de datos base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nombre de rasgo 2</span></b> </td> 
   <td colname="col2"> Nombre del rasgo en la fuente de datos base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Solapamiento de elementos únicos</span></b> </td> 
   <td colname="col2"> <p>Para obtener el porcentaje de superposición Audience Manager utiliza la siguiente fórmula:</p> <p>Características únicas superpuestas / (Características básicas únicas + Características superpuestas únicas – Únicas superpuestas)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Características únicas superpuestas</span></b> </td> 
   <td colname="col2"> El número de visitantes únicos de la característica de superposición. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Características únicas de base</span></b> </td> 
   <td colname="col2"> El número de visitantes únicos desde la característica base. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrar los resultados del informe con las barras de desplazamiento de datos](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, colores y tamaños utilizados en los informes dinámicos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explicación de los iconos y Herramientas del informe](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes de superposición: actualizar programación y tamaño mínimo del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestreo de datos y tasas de Error en informes Audience Manager seleccionados...](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)
