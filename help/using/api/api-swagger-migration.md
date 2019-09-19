---
description: Aquí en Audience Manager somos ingenieros, desarrolladores y ninjas de código como usted. Y, como usted, queremos trabajar con documentación de API confiable y precisa. Como resultado, estamos reescribiendo el contenido de nuestra API en Swagger y moviéndolo a una nueva ubicación. Estos cambios están diseñados para ayudar a mejorar su experiencia con el código de API de Audience Manager.
seo-description: Aquí en Audience Manager somos ingenieros, desarrolladores y ninjas de código como usted. Y, como usted, queremos trabajar con documentación de API confiable y precisa. Como resultado, estamos reescribiendo el contenido de nuestra API en Swagger y moviéndolo a una nueva ubicación. Estos cambios están diseñados para ayudar a mejorar su experiencia con el código de API de Audience Manager.
seo-title: Migración de código de API de Audience Manager
solution: Audience Manager
title: Migración de código de API de Audience Manager
uuid: 93cc28c4-4b91-4c79-93d5-ece9bb4cc9d5
translation-type: tm+mt
source-git-commit: d368699d0de9a43cb7cf2c1af64da941a811db71

---


# Audience Manager API Code Migration {#audience-manager-api-code-migration}

Aquí en Audience Manager somos ingenieros, desarrolladores y ninjas de código como usted. Y, como ustedes, queremos trabajar con [!DNL API] documentación confiable y precisa. Como resultado, estamos reescribiendo nuestro [!DNL API] contenido [!DNL Swagger] y moviéndolo a una nueva ubicación. Estos cambios están diseñados para ayudar a mejorar su experiencia con el código de Audience Manager [!DNL API] .

## Subir {#code-migration-details}

<!-- api-swagger-migration.xml -->

El sitio de documentos [de API de](https://bank.demdex.com/portal/swagger/index.html) Adobe Audience Manager es la nueva página de inicio de nuestro contenido revisado [!DNL API] . Intentaremos reescribir y mover algunos conjuntos de [!DNL API] métodos con cada versión. Esto significa que tendrá que comprobar la nueva ubicación y la documentación de la API [de](../api/rest-api-main/rest-api-main.md) REST para encontrar todos los métodos disponibles. Al final, todos los ciudadanos [!DNL API]estarán en el [!DNL Audience Manager] sitio [!DNL API] de documentos. En la tabla siguiente se enumeran las versiones revisadas y [!DNL API]las migradas.

<table id="table_CD3C244CB02C48C898745FB982EC828C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de API </th> 
   <th colname="col2" class="entry"> Métodos de API </th> 
  </tr> 
 </thead>
 <tbody>
 <tr> 
   <td colname="col1"> <p> <b>Modelos algorítmicos</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API" format="https" scope="external"> Modelos algorítmicos</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Marketplace</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4CFB3FAAC0B04E5AADD80E7D7FAF2722"> 
      <li id="li_50EE5F6B2278480E9FEA04AD51664F9D"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_API" format="https" scope="external"> Archivo de fuentes de datos</a> </li> 
      <li id="li_5D372E3819014AB78C12048A9A2DC89F"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Request_API/" format="https" scope="external"> Solicitud de fuente de datos</a> </li> 
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> Finanzas de fuentes de datos</a> </li> 
      <li id="li_C1C1CB42D6A74803B4672F6EE2D2D08C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Plans_API" format="https" scope="external"> Planes de fuentes de datos</a> </li> 
      <li id="li_D8F9D791D0824287B9D0B0585E3106AB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Subscription_API" format="https" scope="external"> Suscripciones a fuentes de datos</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Fuente de datos</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Source_API" format="https" scope="external"> Fuentes de datos</a> </p> </td> 
  </tr> 
   <td colname="col1"> <p> <b>Señales derivadas</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Derived_Signals_API" format="https" scope="external"> Señales derivadas</a> </p> </td> 
  </tr>   
  <tr> 
   <td colname="col1"> <p> <b>Carpetas</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FD05673B372141F3B0EF2C79A338F744"> 
      <li id="li_5D16FCAF6F0E411694A1CFBE9571BDAC"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Folder_API" format="https" scope="external"> Carpetas de segmento</a> </li> 
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> Carpetas de características</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Informes</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Reporting_API" format="https" scope="external"> Informes</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentos</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_098B0655653D4846B70349A35A055C19"> 
      <li id="li_41A3003BF41147969BC88D4F12A5C1BB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segments_API" format="https" scope="external"> Segmentos</a> </li> 
      <li id="li_22A858D377634D88AE58BE2CE924169C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_API/" format="https" scope="external"> Grupos de prueba de segmentos</a> </li> 
      <li id="li_2B505A1B43CF4B29A0336106C321E7FD"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_Draft_API/" format="https" scope="external"> API de borrador del grupo de prueba de segmentos</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Características</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Traits_API" format="https" scope="external"> Características</a> </p> </td> 
  </tr>
 </tbody>
</table>