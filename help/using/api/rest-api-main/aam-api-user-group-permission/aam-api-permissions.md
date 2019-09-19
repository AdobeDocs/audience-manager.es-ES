---
description: Métodos de API de descanso para administrar permisos para objetos y grupos.
seo-description: Métodos de API de descanso para administrar permisos para objetos y grupos.
seo-title: Métodos de API de administración de permisos
solution: Audience Manager
title: Métodos de API de administración de permisos
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Métodos de API de administración de permisos {#permissions-management-api-methods}

Métodos [!DNL API] de descanso para administrar permisos para objetos y grupos.

<!-- c_rest_api_perm_man.xml -->

## Lista de tipos de objetos disponibles {#list-object-types}

Un `GET` método para enumerar los tipos de objeto disponibles en los que se pueden establecer controles de acceso basados en roles.

<!-- r_rest_api_perm_list.xml -->

### Solicitud

`GET /api/v1/permissionable-object-types/`

### Respuesta

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Lista de permisos disponibles para un tipo de objeto {#list-permissions-object-type}

Un `GET` método para enumerar los permisos disponibles para un tipo de objeto.

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