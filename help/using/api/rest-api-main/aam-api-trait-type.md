---
description: Métodos opcionales que permiten asignar características a un tipo o categoría definida por el usuario, generalmente según funciones o procesos de informes internos.
seo-description: Métodos opcionales que permiten asignar características a un tipo o categoría definida por el usuario, generalmente según funciones o procesos de informes internos.
seo-title: Métodos de tipo de características
solution: Audience Manager
title: Métodos de tipo de características
uuid: 082931 d 5-457 b -4622-817 b -86303 f 38 c 26 a
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Trait Type Methods {#trait-type-methods}

Métodos opcionales que permiten asignar características a un tipo o categoría definida por el usuario, generalmente según funciones o procesos de informes internos.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Trait type methods do not assign traits to categories used by the [common taxonomy](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). Piense en ellas como etiquetas separadas de la taxonomía común.

For visual reference, [!UICONTROL Trait Types] is a dropdown control located in the [!DNL UI] under **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Create a New Trait Type {#create-trait-type}

`POST` Método que permite crear un nuevo tipo de características.

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

## Return Properties for a Trait Type {#return-props}

`GET` Método que devuelve detalles sobre el tipo de característica especificado.

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

## Return Properties for all Trait Types {#return-props-all}

`GET` Método que devuelve detalles sobre todos los tipos de características en una matriz.

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
