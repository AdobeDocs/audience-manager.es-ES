---
description: Métodos opcionales que permiten asignar rasgos a un tipo o categoría definidos por el usuario, normalmente según la función o para sus propios procesos internos de creación de informes.
seo-description: Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.
seo-title: Trait Type Methods
solution: Audience Manager
title: Métodos de tipo de rasgo
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
exl-id: d450f9ce-2abb-4a8b-b8db-2962b84fb341
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 3%

---

# Métodos de tipo de rasgo {#trait-type-methods}

Métodos opcionales que permiten asignar rasgos a un tipo o categoría definidos por el usuario, normalmente según la función o para sus propios procesos internos de creación de informes.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Los métodos de tipo de rasgo no asignan rasgos a categorías utilizadas por la [taxonomía común](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). Considere estas etiquetas como si fueran independientes de la taxonomía común.

Para referencia visual, [!UICONTROL Trait Types] es un control desplegable ubicado en [!DNL UI] bajo **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Crear nuevo tipo de rasgo {#create-trait-type}

Un método `POST` que le permite crear un nuevo tipo de rasgo.

<!-- r_rest_api_create_trait_type.xml -->

### Solicitud

`POST https://api.demdex.com/v1/customer-trait-types`

### Solicitud de ejemplo

```
{
"name":"Custom trait type"
}
```

### Respuesta

```
{
    "pixelType": 34,
    "pid": 1099,
    "name": "Custom type",
    "description": null,
    "crUID": 694,
    "upUID": 694,
    "createTime": 1358297352000,
    "updateTime": 1358297352000
}
```

## Devolver propiedades de un tipo de rasgo {#return-props}

Un método `GET` que devuelve detalles sobre el tipo de rasgo especificado.

<!-- r_rest_api_get_trait_type.xml -->

### Solicitud

`GET https://api.demdex.com/v1/customer-trait-types/`*`<customerTraitTypeId>`*

### Respuesta

```
{
    "pixelType": 4,
    "pid": 0,
    "name": "Delivery Event",
    "description": "Delivery Event",
    "crUID": 158,
    "upUID": 158,
    "createTime": 1299115496000,
    "updateTime": 1299115496000
}
```

## Devolver propiedades para todos los tipos de rasgos {#return-props-all}

Un método `GET` que devuelve detalles sobre todos los tipos de rasgos de una matriz.

<!-- r_rest_api_get_trait_types.xml -->

### Solicitud

`GET https://api.demdex.com/v1/customer-trait-types/`

### Respuesta

```
[
    {
        "pixelType": 200,
        "pid": 1099,
        "name": "Customer Specific Trait Type",
        "description": "Test",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1349990458000,
        "updateTime": 1349990458000
    },
    {
        "pixelType": 1,
        "pid": 0,
        "name": "User Trait",
        "description": "User Trait",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115492000,
        "updateTime": 1299115492000
    },
    {
        "pixelType": 2,
        "pid": 0,
        "name": "Site Visitor",
        "description": "Site Visitor",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115493000,
        "updateTime": 1299115493000
    }
]
```
