---
description: Métodos de API de REST para administrar grupos, incluida la creación, actualización, listado y eliminación de grupos.
seo-description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-title: Group Management API Methods
solution: Audience Manager
title: Métodos de API de administración de grupos
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 5%

---

# Métodos de API de administración de grupos {#group-management-api-methods}

Métodos de descanso [!DNL API] para administrar grupos, incluida la creación, actualización, listado y eliminación de grupos.

<!-- c_rest_api_user_man_group.xml -->

## Creación de grupos {#create-group}

Un `POST` método para crear un nuevo grupo de usuarios.

<!-- r_rest_api_group_create.xml -->

### Pedir

`POST /api/v1/groups/`

### Cuerpo de la solicitud de muestra

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

## Actualizar un grupo {#update-group}

Un `PUT` método para actualizar un grupo de usuarios.

<!--
r_rest_api_group_update.xml
-->

### Pedir

`PUT /api/v1/groups/`*`<groupId>`*

### Cuerpo de la solicitud de muestra

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

## Lista de grupos {#list-groups}

Método `GET` para lista usuario grupos.

<!--
r_rest_api_group_list.xml
-->

### Pedir

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

Un `DELETE` método para eliminar un grupo de usuarios y eliminar todos los miembros de ese grupo.

<!-- r_rest_api_group_delete.xml -->

### Pedir

`DELETE /api/v1/groups/`*`<groupId>`*

Regresa `204 No Content` si se realiza correctamente. En caso de conflicto regresa.`409 Conflict`

## Eliminar grupos en masa {#delete-groups-bulk}

Un `DELETE` método para eliminar varios grupos en masa y quitar todos los miembros de ese grupo.

<!-- r_rest_api_group_delete_bulk.xml -->

### Pedir

`DELETE /api/v1/groups/bulk-delete`

Regresa `204 No Content` si se realiza correctamente. En caso de conflicto regresa.`409 Conflict`

## Mostrar todos los permisos de un grupo {#list-permissions-group}

Método `GET` para lista los objetos permiso de un grupo.

<!-- r_rest_api_perm_list_group.xml -->

### Pedir

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

Devuelve `400 Bad Request` el valor si no se puede acceder al grupo.

## Definir permisos para un grupo {#set-permissions-group}

Un `PUT` método para actualizar permisos grupo. Este método sobrescribe los permisos antiguos con los permisos nuevos.

<!-- r_rest_api_perm_set.xml -->

### Pedir

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

La respuesta de ejemplo representa el lista actualizado de permiso objetos.

Regresa `200 OK` si se realiza correctamente. Devuelve el valor `400` si alguno de los permiso es no válido. También se puede devolver `403` si el usuario que ha iniciado sesión no puede acceder al objeto.
