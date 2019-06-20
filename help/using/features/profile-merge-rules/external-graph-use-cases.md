---
description: Recomendaciones y casos de uso para la publicación, retargeting y personalización para usuarios desconocidos con un gráfico de dispositivos externo. Un gráfico de dispositivo externo se define como un gráfico de dispositivos independiente de Audience Manager. Esto incluye Adobe Experience Cloud Device Co-op y otras integraciones que Adobe tiene con empresas de gráficos de dispositivos probabilísticos o probabilísticos de terceros.
seo-description: Recomendaciones y casos de uso para la publicación, retargeting y personalización para usuarios desconocidos con un gráfico de dispositivos externo. Un gráfico de dispositivo externo se define como un gráfico de dispositivos independiente de Audience Manager. Esto incluye Adobe Experience Cloud Device Co-op y otras integraciones que Adobe tiene con empresas de gráficos de dispositivos probabilísticos o probabilísticos de terceros.
seo-title: Ejemplos de uso de los Gráficos de dispositivos externos
solution: Audience Manager
title: Ejemplos de uso de los Gráficos de dispositivos externos
uuid: f 4 bc 822 d -39 d 2-4680-90 ed -7 ee 2 ead 6 db 6 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ejemplos de uso de los Gráficos de dispositivos externos {#external-device-graph-use-cases}

Recomendaciones y casos de uso para la publicación, retargeting y personalización para usuarios desconocidos con un gráfico de dispositivos externo. Un gráfico de dispositivo externo se define como un gráfico de dispositivos independiente de Audience Manager. This includes the [!DNL Adobe Experience Cloud Device Co-op] and other integrations Adobe has with third-party deterministic or probabilistic device graph companies.

## Recomendaciones {#recommendations}

Consider the [!DNL Experience Cloud Device Co-op] and third-party device graph options for campaigns that:

* Tener un bajo nivel de autenticación en sus propiedades digitales. Use the [Profile Link device graph option](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) if you have a large number of authenticated users.
* Segmente audiencias grandes. The [!DNL Experience Cloud Device Co-op] and third-party device graphs contain authenticated and un-authenticated data.
* Segmentos autenticados o no autenticados a nivel individual y doméstico.

![](assets/merge-rule-triangle1.png)

## Prospecting/Branding Use Case {#prospecting-branding-use-cases}

Una campaña de marca está diseñada para llegar a la mayor cantidad de personas posibles. Coloca pocos límites en la cualificación de segmentos. Sin embargo, estas campañas pueden desperdiciar presupuesto e impresiones dirigiendo constantemente a personas que ven el contenido varias veces y no convierten. A [!UICONTROL Profile Merge] rule that uses the [!DNL Device Co-op] or third-party option can help you create an efficient branding campaign. Por ejemplo, puede agregar a estos usuarios desconocidos a un segmento &quot;no en mercado&quot; después de verlos en varios dispositivos para el límite de frecuencia de su conjunto.

<table id="table_00F6EED172574E80A38CADA8A92A23B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condiciones</b> </p> </td> 
   <td colname="col2">Este caso de uso asume estas condiciones: <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">Desea ofrecer un máximo de 10 impresiones a un usuario anónimo para una campaña de publicidad específica. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">Un usuario tiene varios dispositivos y es posible que o no se haya autenticado en el sitio. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">Un usuario anónimo ve la publicidad un total de 10 veces mientras navega por un estado no autenticado en su dispositivo actual y hasta 3 dispositivos vinculados por un gráfico de dispositivos externo. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify anonymous users after they have seen 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Combina la actividad anónima y no autenticada recopilada del dispositivo actual y los 3 dispositivos vinculados por el gráfico de dispositivos externos (las impresiones de publicidad de cada dispositivo). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Evalúa al usuario no autenticado para la cualificación de segmentos en función de una combinación de actividad anónima en todos los 3 dispositivos vinculados por el gráfico de dispositivos externos y el dispositivo actual. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Envía el segmento a cualquier destino en tiempo real para utilizarlo como segmento de supresión en el dispositivo actual y todos los 3 dispositivos vinculados por el gráfico de dispositivos externos. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retargeting or Site Personalization Use Case {#retargeting-use-case}

Estas estrategias están diseñadas para devolver un usuario no autenticado o desconocido al sitio, o para personalizar su experiencia de navegación mientras se encuentran en el sitio.

<table id="table_0EE2052AA3E744B3B76036FC06B5A453"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condiciones</b> </p> </td> 
   <td colname="col2">Este caso de uso asume estas condiciones: <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">Desea ofrecer una experiencia interna o externa personalizada a un usuario anónimo según su actividad en el sitio mientras se encuentra en un estado no autenticado. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">Un usuario tiene varios dispositivos y es posible que o no se haya autenticado en el sitio. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">Un usuario ve varias páginas en el sitio mientras navega por un estado no autenticado en su dispositivo actual y hasta 3 dispositivos vinculados por un gráfico de dispositivos externo. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify users after they have viewed multiple pages on your site while browsing in an unauthenticated state. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Combina la actividad anónima y no autenticada recopilada de los dispositivos actuales y los 3 dispositivos vinculados por el gráfico de dispositivos externos (las vistas de varias páginas desde cada dispositivo). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Evalúa al usuario no autenticado para la cualificación de segmentos en función de una combinación de actividad anónima en todos los 3 dispositivos vinculados por el gráfico de dispositivos externos y el dispositivo actual. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Envía el segmento a cualquier destino en tiempo real para ofrecer una experiencia interna o externa personalizada en el dispositivo actual y en todos los 3 dispositivos vinculados por el gráfico de dispositivos externos. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## Profile Merge Rule Options for External Device Graph Use Cases {#profile-merge}

Las opciones de regla de combinación para estos casos de uso tendrían un aspecto similar al de las opciones disponibles a continuación. [!UICONTROL Authenticated Profile] Las opciones se desactivan porque esta configuración solo está disponible cuando se selecciona **[!UICONTROL Current Authenticated Profile]** o **[!UICONTROL Last Authenticated Profile]**. Your [!UICONTROL Device Options] will vary depending on the type of device graph setting that you want to use or that is available to you.

![](assets/merge-rules-external.png)

For more information about how these device graph processes work, download our PDF, [Audience Manager and External Device Graphs](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_ LIKE_ THIS]
>
>* [Casos de uso del gráfico de dispositivos de vínculo de perfil](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Casos de uso generales para reglas de combinación de perfiles](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [Preguntas frecuentes sobre reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

