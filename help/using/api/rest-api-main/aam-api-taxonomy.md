---
description: Métodos que permiten la vista de la taxonomía común del Audience Manager. Este esquema de clasificación opcional organiza las características en categorías estándar de la industria.
seo-description: Métodos que permiten la vista de la taxonomía común del Audience Manager. Este esquema de clasificación opcional organiza las características en categorías estándar de la industria.
seo-title: Métodos taxonómicos API
solution: Audience Manager
title: Métodos taxonómicos API
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 7%

---


# Métodos taxonómicos API {#taxonomic-api-methods}

Métodos que permiten la vista de la taxonomía común del Audience Manager. Este esquema de clasificación opcional organiza las características en categorías estándar de la industria.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>No puede crear nuevas categorías taxonómicas ni clasificar características con estos métodos. Para clasificar una característica, especifique el `categoryId` apropiado con un método de creación o actualización de características.

## Devolver una taxonomía específica {#return-specific-taxonomy}

Un método `GET` que devuelve detalles sobre la categoría taxonómica especificada.

<!-- r_rest_api_taxonomy.xml -->

### Solicitud

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Respuesta

Una respuesta correcta devuelve `200 OK` y la categoría del ID especificado. Una solicitud incorrecta devuelve `404 No Content` si el ID no existe.

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

## Devolver todas las Categorías taxonómicas {#return-all-taxonomy-categories}

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

## Devolver subCategorías taxonómicas {#return-taxonomy-sub-categories}

Un método `GET` que devuelve subcategorías para la categoría principal especificada en una matriz.

<!-- r_rest_api_taxonomy_sub.xml -->

### Solicitud

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Respuesta

Una respuesta correcta devuelve `200 OK` y la categoría del ID especificado. Una solicitud incorrecta devuelve `404 No Content` si el ID no existe. Truncado para la brevedad.

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
