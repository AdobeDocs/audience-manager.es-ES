---
description: Métodos que le permiten enumerar mediante programación regiones de DCS de Audience Manager.
seo-description: Métodos que le permiten enumerar mediante programación regiones de DCS de Audience Manager.
seo-title: Métodos de API de región DCS
solution: Audience Manager
title: Métodos de API de región DCS
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Métodos de API de región DCS {#dcs-region-api-methods}

Métodos que le permiten enumerar mediante programación [!UICONTROL DCS] regiones de Audience Manager.

<!-- c_rest_api_regions.xml -->

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Enumerar una región específica de DCS {#list-specific-dcs-region}

Un `GET` método para mostrar una [!UICONTROL DCS] región específica.

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

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Lista de regiones DCS {#list-dcs-regions}

Un `GET` método para enumerar [!UICONTROL DCS] regiones.

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

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
