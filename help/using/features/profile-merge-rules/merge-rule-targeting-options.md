---
description: Las opciones de las reglas de combinación de perfiles le permiten ampliar o ajustar el enfoque de la audiencia en audiencias específicas en función de necesidades comerciales o objetivos. Estos casos de uso general exploran cómo utilizar las opciones disponibles y crear reglas de combinación para objetivos individuales, domésticos y entre dispositivos. Actualmente, las reglas de combinación de perfiles solo funcionan con destinos en tiempo real.
seo-description: Las opciones de las reglas de combinación de perfiles le permiten ampliar o ajustar el enfoque de la audiencia en audiencias específicas en función de necesidades comerciales o objetivos. Estos casos de uso general exploran cómo utilizar las opciones disponibles y crear reglas de combinación para objetivos individuales, domésticos y entre dispositivos. Actualmente, las reglas de combinación de perfiles solo funcionan con destinos en tiempo real.
seo-title: Casos generales de uso de reglas de combinación de perfiles
solution: Audience Manager
title: Casos generales de uso de reglas de combinación de perfiles
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Casos generales de uso de reglas de combinación de perfiles {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] las opciones le permiten ampliar o ajustar el enfoque de la audiencia en audiencias específicas en función de las necesidades o objetivos del negocio. Estos casos de uso general exploran cómo utilizar las opciones disponibles y crear reglas de combinación para objetivos individuales, domésticos y entre dispositivos. Actualmente, [!UICONTROL Profile Merge Rules] solo funciona con destinos en tiempo real.

![](assets/merge-rules-options.png)

>[!TIP]
>
>Para obtener definiciones y descripciones de estos [!UICONTROL Merge Rule] ajustes, consulte Opciones de regla de combinación [de perfiles definidas](../../features/profile-merge-rules/merge-rule-definitions.md).

## Orientación centrada {#focused-targeting}

La autenticación de usuarios en un sitio web debe activar una llamada de ID declarada a [!DNL Audience Manager]. Después de este evento, [!DNL Audience Manager] escribe datos de características en un perfil autenticado (y los lee). El perfil autenticado permite [!DNL Audience Manager]:

* Escriba características en el perfil autenticado específico de un usuario en particular.
* Identifique y diferencie entre varios usuarios de dispositivos para la segmentación.

### Llegar a usuarios autenticados

Las opciones de perfil autenticadas crean reglas que le permiten dirigirse a los usuarios que han iniciado sesión en un sitio web o una aplicación en función de atributos sin conexión. Por ejemplo, una empresa de servicios financieros utilizaría esta opción para dirigirse a usuarios autenticados con ofertas de actualización de tarjetas de crédito con objetivo u ofertas de servicios especializados en función de los ingresos o de la actividad sin conexión. Otro ejemplo sería una aerolínea que dirigiera vuelos autenticados a clientes frecuentes con acuerdos basados en el kilometraje acumulado.

Para crear una regla que solo llegue a usuarios autenticados, seleccione **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**. Esta opción evaluará un segmento usando solamente datos de perfil autenticados. Esta regla omitirá los datos del perfil de dispositivo anónimo.

Para incluir también datos en el perfil de dispositivo anónimo, utilice la regla **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL Current Device Profile]** .

### Llegar a los usuarios en función del estado de autenticación anterior

Estas opciones llegan a usuarios específicos cuando están explorando pero no han iniciado sesión. Esto se puede hacer con opciones que dependen de segmentación deducida por el usuario. El objetivo preferido ayuda a llegar a las personas que no están explícitamente autenticadas en el sitio pero que pueden estar navegando en línea. Funciona leyendo (pero no escribiendo) datos del último perfil autenticado. Y, para ayudar a mantener limpio el perfil autenticado, [!DNL Audience Manager] escribe nuevas cualificaciones de características en el perfil del dispositivo en lugar del perfil autenticado. Por ejemplo, supongamos que es un especialista en marketing que desea probar distintas ofertas con clientes existentes que no han iniciado sesión en su sitio o aplicación. Como especialista en mercadotecnia, puede probar estas publicidades con clientes actuales no autenticados para ver qué ofertas obtienen la mayor cantidad de respuestas.

Un ejemplo de regla que llega a los usuarios en función de la autenticación anterior es:

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## Objetivos ampliados {#expanded-targeting}

Junto con las reglas que ayudan a llegar a clientes específicos, los especialistas en marketing también necesitan reglas que aumenten el tamaño de los conjuntos de datos disponibles para la segmentación. [!UICONTROL Profile Merge Rules] permita hacer esto con la opción de perfil del dispositivo. Las opciones del dispositivo amplían el conjunto de datos que se pueden segmentar porque se basan en características realizadas mientras un usuario se encuentra en un estado anónimo en uno o varios dispositivos. Esto puede resultar útil cuando se trata de llegar a un usuario en todos sus dispositivos utilizando un gráfico de personas o todos los dispositivos de un hogar utilizando un gráfico de dispositivos domésticos. Un caso de uso para esta opción podría incluir la publicidad de una oferta de vacaciones familiares. En este caso, querrá llegar a todos los dispositivos de un hogar con la oferta si un usuario de cualquier dispositivo ha mostrado interés en la oferta.

Para crear una regla que expanda el conjunto de datos de objetivo, seleccione la regla **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Graph]** .

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

## Opciones de Device Graph {#device-graph-options}

La selección de una [!UICONTROL device graph] opción para una [!UICONTROL Profile Merge] regla depende de condiciones exclusivas para sus propiedades digitales y objetivos comerciales. Estas directrices generales pueden ayudarle a saber cuándo utilizar un tipo de gráfico frente a otro. Tenga en cuenta que debe ser miembro del [!DNL Adobe Experience Cloud Device Co-op] o tener una relación contractual con un gráfico de dispositivos externo para utilizar estas opciones. Consulte la siguiente tabla para obtener instrucciones generales sobre cuándo elegir una opción de gráfico de dispositivos. Para casos de uso específicos, consulte Vínculo [de perfil Device Graph Casos](../../features/profile-merge-rules/profile-link-use-case.md) de uso y Casos [de uso de Device Graph](../../features/profile-merge-rules/external-graph-use-cases.md)externos.

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
   <td colname="col2"> <p><span class="wintitle"> Las reglas de combinación</span> de perfiles creadas con la opción Vínculo <span class="wintitle"> de</span> perfil son ideales para: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propiedades digitales que tienen un alto nivel de autenticación de clientes. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Campañas centradas de bajo alcance. El gráfico del dispositivo Vínculo <span class="wintitle"></span> de perfil se basa únicamente en datos determinísticos. Este grupo de perfiles de dispositivo siempre será más pequeño en relación con el grupo de usuarios y dispositivos no autenticados. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Casos de uso en los que los clientes necesitan estar en un estado autenticado para poder optar a la segmentación. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opciones de Device Graph externas </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Las reglas de combinación</span> de perfiles creadas con la cooperación <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> entre dispositivos de</a> Experience Cloud o cualquier gráfico de dispositivo externo integrado con <span class="keyword"> Audience Manager</span> son ideales para: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propiedades digitales con un bajo nivel de autenticación de cliente. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Campañas de marca amplias y de gran alcance. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Casos de uso en los que los clientes no necesitan estar autenticados para poder optar a la segmentación. </li> 
     </ul> </p> <p> <p>Sugerencia: Device Co-op <span class="keyword"> es su mejor opción si es cliente de</span> Experience Cloud <span class="keyword"></span> con baja autenticación y sin relación con ningún proveedor de gráficos de dispositivos. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Casos de uso de Device Graph de vínculo de perfil](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Ejemplos de uso de los Gráficos de dispositivos externos](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [Preguntas más frecuentes sobre las reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

