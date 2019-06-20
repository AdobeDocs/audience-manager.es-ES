---
description: Este artículo describe las convenciones de nomenclatura utilizadas por la variable clave en un par clave-valor.
seo-description: Este artículo describe las convenciones de nomenclatura utilizadas por la variable clave en un par clave-valor.
seo-title: Requisitos de nombre para variables clave
solution: Audience Manager
title: Requisitos de nombre para variables clave
uuid: fa 72 e 732-895 d -4 cf 6-bea 0-66 b 404 c 2 b 059
translation-type: tm+mt
source-git-commit: bdbc2525a13eb04898b0a844ba478cde07e83252

---


# Name Requirements for Key Variables {#name-requirements-for-key-variables}

Este artículo describe las convenciones de nomenclatura utilizadas por la variable clave en un par clave-valor.

## Requisitos de nomenclatura para claves

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder], the name of a key variable in a key-value pair can consist of any number of digits followed by 1 (or more) letters, a dash, an underscore, and additional digits.

* Valid key names: `price123`, `123price`, `price-123`, `c_price123`.

* Invalid key names: `123`, `price!123`.

## Prefixing Key Variables with `c_`

The `c_` prefix is *always* required if the parameters that send in data on an event call URL use that syntax.