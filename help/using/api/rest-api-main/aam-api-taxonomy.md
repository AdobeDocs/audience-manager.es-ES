---
description: Métodos que permiten ver la taxonomía común del Audience Manager. Este esquema de clasificación opcional organiza los rasgos en categorías estándar del sector.
seo-description: Métodos que permiten ver la taxonomía común del Audience Manager. Este esquema de clasificación opcional organiza los rasgos en categorías estándar del sector.
seo-title: Métodos taxonómicos API
solution: Audience Manager
title: Métodos taxonómicos API
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 8%

---

# Métodos taxonómicos API {#taxonomic-api-methods}

Métodos que permiten ver la taxonomía común del Audience Manager. Este esquema de clasificación opcional organiza los rasgos en categorías estándar del sector.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>No se pueden crear nuevas categorías taxonómicas ni clasificar características con estos métodos. Para clasificar un rasgo, especifique el `categoryId` apropiado con un método de creación o actualización de rasgos.

## Devolver una taxonomía específica {#return-specific-taxonomy}

Un método `GET` que devuelve detalles sobre la categoría taxonómica especificada.

<!-- r_rest_api_taxonomy.xml -->

### Solicitud

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Respuesta

Una respuesta correcta devuelve `200 OK` y la categoría del ID especificado. Una solicitud incorrecta devolverá `404 No Content` si el ID no existe.

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

## Devolver todas las categorías taxonómicas {#return-all-taxonomy-categories}

Método `GET` que devuelve una lista de las categorías de nivel superior de una matriz.

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

## Subcategorías taxonómicas de retorno {#return-taxonomy-sub-categories}

Método `GET` que devuelve subcategorías para la categoría principal especificada en una matriz.

<!-- r_rest_api_taxonomy_sub.xml -->

### Solicitud

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Respuesta

Una respuesta correcta devuelve `200 OK` y la categoría del ID especificado. Una solicitud incorrecta devolverá `404 No Content` si el ID no existe. Truncado para la brevedad.

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
