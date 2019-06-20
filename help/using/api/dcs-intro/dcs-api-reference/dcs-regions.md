---
description: Se requiere el nombre de host de servidor DCS regional para realizar llamadas al DCS. Esto se debe a que el DCS almacena información en centros de datos que están geográficamente cerca de los visitantes del sitio. Las consultas funcionarán si se envían al DCS incorrecto, pero estas llamadas son ineficientes y pueden retrasar la respuesta. Para realizar una solicitud de DCS, haga coincidir el ID de región con su nombre de host regional correspondiente y forme la consulta con el nombre de host adecuado.
seo-description: Se requiere el nombre de host de servidor DCS regional para realizar llamadas al DCS. Esto se debe a que el DCS almacena información en centros de datos que están geográficamente cerca de los visitantes del sitio. Las consultas funcionarán si se envían al DCS incorrecto, pero estas llamadas son ineficientes y pueden retrasar la respuesta. Para realizar una solicitud de DCS, haga coincidir el ID de región con su nombre de host regional correspondiente y forme la consulta con el nombre de host adecuado.
seo-title: ID de región de DCS, ubicaciones y nombres de host
solution: Audience Manager
title: ID de región de DCS, ubicaciones y nombres de host
uuid: ad 150 ffe -4583-472 b-ac 8 b-fb 900 a 7966 e 4
translation-type: tm+mt
source-git-commit: 51a326d0ac02175e0e1452e0a00b4a3a415d88ff

---


# DCS Region IDs, Locations, and Host Names {#dcs-region-ids-locations-and-host-names}

The regional [!UICONTROL DCS] server host name is required to make calls to the [!UICONTROL DCS]. This is because the [!UICONTROL DCS] stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong [!UICONTROL DCS], but these calls are inefficient and can delay the response. To make a [!UICONTROL DCS] request, match the region ID to its corresponding regional host name and form your query with the proper host name.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de región DCS (dcs_ region) </th> 
   <th colname="col2" class="entry"> Región (y ubicación) </th> 
   <th colname="col3" class="entry"> Nombre de host </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID3 </p> </td> 
   <td colname="col2"> <p>Sudeste Asia (Singapur) </p> </td> 
   <td colname="col3"> <p> <code> apse. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID4 </p> </td> 
   <td colname="col2"> <p>América del Sur (São Paulo, Brasil) </p> </td> 
   <td colname="col3"> <p> <code> sae. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID6 </p> </td> 
   <td colname="col2"> <p>Europa (Dublín, Irlanda) </p> </td> 
   <td colname="col3"> <p> <code> irl 1. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>EE. UU. (Virginia, EE. UU.) </p> </td> 
   <td colname="col3"> <p> <code> use. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>South Pacífico/Oceanía (Sídney, Australia) </p> </td> 
   <td colname="col3"> <p> <code> apse 2. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>EE. UU Oeste (Oregón, EE. UU.) </p> </td> 
   <td colname="col3"> <p> <code> usw 2. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>Asia (Tokio, Japón) </p> </td> 
   <td colname="col3"> <p> <code> tyo 3. demdex. net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>India </p> </td> 
   <td colname="col3"> <p> <code> ind 1. demdex. net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

You can also use [!DNL API] methods to get a list of the available [!UICONTROL DCS] regions. See [DCS Region API Methods](../../../api/rest-api-main/aam-api-dcs-regions.md).