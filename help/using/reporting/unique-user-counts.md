---
description: Describe la variación en los totales de usuarios únicos entre los informes para el mismo rasgo y período de tiempo.
seo-description: Describe la variación en los totales de usuarios únicos entre los informes para el mismo rasgo y período de tiempo en Adobe Audience Manager
seo-title: Recuento de usuarios únicos en superposiciones e informes generales en AAM
solution: Audience Manager
title: Recuento de usuarios únicos en informes generales y superpuestos
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 10%

---


# Recuento de usuarios únicos en informes generales y superpuestos{#counting-unique-users-in-overlap-and-general-reports}

Esta página describe la variación en los totales de usuarios únicos entre los informes para el mismo rasgo y período de tiempo.

<!-- 

c_unique_user_counts.xml

 -->

## Informe de superposición: Recuento de usuarios únicos

Los informes de superposición cuentan a los usuarios como únicos cuando cumplen los requisitos para una característica:

* Durante el intervalo de tiempo seleccionado para el informe.
* Tiene un valor [tiempo de vida](../features/traits/segment-ttl-explained.md) mayor que el intervalo de tiempo seleccionado para el informe.
* Si son vistos como activos en nuestro sistema (es decir, calificados para cualquier otra característica, con una sincronización de ID, etc.) en los últimos 60 días.

## Informe general: Recuento de usuarios únicos

El informe General cuenta los visitantes del sitio como únicos si cumplen los requisitos para el rasgo durante el período de tiempo seleccionado.

>[!MORELIKETHIS]
>
>* [Informes interactivos](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Informes generales](../reporting/general-reports.md#general-reports-overview)

