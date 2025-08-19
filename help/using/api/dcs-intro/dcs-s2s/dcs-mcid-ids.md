---
description: Los clientes del servicio de ID deben consultar esta sección para obtener información sobre cómo leer la cookie de visitante para los ID necesarios para realizar llamadas a la API de DCS.
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: Obtención de ID y regiones de usuario a través del servicio de identidad de Adobe Experience Platform
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: e17eedfb94f2936c61298c44f3d556bae254b2a7
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 2%

---

# Obtención de ID y regiones de usuario a través del servicio de identidad de Adobe Experience Platform {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Los clientes del servicio de ID deben consultar esta sección para obtener información sobre cómo leer la cookie de visitante para los ID necesarios para realizar llamadas a la API [!DNL DCS].

## Obtención del ID de usuario desde la cookie del servicio de ID {#get-user-ids-from-service-cookie}

El [servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html) asigna ID de visitante y región a los usuarios que visitan su sitio web. Estos identificadores identifican a los usuarios en todas las soluciones de [!DNL Experience Cloud] y son necesarios si desea realizar llamadas de [!DNL DCS].

* Se requiere [!UICONTROL user ID] para identificar y asociar datos con un visitante en particular.
* Se requiere el [!UICONTROL region ID] porque está vinculado a un nombre de servidor regional, que necesita para enviar datos al [!DNL DCS]. [!DNL DCS] almacena información en los centros de datos ubicados geográficamente más cerca de los visitantes del sitio. Consulte [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) (ID de región de DCS, ubicaciones y nombres de host).

Los clientes del servicio de ID pueden extraer esta información de la cookie del servicio de ID o llamando a una función. En la tabla siguiente se describen las tareas o pasos que debe completar para comenzar.

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
   <td colname="col1"> <p> <b>1. Comprueba tu <span class="keyword"> estado de Experience Cloud</span></b> </p> </td> 
   <td colname="col2"> <p>Necesita una cuenta de <span class="keyword"> Experience Cloud</span> para usar el servicio de ID. Si tiene una cuenta de <span class="keyword"> Experience Cloud</span>, ¡genial! </p> <p> Si no eres parte de <span class="keyword"> Experience Cloud</span>, entonces regístrate. Nos encantaría tenerte a ti y siempre hay espacio para más. Para obtener instrucciones sobre cómo configurar una cuenta, consulte <a href="https://experienceleague.adobe.com/en/docs/core-services/interface/services/getting-started" format="https" scope="external"> Habilitar las soluciones para los servicios principales</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Configurar el servicio de ID <span class="keyword"></span></b> </p> </td> 
   <td colname="col2"> <p>El servicio de ID <span class="keyword"></span> consiste en código JavaScript que se coloca en cada página que desee usar para la recopilación de datos. Consulte las guías de implementación del servicio de ID <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"></a> para obtener más información. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Leer la cookie <span class="keyword"> del servicio de ID </span></b> </p> </td> 
   <td colname="col2"> <p>El servicio de ID <span class="keyword"></span> almacena el ID de usuario y de región en la cookie AMCV. El nombre completo de la cookie es <code>AMCV_<i>###</i>@AdobeOrg</code>. Los elementos <code><i>###</i></code> son marcadores de posición para su ID de organización. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies y el Experience Cloud ID</a> para obtener más información. </p> <p>Analice la cookie AMCV para estos pares clave-valor: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: este par clave-valor contiene el identificador de usuario <span class="keyword"> Experience Cloud</span>. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: este par clave-valor contiene el id. de región (a veces denominado <span class="term"> indicio de ubicación </span>) que está asociado con un nombre de servidor regional. </li> 
     </ul> </p> <p>Puede realizar llamadas al DCS<span class="wintitle"> de </span> una vez que tenga los ID de usuario y región. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Recupere el Experience Cloud ID <span class="keyword"></span> con getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Opcional)</i> Esta función devuelve el ID de visitante <span class="keyword"> Experience Cloud</span>. Está diseñado para soluciones personalizadas y casos de uso específicos. Vea <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> trabajar con getMarketingCloudVisitorID</a> a continuación y la <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> documentación del servicio de ID relacionada</a>. </p> <p>No es necesario que utilice esta opción si obtiene los ID de usuario y de ubicación de la cookie del servicio de ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trabajando Con `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Otra forma de obtener el ID de visitante es con la función `getMarketingCloudVisitorID`. Cuando se invoca, esta función consulta [!DNL ID service] y devuelve un identificador. `getMarketingCloudVisitorID` acepta el argumento `callback` opcional como se muestra:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Uso y propósito de la llamada {#callback-usage}

`callback` es opcional. Esta función funciona sin ella, pero devuelve un ID solo cuando un visitante tiene una cookie [!DNL Experience Cloud] en su explorador. Si falta la cookie del visitante o si un visitante no tiene un ID, la función devuelve un objeto `()` vacío. Esto puede ocurrir incluso después de que la página se cargue y el visitante reciba un nuevo ID. Para evitarlo, `callback` fuerza a esta función a comprobar si hay un ID de visitante después de que se cargue la página. Sin `callback`, la función de ID de visitante no devolverá un ID aunque se escriba más adelante en el explorador del visitante.

## Pasos siguientes {#next-steps}

Una vez que tenga el usuario y el ID de región, podrá empezar a enviar y recibir datos de [!DNL DCS]. Consulte [Realización de llamadas a la API de DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
