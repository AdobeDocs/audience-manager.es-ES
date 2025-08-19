---
description: Describe los requisitos de tamaño segmento y tiempo de creación requeridos por el proceso de actualización del informe de superposición.
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: Informes superpuestos Actualizar la programación y el tamaño mínimo del segmento
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 3%

---

# Informes superpuestos: Programación de actualización y tamaño mínimo del segmento{#overlap-reports-update-schedule-and-minimum-segment-size}

Describe los requisitos de tamaño y tiempo de creación de características y segmento requeridos por el proceso de actualización del informe de superposición.

## Actualizar calendario y requisitos {#update-schedule}

[!UICONTROL Overlap] Los informes se actualizan semanalmente los domingos. El procesamiento previo de informes comienza el sábado. Esto afecta a la forma en que los segmentos nuevos o existentes aparecen en un informe de superposición el lunes. Para incluir en un informe de superposición:

* Una segmento debe contener un mínimo de 70.000 usuarios en tiempo real durante los últimos 14 días.
* Un rasgo debe contener 28.000 [realizaciones](/help/using/features/traits/trait-and-segment-qualification-reference.md) de rasgos únicos durante los últimos 14 días.
* Se debe haber creado un segmento antes de las 12:00 h del jueves UTC (2 días completos antes de que comience el proceso de actualización del informe de superposición semanal).
* Su compañía debe ser un cliente completo [!DNL Audience Manager] . Para obtener más información, póngase en contacto con su asesor o con el [!DNL Audience Manager] servicio de atención al cliente.

## El tamaño del segmento y/o el tiempo de creación afectan a los informes {#segment-size}

Si no ve un segmento en uno de los [!UICONTROL Overlap] informes, puede deberse a que el segmento no cumple estos requisitos mínimos.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>El tamaño del segmento es demasiado pequeño</b> </p> </td> 
   <td colname="col2"> <p>Supongamos que crea un segmento antes de las 12 a. m. del jueves UTC, pero contiene menos de 70,000 usuarios en tiempo real en total. Este segmento no aparecerá en un <span class="wintitle"> informe</span> de superposición hasta que cumpla los requisitos umbral de usuario. Tenga en cuenta, además, que el segmento debe cumplir con los requisitos usuario contar en, o antes, el período de corte del jueves. Si no cumple con la fecha límite semanal, la segmento aparecerá en los <span class="wintitle"> informes</span> de superposición de la semana siguiente a la ejecución de los datos del próximo domingo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmento creado demasiado tarde</b> </p> </td> 
   <td colname="col2"> <p>Supongamos que crea una segmento el viernes y contiene más de 70.000 usuarios en tiempo real en total. Este segmento no aparecerá en los <span class="wintitle"> informes</span> de superposición de la semana siguiente porque se creó menos de 2 días antes del período de actualización del informe. Sin embargo, la segmento aparecerá en un <span class="wintitle"> informe</span> de superposición después de la próxima actualización semanal. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Informe de solapamiento entre rasgos](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Informe de solapamiento entre segmento y rasgo](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Informe de solapamiento entre segmentos](../../reporting/dynamic-reports/segment-segment-overlap-report.md)
