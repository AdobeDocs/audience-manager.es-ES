---
description: Métodos de API Rest para administrar permisos para objetos y grupos.
seo-description: Métodos de API Rest para administrar permisos para objetos y grupos.
seo-title: Métodos API de administración de permisos
solution: Audience Manager
title: Métodos API de administración de permisos
uuid: 111 d 0 f 92-d 92 c -4 d 4 b-b 0 d 6-10 dd 3 fa 466 ad
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Permissions Management API Methods {#permissions-management-api-methods}

Rest [!DNL API] methods to manage permissions for objects and groups.

<!-- c_rest_api_perm_man.xml -->

## List Available Object Types {#list-object-types}

`GET` Método para enumerar los tipos de objeto disponibles en los que se pueden establecer controles de acceso basados en roles.

<!-- r_rest_api_perm_list.xml -->

### Solicitud

`GET /api/v1/permissionable-object-types/`

### Respuesta

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## List Available Permissions for an Object Type {#list-permissions-object-type}

`GET` Método para enumerar permisos disponibles para un tipo de objeto.

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
>Los tipos de objeto y las SEÑALES DERIVADAS no tienen permisos normales para utilizar. Los controles de estos tipos de objetos se modifican solo con los permisos Todos o Nada de comodines.