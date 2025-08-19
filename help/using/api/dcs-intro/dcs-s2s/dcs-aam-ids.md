---
description: En esta sección se describe cómo analizar una respuesta del DCS para recuperar los ID de visitante y área geográfica necesarios para realizar llamadas en tiempo real al DCS.
seo-description: This section describes how to parse a DCS response to retrieve the visitor and region IDs required to make real-time calls to the DCS.
seo-title: Get User IDs and Regions From a DCS Response
solution: Audience Manager
title: Obtención de ID y regiones de usuario a partir de una respuesta de DCS
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
exl-id: 3c0c5e57-2d59-4938-9bbd-761495142c31
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 7%

---

# Obtención de ID y regiones de usuario a partir de una respuesta de DCS {#get-user-ids-and-regions-from-a-dcs-response}

En esta sección se describe cómo analizar una [!DNL DCS] respuesta para recuperar los ID de visitante y área geográfica necesarios para realizar llamadas en tiempo real al [!DNL DCS].

## ID de usuario y región {#user-region-ids}

Una [!DNL DCS] respuesta contiene datos sobre los visitantes del sitio. Necesitará el ID de visitante y área geográfica para poder realizar llamadas de servidor a servidor al [!DNL DCS].

* El ID de usuario es necesario para identificar y asociar datos con un visitante determinado.
* El ID de área geográfica es necesario porque está vinculado a un nombre de servidor regional, que necesita para enviar datos al [!DNL DCS]. Almacena [!DNL DCS] información en los centros de datos que están geográficamente más cerca de los visitantes del sitio. Consulte [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) (ID de región de DCS, ubicaciones y nombres de host).

Estos parámetros se describen a continuación. Code en *cursiva representa un marcador de* posición variable.

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
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code></span> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Respuesta de ejemplo {#sample-response}

Esta sencilla respuesta muestra el `UUID` y área geográfica `ID`. Tenga en cuenta que solo se trata de datos de ejemplo. Los archivos de registro podrían ser más largos y complejos.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Pasos siguientes {#next-steps}

Una vez que tenga el ID de usuario y el nombre del servidor regional, puede inicio enviar y recibir [!DNL DCS] datos. Consulte [Realización de llamadas a la API de DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
