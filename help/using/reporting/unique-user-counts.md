---
description: Describe la variación en totales de usuarios únicos entre los informes para el mismo atributo y período de tiempo.
seo-description: Describe la variación en totales de usuarios únicos entre los informes para el mismo atributo y período de tiempo en Adobe Audience Manager.
seo-title: Recuento de usuarios únicos en superposición e informes generales en AAM
solution: Audience Manager
title: Recuento de usuarios únicos en informes superpuestos y generales
uuid: 450 f 6 a 8 c-f 363-43 de-b 2 d 8-0 a 156 f 14 ecae
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Counting Unique Users in Overlap and General Reports{#counting-unique-users-in-overlap-and-general-reports}

Esta página describe la variación en totales de usuarios únicos entre los informes para el mismo atributo y período de tiempo.

<!-- 

c_unique_user_counts.xml

 -->

## Informe Superpuesto: Recuento de usuarios únicos

Los informes de superposición cuentan a los usuarios como únicos cuando cumplen los requisitos para realizar una característica:

* Durante el intervalo de tiempo seleccionado para el informe.
* That has a [time-to-live](../features/traits/segment-ttl-explained.md) value longer than the selected time interval for the report.
* Si se ven como activas en nuestro sistema (es decir, calificado para cualquier otro rasgo, tenían una sincronización de ID, etc.) de los últimos 60 días.

## Informe general: Recuento de usuarios únicos

El informe General cuenta los visitantes del sitio como únicos si se califican para la característica durante el período de tiempo seleccionado.

>[!MORE_ LIKE_ THIS]
>
>* [Informes interactivos](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Informes generales](../reporting/general-reports.md#general-reports-overview)

