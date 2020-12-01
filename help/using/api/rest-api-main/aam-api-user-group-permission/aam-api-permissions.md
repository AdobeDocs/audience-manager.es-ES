---
description: Métodos de API de descanso para administrar permisos para objetos y grupos.
seo-description: Métodos de API de descanso para administrar permisos para objetos y grupos.
seo-title: Métodos de API de administración de permisos
solution: Audience Manager
title: Métodos de API de administración de permisos
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 14%

---


# Métodos de API de administración de permisos {#permissions-management-api-methods}

Rest [!DNL API] métodos para administrar permisos para objetos y grupos.

<!-- c_rest_api_perm_man.xml -->

## Tipos de objetos disponibles de lista {#list-object-types}

Un método `GET` para lista de tipos de objeto disponibles en los que se pueden establecer controles de acceso basados en roles.

<!-- r_rest_api_perm_list.xml -->

### Solicitud

`GET /api/v1/permissionable-object-types/`

### Respuesta

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Permisos disponibles de lista para un tipo de objeto {#list-permissions-object-type}

Un método `GET` para lista de los permisos disponibles para un tipo de objeto.

<!-- r_rest_api_perm_list_perms.xml -->

### Solicitud

`GET /api/v1/permissionable-object-types/SEGMENT/`

### Respuesta

```
{ 
 "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ], 
 "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ]
}
```

>[!NOTE]
>
>Los tipos de objeto TAGS y SEÑALES DERIVADAS no tienen permisos regulares para usar. Los controles de estos tipos de objetos se modifican únicamente con los permisos de la tarjeta comodín Todo o Nada.