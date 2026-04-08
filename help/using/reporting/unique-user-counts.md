---
description: Describe la variación en totales de usuarios únicos entre informes para el mismo rasgo y período de tiempo.
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: Recuento de usuarios únicos en informes generales y superpuestos
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
TQID: https://experienceleague.adobe.com/zQamEx1r5buK4Q4FN-meT3l-8-j3f9Q5Kw2RtO0iPQ8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
  - id: ec0be1ae-7ea9-4f62-869a-963a97d2edc1
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 1%

---

# Recuento de usuarios únicos en informes generales y superpuestos{#counting-unique-users-in-overlap-and-general-reports}

En esta página se describe la variación en los totales de usuarios únicos entre los informes para el mismo rasgo y período de tiempo.

<!-- 

c_unique_user_counts.xml

 -->

## Informe de superposición: recuento de usuarios únicos

Los informes de superposición cuentan a los usuarios como únicos cuando cumplen los requisitos para una característica:

* Durante el intervalo seleccionado para el informe.
* Tiene un valor [time-to-live](../features/traits/segment-ttl-explained.md) superior al intervalo de tiempo seleccionado para el informe.
* Si se les ve como activos en nuestro sistema (es decir, cualificados para cualquier otro rasgo, han tenido una sincronización de ID, etc.) en los últimos 60 días.

## Informe general: Recuento de usuarios únicos

El informe General cuenta los visitantes del sitio como únicos si cumplen los requisitos para el rasgo durante el período de tiempo seleccionado.

>[!MORELIKETHIS]
>
>* [Informes interactivos](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Informes generales](../reporting/general-reports.md#general-reports-overview)
