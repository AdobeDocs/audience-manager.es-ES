---
description: Métodos opcionales que permiten asignar características a un tipo o categoría definida por el usuario, generalmente según la función o para sus propios procesos de sistema de informes internos.
seo-description: Métodos opcionales que permiten asignar características a un tipo o categoría definida por el usuario, generalmente según la función o para sus propios procesos de sistema de informes internos.
seo-title: Métodos de tipo de rasgo
solution: Audience Manager
title: Métodos de tipo de rasgo
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 9%

---


# Métodos de tipo de rasgo {#trait-type-methods}

Métodos opcionales que permiten asignar características a un tipo o categoría definida por el usuario, generalmente según la función o para sus propios procesos de sistema de informes internos.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Los métodos de tipo de característica no asignan características a categorías utilizadas por la [taxonomía común](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). Considérelos como etiquetas separadas de la taxonomía común.

Para referencia visual, [!UICONTROL Trait Types] es un control desplegable ubicado en [!DNL UI] en **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Crear un nuevo tipo de característica {#create-trait-type}

Un método `POST` que permite crear un nuevo tipo de característica.

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

## Propiedades de retorno para un tipo de característica {#return-props}

Un método `GET` que devuelve detalles sobre el tipo de característica especificado.

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

## Propiedades de retorno para todos los tipos de características {#return-props-all}

Un método `GET` que devuelve detalles sobre todos los tipos de características de una matriz.

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
