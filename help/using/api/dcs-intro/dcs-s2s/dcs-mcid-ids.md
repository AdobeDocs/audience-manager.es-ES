---
description: Los clientes del servicio de ID deben consultar esta sección para obtener información sobre cómo leer la cookie del visitante para los ID necesarios para realizar llamadas a la API de DCS.
seo-description: Los clientes del servicio de ID deben consultar esta sección para obtener información sobre cómo leer la cookie del visitante para los ID necesarios para realizar llamadas a la API de DCS.
seo-title: Obtención de ID y regiones de usuario a través del servicio de identidad de Adobe Experience Platform
solution: Audience Manager
title: Obtención de ID y regiones de usuario a través del servicio de identidad de Adobe Experience Platform
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 7%

---

# Obtención de ID y regiones de usuario a través del servicio de identidad de Adobe Experience Platform {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Los clientes del servicio de ID deben consultar esta sección para obtener información sobre cómo leer la cookie del visitante para los ID necesarios para realizar [!DNL DCS] llamadas de API.

## Obtención del ID de usuario desde la cookie del servicio de ID {#get-user-ids-from-service-cookie}

El [servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html) asigna ID de visitante y región a los usuarios que llegan al sitio web. Estos ID identifican a los usuarios en todas las soluciones de [!DNL Experience Cloud] y son necesarios si desea realizar [!DNL DCS] llamadas.

* El [!UICONTROL user ID] es necesario para identificar y asociar datos con un visitante en particular.
* El [!UICONTROL region ID] es obligatorio porque está vinculado a un nombre de servidor regional, que debe enviar datos al [!DNL DCS]. El [!DNL DCS] almacena información en centros de datos geográficamente más cercanos a los visitantes del sitio. Consulte [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) (ID de región de DCS, ubicaciones y nombres de host).

Los clientes del servicio de ID pueden extraer esta información de la cookie del servicio de ID o llamando a una función . La tabla siguiente describe las tareas o los pasos que debe completar para comenzar.

El código de *cursiva* representa un marcador de posición de variable.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tarea </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Compruebe su estado <span class="keyword"> del Experience Cloud</span></b> </p> </td> 
   <td colname="col2"> <p>Necesita una cuenta <span class="keyword"> Experience Cloud</span> para utilizar el servicio de ID. Si tiene una cuenta <span class="keyword"> Experience Cloud</span>, ¡buena! </p> <p> Si no forma parte del Experience Cloud <span class="keyword"></span>, regístrese. Nos encantaría tenerte y siempre hay espacio para más. Para obtener instrucciones sobre cómo configurar una cuenta, consulte <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Activación de las soluciones para los servicios principales</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Configurar el <span class="keyword"> servicio de ID</span></b> </p> </td> 
   <td colname="col2"> <p>El <span class="keyword"> servicio de ID</span> consta de código JavaScript que se coloca en cada página que desee utilizar para la recopilación de datos. Consulte las <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> guías de implementación del servicio de ID</a> para obtener más información. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Lea la <span class="keyword"> cookie del servicio de ID</span></b> </p> </td> 
   <td colname="col2"> <p>El <span class="keyword"> servicio de ID</span> almacena el ID de usuario y región en la cookie AMCV. El nombre completo de la cookie es <code>AMCV_<i>###</i>@AdobeOrg</code>. Los elementos <code><i>###</i></code> son marcadores de posición para su ID de organización. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies y el ID de Experience Cloud</a> para obtener más información. </p> <p>Analice la cookie AMCV para estos pares clave-valor: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Este par clave-valor contiene el ID de usuario de  <span class="keyword"> Experience </span> Cloud. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Este par clave-valor contiene el ID de región (también llamado indicio de  <span class="term"> ubicación</span>) asociado a un nombre de servidor regional. </li> 
     </ul> </p> <p>Puede realizar llamadas al <span class="wintitle"> DCS</span> una vez que tenga los ID de usuario y región. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Recupere el <span class="keyword"> ID de Experience Cloud</span> con getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Opcional)</i> Esta función devuelve el ID de visitante de  <span class="keyword"> Experience </span> Cloud. Está diseñado para soluciones personalizadas y casos de uso específicos. Consulte <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Trabajo con getMarketingCloudVisitorID</a> a continuación y la <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> documentación del servicio de ID relacionada</a>. </p> <p>No es necesario que utilice esto si obtiene los ID de usuario y ubicación de la cookie del servicio de ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trabajo con `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Otra forma de obtener el ID de visitante es con la función `getMarketingCloudVisitorID` . Cuando se invoca, esta función consulta el [!DNL ID service] y devuelve un ID. `getMarketingCloudVisitorID` acepta el  `callback` argumento opcional como se muestra a continuación:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Uso y propósito de la devolución de llamada {#callback-usage}

`callback` es opcional. Esta función funciona sin él, pero devuelve un ID solo cuando un visitante tiene una cookie [!DNL Experience Cloud] en su explorador. Si falta la cookie del visitante o un visitante no tiene un ID, la función devuelve un objeto `()` vacío. Esto puede suceder incluso después de que la página se cargue y el visitante reciba un nuevo ID. Para evitar esto, `callback` fuerza a esta función a comprobar si hay un ID de visitante después de que se cargue la página. Sin `callback`, la función de ID de visitante no devolverá un ID aunque se escriba en el explorador del visitante más adelante.

## Pasos siguientes {#next-steps}

Una vez que tenga el ID de usuario y región, puede empezar a enviar y recibir datos [!DNL DCS]. Consulte [Realización de llamadas a la API DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
