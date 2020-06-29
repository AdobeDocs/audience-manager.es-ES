---
description: En este artículo se describen las convenciones de nomenclatura utilizadas por la variable clave en un par clave-valor.
seo-description: En este artículo se describen las convenciones de nomenclatura utilizadas por la variable clave en un par clave-valor.
seo-title: Requisitos de nombre para variables clave
solution: Audience Manager
title: Requisitos de nombre para variables clave
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---


# Requisitos de nombre para variables clave {#name-requirements-for-key-variables}

En este artículo se describen las convenciones de nomenclatura utilizadas por la variable clave en un par clave-valor.

## Requisitos de nombres para claves

<!-- c_tb_key_name_requirements.xml -->

En [!UICONTROL Expression Builder], el nombre de una variable clave en un par de valor clave puede constar de cualquier número de dígitos seguido de 1 (o más) letras, un guión, un guión bajo y dígitos adicionales.

* Nombres de clave válidos: `price123`, `123price`, `price-123`, `c_price123`.

* Nombres de clave no válidos: `123`, `price!123`.

## Prefijación de variables clave con `c_`

El `c_` prefijo *siempre* es obligatorio si los parámetros que envían datos en una URL de llamada de evento utilizan esa sintaxis.