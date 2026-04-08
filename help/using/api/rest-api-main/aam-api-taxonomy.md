---
description: Métodos que permiten ver la taxonomía común de Audience Manager. Este esquema de clasificación opcional organiza los rasgos por categorías estándar del sector.
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: Métodos taxonómicos API
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
TQID: https://experienceleague.adobe.com/LIHEWvF3t-VNHJEviomvCF-dxE2Jy-BFxBynonvwP3w
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
topic_v2:
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 1%

---

# Métodos taxonómicos API {#taxonomic-api-methods}

Métodos que permiten ver la taxonomía común de Audience Manager. Este esquema de clasificación opcional organiza los rasgos por categorías estándar del sector.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>No se pueden crear nuevas categorías taxonómicas ni clasificar rasgos con estos métodos. Para clasificar un rasgo, especifique el `categoryId` apropiado con un método de creación o actualización de rasgos.

## Devolver una taxonomía específica {#return-specific-taxonomy}

Un método `GET` que devuelve detalles acerca de la categoría taxonómica especificada.

<!-- r_rest_api_taxonomy.xml -->

### Solicitud

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Respuesta

Una respuesta correcta devuelve `200 OK` y la categoría para el identificador especificado. Una solicitud incorrecta devolverá `404 No Content` si el identificador no existe.

```
{
    "crUID": 158,
    "name": "Arts & Entertainment",
    "upUID": 158,
    "description": "Arts & Entertainment",
    "categoryID": 1,
    "parentCategoryID": 0
}
```

## Devuelve todas las categorías taxonómicas {#return-all-taxonomy-categories}

Un método `GET` que devuelve una lista de las categorías de nivel superior de una matriz.

<!-- r_rest_api_taxonomies.xml -->

### Solicitud

`GET https://api.demdex.com/v1/taxonomies/0/`

### Respuesta

Truncado para la brevedad.

```
[
    {
        "crUID": 158,
        "name": "Arts & Entertainment",
        "upUID": 158,
        "description": "Arts & Entertainment",
        "categoryID": 1,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Automotive",
        "upUID": 158,
        "description": "Automotive",
        "categoryID": 2,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Business",
        "upUID": 158,
        "description": "Business",
        "categoryID": 3,
        "parentCategoryID": 0
    }
]
```

## Devolver subcategorías taxonómicas {#return-taxonomy-sub-categories}

Un método `GET` que devuelve subcategorías para la categoría principal especificada en una matriz.

<!-- r_rest_api_taxonomy_sub.xml -->

### Solicitud

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Respuesta

Una respuesta correcta devuelve `200 OK` y la categoría para el identificador especificado. Una solicitud incorrecta devolverá `404 No Content` si el identificador no existe. Truncado para la brevedad.

```
[
    {
        "crUID": 158,
        "name": "Books & Literature",
        "upUID": 158,
        "description": "Books & Literature",
        "categoryID": 25,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Celebrity Fan/Gossip",
        "upUID": 158,
        "description": "Celebrity Fan/Gossip",
        "categoryID": 49,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Fine Art",
        "upUID": 158,
        "description": "Fine Art",
        "categoryID": 72,
        "parentCategoryID": 1
    }
]
```
