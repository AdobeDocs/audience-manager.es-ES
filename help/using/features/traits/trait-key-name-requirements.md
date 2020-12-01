---
description: En este artículo se describen las convenciones de nomenclatura utilizadas por la variable clave en un par clave-valor.
seo-description: En este artículo se describen las convenciones de nomenclatura utilizadas por la variable clave en un par clave-valor.
seo-title: Requisitos de nombre para variables clave
solution: Audience Manager
title: Requisitos de nombre para variables clave
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 12%

---


# Requisitos de nombre para variables clave {#name-requirements-for-key-variables}

En este artículo se describen las convenciones de nomenclatura utilizadas por la variable clave en un par clave-valor.

## Requisitos de nombres para claves

<!-- c_tb_key_name_requirements.xml -->

En [!UICONTROL Expression Builder], el nombre de una variable clave en un par de valor clave puede constar de cualquier número de dígitos seguido de 1 (o más) letras, un guión, un guión bajo y dígitos adicionales.

* Nombres de clave válidos: `price123`, `123price`, `price-123`, `c_price123`.

* Nombres de clave no válidos: `123`, `price!123`.

## Prefijo de variables clave con `c_`

El prefijo `c_` es *siempre* requerido si los parámetros que envían datos en una dirección URL de llamada de evento utilizan esa sintaxis.