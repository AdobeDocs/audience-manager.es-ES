---
description: Describe el tamaño del segmento y los requisitos de tiempo de creación requeridos por el proceso de actualización del informe de superposición.
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: Programación de actualización de informes de superposición y tamaño mínimo del segmento
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 6%

---

# Informes de superposición: actualizar programación y tamaño mínimo del segmento{#overlap-reports-update-schedule-and-minimum-segment-size}

Describe los requisitos de tamaño de rasgos y segmentos y el tiempo de creación requeridos por el proceso de actualización del informe Superposición.

## Calendario de actualizaciones y requisitos {#update-schedule}

[!UICONTROL Overlap] Los informes de se actualizan semanalmente los domingos. El procesamiento previo del informe comienza el sábado. Esto afecta a cómo aparecen los segmentos nuevos o existentes en un informe de superposición el lunes. Para incluir en un informe de superposición:

* Un segmento debe contener un mínimo de 70 000 usuarios en tiempo real durante los últimos 14 días.
* Un rasgo debe contener 28 000 [realizaciones de rasgos únicos](/help/using/features/traits/trait-and-segment-qualification-reference.md) durante los últimos 14 días.
* Se debe crear un segmento antes de las 00:00 del jueves UTC (2 días completos antes de que comience el proceso semanal de actualización de informes de superposición).
* Su compañía debe ser un [!DNL Audience Manager] cliente. Póngase en contacto con su [!DNL Audience Manager] o al Servicio de atención al cliente para obtener más información.

## El tamaño del segmento o el tiempo de creación afectan a la creación de informes {#segment-size}

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
   <td colname="col1"> <p> <b>Tamaño de segmento demasiado pequeño</b> </p> </td> 
   <td colname="col2"> <p>Supongamos que crea un segmento antes de las 00:00 del jueves UTC, pero contiene menos de 70 000 usuarios en tiempo real totales. Este segmento no aparecerá en un <span class="wintitle"> Informe de superposición</span> hasta que cumpla los requisitos de umbral del usuario. Tenga en cuenta también que el segmento debe cumplir el recuento de usuarios necesario en el período de corte del jueves o antes. Si no cumple la fecha límite semanal, el segmento aparecerá en el <span class="wintitle"> Informes superpuestos</span> para la semana siguiente a la próxima ejecución de datos dominical. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmento creado demasiado tarde</b> </p> </td> 
   <td colname="col2"> <p>Supongamos que crea un segmento el viernes y que contiene más de 70 000 usuarios en tiempo real totales. Este segmento no aparecerá en la <span class="wintitle"> Informes superpuestos</span> para la semana siguiente, ya que se creó menos de dos días antes del período de actualización del informe. Sin embargo, el segmento aparecerá en un <span class="wintitle"> Informe de superposición</span> después de la siguiente actualización semanal. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Informe de solapamiento entre rasgos](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Informe de solapamiento entre segmento y rasgo](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Informe de solapamiento entre segmentos](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

