---
description: Los clientes del servicio de ID deben consultar esta sección para obtener información sobre cómo leer la cookie de visitante para los ID necesarios para realizar llamadas de API de DCS.
seo-description: Los clientes del servicio de ID deben consultar esta sección para obtener información sobre cómo leer la cookie de visitante para los ID necesarios para realizar llamadas de API de DCS.
seo-title: Obtención de ID y regiones de usuario a través del servicio de identidad de Adobe Experience Platform
solution: Audience Manager
title: Obtención de ID y regiones de usuario a través del servicio de identidad de Adobe Experience Platform
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 9%

---


# Obtención de ID y regiones de usuario a través del servicio de identidad de Adobe Experience Platform {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Los clientes del servicio de ID deben consultar esta sección para obtener información sobre cómo leer la cookie de visitante para los ID necesarios para realizar llamadas [!DNL DCS] de API.

## Obtener el ID de usuario de la cookie del servicio de ID {#get-user-ids-from-service-cookie}

El servicio [de identidad de](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html) Adobe Experience Platform asigna ID de visitante y región a los usuarios que visitan el sitio web. Estos ID identifican a los usuarios en todas las soluciones del [!DNL Experience Cloud] y son necesarios si desea realizar [!DNL DCS] llamadas.

* El [!UICONTROL user ID] requisito es identificar y asociar datos con un visitante en particular.
* El [!UICONTROL region ID] se requiere porque está vinculado a un nombre de servidor regional, que debe enviar datos al [!DNL DCS]. El [!DNL DCS] almacena información en centros de datos geográficamente más cercanos a los visitantes del sitio. Consulte [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) (ID de región de DCS, ubicaciones y nombres de host).

Los clientes del servicio de ID pueden extraer esta información de la cookie del servicio de ID o llamando a una función. En la tabla siguiente se describen las tareas o pasos que debe completar para comenzar.

El código en *cursiva* representa un marcador de posición de variable.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tarea </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Compruebe el estado <span class="keyword"> del Experience Cloud</span></b> </p> </td> 
   <td colname="col2"> <p>Necesita una cuenta de <span class="keyword"> Experience Cloud</span> para utilizar el servicio de ID. Si tiene una cuenta de <span class="keyword"> Experience Cloud</span> , ¡bueno! </p> <p> Si no eres parte del <span class="keyword"> Experience Cloud</span>, regístrate. Nos encantaría tenerte y siempre hay espacio para más. Para obtener instrucciones sobre cómo configurar una cuenta, consulte <a href="https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Activación de soluciones para servicios</a>principales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Set up the <span class="keyword"> ID service</span></b> </p> </td> 
   <td colname="col2"> <p>El servicio <span class="keyword"> de</span> ID consta de código JavaScript que se coloca en cada página que desee utilizar para la recopilación de datos. Consulte las guías <a href="https://docs.adobe.com/content/help/en/id-service/using/implementation/implementation-guides.html" format="https" scope="external"></a> de implementación del servicio de ID para obtener más información. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Lea la cookie del servicio <span class="keyword"> de</span> ID</b> </p> </td> 
   <td colname="col2"> <p>El servicio <span class="keyword"> de</span> ID almacena el ID de usuario y región en la cookie AMCV. El nombre completo de la cookie es <code>AMCV_<i>###</i>@AdobeOrg</code>. Los <code><i>###</i></code> elementos son marcadores de posición para su ID de organización. See <a href="https://docs.adobe.com/content/help/es-ES/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>Analice la cookie AMCV para estos pares clave-valor: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>:: Este par clave-valor contiene el ID de usuario del <span class="keyword"> Experience Cloud</span> . </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>:: Este par clave-valor contiene el ID de región (a veces llamado indicio <span class="term"></span>de ubicación), que está asociado con un nombre de servidor regional. </li> 
     </ul> </p> <p>Puede realizar llamadas al <span class="wintitle"> DCS</span> una vez que tenga los ID de usuario y región. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Recuperar el ID <span class="keyword"> del</span> Experience Cloud con getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Opcional)</i> Esta función devuelve el ID de visitante del <span class="keyword"> Experience Cloud</span> . Está diseñado para soluciones personalizadas y casos de uso específicos. Consulte <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Uso de getMarketingCloudVisitorID</a> a continuación y la documentación <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> del servicio de ID</a>relacionada. </p> <p>No es necesario que utilice esto si obtiene los ID de usuario y ubicación de la cookie del servicio de ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trabajar con `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Otra forma de obtener el ID de visitante es con la `getMarketingCloudVisitorID` función. Cuando se invoca, esta función consulta el [!DNL ID service] y devuelve un ID. `getMarketingCloudVisitorID` acepta el `callback` argumento opcional como se muestra a continuación:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Uso y propósito de la llamada de retorno {#callback-usage}

`callback` es opcional. Esta función funciona sin ella, pero devuelve un ID únicamente cuando un visitante tiene una [!DNL Experience Cloud] cookie en su explorador. Si falta la cookie de visitante o un visitante no tiene un ID, la función devuelve un `()` objeto vacío. Esto puede suceder incluso después de que la página se cargue y el visitante reciba un nuevo ID. Para evitarlo, `callback` fuerza a esta función a buscar un ID de visitante después de que se cargue la página. Sin `callback`, la función de ID de visitante no devolverá un ID aunque se haya escrito más tarde en el navegador del visitante.

## Pasos siguientes {#next-steps}

Una vez que tenga el ID de usuario y región, puede enviar y recibir [!DNL DCS] datos en inicio. Consulte [Realización de llamadas](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)de API de DCS.