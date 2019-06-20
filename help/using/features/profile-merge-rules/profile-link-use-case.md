---
description: Recomendaciones y casos de uso para volver a segmentar segmentos y clasificar segmentos personalizados con el gráfico del dispositivo Vínculo de perfil.
seo-description: Recomendaciones y casos de uso para volver a segmentar segmentos y clasificar segmentos personalizados con el gráfico del dispositivo Vínculo de perfil.
seo-title: Casos de uso del gráfico de dispositivos de vínculo de perfil
solution: Audience Manager
title: Casos de uso del gráfico de dispositivos de vínculo de perfil
uuid: bd 5567 fd-fcd 5-40 ba-b 6 f 1-035 d 2 ddbcd 3 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Link Device Graph Use Cases {#profile-link-device-graph-use-cases}

Recommendations and use cases for segment retargeting and personalized segment qualification with the [!UICONTROL Profile Link] device graph.

## Recomendaciones {#recommendations}

Consider the [!UICONTROL Profile Link] device graph for campaigns that:

* Tener un alto nivel de autenticación en sus propiedades digitales. Use an [external device graph option](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) if you have a small amount of authenticated users.
* Requiere un targeting preciso de las audiencias conocidas. The [!UICONTROL Profile Link device graph] is built using first-party, authenticated data.
* Establezca como objetivo audiencias conocidas en los estados autenticados y no autenticados en tiempo real.

![](assets/merge-rule-triangle2.png)

## Retargeting Use Case and Profile Merge Rule Configuration {#retargeting-use-cases}

Retarget audiencias que previamente se autenticaron en el sitio o en la aplicación en varios dispositivos. Los segmentos pueden estar compuestos de los siguientes perfiles:

* Último perfil de dispositivo autenticado conocido.
* Actividad anónima en cada perfil de dispositivo.

>[!NOTE]
>
>La información de características de cualquier tipo de perfil puede utilizarse para crear el segmento.

### Ejemplo de retargeting

Veamos cómo funciona con una empresa de tarjetas de crédito de muestra. Este ejemplo utiliza la información de rasgos recopilada de la actividad anónima visualizada en 3 perfiles de dispositivo solamente.

<table id="table_8C5ABA47A0634EBA9B1AA1B5C2AABF07"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condiciones</b> </p> </td> 
   <td colname="col2"> <p>Este caso de uso asume estas condiciones: </p> <p> 
     <ul id="ul_72373D0F304044AE84E4CC055E3E8154"> 
      <li id="li_375DA786ED4D4F18A74C8FE42ABF8448">Un usuario tiene 3 dispositivos y es la última persona que se autentica en el sitio o la aplicación de la empresa de tarjetas de crédito en los 3 dispositivos. </li> 
      <li id="li_77FDBFAED21B4DE19AB2B6C112E0C64B">En el primer dispositivo, un usuario de un estado no autenticado visita una oferta para una tarjeta de crédito premium. </li> 
      <li id="li_D3BE1B30BCCA49EA931AA9D97DD5F86D">En el segundo dispositivo, un usuario de un estado no autenticado ve la página de ventajas Premium de la tarjeta de crédito. </li> 
      <li id="li_39D894624FC44806B6DB2C77F459B39E">En el tercer dispositivo, un usuario de un estado no autenticado ve la página de tarifas y tarifas de tarjeta de crédito premium. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_1B6174F5C3AF4C32831D4217C5113789"> 
      <li id="li_98FE54696B604C3C8D93CC1C1FBB48D9">Combina la actividad anónima y no autenticada recopilada de los 3 dispositivos utilizando el último perfil autenticado en el dispositivo actual. </li> 
      <li id="li_A73C7DCE36BA42B6BAD26D8A075416C1">Evalúa al usuario anónimo para la cualificación de segmentos según: 
       <ul id="ul_EF66EAFD12CA44F5ACCB66319606D937"> 
        <li id="li_541762056ECF4BC1ABF1F5116B5FED6C">Combinación de actividad anónima en los 3 dispositivos. </li> 
        <li id="li_C386CB62E5234E10AFEDE900ADC0E261">El último perfil autenticado en el dispositivo actual. </li> 
       </ul> </li> 
      <li id="li_5C9BDC8FF886494589F005C9658A923C">Envía el segmento a cualquier destino en tiempo real para volver a ser un objetivo en los 3 dispositivos. </li>
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Ejemplo de ejemplo de regla de combinación de perfiles

To set up retargeting with [!UICONTROL Profile Link], your [!UICONTROL Authenticated Options] and [!UICONTROL Device Options] should look like the rule configuration shown below. [!UICONTROL Authenticated Profile] Las opciones serán diferentes a este ejemplo, ya que estas configuraciones utilizan los nombres de las fuentes de datos entre dispositivos.

![Configuración de la regla de combinación de perfiles](assets/merge-rules-internal3.png)

## Personalization Use Case and Profile Merge Rule Configuration {#personalization-use-case}

Personalice la experiencia para audiencias autenticadas en el sitio o en la aplicación según la actividad en varios dispositivos. Los segmentos pueden estar compuestos de los siguientes perfiles:

* Perfil de dispositivo autenticado actualmente.
* Perfiles de dispositivo anónimos.

>[!NOTE]
>
>Un usuario debe estar en un estado autenticado para poder optar a un segmento.

### Ejemplo de personalización

Veamos cómo funciona con una empresa de tarjetas de crédito de muestra.

<table id="table_D2F4D5D27EB54224BB2CC1D843DDEDA3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condiciones</b> </p> </td> 
   <td colname="col2"> <p>Nuestro caso de uso asume estas condiciones: </p> <p> 
     <ul id="ul_C4D2108E7B1C4D3C89411A9CCCDA6DAC"> 
      <li id="li_2F10EB17466B4B91A94DF707C3CB6BE5">Un usuario tiene 3 dispositivos y es la última persona que se autentica en el sitio o la aplicación de la empresa de tarjetas de crédito en los 3 dispositivos. </li> 
      <li id="li_1559C4DA51254BCF95291133F32A4057">En el primer dispositivo, un usuario de un estado no autenticado visita una oferta para una tarjeta de crédito premium. </li> 
      <li id="li_734465E5619C474291C42921160CEC6B">En el segundo dispositivo, un usuario de un estado no autenticado ve la página de ventajas Premium de la tarjeta de crédito. </li> 
      <li id="li_B96ABC0205384B59A1901708505B8BF8">En el tercer dispositivo, un usuario de un estado no autenticado ve la página de tarifas y tarifas de tarjeta de crédito premium. </li> 
      <li id="li_1A7BDBD546BD4B8EACF4292D885127F2">En cualquiera de estos dispositivos, el cliente se autentica (iniciando sesión) para comprobar su balance. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_37DBF5FEABC5463D85C74AD9150EA177"> 
      <li id="li_B60FFA5CF3F64FB69997AA05595900D7">Combina la actividad anónima y no autenticada recopilada de los 3 dispositivos utilizando el perfil autenticado actual. El perfil autenticado proporciona un identificador común en cada dispositivo. </li> 
      <li id="li_AB9FD87DD804474BA33805C364B7B92D">Evalúa el usuario autenticado para la cualificación de segmentos en función de: 
       <ul id="ul_EAF99E72159D4E329052B71344D9C69B"> 
        <li id="li_0B5E52BA6D8B493980291EA7B0AE235A">Combinación de actividad anónima en los 3 dispositivos. </li> 
        <li id="li_07588DEFBEF64F97850CB12CD62D0213">Su perfil autenticado actual. </li> 
       </ul> </li> 
      <li id="li_E7CFCEAD7610496189F4486000D7860A">Envía el segmento a cualquier destino en tiempo real para crear una experiencia de navegación personalizada para el usuario al autenticarse en su dispositivo actual. <p>Nota: Esto califica los 3 dispositivos para el segmento, independientemente del estado de autenticación. Este resultado puede provocar problemas de privacidad si son dispositivos compartidos. </p> </li>
     </ul> </p> </td>
  </tr>
 </tbody> 
</table>

### Ejemplo de regla de combinación de perfiles de personalización

To set up personalization with [!UICONTROL Profile Link], your [!UICONTROL Authenticated Options] and [!UICONTROL Device Options] should look like the rule configuration shown below. [!UICONTROL Authenticated Profile] Las opciones serán diferentes a este ejemplo, ya que estas configuraciones utilizan los nombres de las fuentes de datos entre dispositivos.

![](assets/merge-rules-internal4.png)

For more information about how these device graph processes work, download our PDF, [Audience Manager and External Device Graphs](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_ LIKE_ THIS]
>
>* [Ejemplos de uso de los Gráficos de dispositivos externos](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [Casos de uso generales para reglas de combinación de perfiles](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [Preguntas frecuentes sobre reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

