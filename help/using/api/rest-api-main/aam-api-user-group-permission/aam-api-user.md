---
description: Métodos de API Rest para administrar usuarios, incluida la creación, actualización, lista, eliminación y devolución de objetos de usuario.
seo-description: Métodos de API Rest para administrar usuarios, incluida la creación, actualización, lista, eliminación y devolución de objetos de usuario.
seo-title: Métodos API de administración de usuarios
solution: Audience Manager
title: Métodos API de administración de usuarios
uuid: 6 e 1 f 2 c 35-bb 9 d -4166-b 7 d 4-d 9 c 5518 a 61 ad
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# User Management API Methods {#user-management-api-methods}

Rest [!DNL API] methods to manage users, including creating, updating, listing, deleting, and returning user objects.

<!-- c_rest_api_user_man_user.xml -->

## Create a User {#create-user}

`POST` Método para crear un nuevo usuario.

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

If `isAdmin` is set to true, the user is created as a partner admin. Esta propiedad también permite saber si un usuario es administrador del socio.

Returns `409 Conflict` if the username is already taken.

## Update a User {#update-user}

`PUT` Método para actualizar a un usuario.

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

Returns `409 Conflict` if the username is already taken.

## Update Logged-In User {#update-logged-in-user}

`PUT` Método para actualizar al usuario que ha iniciado sesión.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

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

Returns `409 Conflict` if the username is already taken.

## Update Logged-In User Password {#update-logged-in-user-pw}

`PUT` Método para actualizar al usuario que ha iniciado sesión.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

### Solicitud

`POST /users/self/update-password`

### Cuerpo de solicitud de muestra

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Returns `200 OK` if successful. Returns `400 Bad Request` if something is wrong with either password.

## Reset Logged-In User Password {#reset-logged-in-user-pw}

`PUT` Método para restablecer el usuario que ha iniciado sesión. [!UICONTROL Audience Management] envía al usuario una contraseña generada por el sistema.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

### Solicitud

`POST /self/reset-password`

Returns `200 OK` if successful.

## Return User Object for a User ID {#return-user-object-for-id}

`Get` Método para devolver el objeto de usuario para un ID de usuario.

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

## Return User Object for Logged-In User {#return-user-object-for-logged-in-user}

`Get` Método para devolver el objeto de usuario para el usuario que ha iniciado sesión.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

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

## List Users {#list-users}

`GET` Método para listar usuarios.

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

## Delete a User {#delete-users}

`DELETE` Método para eliminar un usuario.

<!-- r_rest_api_user_delete.xml -->

### Solicitud

`DELETE /api/v1/users/`*`<user_id>`*

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## Delete Users in Bulk {#delete-users-bulk}

`POST` Método para eliminar varios usuarios de forma masiva.

<!-- r_rest_api_user_delete_bulk.xml -->

### Solicitud

`POST /api/v1/users/bulk-delete`

### Cuerpo de solicitud de muestra

```
{[<user_id_1>, <user_id_2>, ...]}
```
