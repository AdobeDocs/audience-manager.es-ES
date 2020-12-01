---
description: Asigne segmentos a destinos con estos métodos de API RESTful.
seo-description: Asigne segmentos a destinos con estos métodos de API RESTful.
seo-title: Asignar segmentos a un destino
solution: Audience Manager
title: Asignar segmentos a un destino
uuid: 35358ace-3082-4e86-a6eb-d77281af6d7e
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 11%

---


# Asignar segmentos a un destino {#map-segments-to-a-destination}

Asigne segmentos a destinos con estos métodos [!DNL RESTful API].

<!-- c_api_map_seg_dest.xml -->

## Tipos de destino admitidos: Solo URL y cookie

Los métodos `POST` disponibles le permiten asignar segmentos sólo a [!UICONTROL URL] y [!UICONTROL cookie destinations]. Actualmente, no puede asignar segmentos a [!UICONTROL server-to-server destinations] con estos métodos [!DNL REST API]. En su lugar, utilice la interfaz de usuario. Sin embargo, los métodos `GET` de destino relacionados permiten recuperar información sobre [!UICONTROL server-to-server destinations] creada en la interfaz de usuario.

## Asignar un segmento a un destino de URL no serializado {#map-segment-non-serial}

Un método `POST` que permite asignar un segmento a un destino [!UICONTROL URL] no serial.

<!-- r_map_noserial_url.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitud de ejemplo

Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-07-04"
}
```

### Respuesta

```
{
   "mappingId":65334,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4033,
   "elementName":"Sample games",
   "elementDescription":"Sample games pixel",
   "elementStatus":"active",
   "createTime":1338940094000,
   "updateTime":1338940094000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"https://adobe.com",
   "secureUrl":null,
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":null
}
```

## Asignar un segmento a un destino de URL serializado {#map-segment-serial}

Un método `POST` que permite asignar un segmento a un destino serializado [!UICONTROL URL].

<!-- r_map_serialized_url.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### Solicitud de ejemplo

En la solicitud, `traitAlias` corresponde a la clave en un par clave-valor. Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Respuesta

```
{
   "mappingId":65335,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4034,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940401000,
   "updateTime":1338940401000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"123",
   "secureUrl":"123",
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":"123"
}
```

## Asignar un segmento a un destino de cookie: Clave única, sin serializar {#map-segment-cookie-noserial}

Un método `POST` que permite asignar un segmento a un destino de clave única y no serializada [!UICONTROL cookie].

<!-- r_map_cookie_noserial.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitud de ejemplo

En la solicitud, `valueAlias` corresponde al valor en un par clave-valor. Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "valueAlias":"123"
}
```

### Respuesta

```
{
   "destinationMappingId":65336,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4035,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940704000,
   "updateTime":1338940704000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":null,
   "valueAlias":"123"
}
```

## Asignar un segmento a un destino de cookie: Clave múltiple, sin serializar {#map-segment-cookie-multi-noserial}

Un método `POST` que permite asignar un segmento a un destino de varias claves y no serializadas [!UICONTROL cookie].

<!-- r_map_cookie_multikey_noserial.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitud de ejemplo

En la solicitud, `traitAlias` y `valueAlias` configuran la clave y el valor respectivamente en un par clave-valor. Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Respuesta

```
{
   "mappingId":65338,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4037,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941092000,
   "updateTime":1338941092000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Asignar un segmento a un destino de cookie: Clave múltiple, serializada {#map-segment-cookie-multi-serial}

Un método `POST` que permite asignar un segmento a un segmento con varias claves, serializado [!UICONTROL cookie destination].

<!-- r_map_cookie_multikey_serialized.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitud de ejemplo

En la solicitud, `traitAlias` y `valueAlias` establecen la clave y el valor en un par clave-valor. Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Respuesta

```
{
   "destinationMappingId":65340,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4038,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941273000,
   "updateTime":1338941273000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":2,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Asignar un segmento a un destino de servidor a servidor {#map-segment-s2s}

Un método `POST` que permite asignar un segmento a un destino [!UICONTROL server-to-server] existente. Sin embargo, tenga en cuenta que no puede crear destinos [!UICONTROL server-to-server] con estos métodos [!DNL API] disponibles actualmente.

<!-- r_map_segment_s2s.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitud de ejemplo

En la solicitud, `traitAlias` corresponde a la clave en un par clave-valor. Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Respuesta

```
{
   "destinationMappingId":65341,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":566,
   "elementName":"Sample",
   "elementDescription":"",
   "elementStatus":"active",
   "createTime":1338942118000,
   "updateTime":1338942118000,
   "crUID":308,
   "upUID":308,
   "sid":84326,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "traitAlias":"123"
}
```

## Asignaciones de destino de creación masiva {#bulk-create}

Un método `POST` que permite pasar una matriz de asignaciones de destino [!UICONTROL cookie] o [!UICONTROL URL].

<!-- r_bulk_create.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### Solicitud de ejemplo

Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Respuesta

Una respuesta correcta devuelve la matriz de asignaciones creadas.

```
[
    {
        "mappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "mappingId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "orderId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Añadir varios segmentos a un destino {#add-segments-dest}

Un método `POST` que permite asignar varios segmentos a un destino.

<!-- r_add_segments_to_destination.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### Solicitud de ejemplo

Cree varias asignaciones de destino en una matriz. Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Respuesta

Devuelve una matriz de asignaciones creadas.

```
[
    {
        "destinationMappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "traitToDataOrderId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Actualizar un destino por ID de destino {#update-dest-data-order}

Un método `PUT` que permite actualizar un destino existente mediante `destinationId`.

<!-- r_update_destination_data_order_id.xml -->

### Solicitud

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### Solicitud de ejemplo

Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
{
   "name":"Updated URL Destination (not serialized)",
   "description":"new description",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Respuesta

```
{
    "destinationType": "PUSH",
    "destinationId": 780,
    "dataSourceId": null,
    "pid": 1099,
    "name": "Updated URL Destination (not serialized)",
    "description": "new description",
    "startDate": null,
    "endDate": null,
    "status": 1,
    "createTime": 1348851790000,
    "updateTime": 1353372029000,
    "crUID": 884,
    "upUID": 1065,
    "domainRestrictions":"all_domains",
    "tagType": 0,
    "serializationEnabled": false,
    "urlFormatString": null,
    "secureUrlFormatString": null,
    "delimiter": null,
    "mappings": null
}
```

## Actualizar una asignación a un destino mediante el identificador de asignación {#update-mapping-dest-id}

Un método `PUT` que permite actualizar una asignación a un destino según el `mappingId` especificado.

<!-- r_update_destination_trait_data_order_id.xml -->

### Solicitud

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### Solicitud de ejemplo

Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
}
```

### Respuesta

```
{
    "mappingId": 103453,
    "traitType": "SEGMENT",
    "traitValue": 0,
    "destinationId": 780,
    "elementName": "sample",
    "elementDescription": "test",
    "elementStatus": "active",
    "createTime": 1353373005000,
    "updateTime": 1353373005000,
    "crUID": 1065,
    "upUID": 1065,
    "sid": 105123,
    "startDate": "2012-11-19",
    "endDate": null,
    "priority": null,
    "url": "https://www.adobe.com/send?%ALIAS%",
    "secureUrl": null,
    "tagCode": null,
    "secureTagCode": null,
    "traitAlias": null
}
```

>[!MORELIKETHIS]
>
>* [Destinos ](../../../features/destinations/destinations.md)
>* [Serialización de destino](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Pares de clave-valor explicados](../../../reference/key-value-pairs-explained.md)

