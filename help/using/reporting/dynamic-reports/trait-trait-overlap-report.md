---
description: Devuelve datos sobre el número de usuarios únicos compartidos entre todas las características de origen y de terceros.
seo-description: Devuelve datos sobre el número de usuarios únicos compartidos entre todas las características de origen y de terceros.
seo-title: Informe de solapamiento entre características
solution: Audience Manager
title: Informe de solapamiento entre características
uuid: 7 fb 3 fc 9 e -0 e 0 b -492 a -9 c 3 a -04356 afb 19 c 7
translation-type: tm+mt
source-git-commit: 4dc8aad623198cbc24c5c76ac3818d7ee00e9a5e

---


# Informe de solapamiento entre características{#trait-to-trait-overlap-report}

Devuelve datos sobre el número de usuarios únicos compartidos entre todas las características de origen y de terceros.

>[!NOTE]
>
>Los informes Superponer de Audience Manager respetan los principios RBAC. You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_overlap_reports.xml

 -->

## Información general

The [!UICONTROL Trait-to-Trait Overlap] report returns data on the % of unique users shared between all your own traits and your third-party traits. Como herramienta de optimización, este informe le ayuda a:

* Cree segmentos con superposición alta o baja, según sus necesidades. Las características con superposición alta proporcionan una audiencia segmentada, pero menos visitantes únicos. Las características con superposición baja pueden resultar útiles para alcanzar un conjunto de visitantes único y más grande.
* Validar los datos de características de terceros: La fuerte superposición entre características similares de origen y de terceros sugiere que la característica del socio de datos es precisa y fiable. Por el contrario, la superposición baja puede indicar que una característica de terceros puede no contener la misma información que su propio rasgo de origen similar.
* Encuentre superposición inesperada entre características y utilice esa información para crear segmentos innovadores.

## Informe de muestra

The following illustration provides a high-level overview of elements in the [!UICONTROL Trait-to-Trait Overlap] report.

>[!NOTE]
>
>[!UICONTROL Trait-to-Trait Overlap] El informe devuelve un campo vacío cuando compara el mismo rasgo consigo mismo.

![](assets/trait-to-trait-overlap.png)

## Explorar en profundidad puntos de datos individuales

Seleccione un punto individual para ver los detalles de los datos en una ventana emergente. Las acciones de clic actualizan automáticamente los datos mostrados en el informe.

## Trait-to-Trait Overlap Data Pop Fields Defined {#field-definitions}

Describe las métricas mostradas en la ventana emergente al hacer clic en un punto de datos individual.

<!-- 

r_t2t_data_pop.xml

 -->

The popup for the [!UICONTROL Trait-to-Trait Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nombre del proveedor de datos</span></b> </td> 
   <td colname="col2"> Nombre del propietario de características. </td> 
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
   <td colname="col1"><b><span class="wintitle"> ID de característica</span></b> </td> 
   <td colname="col2"> ID numérico único para esa característica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nombre de característica</span></b> </td> 
   <td colname="col2"> Nombre del atributo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Superposición %</span></b> </td> 
   <td colname="col2"> Muestra el % de superposición única entre características comparadas (superposición de únicos únicos/características únicos). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Superposición de únicos</span></b> </td> 
   <td colname="col2"> <p>Para obtener el porcentaje de superposición %, Audience Manager utiliza la fórmula siguiente:</p> <p>Superposición de únicos/(únicos de segmento base + únicos de segmentos solapados - Superposición de únicos)</p> </td> 
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
>* [Formas, colores y tamaños utilizados en los informes dinámicos](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explicación de los iconos y las herramientas del informe](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Informes superpuestos: Actualizar programación y tamaño mínimo de segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Muestras de datos y tasas de error en informes de Audience Manager seleccionados…](../../reporting/report-sampling.md)
>* [Archivos CSV para informes superpuestos](../../reporting/dynamic-reports/overlap-csv-files.md)