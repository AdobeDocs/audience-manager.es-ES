---
description: Describe los requisitos de tamaño y tiempo de creación del segmento requeridos por el proceso de actualización del informe de superposición.
seo-description: Describe los requisitos de tamaño y tiempo de creación del segmento requeridos por el proceso de actualización del informe de superposición.
seo-title: Informes de superposición Actualizar programación y tamaño mínimo del segmento
solution: Audience Manager
title: Informes de superposición Actualizar programación y tamaño mínimo del segmento
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Informes de superposición
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 5%

---

# Informes de superposición: actualizar programación y tamaño mínimo del segmento{#overlap-reports-update-schedule-and-minimum-segment-size}

Describe los requisitos de tamaño de rasgo y segmento y tiempo de creación requeridos por el proceso de actualización del informe de superposición.

## Actualizar programación y requisitos {#update-schedule}

[!UICONTROL Overlap] los informes se actualizan semanalmente el domingo. El procesamiento previo del informe comienza el sábado. Esto afecta a cómo aparecen los segmentos nuevos o existentes en un informe de superposición el lunes. Para incluir en un informe de superposición:

* Un segmento debe contener un mínimo de 70 000 usuarios en tiempo real durante los últimos 14 días.
* Un rasgo debe contener 28 000 [realizaciones de rasgos únicas](/help/using/features/traits/trait-and-segment-qualification-reference.md) durante los últimos 14 días.
* Se debe crear un segmento antes de las 12 AM del jueves UTC (2 días completos antes de que comience el proceso de actualización del informe de superposición semanal).
* Su empresa debe ser cliente [!DNL Audience Manager] completo. Póngase en contacto con su asesor de [!DNL Audience Manager] o con el Servicio de atención al cliente para obtener más información.

## El tamaño del segmento o el tiempo de creación afectan a los informes {#segment-size}

Si no ve un segmento en uno de los informes [!UICONTROL Overlap], puede deberse a que el segmento no cumple estos requisitos mínimos.

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
   <td colname="col2"> <p>Supongamos que crea un segmento antes de las 12 AM del jueves UTC, pero contiene menos de 70 000 usuarios totales en tiempo real. Este segmento no aparecerá en un <span class="wintitle"> Informe superpuesto</span> hasta que cumpla los requisitos de umbral del usuario. Tenga en cuenta que el segmento también debe satisfacer el recuento de usuarios requerido antes del período de corte del jueves. Si no cumple la fecha límite semanal, el segmento aparecerá en los <span class="wintitle"> Informes de superposición</span> durante la semana siguiente a la próxima ejecución de los datos del domingo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmento creado demasiado tarde</b> </p> </td> 
   <td colname="col2"> <p>Supongamos que crea un segmento el viernes y contiene más de 70 000 usuarios en tiempo real. Este segmento no aparece en los <span class="wintitle"> informes de superposición</span> para la semana siguiente porque se creó menos de 2 días antes del período de actualización del informe. Sin embargo, el segmento aparecerá en un <span class="wintitle"> Informe superpuesto</span> después de la siguiente actualización semanal. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Informe de solapamiento entre rasgos](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Informe de solapamiento entre segmento y rasgo](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Informe de solapamiento entre segmentos](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

