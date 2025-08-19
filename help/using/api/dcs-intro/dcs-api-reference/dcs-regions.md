---
description: Se requiere el nombre de la host del servidor DCS regional para realizar llamadas al DCS. Esto se debe a que el DCS almacena información en centros de datos que están geográficamente cerca de los visitantes del sitio. Sus consultas funcionarán si las envía al DCS incorrecto, pero estas llamadas son ineficientes y pueden retrasar la respuesta. Para crear un solicitud DCS, haga coincidir el ID de área geográfica con su nombre de host regional correspondiente y forme su consulta con el nombre de host adecuado.
seo-description: The regional DCS server host name is required to make calls to the DCS. This is because the DCS stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong DCS, but these calls are inefficient and can delay the response. To make a DCS request, match the region ID to its corresponding regional host name and form your query with the proper host name.
seo-title: DCS Region IDs, Locations, and Host Names
solution: Audience Manager
title: ID de región de DCS, ubicaciones y nombres de host
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
exl-id: 9b12946c-89f1-4f6f-adb9-961e15a0b816
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---

# ID de región de DCS, ubicaciones y nombres de host {#dcs-region-ids-locations-and-host-names}

Se requiere el nombre del host del servidor regional [!DNL DCS] para realizar llamadas al [!DNL DCS]. Esto se debe a que almacena [!DNL DCS] información en centros de datos que están geográficamente cerca de los visitantes del sitio. Tus consultas funcionarán si las envías a las incorrectas [!DNL DCS], pero estas llamadas son ineficientes y pueden retrasar la respuesta. Para realizar un [!DNL DCS] solicitud, haga coincidir el ID de área geográfica con su nombre de host regional correspondiente y forme su consulta con el nombre de host adecuado.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de región DCS (dcs_área geográfica) </th> 
   <th colname="col2" class="entry"> Región (y ubicación) </th> 
   <th colname="col3" class="entry"> Nombre de host </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID 3 </p> </td> 
   <td colname="col2"> <p>Sudeste Asiático (Singapur) </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 4 </p> </td> 
   <td colname="col2"> <p>Sudamérica (São Paulo, Brasil) </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 6 </p> </td> 
   <td colname="col2"> <p>Europa (Dublín, Irlanda) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Id. 7 </p> </td> 
   <td colname="col2"> <p>Este de EE. UU. (Virginia, EE. UU.) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 8 </p> </td> 
   <td colname="col2"> <p>Pacífico Sur / Oceanía (Sídney, Australia) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Id. 9 </p> </td> 
   <td colname="col2"> <p>Zona occidental de EE. UU. (Oregón, EE. UU.) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 11 </p> </td> 
   <td colname="col2"> <p>Asia (Tokio, Japón) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>Id. 12 </p> </td> 
   <td colname="col2"> <p>India </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

También puede utilizar [!DNL API] métodos para obtener una lista de las regiones disponibles [!DNL DCS] . Consulte [Métodos](../../../api/rest-api-main/aam-api-dcs-regions.md) de API de región DCS.
