---
description: Métodos que permiten ver la taxonomía común de Audience Manager. Este esquema de clasificación opcional organiza características en las categorías estándar del sector.
seo-description: Métodos que permiten ver la taxonomía común de Audience Manager. Este esquema de clasificación opcional organiza características en las categorías estándar del sector.
seo-title: Métodos de la API Taxonomic
solution: Audience Manager
title: Métodos de la API Taxonomic
uuid: 4 ee 29 ba 5-e 9 ba -4498-a 6 ee -7343227 dd 7 ba
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Taxonomic API Methods {#taxonomic-api-methods}

Métodos que permiten ver la taxonomía común de Audience Manager. Este esquema de clasificación opcional organiza características en las categorías estándar del sector.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>No se pueden crear nuevas categorías taxonómicas ni clasificar características con estos métodos. To classify a trait, specify the appropriate `categoryId` with a trait create or update method.

## Return a Specific Taxonomy {#return-specific-taxonomy}

`GET` Método que devuelve detalles sobre la categoría taxonómica especificada.

<!-- r_rest_api_taxonomy.xml -->

### Solicitud

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Respuesta

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist.

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

## Return all Taxonomic Categories {#return-all-taxonomy-categories}

`GET` Método que devuelve una lista de categorías de nivel superior en una matriz.

<!-- r_rest_api_taxonomies.xml -->

### Solicitud

`GET https://api.demdex.com/v1/taxonomies/0/`

### Respuesta

Truncado por brevedad.

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

## Return Taxonomic Sub-Categories {#return-taxonomy-sub-categories}

`GET` Método que devuelve subcategorías para la categoría principal especificada en una matriz.

<!-- r_rest_api_taxonomy_sub.xml -->

### Solicitud

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Respuesta

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist. Truncado por brevedad.

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
