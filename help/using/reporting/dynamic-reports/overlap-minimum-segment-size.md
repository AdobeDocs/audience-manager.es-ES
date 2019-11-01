---
description: Describe los requisitos de tamaño y tiempo de creación del segmento requeridos por el proceso de actualización del informe de superposición.
seo-description: Describe los requisitos de tamaño y tiempo de creación del segmento requeridos por el proceso de actualización del informe de superposición.
seo-title: Sobreponer informes Actualizar programación y tamaño mínimo del segmento
solution: Audience Manager
title: Sobreponer informes Actualizar programación y tamaño mínimo del segmento
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Informes de superposición: Actualizar programación y tamaño mínimo del segmento{#overlap-reports-update-schedule-and-minimum-segment-size}

Describe los requisitos de tamaño y tiempo de creación del segmento requeridos por el proceso de actualización del informe de superposición.

## Actualizar programación y requisitos {#update-schedule}

[!UICONTROL Overlap] los informes se actualizan semanalmente el domingo. El procesamiento previo del informe comienza el sábado. Esto afecta a cómo aparecen los segmentos nuevos o existentes en un informe de superposición el lunes. Para incluirlo en un informe de superposición:

* Un segmento debe contener un mínimo de 70.000 usuarios en tiempo real durante los últimos 14 días. Obtenga más información sobre los requisitos [mínimos de visitantes únicos para características y segmentos](../../reporting/report-sampling.md#data-sampling-ratio).
* Se debe crear un segmento antes de las 12 AM del jueves UTC (2 días completos antes de que comience el proceso de actualización semanal del informe de superposición).
* Su empresa debe ser cliente [!DNL Audience Manager] completo. Para obtener más información, póngase en contacto con su consultor [!DNL Audience Manager] o con el Servicio de atención al cliente.

## El tamaño del segmento y/o el tiempo de creación afectan a los informes {#segment-size}

Si no ve ningún segmento en uno de los [!UICONTROL Overlap] informes, puede deberse a que el segmento no cumple estos requisitos mínimos.

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
   <td colname="col2"> <p>Supongamos que crea un segmento antes de las 12 AM del jueves UTC, pero contiene menos de 70.000 usuarios en tiempo real. Este segmento no aparecerá en un <span class="wintitle"> informe</span> superpuesto hasta que cumpla los requisitos de umbral del usuario. Además, tenga en cuenta que el segmento debe cumplir el recuento de usuarios requerido o antes del período de corte del jueves. Si no cumple el plazo semanal, el segmento aparecerá en los <span class="wintitle"> informes</span> de superposición durante la semana siguiente a la próxima ejecución de los datos del domingo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmento creado demasiado tarde</b> </p> </td> 
   <td colname="col2"> <p>Supongamos que crea un segmento el viernes y contiene más de 70.000 usuarios en tiempo real. Este segmento no aparecerá en los <span class="wintitle"> informes</span> de superposición para la semana siguiente porque se creó menos de 2 días antes del período de actualización del informe. Sin embargo, el segmento aparecerá en un <span class="wintitle"> informe</span> superpuesto después de la siguiente actualización semanal. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Informe de solapamiento entre características](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Informe de solapamiento entre segmento y característica](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Informe de solapamiento entre segmentos](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

