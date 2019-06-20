---
description: En esta sección se describe cómo analizar una respuesta de DCS para recuperar los ID de región y visitante necesarios para realizar llamadas en tiempo real al DCS.
seo-description: En esta sección se describe cómo analizar una respuesta de DCS para recuperar los ID de región y visitante necesarios para realizar llamadas en tiempo real al DCS.
seo-title: Obtención de ID de usuario y regiones desde una respuesta de DCS
solution: Audience Manager
title: Obtención de ID de usuario y regiones desde una respuesta de DCS
uuid: 08036045-3 b 26-4 d 40-8 e 94-7 d 0884048683
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions From a DCS Response {#get-user-ids-and-regions-from-a-dcs-response}

This section describes how to parse a [!UICONTROL DCS] response to retrieve the visitor and region IDs required to make real-time calls to the [!UICONTROL DCS].

## User and Region IDs {#user-region-ids}

[!UICONTROL DCS] Una respuesta contiene datos sobre los visitantes del sitio. You need the visitor and region ID before you can make server-to-server calls to the [!UICONTROL DCS].

* El ID de usuario es necesario para identificar y asociar datos con un visitante concreto.
* The region ID is required because it is tied to a regional server name, which you need to send data to the [!UICONTROL DCS]. The [!UICONTROL DCS] stores information in data centers that are geographically closest to site visitors. Consulte [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) (ID de región de DCS, ubicaciones y nombres de host).

Estos parámetros se describen a continuación. Code in *italics* represents a variable placeholder.

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Tipo de datos </th> 
   <th colname="col3" class="entry"> Ejemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>" uuid ": <i>ID de usuario</i></code></span> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p> <code> " uuid ": " 123456789 "</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>" dcs_ region ":<i>ID de región</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> " dcs_ region ": 9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Respuesta de ejemplo {#sample-response}

This simple response shows the `UUID` and region `ID`. Tenga en cuenta que solo son datos de ejemplo. Los archivos de registro pueden ser más largos y complejos.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Pasos siguientes {#next-steps}

Once you have the user ID and regional server name, you can start sending and receiving [!UICONTROL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
