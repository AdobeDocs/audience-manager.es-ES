---
description: El nombre de host del servidor DCS regional es necesario para realizar llamadas al DCS. Esto se debe a que el DCS almacena información en centros de datos geográficamente cercanos a los visitantes del sitio. Sus consultas funcionarán si las envía al DCS incorrecto, pero estas llamadas son ineficientes y pueden retrasar la respuesta. Para realizar una solicitud de DCS, combine el ID de región con el nombre de host regional correspondiente y forme la consulta con el nombre de host adecuado.
seo-description: El nombre de host del servidor DCS regional es necesario para realizar llamadas al DCS. Esto se debe a que el DCS almacena información en centros de datos geográficamente cercanos a los visitantes del sitio. Sus consultas funcionarán si las envía al DCS incorrecto, pero estas llamadas son ineficientes y pueden retrasar la respuesta. Para realizar una solicitud de DCS, combine el ID de región con el nombre de host regional correspondiente y forme la consulta con el nombre de host adecuado.
seo-title: ID de región de DCS, ubicaciones y nombres de host
solution: Audience Manager
title: ID de región de DCS, ubicaciones y nombres de host
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 9%

---


# ID de región de DCS, ubicaciones y nombres de host {#dcs-region-ids-locations-and-host-names}

El nombre de host del servidor [!DNL DCS] regional es necesario para realizar llamadas al [!DNL DCS]. Esto se debe a que [!DNL DCS] almacena información en los centros de datos que están geográficamente cerca de los visitantes del sitio. Sus consultas funcionarán si las envía a un [!DNL DCS] incorrecto, pero estas llamadas son ineficientes y pueden retrasar la respuesta. Para realizar una solicitud [!DNL DCS], haga coincidir el ID de región con el nombre de host regional correspondiente y forme la consulta con el nombre de host adecuado.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de región de DCS (dcs_region) </th> 
   <th colname="col2" class="entry"> Región (y ubicación) </th> 
   <th colname="col3" class="entry"> Nombre del host </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID3 </p> </td> 
   <td colname="col2"> <p>Sudeste de Asia (Singapur) </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID4 </p> </td> 
   <td colname="col2"> <p>Sudamérica (São Paulo, Brasil) </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID6 </p> </td> 
   <td colname="col2"> <p>Europa (Dublín, Irlanda) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>EE.UU. Este (Virginia, EE.UU.) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>Pacífico Sur/Oceanía (Sydney, Australia) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>Oeste de EE.UU. (Oregón, EE.UU.) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>Asia (Tokio, Japón) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>India </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

También puede utilizar métodos [!DNL API] para obtener una lista de las regiones [!DNL DCS] disponibles. Consulte [Métodos de API de región DCS](../../../api/rest-api-main/aam-api-dcs-regions.md).