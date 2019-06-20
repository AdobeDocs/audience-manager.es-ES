---
description: Describe el tamaño de segmento y los requisitos de tiempo de creación requeridos por el proceso de actualización del informe Superposición.
seo-description: Describe el tamaño de segmento y los requisitos de tiempo de creación requeridos por el proceso de actualización del informe Superposición.
seo-title: Informe de superposición de informes y tamaño mínimo de segmento
solution: Audience Manager
title: Informe de superposición de informes y tamaño mínimo de segmento
uuid: 35 c 1 cb 39-e 28 d -4 d 20-88 c 9-5 ff 4 fe 154 e 9 e
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Overlap Reports: Update Schedule and Minimum Segment Size{#overlap-reports-update-schedule-and-minimum-segment-size}

Describe el tamaño de segmento y los requisitos de tiempo de creación requeridos por el proceso de actualización del informe Superposición.

## Update Schedule and Requirements {#update-schedule}

[!UICONTROL Overlap] los informes se actualizan semanalmente el domingo. El procesamiento previo del informe comienza el sábado. Esto afecta a la forma en que los segmentos nuevos o existentes aparecen en un informe superpuesto el lunes. Para incluirse en un informe superpuesto:

* Un segmento debe contener un mínimo de 70.000 usuarios en tiempo real durante los últimos 14 días. Read more about [Minimum Unique Visitor Requirements for Traits and Segments](../../reporting/report-sampling.md#data-sampling-ratio).
* Un segmento debe haberse creado antes del jueves 12 de noviembre de 2010 (2 días completos antes de que comience el proceso de actualización semanal de los informes superpuestos).
* Your company must be a Full [!DNL Audience Manager] customer. Please contact your [!DNL Audience Manager] consultant or Customer Care to find out more.

## Segment Size and/or Creation Time Affects Reporting {#segment-size}

If you do not see a segment in one of the [!UICONTROL Overlap] reports, it may be because the segment does not meet these minimum requirements.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Tamaño del segmento demasiado pequeño</b> </p> </td> 
   <td colname="col2"> <p>Supongamos que crea un segmento antes del jueves 12 de noviembre, pero contiene menos de 70.000 usuarios en tiempo real. This segment won't appear in an <span class="wintitle"> Overlap Report</span> until it meets the user threshold requirements. Asimismo, tenga en cuenta que el segmento debe cumplir el recuento de usuarios requerido, o antes del periodo de corte jueves. If it does not meet the weekly deadline, the segment will appear in the <span class="wintitle"> Overlap Reports</span> for the week after the upcoming Sunday data run. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmento creado demasiado tarde</b> </p> </td> 
   <td colname="col2"> <p>Supongamos que crea un segmento el viernes y contiene más de 70.000 usuarios en tiempo real. This segment won't appear in the <span class="wintitle"> Overlap Reports</span> for the next week because it was created less than 2 days prior to the report update period. However, the segment will appear in an <span class="wintitle"> Overlap Report</span> after the next weekly update. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Informe de solapamiento entre características](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Informe de solapamiento entre segmento y característica](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Informe de solapamiento entre segmentos](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

