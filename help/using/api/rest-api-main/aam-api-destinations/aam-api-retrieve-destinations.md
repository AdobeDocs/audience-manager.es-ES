---
description: Método GET que devuelve el destino para el destino especificado.
seo-description: Método GET que devuelve el destino para el destino especificado.
seo-title: Devolver destino por ID de destino
solution: Audience Manager
title: Devolver destino por ID de destino
uuid: abce 7426-55 a 5-4045-93 a 7-0487652 a 7189
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Return A Destination by Destination ID {#return-a-destination-by-destination-id}

`GET` Método que devuelve el destino del especificado `destinationId`.

<!-- r_get_all_destinations_order_id.xml -->

## Solicitud

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>To populate the `mappings` field pass in `includeMappings=true` in the URL.

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

## Return All Destinations {#return-all-destinations}

`GET` Método que devuelve todos los destinos del socio especificado.

<!-- r_get_all_destinations.xml -->

### Solicitud

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *(Opcional)* Pase `containsSegment=<sid>` para devolver una matriz de todos los destinos asignados al segmento especificado. For example, your query could look similar to this: `GET .../destinations/?containsSegment=4321`.
   >
   >
* No devuelve el objeto de destino completo. Obtenga el destino por orden de datos si necesita un objeto totalmente rellenado.


### Parámetros de consulta opcionales

You can use these optional parameters with API methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. See [Optional Parameters](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> Devuelve resultados por número de página. La numeración comienza en 0. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> Pagesize</code> </td>
   <td colname="col2"> Define el número de resultados de respuesta devueltos por la solicitud (10 es predeterminado). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> Sortby</code> </td>
   <td colname="col2">Sorts and returns results according to the specified <span class="keyword"> JSON</span> property. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descendente</code> </td>
   <td colname="col2"> Ordena y devuelve resultados en orden descendente. Ascendente es predeterminado. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> buscar</code> </td>
   <td colname="col2">Devuelve resultados basados en la cadena especificada que se desea utilizar como parámetro de búsqueda. Por ejemplo, supongamos que desea encontrar resultados para todos los modelos que tengan la palabra "Test" en cualquiera de los campos de valor de dicho elemento. Su solicitud de ejemplo podría verse así: <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>. </p> <p>Puede buscar cualquier valor devuelto por el método "get all". </p> </td>
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

## Return a Destination Mapping With the Mapping ID {#return-dest-mapping-id}

`GET` Método que devuelve una asignación de destino individual basada en `mappingId`la.

<!-- r_get_destination_trait_data_order.xml -->

### Solicitud

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

## Return Destination Mappings {#return-dest-mappings}

`GET` Método que devuelve las asignaciones de un destino.

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>La asignación devuelta es específica del tipo de destino y la configuración.

### Solicitud

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

## Return All Available Destination Platforms {#return-dest-platforms}

`GET` Método que devuelve todas las plataformas de dispositivo disponibles para destinos.

<!-- r_get_dest_platforms.xml -->

### Solicitud

`GET /destinations/configurations/available-platforms/`

### Respuesta

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## Return S2S and Bulk S2S Destination Job History {#return-job-history}

`GET` Método que devuelve información de historial de trabajo de destino saliente [!UICONTROL Server-to-Server] ( [!UICONTROL S2S]) y de [!UICONTROL S2S] destino masivo.

<!-- r_get_job_history.xml -->

### Solicitud

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Required query parameters: `startDate` = *&lt;`epochtime`&gt;* and `endDate` = *&lt;`epochtime`&gt;*.

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
