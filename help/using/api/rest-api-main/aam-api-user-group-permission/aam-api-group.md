---
description: Métodos de API de descanso para administrar grupos, incluida la creación, actualización, listado y eliminación de grupos.
seo-description: Métodos de API de descanso para administrar grupos, incluida la creación, actualización, listado y eliminación de grupos.
seo-title: Métodos de API de administración de grupos
solution: Audience Manager
title: Métodos de API de administración de grupos
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 8%

---


# Métodos de API de administración de grupos {#group-management-api-methods}

Métodos [!DNL API] de descanso para administrar grupos, como crear, actualizar, enumerar o eliminar grupos.

<!-- c_rest_api_user_man_group.xml -->

## Creación de grupos {#create-group}

Un `POST` método para crear un nuevo grupo de usuarios.

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

## Actualizar un grupo {#update-group}

Un `PUT` método para actualizar un grupo de usuarios.

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

## Grupos de Listas {#list-groups}

Un `GET` método para la lista de grupos de usuarios.

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

Un `DELETE` método para eliminar un grupo de usuarios y eliminar todos los miembros de dicho grupo.

<!-- r_rest_api_group_delete.xml -->

### Solicitud

`DELETE /api/v1/groups/`*`<groupId>`*

Devuelve `204 No Content` si se realiza correctamente. En caso de conflicto retorna `409 Conflict`.

## Eliminar grupos de forma masiva {#delete-groups-bulk}

Un `DELETE` método para eliminar varios grupos de forma masiva y eliminar todos los miembros de ese grupo.

<!-- r_rest_api_group_delete_bulk.xml -->

### Solicitud

`DELETE /api/v1/groups/bulk-delete`

Devuelve `204 No Content` si se realiza correctamente. En caso de conflicto retorna `409 Conflict`.

## Lista de todos los permisos de un grupo {#list-permissions-group}

Un `GET` método de lista de los objetos de permiso de un grupo.

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

Devuelve `400 Bad Request` si no se puede acceder al grupo.

## Set Permissions for a Group {#set-permissions-group}

Un `PUT` método para actualizar los permisos de grupo. Este método sobrescribe los permisos anteriores con los nuevos permisos.

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

La respuesta de ejemplo representa la lista actualizada de los objetos de permiso.

Devuelve `200 OK` si se realiza correctamente. Devuelve `400` si algún permiso dado no es válido. También se puede devolver `403` si el usuario que ha iniciado sesión no puede acceder al objeto.