---
description: En esta sección se describe cómo analizar una respuesta de DCS para recuperar los ID de visitante y región necesarios para realizar llamadas en tiempo real al DCS.
seo-description: En esta sección se describe cómo analizar una respuesta de DCS para recuperar los ID de visitante y región necesarios para realizar llamadas en tiempo real al DCS.
seo-title: Obtención de ID y regiones de usuario a partir de una respuesta de DCS
solution: Audience Manager
title: Obtención de ID y regiones de usuario a partir de una respuesta de DCS
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 17%

---


# Obtención de ID y regiones de usuario a partir de una respuesta de DCS {#get-user-ids-and-regions-from-a-dcs-response}

En esta sección se describe cómo analizar una respuesta [!DNL DCS] para recuperar los ID de visitante y región necesarios para realizar llamadas en tiempo real a [!DNL DCS].

## ID de usuario y región {#user-region-ids}

Una respuesta [!DNL DCS] contiene datos sobre los visitantes del sitio. Necesita el ID de visitante y región para poder realizar llamadas de servidor a servidor a [!DNL DCS].

* El ID de usuario es necesario para identificar y asociar datos con un visitante en particular.
* El ID de región es necesario porque está vinculado a un nombre de servidor regional, que debe enviar datos a [!DNL DCS]. El [!DNL DCS] almacena información en los centros de datos más cercanos geográficamente a los visitantes del sitio. Consulte [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) (ID de región de DCS, ubicaciones y nombres de host).

Estos parámetros se describen a continuación. El código de *cursiva* representa un marcador de posición de variable.

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
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code> </p> </td> 
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

Esta respuesta simple muestra la `UUID` y la región `ID`. Tenga en cuenta que se trata únicamente de datos de ejemplo. Los archivos de registro pueden ser más largos y complejos.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Pasos siguientes {#next-steps}

Una vez que tenga el ID de usuario y el nombre de servidor regional, puede enviar y recibir datos [!DNL DCS] en inicio. Consulte [Realización de llamadas de API de DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
