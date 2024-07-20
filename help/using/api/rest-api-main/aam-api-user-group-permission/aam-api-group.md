---
description: Métodos de API de REST para administrar grupos, incluida la creación, actualización, inclusión en listas y eliminación de grupos.
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

Rest [!DNL API] métodos para administrar grupos, incluyendo la creación, actualización, listado y eliminación de grupos.

<!-- c_rest_api_user_man_group.xml -->

## Creación de grupos {#create-group}

Un método `POST` para crear un nuevo grupo de usuarios.

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

Un método `PUT` para actualizar un grupo de usuarios.

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

## Grupos de lista {#list-groups}

Un método `GET` para enumerar grupos de usuarios.

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

Un método `DELETE` para eliminar un grupo de usuarios y quitar todos los miembros de ese grupo.

<!-- r_rest_api_group_delete.xml -->

### Solicitud

`DELETE /api/v1/groups/`*`<groupId>`*

Devuelve `204 No Content` si se realizó correctamente. En caso de conflicto, devuelve `409 Conflict`.

## Eliminar grupos por lotes {#delete-groups-bulk}

Un método `DELETE` para eliminar varios grupos de forma masiva y quitar todos los miembros de ese grupo.

<!-- r_rest_api_group_delete_bulk.xml -->

### Solicitud

`DELETE /api/v1/groups/bulk-delete`

Devuelve `204 No Content` si se realizó correctamente. En caso de conflicto, devuelve `409 Conflict`.

## Mostrar todos los permisos de un grupo {#list-permissions-group}

Un método `GET` para enumerar los objetos de permiso de un grupo.

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

Devuelve `400 Bad Request` si no se puede obtener acceso al grupo.

## Definición de permisos para un grupo {#set-permissions-group}

Un método `PUT` para actualizar permisos de grupo. Este método sobrescribe los permisos antiguos con los nuevos permisos.

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

La respuesta de ejemplo representa la lista actualizada de objetos de permiso.

Devuelve `200 OK` si se realizó correctamente. Devuelve `400` si algún permiso dado no es válido. También puede devolver `403` si el usuario que ha iniciado sesión no puede obtener acceso al objeto.
