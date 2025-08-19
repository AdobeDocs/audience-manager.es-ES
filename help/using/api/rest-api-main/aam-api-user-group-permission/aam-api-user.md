---
description: Métodos de API de REST para administrar a los usuarios, incluida la creación, actualización, listado, eliminación y devolución de objetos usuario.
seo-description: Rest API methods to manage users, including creating, updating, listing, deleting, and returning user objects.
seo-title: User Management API Methods
solution: Audience Manager
title: User Management métodos de API
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
exl-id: c015c42c-63c7-4392-9fef-f48dc787a56f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 1%

---

# User Management métodos de API {#user-management-api-methods}

Métodos REST [!DNL API] para administrar usuarios, incluida la creación, actualización, enumeración, eliminación y devolución de objetos usuario.

<!-- c_rest_api_user_man_user.xml -->

## Crear usuario {#create-user}

Un `POST` método para crear un nuevo usuario.

<!-- r_rest_api_user_create.xml -->

### Pedir

`POST /api/v1/users/`

### Cuerpo de la solicitud de muestra

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

Si `isAdmin` se establece en true, la usuario se crea como administrador socio. Este Propiedad también le permite saber si un usuario es un administrador socio.

Devuelve `409 Conflict` el valor si el nombre de usuario ya está en uso.

## Actualizar un usuario {#update-user}

Método `PUT` para actualizar un usuario.

<!-- r_rest_api_user_update.xml -->

### Pedir

`PUT /api/v1/users/`*`<userId>`*

### Cuerpo de la solicitud de muestra

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

Devuelve `409 Conflict` el valor si el nombre de usuario ya está en uso.

## Actualizar usuario conectado {#update-logged-in-user}

Un `PUT` método para actualizar la usuario que ha iniciado sesión actualmente.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Mientras que la mayoría [!DNL API] de los métodos solo los pueden llamar los administradores de socio, este método lo pueden llamar los usuarios que no son administradores.

### Pedir

`PUT /self/update`

### Cuerpo de la solicitud de muestra

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

Devuelve `409 Conflict` el valor si el nombre de usuario ya está en uso.

## Actualizar el Contraseña de usuario conectado {#update-logged-in-user-pw}

Un `PUT` método para actualizar la usuario que ha iniciado sesión actualmente.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Mientras que la mayoría [!DNL API] de los métodos solo los pueden llamar los administradores de socio, este método lo pueden llamar los usuarios que no son administradores.

### Pedir

`POST /users/self/update-password`

### Cuerpo de la solicitud de muestra

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Regresa `200 OK` si se realiza correctamente. Devuelve `400 Bad Request` el valor si alguno de los contraseña está mal.

## Restablecer Contraseña de usuario conectado {#reset-logged-in-user-pw}

Método `PUT` para restablecer el usuario conectado actualmente. [!UICONTROL Audience Management] Envía el usuario un contraseña generado por el sistema.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Mientras que la mayoría [!DNL API] de los métodos solo los pueden llamar los administradores de socio, este método lo pueden llamar los usuarios que no son administradores.

### Pedir

`POST /self/reset-password`

Regresa `200 OK` si se realiza correctamente.

## Devolver objeto de usuario para un ID de usuario {#return-user-object-for-id}

Método `Get` para devolver el objeto usuario para un ID de usuario.

<!-- r_rest_api_user_get_user_obj.xml -->

### Pedir

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

## Devolver objeto de usuario para usuario conectado {#return-user-object-for-logged-in-user}

Método `Get` para devolver el objeto usuario para el usuario conectado actualmente.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Mientras que la mayoría [!DNL API] de los métodos solo los pueden llamar los administradores de socio, este método lo pueden llamar los usuarios que no son administradores.

### Pedir

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

## Lista de usuarios {#list-users}

Método `GET` para lista usuarios.

<!-- r_rest_api_user_list.xml -->

### Pedir

`GET /api/v1/users/`

Puede especificar varios ID de grupo en los parámetros consulta:

`GET /api/v1/users/?groupId=343&groupdId=12`

Este consulta devuelve un lista de todos los usuarios de los grupos especificados.

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

## Eliminar usuario {#delete-users}

Un `DELETE` método para eliminar un usuario.

<!-- r_rest_api_user_delete.xml -->

### Pedir

`DELETE /api/v1/users/`*`<user_id>`*

Regresa `204 No Content` si se realiza correctamente. En caso de conflicto regresa.`409 Conflict`

## Eliminar usuarios en masa {#delete-users-bulk}

Un `POST` método para eliminar varios usuarios en masa.

<!-- r_rest_api_user_delete_bulk.xml -->

### Pedir

`POST /api/v1/users/bulk-delete`

### Cuerpo de la solicitud de muestra

```
{[<user_id_1>, <user_id_2>, ...]}
```
