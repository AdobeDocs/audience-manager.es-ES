---
description: Asigne segmentos a destinos con estos métodos de API restful.
seo-description: Asigne segmentos a destinos con estos métodos de API restful.
seo-title: Asignar segmentos a un destino
solution: Audience Manager
title: Asignar segmentos a un destino
uuid: 35358 ace -3082-4 e 86-a 6 eb-d 77281 af 6 d 7 e
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Map Segments to a Destination {#map-segments-to-a-destination}

Map segments to destinations with these [!DNL RESTful API] methods.

<!-- c_api_map_seg_dest.xml -->

## Tipos de destino admitidos: Solo URL y cookie

The available `POST` methods let you map segments to [!UICONTROL URL] and [!UICONTROL cookie destinations] only. Currently, you cannot map segments to [!UICONTROL server-to-server destinations] with these [!DNL REST API] methods. Utilice la interfaz de usuario en su lugar. However, the related destination `GET` methods let you retrieve information about [!UICONTROL server-to-server destinations] created in the user interface.

>[!MORE_ LIKE_ THIS]
>
>* [Destinos](../../../features/destinations/destinations.md#destination-api-methods)
>* [Serialización de destino](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Pares de clave-valor explicados](../../../reference/key-value-pairs-explained.md)


## Map a Segment to a Non-Serialized URL Destination {#map-segment-non-serial}

`POST` Método que permite asignar un segmento a [!UICONTROL URL] un destino no serializado.

<!-- r_map_noserial_url.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitud de ejemplo

Se requieren todos los valores de solicitud a menos que se indique lo contrario.

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

## Map a Segment to a Serialized URL Destination {#map-segment-serial}

`POST` Método que permite asignar un segmento a [!UICONTROL URL] un destino serializado.

<!-- r_map_serialized_url.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### Solicitud de ejemplo

In the request, the `traitAlias` corresponds to the key in a key-value pair. Se requieren todos los valores de solicitud a menos que se indique lo contrario.

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

## Map a Segment to a Cookie Destination: Single-Key, Non-Serialized {#map-segment-cookie-noserial}

`POST` Método que permite asignar un segmento a destinos no serializados [!UICONTROL cookie] ni de una sola tecla.

<!-- r_map_cookie_noserial.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitud de ejemplo

In the request, the `valueAlias` corresponds to the value in a key-value pair. Se requieren todos los valores de solicitud a menos que se indique lo contrario.

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

## Map a Segment to a Cookie Destination: Multi-Key, Non-Serialized {#map-segment-cookie-multi-noserial}

`POST` Método que permite asignar un segmento a [!UICONTROL cookie] destinos multiclave y no serializados.

<!-- r_map_cookie_multikey_noserial.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitud de ejemplo

In the request, the `traitAlias` and `valueAlias` set the key and the value respectively in a key-value pair. Se requieren todos los valores de solicitud a menos que se indique lo contrario.

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

## Map a Segment to a Cookie Destination: Multi-Key, Serialized {#map-segment-cookie-multi-serial}

`POST` Método que permite asignar un segmento a una serialización múltiple [!UICONTROL cookie destination].

<!-- r_map_cookie_multikey_serialized.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitud de ejemplo

In the request, the `traitAlias` and `valueAlias` set the key and the value in a key-value pair. Se requieren todos los valores de solicitud a menos que se indique lo contrario.

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

## Map a Segment to a Server-to-Server Destination {#map-segment-s2s}

`POST` Método que permite asignar un segmento a un [!UICONTROL server-to-server] destino existente. Note, however, that you cannot create [!UICONTROL server-to-server] destinations with these currently available [!DNL API] methods.

<!-- r_map_segment_s2s.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Solicitud de ejemplo

In the request, the `traitAlias` corresponds to the key in a key-value pair. Se requieren todos los valores de solicitud a menos que se indique lo contrario.

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

## Bulk Create Destination Mappings {#bulk-create}

`POST` Método que permite pasar una matriz de [!UICONTROL cookie] asignaciones [!UICONTROL URL] de destino o de destino.

<!-- r_bulk_create.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### Solicitud de ejemplo

Se requieren todos los valores de solicitud a menos que se indique lo contrario.

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

## Add Multiple Segments to a Destination {#add-segments-dest}

`POST` Método que permite asignar varios segmentos a un destino.

<!-- r_add_segments_to_destination.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### Solicitud de ejemplo

Cree varias asignaciones de destino en una matriz. Se requieren todos los valores de solicitud a menos que se indique lo contrario.

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

## Update a Destination by Destination ID {#update-dest-data-order}

`PUT` Método que permite actualizar un destino existente.`destinationId`

<!-- r_update_destination_data_order_id.xml -->

### Solicitud

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### Solicitud de ejemplo

Se requieren todos los valores de solicitud a menos que se indique lo contrario.

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

## Update a Mapping to a Destination by Mapping ID {#update-mapping-dest-id}

`PUT` Método que permite actualizar una asignación a un destino según el valor especificado `mappingId`.

<!-- r_update_destination_trait_data_order_id.xml -->

### Solicitud

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### Solicitud de ejemplo

Se requieren todos los valores de solicitud a menos que se indique lo contrario.

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
