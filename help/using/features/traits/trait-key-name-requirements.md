---
description: Este artículo describe las convenciones de nomenclatura utilizadas por la variable clave en un par clave-valor.
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: Requisitos de nombre para variables clave
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
TQID: https://experienceleague.adobe.com/OEw-vhgEQtUfiyA4FzKp7rnxeFOZh2nL3r1-YudPAhc
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2: id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 105
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
