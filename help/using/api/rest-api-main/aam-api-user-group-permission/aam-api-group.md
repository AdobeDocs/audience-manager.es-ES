---
description: Métodos API de Rest para administrar grupos, como crear, actualizar, enumerar y eliminar grupos.
seo-description: Métodos API de Rest para administrar grupos, como crear, actualizar, enumerar y eliminar grupos.
seo-title: Métodos API de administración de grupos
solution: Audience Manager
title: Métodos API de administración de grupos
uuid: fe 042 eb 5-ea 12-42 fe-be 98-d 721 f 987 a 914
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Group Management API Methods {#group-management-api-methods}

Rest [!DNL API] methods to manage groups, including creating, updating, listing, deleting groups.

<!-- c_rest_api_user_man_group.xml -->

## Creación de grupos {#create-group}

`POST` Método para crear un nuevo grupo de usuarios.

<!-- r_rest_api_group_create.xml -->

### Solicitud

`POST /api/v1/groups/`

### Cuerpo de solicitud de muestra

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Respuesta

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## Update a Group {#update-group}

`PUT` Método para actualizar un grupo de usuarios.

<!--
r_rest_api_group_update.xml
-->

### Solicitud

`PUT /api/v1/groups/`*`<groupId>`*

### Cuerpo de solicitud de muestra

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Respuesta

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## List Groups {#list-groups}

`GET` Método para enumerar grupos de usuarios.

<!--
r_rest_api_group_list.xml
-->

### Solicitud

`GET /api/v1/groups/`

### Respuesta

```
[
  { 
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }, ...
]
```

## Eliminar un grupo {#delete-groups}

`DELETE` Método para eliminar un grupo de usuarios y eliminar todos los miembros de ese grupo.

<!-- r_rest_api_group_delete.xml -->

### Solicitud

`DELETE /api/v1/groups/`*`<groupId>`*

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## Delete Groups in Bulk {#delete-groups-bulk}

`DELETE` Método para eliminar varios grupos de forma masiva y eliminar todos los miembros de ese grupo.

<!-- r_rest_api_group_delete_bulk.xml -->

### Solicitud

`DELETE /api/v1/groups/bulk-delete`

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## List All Permissions for a Group {#list-permissions-group}

`GET` Método para enumerar los objetos de permisos en un grupo.

<!-- r_rest_api_perm_list_group.xml -->

### Solicitud

`GET /api/v1/groups/{groupId}/permissions`

### Respuesta

```
[{
 "objectId" : 34,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },

{
 "objectId" : "234",
 "objectType": "TRAIT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },
 {
 "objectId" : 277,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "MAP_TO_MODELS"]
 }
]
```

Returns `400 Bad Request` if the group is inaccessible.

## Set Permissions for a Group {#set-permissions-group}

`PUT` Método para actualizar permisos de grupo. Este método sobrescribe los antiguos permisos con los nuevos permisos.

<!-- r_rest_api_perm_set.xml -->

### Solicitud

`PUT /api/v1/groups/{groupId}/permissions/`

### Respuesta

```
[ 
  { "objectType" : "SEGMENT",
    "objectId" : 563,
    "permissions" : [ "READ", "WRITE"]
  },
  { "objectType" : "SEGMENT",
    "objectId" : 2363,
    "permissions" : [ "CREATE", "WRITE"]
  },
  { "objectType" : "TRAIT",
    "objectId" : 83498,
    "permissions" : [ "READ", "MAP_TO_SEGMENTS"]
  },
  { "objectType" : "DESTINATION",
    "objectId" : 304,
    "permissions" : [ "READ", "WRITE", "CREATE"]
  }
]
```

La respuesta de muestra representa la lista actualizada de objetos de permisos.

Returns `200 OK` if successful. Returns `400` if any given permission is invalid. Can also return `403` if the object is not accessible by the logged-in user.