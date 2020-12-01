---
description: Recommendations y casos de uso para la prospección, resegmentación y personalización de usuarios desconocidos con un gráfico de dispositivos externo. Un gráfico de dispositivo externo se define como un gráfico de dispositivo independiente del Audience Manager. Esto incluye Adobe Experience Cloud Device Co-op y otras integraciones que el Adobe tiene con compañías de gráficos de dispositivos probabilísticos o determinísticos de terceros.
seo-description: Recommendations y casos de uso para la prospección, resegmentación y personalización de usuarios desconocidos con un gráfico de dispositivos externo. Un gráfico de dispositivo externo se define como un gráfico de dispositivo independiente del Audience Manager. Esto incluye Adobe Experience Cloud Device Co-op y otras integraciones que el Adobe tiene con compañías de gráficos de dispositivos probabilísticos o determinísticos de terceros.
seo-title: Ejemplos de uso de los Gráficos de dispositivos externos
solution: Audience Manager
title: Ejemplos de uso de los Gráficos de dispositivos externos
uuid: f4bc822d-39d2-4680-90ed-7ee2ead6db6f
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 5%

---


# Ejemplos de uso de los Gráficos de dispositivos externos {#external-device-graph-use-cases}

Recommendations y casos de uso para la prospección, resegmentación y personalización de usuarios desconocidos con un gráfico de dispositivos externo. Un gráfico de dispositivo externo se define como un gráfico de dispositivo independiente del Audience Manager. Esto incluye el [!DNL Adobe Experience Cloud Device Co-op] y otras integraciones que el Adobe tiene con compañías de gráficos de dispositivos probabilísticos o determinísticos de terceros.

## Recomendaciones {#recommendations}

Considere las opciones de gráficos de dispositivos [!DNL Experience Cloud Device Co-op] y de terceros para campañas que:

* Tener un bajo nivel de autenticación en sus propiedades digitales. Utilice [!UICONTROL Profile Link Device Graph option] si tiene un gran número de usuarios autenticados.
* Destinatario grandes audiencias. Los gráficos de dispositivos [!DNL Experience Cloud Device Co-op] y de terceros contienen datos autenticados y no autenticados.
* Segmentar visitantes autenticados y/o no autenticados a nivel individual y doméstico.

![](assets/merge-rule-triangle1.png)
<!-- 
## Prospecting/Branding Use Case {#prospecting-branding-use-cases}

A branding campaign is designed to reach as many people as possible. It places few limits on segment qualification. But, these campaigns can waste budget and impressions by constantly targeting people who see your content multiple times and don't convert. A [!UICONTROL Profile Merge] rule that uses the [!DNL Device Co-op] or third-party option can help you create an efficient branding campaign. For example, you can add these unknown users to a "not in-market" segment after seeing them across multiple devices for your set frequency cap.

<table id="table_00F6EED172574E80A38CADA8A92A23B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2">This use case assumes these conditions: <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">You want to deliver a maximum of 10 impressions to an anonymous user for a specific ad campaign. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">A user has 4 devices and may or may not have authenticated on your site. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">An anonymous user sees the ad a total of 10 times while browsing in an unauthenticated state on their current device and 3 devices linked to the current device by an external device graph. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify anonymous users after they have seen 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Merges the anonymous, unauthenticated activity collected from the current device and the 3 devices linked by the external device graph (the ad impressions from each device). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Evaluates the unauthenticated user for segment qualification based on a combination of anonymous activity across all 3 devices linked by the external device graph and the current device. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Sends the segment to any real-time destination for use as a suppression segment on the current device and all 3 devices linked by the external device graph. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retargeting or Site Personalization Use Case {#retargeting-use-case}

These strategies are designed to bring an unauthenticated or unknown user back to your site or personalize their browsing experience while they're on-site.

<table id="table_0EE2052AA3E744B3B76036FC06B5A453"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2">This use case assumes these conditions: <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">You want to deliver a personalized on-site and/or off-site experience to an anonymous user based on their activity on your site while in an unauthenticated state. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">A user has multiple devices and may or may not have authenticated to your site. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">A user views multiple pages on your site while browsing in an unauthenticated state on their current device and 3 other devices linked by an external device graph. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify users after they have viewed multiple pages on your site while browsing in an unauthenticated state.</li>
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Merges the anonymous, unauthenticated activity collected from the current devices and the 3 devices linked by the external device graph (the multiple page views from each device). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Evaluates the unauthenticated user for segment qualification based on a combination of anonymous activity across all 3 devices linked by the external device graph and the current device. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Sends the segment to any real-time destination to deliver a personalized on-site and/or off-site experience across the current device and all 3 devices linked by the external device graph. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table> -->

## Objetivo de dispositivo ampliado {#audience-expansion}

Este caso de uso ejemplifica cómo puede expandir el tamaño de la audiencia direccionable con una personalización precisa entre dispositivos, a través de [!DNL Adobe Co-Op Device Graph] u otro [!DNL External Device Graphs].

Supongamos que Jane posee tres dispositivos que usa regularmente para buscar ofertas de paquetes de vacaciones: su portátil ([!DNL Device 1]), su smartphone ([!DNL Device 2]) y su tablet ([!DNL Device 3]). Mientras usaba el portátil, Jane buscaba vuelos, hoteles y visitas guiadas. Mientras usaba el smartphone y la tableta, solo visitó la página de inicio de la agencia de viajes.

Al utilizar la regla [!UICONTROL No Cross-Device Profile] + [!UICONTROL Adobe Co-op Device Graph], la agencia de viajes puede combinar los tres perfiles de dispositivos, ya que están vinculados al mismo propietario a través de [!UICONTROL Adobe Co-op Device Graph].

![Regla de expansión de audiencia](assets/audience-expansion-rule.png)

En nuestro ejemplo, las características requeridas para calificar para el segmento se recopilaron en [!DNL Device 1]. Dado que Audience Manager califica todos los perfiles de dispositivo que participaron en la combinación de perfiles para un segmento, los tres perfiles de dispositivo de Jane ahora están segmentados.

A través de esta regla, el gráfico de dispositivos ha ampliado el número de perfiles de dispositivos que califican para el segmento de uno a tres y ha permitido a la agencia de viajes entregar un mensaje coherente a los tres dispositivos propiedad de Jane.

![audiencia-expansión](assets/audience-expansion.png)

## Targeting cruzado de dispositivos avanzado {#advanced-graph-expansion}

Este caso de uso muestra cómo puede expandir el objetivo de audiencias para visitantes autenticados con dispositivos desde un gráfico de dispositivos externo o desde [!DNL Adobe Co-Op Device Graph], mediante la regla **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Adobe Co-Op Device Graph]**.

![último dispositivo-gráfico](assets/last-device-coop.png)

En el ejemplo siguiente, la compañía Acme Inc. desea destinatario a todos los hogares con ingresos superiores a 100.000 dólares al año, que tienen [!DNL Acme Inc.] suscriptores en [!DNL Data Plan A], que utilizan un dispositivo [!DNL iPhone 7].

John utiliza su iPhone 7 en el plan de datos A para autenticarse en el sitio web de Acme Inc. Al mismo tiempo, el [!DNL Co-Op Device Graph] clúster de John contiene dos dispositivos adicionales que utiliza con regularidad: su portátil ([!DNL Device 1]) y su smartphone secundario, [!DNL Device 2] (a [!DNL Samsung S7] el [!DNL Data Plan B]).

Al utilizar **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Adobe Co-Op Device Graph]**, [!DNL Acme Inc.] puede enviar mensajes personalizados a los tres dispositivos desde el clúster de gráficos de dispositivos de John, aunque solo uno de ellos califique inicialmente para el segmento.

![expansión de gráficos avanzada](assets/advanced-device-graph-expansion.png)

>[!MORELIKETHIS]
>
>* [Casos de uso de Device Graph de enlace de Perfil](profile-link-use-case.md)
>* [Casos generales de uso de las reglas de combinación de Perfiles](merge-rule-targeting-options.md)
>* [Preguntas más frecuentes sobre las reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

