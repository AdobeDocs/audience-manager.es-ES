---
description: Las opciones de Reglas de combinación de perfiles permiten ampliar o reducir la audiencia en determinadas audiencias según las necesidades o los objetivos comerciales. En estos casos de uso generales se explica cómo utilizar las opciones disponibles y crear reglas de combinación para segmentación individual, doméstica y entre dispositivos. Actualmente, las reglas de combinación de perfiles solo funcionan con destinos en tiempo real.
seo-description: Las opciones de Reglas de combinación de perfiles permiten ampliar o reducir la audiencia en determinadas audiencias según las necesidades o los objetivos comerciales. En estos casos de uso generales se explica cómo utilizar las opciones disponibles y crear reglas de combinación para segmentación individual, doméstica y entre dispositivos. Actualmente, las reglas de combinación de perfiles solo funcionan con destinos en tiempo real.
seo-title: Casos de uso generales para reglas de combinación de perfiles
solution: Audience Manager
title: Casos de uso generales para reglas de combinación de perfiles
uuid: c 9 eb 41 c 8-fe 19-45 f 8-9 ff 1-552 c 11 ef 08 da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# General Use Cases for Profile Merge Rules {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] permiten ampliar o reducir la audiencia en determinadas audiencias según las necesidades o los objetivos comerciales. En estos casos de uso generales se explica cómo utilizar las opciones disponibles y crear reglas de combinación para segmentación individual, doméstica y entre dispositivos. Currently, [!UICONTROL Profile Merge Rules] work with real-time destinations only.

![](assets/merge-rules-options.png)

>[!TIP]
>
>For definitions and descriptions of these [!UICONTROL Merge Rule] settings, see [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md).

## Focused targeting {#focused-targeting}

User authentication to a website should trigger a declared ID call to [!DNL Audience Manager]. After this event, [!DNL Audience Manager] writes trait data to (and reads from) an authenticated profile. The authenticated profile lets [!DNL Audience Manager]:

* Escriba características en el perfil autenticado específico de un usuario concreto.
* Identificar y diferenciar entre varios usuarios de dispositivo para la segmentación.

### Alcance de usuarios autenticados

Las opciones de perfil autenticado crean reglas que permiten a los usuarios que inician sesión en un sitio Web o aplicación basado en atributos sin conexión. Por ejemplo: una empresa de servicios financieros utilizaría esta opción para dirigirse a usuarios autenticados con ofertas de actualización de tarjeta de crédito objetivo o ofertas de servicio especializadas basadas en ingresos o actividades sin conexión. Otro ejemplo sería una aerolínea dirigida a fliers frecuentes autenticados con acuerdos basados en milisedades acumuladas.

To create a rule that reaches only authenticated users, select **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**. Esta opción evaluará un segmento utilizando solamente datos de perfil autenticados. Esta regla ignorará los datos del perfil de dispositivo anónimo.

To also include data in the anonymous device profile, use the **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL Current Device Profile]** rule.

### Llegar a los usuarios en función del estado de autenticación anterior

Estas opciones llegan a usuarios específicos cuando navegan pero no inician sesión. Puede hacerlo con opciones que dependen de la segmentación por nivel de usuario inferida. La segmentación inferida ayuda a llegar a personas que no se autentican explícitamente en el sitio pero que pueden estar explorando en línea. Funciona leyendo (pero no escribiendo) datos del último perfil autenticado. And, to help keep the authenticated profile clean, [!DNL Audience Manager] writes new trait qualifications to the device profile instead of the authenticated profile. Por ejemplo, supongamos que usted es un especialista en mercadotecnia que desea probar distintas ofertas con clientes existentes que no iniciaron sesión en su sitio o aplicación. Como especialista en mercadotecnia, puede probar estas publicidades con clientes actuales no autenticados para ver qué ofertas obtienen la mayor respuesta.

Un ejemplo de una regla que llega a los usuarios en base a la autenticación predeterminada es:

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## Expanded targeting {#expanded-targeting}

Junto con reglas que ayudan a clientes específicos, los especialistas en marketing también necesitan reglas que incrementen el tamaño de los conjuntos de datos disponibles para la segmentación. [!UICONTROL Profile Merge Rules] permite hacerlo con la opción de perfil de dispositivo. Las opciones del dispositivo expanden el conjunto de datos elegible para la segmentación porque dibujan en características obtenidas mientras un usuario estaba en estado anónimo en uno o varios dispositivos. Esto podría resultar útil cuando intenta contactar con un usuario en todos sus dispositivos mediante un gráfico de dispositivos personales o todos los dispositivos de un hogar utilizando un gráfico de dispositivos doméstico. Un caso de uso para esta opción podría ser la publicidad de una oferta de vacaciones familiar. En este caso, deseará alcanzar todos los dispositivos de un hogar con la oferta si un usuario de algún dispositivo ha mostrado interés en la oferta.

To create a rule that expands the targeting data set, select the **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Graph]** rule.

<!-- 

<p>Rules that use the device graph option extend your data set even further. With the device graph option, <span class="keyword"> Audience Manager</span> relies on the device profiles aggregated from the last 3 devices that a visitor used for authentication to your site. The device graph rules include: </p> 
<p> 
 <ul id="ul_3008B6AF16EC408F98EC4088111281FB"> 
  <li id="li_FA2087F1ED454CD0B9E09656B79ED23B"> <b><span class="uicontrol"> Current Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
  <li id="li_001A8DB517CB4EE394DBD530F2080FD5"> <b><span class="uicontrol"> Last Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
 </ul> </p> 
<p> 
 <note type="tip">
  Create a simple rule with 
  <b><span class="uicontrol"> No Authenticated Profile</span></b> + 
  <b><span class="uicontrol"> Current Device Profile</span></b> when you're still developing a strategy and are unsure about which options to choose or if your site doesn't use authentication. 
 </note> </p>

 -->

## Device Graph Options {#device-graph-options}

Choosing a [!UICONTROL device graph] option for a [!UICONTROL Profile Merge] rule depends on conditions unique to your digital properties and business goals. Estas directrices generales pueden ayudarle a comprender cuándo utilizar un tipo de gráfico frente a otro. Note, you must be a member of the [!DNL Adobe Experience Cloud Device Co-op] or have a contractual relationship with an external device graph to use these options. Consulte la tabla siguiente para obtener instrucciones generales sobre cuándo elegir una opción gráfica de dispositivo. For specific use cases, see [Profile Link Device Graph Use Cases](../../features/profile-merge-rules/profile-link-use-case.md) and [External Device Graph Use Cases](../../features/profile-merge-rules/external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de gráfico de dispositivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Vínculo de perfil</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Las reglas de combinación</span> de perfiles creadas con <span class="wintitle"> la opción Vínculo</span> de perfil son ideales para: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propiedades digitales que tienen un alto nivel de autenticación de cliente. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Campañas enfocadas y de poco alcance. The <span class="wintitle"> Profile Link</span> device graph is built on deterministic data only. Este grupo de perfiles de dispositivo siempre será menor en relación con el grupo de usuarios y dispositivos no autenticados. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Utilice casos en los que los clientes deban estar en un estado autenticado para poder segmentación. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opciones de gráfico de dispositivos externas </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Las reglas de combinación</span> de perfiles creadas con <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op</a> o cualquier gráfico de dispositivo externo integrado con <span class="keyword"> Audience Manager</span> son ideales para: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propiedades digitales que tienen un bajo nivel de autenticación de cliente. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Campañas de marca amplia y de alto alcance. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Utilice casos en los que los clientes no necesiten estar en un estado autenticado para poder segmentación. </li> 
     </ul> </p> <p> <p>Tip: The <span class="keyword"> Device Co-op</span> is your best option if you're a <span class="keyword"> Experience Cloud</span> customer with low authentication and no relationship with any device graph provider. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Casos de uso del gráfico de dispositivos de vínculo de perfil](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Ejemplos de uso de los Gráficos de dispositivos externos](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [Preguntas frecuentes sobre reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

