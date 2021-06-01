---
description: Describe la variación en los totales de usuarios únicos entre los informes para el mismo rasgo y período de tiempo.
seo-description: Describe la variación en los totales de usuarios únicos entre los informes para el mismo rasgo y período de tiempo en Adobe Audience Manager
seo-title: Recuento de usuarios únicos en informes generales y superpuestos en AAM
solution: Audience Manager
title: Recuento de usuarios únicos en informes generales y superpuestos
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Referencia de informes
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 10%

---

# Recuento de usuarios únicos en informes generales y superpuestos{#counting-unique-users-in-overlap-and-general-reports}

Esta página describe la variación en los totales de usuarios únicos entre los informes para el mismo rasgo y período de tiempo.

<!-- 

c_unique_user_counts.xml

 -->

## Informe de superposición: Recuento de usuarios único

Los informes de superposición cuentan a los usuarios como únicos cuando cumplen los requisitos para un rasgo:

* Durante el intervalo de tiempo seleccionado para el informe.
* Tiene un valor [time-to-live](../features/traits/segment-ttl-explained.md) mayor que el intervalo de tiempo seleccionado para el informe.
* Si se ven como activos en nuestro sistema (es decir, calificados para cualquier otro rasgo, con una sincronización de ID, etc.) en los últimos 60 días.

## Informe general: Recuento de usuarios único

El informe General cuenta a los visitantes del sitio como únicos si cumplen los requisitos para el rasgo durante el período de tiempo seleccionado.

>[!MORELIKETHIS]
>
>* [Informes interactivos](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
* [Informes generales](../reporting/general-reports.md#general-reports-overview)

