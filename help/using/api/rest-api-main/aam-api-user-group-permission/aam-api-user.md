---
description: Rest métodos de API para administrar usuarios, incluida la creación, actualización, lista, eliminación y devolución de objetos de usuario.
seo-description: Rest métodos de API para administrar usuarios, incluida la creación, actualización, lista, eliminación y devolución de objetos de usuario.
seo-title: Métodos de API de administración de usuario
solution: Audience Manager
title: Métodos de API de administración de usuario
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
exl-id: c015c42c-63c7-4392-9fef-f48dc787a56f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 7%

---

# Métodos de API de administración de usuario {#user-management-api-methods}

Rest [!DNL API] métodos para administrar usuarios, como crear, actualizar, listar, eliminar y devolver objetos de usuario.

<!-- c_rest_api_user_man_user.xml -->

## Crear un usuario {#create-user}

Un método `POST` para crear un nuevo usuario.

<!-- r_rest_api_user_create.xml -->

### Solicitud

`POST /api/v1/users/`

### Cuerpo de la solicitud de ejemplo

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

Si `isAdmin` se establece en true, el usuario se crea como administrador del socio. Esta propiedad también le permite saber si un usuario es administrador del socio.

Devuelve `409 Conflict` si el nombre de usuario ya se ha tomado.

## Actualizar un usuario {#update-user}

Método `PUT` para actualizar a un usuario.

<!-- r_rest_api_user_update.xml -->

### Solicitud

`PUT /api/v1/users/`*`<userId>`*

### Cuerpo de la solicitud de ejemplo

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

Devuelve `409 Conflict` si el nombre de usuario ya se ha tomado.

## Actualizar usuario de inicio de sesión {#update-logged-in-user}

Un método `PUT` para actualizar el usuario que ha iniciado sesión.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Mientras que la mayoría de los métodos [!DNL API] solo los pueden llamar los administradores asociados, este método lo pueden hacer los usuarios que no sean administradores.

### Solicitud

`PUT /self/update`

### Cuerpo de la solicitud de ejemplo

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

Devuelve `409 Conflict` si el nombre de usuario ya se ha tomado.

## Actualizar la contraseña de usuario con sesión iniciada {#update-logged-in-user-pw}

Un método `PUT` para actualizar el usuario que ha iniciado sesión.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Mientras que la mayoría de los métodos [!DNL API] solo los pueden llamar los administradores asociados, este método lo pueden hacer los usuarios que no sean administradores.

### Solicitud

`POST /users/self/update-password`

### Cuerpo de la solicitud de ejemplo

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Devuelve `200 OK` si se realiza correctamente. Devuelve `400 Bad Request` si hay algún problema con cualquiera de las contraseñas.

## Restablecer la contraseña de usuario con sesión iniciada {#reset-logged-in-user-pw}

Un método `PUT` para restablecer el usuario que ha iniciado sesión. [!UICONTROL Audience Management] envía al usuario una contraseña generada por el sistema.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Mientras que la mayoría de los métodos [!DNL API] solo los pueden llamar los administradores asociados, este método lo pueden hacer los usuarios que no sean administradores.

### Solicitud

`POST /self/reset-password`

Devuelve `200 OK` si se realiza correctamente.

## Devolver objeto de usuario para un identificador de usuario {#return-user-object-for-id}

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

## Devolver objeto de usuario para usuario registrado {#return-user-object-for-logged-in-user}

Un método `Get` para devolver el objeto de usuario para el usuario que ha iniciado sesión en ese momento.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Mientras que la mayoría de los métodos [!DNL API] solo los pueden llamar los administradores asociados, este método lo pueden hacer los usuarios que no sean administradores.

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

## Lista de usuarios {#list-users}

Un método `GET` para enumerar usuarios.

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

Método `DELETE` para eliminar un usuario.

<!-- r_rest_api_user_delete.xml -->

### Solicitud

`DELETE /api/v1/users/`*`<user_id>`*

Devuelve `204 No Content` si se realiza correctamente. En caso de conflicto devuelve `409 Conflict`.

## Eliminar usuarios de forma masiva {#delete-users-bulk}

Un método `POST` para eliminar varios usuarios de forma masiva.

<!-- r_rest_api_user_delete_bulk.xml -->

### Solicitud

`POST /api/v1/users/bulk-delete`

### Cuerpo de la solicitud de ejemplo

```
{[<user_id_1>, <user_id_2>, ...]}
```
