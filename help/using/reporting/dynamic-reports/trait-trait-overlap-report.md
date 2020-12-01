---
description: Devuelve datos sobre el número de usuarios únicos compartidos entre todas las características de origen y de terceros.
seo-description: Devuelve datos sobre el número de usuarios únicos compartidos entre todas las características de origen y de terceros.
seo-title: Informe de solapamiento entre rasgos
solution: Audience Manager
title: Informe de solapamiento entre rasgos
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 8%

---


# Informe de solapamiento entre rasgos{#trait-to-trait-overlap-report}

Devuelve datos sobre el número de usuarios únicos compartidos entre todas las características de origen y de terceros.

>[!NOTE]
>
>Los informes de superposición en Audience Manager se ajustan a los principios de RBAC. Solo puede ver características de orígenes de datos a los que tiene acceso en función del [grupo de usuarios de RBAC](/help/using/features/administration/administration-overview.md) al que pertenece.

<!-- 

c_overlap_reports.xml

 -->

## Información general

El informe [!UICONTROL Trait-to-Trait Overlap] devuelve datos sobre el % de usuarios únicos compartidos entre todas sus características y las de terceros. Como herramienta de optimización, este informe le ayuda a:

* Cree segmentos con superposición alta o baja, según sus necesidades. Las características con alta superposición le proporcionan una audiencia de objetivo, pero menos visitantes únicos. Las características con superposición baja pueden ser útiles para alcanzar un conjunto de visitantes más grande y único.
* Validar datos de características de terceros: Una fuerte superposición entre características similares de origen y de terceros sugiere que la característica de su socio de datos es precisa y confiable. Por el contrario, una superposición baja puede indicar que una característica de terceros puede no contener realmente la misma información que la suya propia, una característica de origen similar.
* Encuentre superposiciones inesperadas entre características y utilice esa información para crear segmentos innovadores.

## Informe de muestra

La siguiente ilustración proporciona una visión general de alto nivel de los elementos del informe [!UICONTROL Trait-to-Trait Overlap].

>[!NOTE]
>
>El informe [!UICONTROL Trait-to-Trait Overlap] devuelve un campo vacío cuando compara la misma característica con sí mismo.

![](assets/trait-to-trait-overlap.png)

## Explorar en profundidad puntos de datos individuales

Seleccione un punto individual para los detalles de los datos de vista en una ventana emergente. Las acciones de clic actualizan automáticamente los datos mostrados en el informe.

## Campos de la ventana emergente de datos de superposición de rasgo a rasgo definidos {#field-definitions}

Describe las métricas que se muestran en la ventana emergente al hacer clic en un punto de datos individual.

<!-- 

r_t2t_data_pop.xml

 -->

La ventana emergente del informe [!UICONTROL Trait-to-Trait Overlap] contiene las métricas siguientes. Tenga en cuenta que la métrica de valores exclusivos de la tabla representa a sus *usuarios en tiempo real*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> % de superposición</span></b> </td> 
   <td colname="col2"> Muestra el porcentaje de superposición única entre características comparadas (superposición de valores únicos/únicos de características). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo de fuente de datos</span></b> </td> 
   <td colname="col2">Define el tipo de origen de datos al que pertenece una característica. Puede ser: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Origen (propio rasgo). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terceros (de un proveedor o socio de datos externo). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sobreposición de ID de características</span></b> </td> 
   <td colname="col2"> ID numérica única para la característica superpuesta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nombre de rasgo superpuesto</span></b> </td> 
   <td colname="col2"> Nombre de la característica superpuesta. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> ID de característica 2</span></b> </td> 
   <td colname="col2"> ID numérica única para la característica en la fuente de datos base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nombre de característica 2</span></b> </td> 
   <td colname="col2"> Nombre de la característica en la fuente de datos base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniones superpuestos</span></b> </td> 
   <td colname="col2"> <p>Para obtener el porcentaje de superposición, Audience Manager utiliza la fórmula siguiente:</p> <p>Únicos superpuestos / (Únicos de características base + Únicos de características superpuestas - Únicos superpuestos)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Características únicas superpuestas</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos de la característica superpuesta. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Únicas características base</span></b> </td> 
   <td colname="col2"> Número de visitantes únicos de la característica base. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrar los resultados del informe con las barras de desplazamiento de datos](../../reporting/dynamic-reports/data-sliders.md)
>* [Formas, colores y tamaños utilizados en informes dinámicos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Iconos y herramientas del informe explicados](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes de superposición: actualizar programación y tamaño mínimo del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestreo de datos y tasas de error en los informes de Audience Manager seleccionado...](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)