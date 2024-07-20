---
description: Este artículo describe las convenciones de nomenclatura utilizadas por la variable clave en un par clave-valor.
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: Requisitos de nombre para variables clave
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 0%

---

# Requisitos de nombre para variables clave {#name-requirements-for-key-variables}

Este artículo describe las convenciones de nomenclatura utilizadas por la variable clave en un par clave-valor.

## Requisitos de nomenclatura para claves

<!-- c_tb_key_name_requirements.xml -->

En [!UICONTROL Expression Builder], el nombre de una variable clave en un par clave-valor puede constar de cualquier número de dígitos seguidos de 1 (o más) letras, un guión, un guion bajo y dígitos adicionales.

* Nombres de clave válidos: `price123`, `123price`, `price-123`, `c_price123`.

* Nombres de clave no válidos: `123`, `price!123`.

## Prefijando variables clave con `c_`

El prefijo `c_` es *siempre* necesario si los parámetros que envían datos en una dirección URL de llamada de evento utilizan esa sintaxis.
