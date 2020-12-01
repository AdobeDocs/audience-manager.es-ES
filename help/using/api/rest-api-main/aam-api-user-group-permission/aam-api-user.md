---
description: Métodos de API de descanso para administrar usuarios, incluida la creación, actualización, listado, eliminación y devolución de objetos de usuario.
seo-description: Métodos de API de descanso para administrar usuarios, incluida la creación, actualización, listado, eliminación y devolución de objetos de usuario.
seo-title: Métodos de API de administración de usuario
solution: Audience Manager
title: Métodos de API de administración de usuario
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 7%

---


# Métodos de API de administración de usuario {#user-management-api-methods}

Los [!DNL API] métodos restantes para administrar usuarios, incluso crear, actualizar, enumerar, eliminar y devolver objetos de usuario.

<!-- c_rest_api_user_man_user.xml -->

## Crear un usuario {#create-user}

Un método `POST` para crear un nuevo usuario.

<!-- r_rest_api_user_create.xml -->

### Solicitud

`POST /api/v1/users/`

### Cuerpo de solicitud de muestra

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : true | false 
}
```

### Respuesta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : <"true"|"false"> 
 
}
```

Si `isAdmin` se establece en true, el usuario se crea como administrador asociado. Esta propiedad también le permite saber si un usuario es administrador asociado.

Devuelve `409 Conflict` si el nombre de usuario ya está en uso.

## Actualizar un usuario {#update-user}

Un método `PUT` para actualizar un usuario.

<!-- r_rest_api_user_update.xml -->

### Solicitud

`PUT /api/v1/users/`*`<userId>`*

### Cuerpo de solicitud de muestra

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
}
```

### Respuesta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

Devuelve `409 Conflict` si el nombre de usuario ya está en uso.

## Actualizar usuario con inicio de sesión {#update-logged-in-user}

Un método `PUT` para actualizar el usuario que ha iniciado sesión.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Mientras que la mayoría de los métodos [!DNL API] solo los pueden llamar los administradores de socios, este método lo hacen los usuarios que no son administradores.

### Solicitud

`PUT /self/update`

### Cuerpo de solicitud de muestra

```
{  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

### Respuesta

```
{ 
  "userId": <integer>,,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string> 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

Devuelve `409 Conflict` si el nombre de usuario ya está en uso.

## Actualizar la contraseña de usuario con inicio de sesión {#update-logged-in-user-pw}

Un método `PUT` para actualizar el usuario que ha iniciado sesión.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Mientras que la mayoría de los métodos [!DNL API] solo los pueden llamar los administradores de socios, este método lo hacen los usuarios que no son administradores.

### Solicitud

`POST /users/self/update-password`

### Cuerpo de solicitud de muestra

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Devuelve `200 OK` si se realiza correctamente. Devuelve `400 Bad Request` si hay algún problema con cualquiera de las contraseñas.

## Restablecer la contraseña de usuario iniciada {#reset-logged-in-user-pw}

Un método `PUT` para restablecer el usuario que ha iniciado sesión. [!UICONTROL Audience Management] envía al usuario una contraseña generada por el sistema.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Mientras que la mayoría de los métodos [!DNL API] solo los pueden llamar los administradores de socios, este método lo hacen los usuarios que no son administradores.

### Solicitud

`POST /self/reset-password`

Devuelve `200 OK` si se realiza correctamente.

## Devolver objeto de usuario para un ID de usuario {#return-user-object-for-id}

Un método `Get` para devolver el objeto de usuario para un ID de usuario.

<!-- r_rest_api_user_get_user_obj.xml -->

### Solicitud

`GET /api/v1/users/`*`<userId>`*

### Respuesta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Devolver objeto de usuario para usuario con sesión iniciada {#return-user-object-for-logged-in-user}

Un método `Get` para devolver el objeto de usuario del usuario que ha iniciado sesión.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Mientras que la mayoría de los métodos [!DNL API] solo los pueden llamar los administradores de socios, este método lo hacen los usuarios que no son administradores.

### Solicitud

`GET /api/v1/users/self`

### Respuesta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Usuarios de lista {#list-users}

Un método `GET` para la lista de usuarios.

<!-- r_rest_api_user_list.xml -->

### Solicitud

`GET /api/v1/users/`

Puede especificar varios ID de grupo en los parámetros de consulta:

`GET /api/v1/users/?groupId=343&groupdId=12`

Esta consulta devuelve una lista de todos los usuarios de los grupos especificados.

### Respuesta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

## Eliminar un usuario {#delete-users}

Un método `DELETE` para eliminar un usuario.

<!-- r_rest_api_user_delete.xml -->

### Solicitud

`DELETE /api/v1/users/`*`<user_id>`*

Devuelve `204 No Content` si se realiza correctamente. En caso de conflicto, devuelve `409 Conflict`.

## Eliminar usuarios de forma masiva {#delete-users-bulk}

Un método `POST` para eliminar varios usuarios de forma masiva.

<!-- r_rest_api_user_delete_bulk.xml -->

### Solicitud

`POST /api/v1/users/bulk-delete`

### Cuerpo de solicitud de muestra

```
{[<user_id_1>, <user_id_2>, ...]}
```
