---
description: Recomendaciones y casos de uso para la prospección, resegmentación y personalización de usuarios desconocidos con un gráfico de dispositivos externo. Un gráfico de dispositivo externo se define como un gráfico de dispositivo independiente de Audience Manager. Esto incluye Adobe Experience Cloud Device Co-op y otras integraciones que Adobe tiene con empresas de gráficos de dispositivos probabilísticos o determinísticos de terceros.
seo-description: Recomendaciones y casos de uso para la prospección, resegmentación y personalización de usuarios desconocidos con un gráfico de dispositivos externo. Un gráfico de dispositivo externo se define como un gráfico de dispositivo independiente de Audience Manager. Esto incluye Adobe Experience Cloud Device Co-op y otras integraciones que Adobe tiene con empresas de gráficos de dispositivos probabilísticos o determinísticos de terceros.
seo-title: Ejemplos de uso de los Gráficos de dispositivos externos
solution: Audience Manager
title: Ejemplos de uso de los Gráficos de dispositivos externos
uuid: f4bc822d-39d2-4680-90ed-7ee2ead6db6f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ejemplos de uso de los Gráficos de dispositivos externos {#external-device-graph-use-cases}

Recomendaciones y casos de uso para la prospección, resegmentación y personalización de usuarios desconocidos con un gráfico de dispositivos externo. Un gráfico de dispositivo externo se define como un gráfico de dispositivo independiente de Audience Manager. Esto incluye las [!DNL Adobe Experience Cloud Device Co-op] y otras integraciones que Adobe tiene con empresas de gráficos de dispositivos determinísticos o probabilísticos de terceros.

## Recomendaciones {#recommendations}

Considere las opciones de gráficos de dispositivos [!DNL Experience Cloud Device Co-op] y de terceros para campañas que:

* Tener un bajo nivel de autenticación en sus propiedades digitales. Utilice la opción [Gráfico del dispositivo Vínculo](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) de perfil si tiene un gran número de usuarios autenticados.
* Diríjase a grandes audiencias. Los gráficos de dispositivos [!DNL Experience Cloud Device Co-op] y de terceros contienen datos autenticados y no autenticados.
* Segmentar visitantes autenticados y/o no autenticados a nivel individual y doméstico.

![](assets/merge-rule-triangle1.png)

## Caso de uso de Prospecting/Branding {#prospecting-branding-use-cases}

Se ha diseñado una campaña de marca para llegar al mayor número posible de personas. Coloca pocos límites en la calificación de segmentos. Sin embargo, estas campañas pueden malgastar el presupuesto y las impresiones dirigiéndose constantemente a las personas que ven el contenido varias veces y no lo convierten. Una [!UICONTROL Profile Merge] regla que utilice la opción [!DNL Device Co-op] o de terceros puede ayudarle a crear una campaña de marca eficiente. Por ejemplo, puede agregar estos usuarios desconocidos a un segmento "no en el mercado" después de verlos en varios dispositivos para el límite de frecuencia establecido.

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
   <td colname="col2">Este caso de uso asume las siguientes condiciones: <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">Desea entregar un máximo de 10 impresiones a un usuario anónimo para una campaña de publicidad específica. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">Un usuario tiene varios dispositivos y puede que no se haya autenticado en el sitio. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">Un usuario anónimo ve la publicidad un total de 10 veces mientras explora en un estado no autenticado en el dispositivo actual y hasta 3 dispositivos vinculados por un gráfico de dispositivos externos. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">Ha definido un segmento de Audience Manager <span class="keyword"></span> para calificar a los usuarios anónimos después de que hayan visto 10 impresiones. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Dadas estas condiciones, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Combina la actividad anónima no autenticada recopilada del dispositivo actual y los 3 dispositivos vinculados por el gráfico de dispositivos externos (las impresiones de publicidad de cada dispositivo). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Evalúa al usuario no autenticado para la cualificación de segmentos en función de una combinación de actividad anónima en los 3 dispositivos vinculados por el gráfico del dispositivo externo y el dispositivo actual. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Envía el segmento a cualquier destino en tiempo real para utilizarlo como segmento de supresión en el dispositivo actual y en los 3 dispositivos vinculados por el gráfico del dispositivo externo. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Caso de uso de redireccionamiento o personalización del sitio {#retargeting-use-case}

Estas estrategias están diseñadas para devolver a un usuario desconocido o no autenticado a su sitio o para personalizar su experiencia de navegación mientras esté en el sitio.

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
   <td colname="col2">Este caso de uso asume las siguientes condiciones: <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">Desea ofrecer una experiencia personalizada en el sitio o fuera de él a un usuario anónimo en función de su actividad en el sitio mientras esté en un estado no autenticado. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">Un usuario tiene varios dispositivos y puede que no se haya autenticado en el sitio. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">Un usuario ve varias páginas del sitio mientras explora en un estado no autenticado en el dispositivo actual y hasta 3 dispositivos vinculados por un gráfico de dispositivos externos. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">Ha definido un segmento de <span class="keyword"> Audience Manager</span> para calificar a los usuarios después de haber visto varias páginas en el sitio mientras navegaban en un estado no autenticado. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Dadas estas condiciones, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Combina la actividad anónima no autenticada recopilada de los dispositivos actuales y los 3 dispositivos vinculados por el gráfico de dispositivos externos (las vistas de páginas múltiples de cada dispositivo). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Evalúa al usuario no autenticado para la cualificación de segmentos en función de una combinación de actividad anónima en los 3 dispositivos vinculados por el gráfico del dispositivo externo y el dispositivo actual. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Envía el segmento a cualquier destino en tiempo real para ofrecer una experiencia personalizada en el sitio o fuera del sitio en el dispositivo actual y en los 3 dispositivos vinculados por el gráfico de dispositivos externos. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## Opciones de regla de combinación de perfiles para casos de uso de gráficos de dispositivos externos {#profile-merge}

Las opciones de regla de combinación para estos casos de uso serían similares a las opciones disponibles que se muestran a continuación. Las [!UICONTROL Authenticated Profile] opciones se desactivan porque estas opciones solo están disponibles cuando selecciona **[!UICONTROL Current Authenticated Profile]** o **[!UICONTROL Last Authenticated Profile]**. El [!UICONTROL Device Options] cambio variará según el tipo de configuración del gráfico del dispositivo que desee utilizar o que esté disponible para usted.

![](assets/merge-rules-external.png)

Para obtener más información sobre cómo funcionan estos procesos de gráficos de dispositivos, descargue nuestro PDF, [Audience Manager y los gráficos](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf)de dispositivos externos.

>[!MORE_LIKE_THIS]
>
>* [Casos de uso de Device Graph de vínculo de perfil](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Casos generales de uso de reglas de combinación de perfiles](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [Preguntas más frecuentes sobre las reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

