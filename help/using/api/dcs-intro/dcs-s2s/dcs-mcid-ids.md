---
description: Los clientes del servicio de ID deben consultar esta sección para obtener información sobre cómo leer la cookie de visitante para los ID necesarios para realizar llamadas a la API de DCS.
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: Obtención de ID y regiones de usuario a través del servicio de identidad de Adobe Experience Platform
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 6%

---

# Obtención de ID y regiones de usuario a través del servicio de identidad de Adobe Experience Platform {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Los clientes del servicio de ID deben consultar esta sección para obtener información sobre cómo leer la cookie de visitante para los ID necesarios para realizar [!DNL DCS] Llamadas de API.

## Obtención del ID de usuario desde la cookie del servicio de ID {#get-user-ids-from-service-cookie}

El [Servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html) asigna ID de visitante y región a los usuarios que visitan el sitio web. Estos ID identifican a los usuarios en todas las soluciones de [!DNL Experience Cloud] y son necesarios si desea realizar una [!DNL DCS] llamadas.

* El [!UICONTROL user ID] es necesario para identificar y asociar datos con un visitante en particular.
* El [!UICONTROL region ID] es obligatorio porque está vinculado a un nombre de servidor regional, que debe enviar datos a la [!DNL DCS]. El [!DNL DCS] almacena información en centros de datos ubicados geográficamente más cerca de los visitantes del sitio. Consulte [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) (ID de región de DCS, ubicaciones y nombres de host).

Los clientes del servicio de ID pueden extraer esta información de la cookie del servicio de ID o llamando a una función. En la tabla siguiente se describen las tareas o pasos que debe completar para comenzar.

Código en *cursiva* representa un marcador de posición variable.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tarea </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Compruebe su <span class="keyword"> Experience Cloud</span> status</b> </p> </td> 
   <td colname="col2"> <p>Necesita un <span class="keyword"> Experience Cloud</span> para utilizar el servicio de ID. Si tiene un <span class="keyword"> Experience Cloud</span> cuenta, bueno! </p> <p> Si no eres parte de la <span class="keyword"> Experience Cloud</span>, luego regístrese. Nos encantaría tenerte a ti y siempre hay espacio para más. Para obtener instrucciones sobre cómo configurar una cuenta, consulte <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Activación de las soluciones en los servicios principales</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Configure las variables <span class="keyword"> Servicio de ID</span></b> </p> </td> 
   <td colname="col2"> <p>El <span class="keyword"> Servicio de ID</span> consiste en código JavaScript que se coloca en cada página que desea utilizar para la recopilación de datos. Consulte el servicio de ID <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> guías de implementación</a> para obtener más información. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Lea el <span class="keyword"> Servicio de ID</span> cookie</b> </p> </td> 
   <td colname="col2"> <p>El <span class="keyword"> Servicio de ID</span> Almacena el ID de usuario y región en la cookie AMCV. El nombre completo de la cookie es <code>AMCV_<i>###</i>@AdobeOrg</code>. El <code><i>###</i></code> son marcadores de posición para su ID de organización. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies y el ID de Experience Cloud</a> para obtener más información. </p> <p>Analice la cookie AMCV para estos pares clave-valor: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: este par clave-valor contiene el <span class="keyword"> Experience Cloud</span> ID de usuario. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: este par clave-valor contiene el ID de región (a veces denominado <span class="term"> indicio de ubicación</span>) que está asociado con un nombre de servidor regional. </li> 
     </ul> </p> <p>Puede realizar llamadas al <span class="wintitle"> DCS</span> una vez que tenga los ID de usuario y de región. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Recupere el <span class="keyword"> ID de Experience Cloud</span> con getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Opcional)</i> Esta función devuelve el valor <span class="keyword"> Experience Cloud</span> ID de visitante. Está diseñado para soluciones personalizadas y casos de uso específicos. Consulte <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Uso de getMarketingCloudVisitorID</a> abajo y el <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> documentación del servicio de ID relacionado</a>. </p> <p>No es necesario que utilice esta opción si obtiene los ID de usuario y de ubicación de la cookie del servicio de ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Uso de `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Otra forma de obtener el ID de visitante es con `getMarketingCloudVisitorID` función. Cuando se invoca, esta función consulta el [!DNL ID service] y devuelve un ID. `getMarketingCloudVisitorID` acepta el opcional `callback` como se muestra:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Uso y propósito de la llamada {#callback-usage}

`callback` es opcional. Esta función funciona sin ella, pero devuelve un ID solo cuando un visitante tiene un [!DNL Experience Cloud] en su explorador. Si falta la cookie del visitante o si un visitante no tiene un ID, la función devuelve un vacío `()` objeto. Esto puede ocurrir incluso después de que la página se cargue y el visitante reciba un nuevo ID. Para evitarlo, `callback` fuerza a esta función a comprobar si hay un ID de visitante después de cargar la página. Sin `callback`Sin embargo, la función de ID de visitante no devolverá un ID aunque se escriba más adelante en el explorador del visitante.

## Pasos siguientes {#next-steps}

Una vez que tenga el ID de usuario y de región, puede empezar a enviar y recibir [!DNL DCS] datos. Consulte [Realización de llamadas API de DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
