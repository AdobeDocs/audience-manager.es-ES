---
description: Se requiere el nombre de host del servidor DCS regional para realizar llamadas al DCS. Esto se debe a que el DCS almacena información en centros de datos ubicados geográficamente cerca de los visitantes del sitio. Sus consultas funcionarán si las envía al DCS incorrecto, pero estas llamadas son ineficientes y pueden retrasar la respuesta. Para realizar una solicitud de DCS, combine el ID de región con su nombre de host regional correspondiente y forme la consulta con el nombre de host adecuado.
seo-description: The regional DCS server host name is required to make calls to the DCS. This is because the DCS stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong DCS, but these calls are inefficient and can delay the response. To make a DCS request, match the region ID to its corresponding regional host name and form your query with the proper host name.
seo-title: DCS Region IDs, Locations, and Host Names
solution: Audience Manager
title: ID de región de DCS, ubicaciones y nombres de host
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
exl-id: 9b12946c-89f1-4f6f-adb9-961e15a0b816
TQID: https://experienceleague.adobe.com/1oK9TLEwbGO-6r9Hempmz8Al6AIYVFkdpKB-ya2UBWw
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: d8f681b8-67cc-42dc-85c5-a0977528a942
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 234
ht-degree: 0%

---

# ID de región de DCS, ubicaciones y nombres de host {#dcs-region-ids-locations-and-host-names}

Se requiere el nombre de host del servidor regional [!DNL DCS] para realizar llamadas a [!DNL DCS]. Esto se debe a que [!DNL DCS] almacena información en centros de datos ubicados geográficamente cerca de los visitantes del sitio. Sus consultas funcionarán si las envía a un(a) [!DNL DCS] incorrecto(a), pero estas llamadas son ineficientes y pueden retrasar la respuesta. Para realizar una solicitud de [!DNL DCS], combine el ID de región con su nombre de host regional correspondiente y forme la consulta con el nombre de host adecuado.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de región DCS (dcs_region) </th> 
   <th colname="col2" class="entry"> Región (y ubicación) </th> 
   <th colname="col3" class="entry"> Nombre de host </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID 3 </p> </td> 
   <td colname="col2"> <p>Sudeste de Asia (Singapur) </p> </td> 
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
   <td colname="col1"> <p>ID 7 </p> </td> 
   <td colname="col2"> <p>Este de Estados Unidos (Virginia, EE. UU.) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 8 </p> </td> 
   <td colname="col2"> <p>Pacífico Sur / Oceanía (Sídney, Australia) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 9 </p> </td> 
   <td colname="col2"> <p>Zona occidental de Estados Unidos (Oregón, EE.UU.) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 11 </p> </td> 
   <td colname="col2"> <p>Asia (Tokio, Japón) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID 12 </p> </td> 
   <td colname="col2"> <p>India </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

También puede usar [!DNL API] métodos para obtener una lista de las [!DNL DCS] regiones disponibles. Consulte [Métodos de API de región DCS](../../../api/rest-api-main/aam-api-dcs-regions.md).
