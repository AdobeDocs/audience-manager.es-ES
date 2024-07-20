---
description: Métodos de API de REST para administrar permisos para objetos y grupos.
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: Métodos de API de administración de permisos
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%

---

# Métodos de API de administración de permisos {#permissions-management-api-methods}

Métodos Rest [!DNL API] para administrar permisos para objetos y grupos.

<!-- c_rest_api_perm_man.xml -->

## Lista de tipos de objetos disponibles {#list-object-types}

Un método `GET` para enumerar los tipos de objetos disponibles en los que se pueden establecer controles de acceso basados en roles.

<!-- r_rest_api_perm_list.xml -->

### Solicitud

`GET /api/v1/permissionable-object-types/`

### Respuesta

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Lista de permisos disponibles para un tipo de objeto {#list-permissions-object-type}

Un método `GET` para enumerar los permisos disponibles para un tipo de objeto.

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
>Los tipos de objeto ETIQUETAS y SEÑALES DERIVADAS no tienen permisos regulares para utilizar. Los controles de estos tipos de objetos se cambian únicamente mediante los permisos de comodín Todos o Nada.
