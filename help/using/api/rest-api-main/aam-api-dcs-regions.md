---
description: Métodos que permiten enumerar mediante programación regiones de DCS Audience Manager.
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: Métodos de API de región DCS
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 12%

---

# Métodos de API de región DCS {#dcs-region-api-methods}

Métodos que permiten enumerar Audience Manager mediante programación [!DNL DCS] regiones.

<!-- c_rest_api_regions.xml -->

Para ver una lista de regiones y sus enteros correspondientes, consulte [ID de región de DCS, ubicaciones y nombres de host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Enumeración de una región DCS específica {#list-specific-dcs-region}

A `GET` para enumerar un método específico [!DNL DCS] región.

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

Devuelve `200 OK` si tiene éxito.

Para ver una lista de regiones y sus enteros correspondientes, consulte [ID de región de DCS, ubicaciones y nombres de host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Enumerar regiones de DCS {#list-dcs-regions}

A `GET` método para enumerar [!DNL DCS] regiones.

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

Devuelve `200 OK` si tiene éxito.

Para ver una lista de regiones y sus enteros correspondientes, consulte [ID de región de DCS, ubicaciones y nombres de host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
