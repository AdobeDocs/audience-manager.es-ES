---
description: Métodos que permiten la lista mediante programación de regiones DCS Audience Manager.
seo-description: Métodos que permiten la lista mediante programación de regiones DCS Audience Manager.
seo-title: Métodos de API de región DCS
solution: Audience Manager
title: Métodos de API de región DCS
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 14%

---


# Métodos de API de región DCS {#dcs-region-api-methods}

Métodos que le permiten lista mediante programación de regiones [!DNL DCS] Audience Manager.

<!-- c_rest_api_regions.xml -->

Para obtener una lista de regiones y sus correspondientes enteros, consulte [ID de región de DCS, ubicaciones y nombres de host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Lista de una región específica de DCS {#list-specific-dcs-region}

Un método `GET` para la lista de una región [!DNL DCS] específica.

<!-- r_rest_api_regions_list_specific.xml -->

### Solicitud

`GET /v1/dcs-regions/`*`<id>`*

### Respuesta de ejemplo

```
{ 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code>",
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  }
```

Devuelve `200 OK` si se realiza correctamente.

Para obtener una lista de regiones y sus correspondientes enteros, consulte [ID de región de DCS, ubicaciones y nombres de host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Regiones DCS de lista {#list-dcs-regions}

Un método `GET` para lista de regiones [!DNL DCS].

<!-- r_rest_api_regions_list.xml -->

### Solicitud

`GET /v1/dcs-regions/`

### Respuesta de ejemplo

```
[
  { 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code> # APSE, USE, etc,
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  },
  ...
]
```

Devuelve `200 OK` si se realiza correctamente.

Para obtener una lista de regiones y sus correspondientes enteros, consulte [ID de región de DCS, ubicaciones y nombres de host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
