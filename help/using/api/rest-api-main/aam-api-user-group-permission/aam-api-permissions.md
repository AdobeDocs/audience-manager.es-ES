---
description: Métodos de API de REST para administrar permisos para objetos y grupos.
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: Métodos de API de administración de permisos
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
TQID: https://experienceleague.adobe.com/E9JWh1JKhHOSd7MzeOR8csVXChyh4Q0RiCj3Y5yb2vM
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2: id: d8f681b8-67cc-42dc-85c5-a0977528a942
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 96
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
