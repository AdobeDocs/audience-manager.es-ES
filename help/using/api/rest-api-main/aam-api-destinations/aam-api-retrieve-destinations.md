---
description: Una método GET que devuelve el destino para el destinationId especificado.
seo-description: A GET method that returns the destination for the specified destinationId.
seo-title: Return A Destination by Destination ID
solution: Audience Manager
title: Devolver un destino por ID de destino
uuid: abce7426-55a5-4045-93a7-0487652a7189
feature: API
exl-id: c0850e71-7830-4635-b773-e9a28ab5bd68
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 2%

---

# Devolver un destino por ID de destino {#return-a-destination-by-destination-id}

Un `GET` método que devuelve el destino del archivo `destinationId`.

<!-- r_get_all_destinations_order_id.xml -->

## Pedir

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>Para rellenar el `mappings` campo, pase `includeMappings=true` por el URL.

## Respuesta

```
{
   "destinationType":"PUSH",
   "destinationId":314,
   "dataSourceId":null,
   "pid":1099,
   "name":"sample destination",
   "description":"Turn",
   "startDate":null,
   "endDate":null,
   "status":"active",
   "destinationType":"PUSH",
   "createTime":1281997484000,
   "updateTime":1300752888000,
   "crUID":224,
   "upUID":308,
   "domainRestrictions":"ALL_DOMAINS",
   "tagType":0,
   "serializationEnabled":false,
   "urlFormatString":null,
   "secureUrlFormatString":null,
   "delimiter":null,
   "mappings":null
}
```

## Volver todos los destinos {#return-all-destinations}

Un `GET` método que devuelve todos los destinos para el socio especificado.

<!-- r_get_all_destinations.xml -->

### Pedir

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *(Opcional)* Pase `containsSegment=<sid>` para devolver una matriz de todos los destinos asignados al segmento especificado. Por ejemplo, su consulta podría tener un aspecto similar al siguiente: `GET .../destinations/?containsSegment=4321`.
>
>* No devuelve el objeto de destino completo. Obtenga el destino por orden de datos si necesita un objeto completamente rellenado.

### Parámetros de consulta opcionales

Puede utilizar estos parámetros opcionales con métodos API que devuelven *todas las* propiedades de un objeto. Establezca estas opciones en la cadena solicitud al pasar esa consulta al [!DNL API]archivo . Consulte [Parámetros opcionales](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th>
   <th colname="col2" class="entry"> Descripción </th>
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td>
   <td colname="col2"> Devuelve los resultados por número Página. La numeración comienza en 0. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> Define el número de resultados de respuesta devueltos por el solicitud (el valor predeterminado es 10). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td>
   <td colname="col2">Ordena y devuelve resultados según el Propiedad JSON<span class="keyword"> especificado</span>. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Ordena y devuelve los resultados en de bajada orden. de subida opción predeterminada. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Devuelve los resultados en función de la cadena especificada que desea utilizar como parámetro búsqueda. Por ejemplo, supongamos que desea encontrar los resultados de todos los modelos que tienen la palabra "Prueba" en cualquiera de los campos de valor de ese elemento. Su solicitud de muestra podría verse gustar esto: <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>. </p> <p>Puede búsqueda cualquier valor devuelto por el método "obtener todo". </p> </td>
  </tr>
 </tbody>
</table>

### Respuesta

```
[
   {
      "destinationId":364,
      "pid":1099,
      "name":"Test",
      "description":"",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1291345192000,
      "updateTime":1291347561000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   },
   {
      "destinationId":369,
      "pid":1099,
      "name":"sample destination",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1292631706000,
      "updateTime":1292631706000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   }
]
```

## Devolver una asignación de destino con el ID de asignación {#return-dest-mapping-id}

Método `GET` que devuelve una asignación de destino individual basada en el `mappingId`método .

<!-- r_get_destination_trait_data_order.xml -->

### Pedir

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`*`<destinationMappingId>`*

### Respuesta

```
{
"mappingId": 14593,
"traitType": "SEGMENT",
"traitValue": 0,
"destinationId": 314,
"elementName": "sample",
"elementDescription": "Migration Pixel",
"elementStatus": "active",
"createTime": 1281997484000,
"updateTime": 1300752888000,
"crUID": 224,
"upUID": 308,
"sid": 80920,
"startDate": "2010-11-15",
"endDate": null,
"priority": null,
"url": "https://www.adobe.com/send?%ALIAS%",
"secureUrl": "https://www.adobe.com/send?%ALIAS%",
"tagCode": null,
"secureTagCode": null,
"traitAlias": null
}
```

## Asignaciones de regreso a destinos {#return-dest-mappings}

Método `GET` que devuelve las asignaciones de un destino.

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>La asignación devuelta es específica para el tipo de destino y la configuración.

### Pedir

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings`

>[!NOTE]
>
>Admite parámetros de paginación.

### Respuesta

```
{
   "total":354,
   "page":0,
   "pageSize":2,
   "list":[
      {
         "destinationMappingId":14395,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":224,
         "upUID":308,
         "sid":80920,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
      {
         "destinationMappingId":15934,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":242,
         "upUID":803,
         "sid":90820,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
   ]
{
```

## Devolver todas las plataformas de destino disponibles {#return-dest-platforms}

Método `GET` que devuelve todas las plataformas dispositivos disponibles para los destinos.

<!-- r_get_dest_platforms.xml -->

### Pedir

`GET /destinations/configurations/available-platforms/`

### Respuesta

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## Historial de trabajos de destino de devolución de S2S y S2S a granel {#return-job-history}

Método `GET` que devuelve información del historial de trabajos saliente [!UICONTROL Server-to-Server] ( [!UICONTROL S2S]) y de destino masivo [!UICONTROL S2S] .

<!-- r_get_job_history.xml -->

### Pedir

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Parámetros de consulta necesarios: `startDate` = *`epochtime`>* y `endDate` = *`epochtime`>*.

### Respuesta

```
[
{
      "pushID":34090,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337292466000,
      "endTime":1337292466000,
      "dataFileName":"ftp_655_269_iter_1337229891903.sync",
      "success":true
   },
   {
      "pushID":34104,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337346397000,
      "endTime":1337346397000,
      "dataFileName":"ftp_655_269_iter_1337285714581.sync",
      "success":true
   },
   {
      "pushID":34124,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337396811000,
      "endTime":1337396812000,
      "dataFileName":"ftp_655_269_iter_1337338243600.sync",
      "success":true
   }
]
```
