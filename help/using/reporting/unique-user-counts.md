---
description: Describe la variación en totales de usuarios únicos entre informes para el mismo rasgo y período de tiempo.
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: Recuento de usuarios únicos en informes generales y superpuestos
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 12%

---

# Recuento de usuarios únicos en informes generales y superpuestos{#counting-unique-users-in-overlap-and-general-reports}

En esta página se describe la variación en los totales de usuarios únicos entre los informes para el mismo rasgo y período de tiempo.

<!-- 

c_unique_user_counts.xml

 -->

## Informe de superposición: recuento de usuarios únicos

Los informes de superposición cuentan a los usuarios como únicos cuando cumplen los requisitos para una característica:

* Durante el intervalo seleccionado para el informe.
* Que tiene un [tiempo de vida](../features/traits/segment-ttl-explained.md) valor superior al intervalo de tiempo seleccionado para el informe.
* Si se les ve como activos en nuestro sistema (es decir, calificados para cualquier otro rasgo, tenían una sincronización de ID, etc.) en los últimos 60 días.

## Informe general: Recuento de usuarios únicos

El informe General cuenta los visitantes del sitio como únicos si cumplen los requisitos para el rasgo durante el período de tiempo seleccionado.

>[!MORELIKETHIS]
>
>* [Informes interactivos](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Informes generales](../reporting/general-reports.md#general-reports-overview)

