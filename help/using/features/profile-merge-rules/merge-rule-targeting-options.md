---
description: Las opciones de las reglas de combinación de Perfiles le permiten ampliar o ajustar el enfoque de la audiencia en audiencias específicas basadas en necesidades o objetivos comerciales. Estos casos de uso general exploran cómo utilizar las opciones disponibles y crear reglas de combinación para objetivos individuales, domésticos y entre dispositivos.
seo-description: Las opciones de las reglas de combinación de Perfiles le permiten ampliar o ajustar el enfoque de la audiencia en audiencias específicas basadas en necesidades o objetivos comerciales. Estos casos de uso general exploran cómo utilizar las opciones disponibles y crear reglas de combinación para objetivos individuales, domésticos y entre dispositivos.
seo-title: Casos generales de uso de las reglas de combinación de Perfiles
solution: Audience Manager
title: Casos generales de uso de las reglas de combinación de Perfiles
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Casos generales de uso de las reglas de combinación de Perfiles {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] las opciones le permiten ampliar o ajustar el enfoque de la audiencia en audiencias específicas basadas en necesidades o objetivos comerciales. Estos casos de uso general exploran cómo utilizar las opciones disponibles y crear reglas de combinación para objetivos individuales, domésticos y entre dispositivos. [!UICONTROL Profile Merge Rules] trabajar con destinos por lotes y en tiempo real.

>[!TIP]
>
>Para obtener definiciones y descripciones de estos [!UICONTROL Merge Rule] ajustes, consulte Opciones de regla de combinación de [Perfiles Definidas](merge-rule-definitions.md).

## Segmentación de dispositivos {#device-personalization}

Este escenario se aplica a los especialistas en marketing que deseen evaluar un solo perfil de dispositivo para un segmento de audiencia definido en el Administrador de Audiencias, con el fin de ofrecer una experiencia coherente al dispositivo mediante plataformas de destino que admitan ID de dispositivo (DSP, plataformas de personalización en el sitio y otras plataformas de destino basadas en dispositivos), sin tener en cuenta la autenticación de usuarios.

Para crear una regla que solo destinatario perfiles de dispositivo, seleccione **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![solo dispositivo](assets/device-only.png)

Digamos que John posee tres smartphones. Dos de ellos son iPhone 7 en el Plan de datos A, y uno de ellos es un Samsung en el Plan de datos B. Al no tener en cuenta su estado autenticado en ninguno de los tres dispositivos, el operador de telefonía móvil de John desea oferta de una actualización del plan de datos, pero solo para dispositivos iPhone 7 que se ejecutan en el plan de datos A.

Al usar la regla **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** [!DNL Device 1] [!DNL Device 3] y ambos califican para el segmento, mientras que el dispositivo 2 se ignora.

![solo dispositivo](assets/device-management.png)

## Segmentación de dispositivos compartidos {#target-shared-devices}

Digamos que John y su esposa, Jane, usan el mismo portátil para visitar una tienda en línea y pedir varios artículos.

John usa su propia cuenta para reservar entradas y ofertas especiales, mientras que Jane usa su propia cuenta para comprar música y películas.

El equipo de mercadotecnia de la tienda puede utilizar la regla **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** para destinatario a John y Jane con ofertas específicas, basándose únicamente en su actividad autenticada.

![current-no-device](assets/current-no-device.png)

Al usar esta regla, el Administrador de Audiencias ignora completamente el perfil del dispositivo, califica el ID de CRM de John para el segmento y no califica el ID de CRM de Jane.

![shared-device-targeting](assets/shared-device-targeting.png)

## Objetivo en línea/sin conexión {#device-household-targeting}

Este caso de uso abarca la gestión de la identidad doméstica. Una compañía puede combinar un solo perfil de dispositivo con el último perfil autenticado en ese dispositivo, mediante la regla **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** .

![último dispositivo-perfil](assets/last-device-profile.png)

Consideremos un segmento hecho de hogares con ingresos buenos por más de $100.000 al año, que contiene al menos un dispositivo que es un [!DNL iPhone 7] on [!DNL Data Plan B]. Tenemos dos perfiles domésticos (perfiles entre dispositivos), cada uno conectado a dos perfiles de dispositivos diferentes. Las características requeridas para poder optar al segmento se distribuyen entre los perfiles de dispositivos y entre dispositivos.

El Administrador de Audiencias combina todos los dispositivos + par de perfiles entre dispositivos para ver si el conjunto combinado de características cumple los requisitos para el segmento. Dado que el Administrador de Audiencias evalúa todos los perfiles que se incluyeron en la combinación, se pueden segmentar tanto el perfil del dispositivo como el perfil doméstico.

El vínculo entre el dispositivo y el perfil doméstico permite que el Administrador de Audiencias cumpla los requisitos [!DNL Household 2] para el segmento, pero no [!DNL Household 1]. Desde [!DNL Household 2], solo [!DNL Device 3] califica para el segmento. Esto [!UICONTROL Profile Merge Rule] ha permitido que el especialista en mercadotecnia envíe un mensaje de marketing coherente a un dispositivo ([!DNL Device 3]) individual y a un hogar ([!DNL Household 2]) más amplio.

![administración del hogar](assets/household-management.png)

## Objetivo para destinos basados en personas {#all-cross-device}

>[!IMPORTANT]
>
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

Este escenario de objetivo solo está disponible para los clientes que han comprado el [!DNL People-Based Destinations] complemento. Esta regla permite que los especialistas en mercadotecnia lleguen a los clientes en función de sus propios datos autenticados.

Supongamos que un minorista en línea desea llegar a los clientes existentes a través de las plataformas sociales y mostrarles ofertas personalizadas basadas en sus pedidos anteriores. Con [!UICONTROL People-Based Destinations], pueden ingerir direcciones de correo electrónico con hash propias [!DNL CRM] en el Administrador de Audiencias, generar segmentos a partir de los datos sin conexión y enviar estos segmentos a las plataformas sociales en las que deseen publicitar, utilizando ese identificador con hash, optimizando así la inversión en publicidad.

Para obtener más información sobre esta opción, consulte Destinos basados en [personas](../destinations/people-based-destinations-overview.md).

![todo entre dispositivos](assets/all-cross-device.png)

## Opciones de Device Graph {#device-graph-options}

La selección de una [!UICONTROL device graph] opción para una [!UICONTROL Profile Merge] regla depende de condiciones exclusivas para sus propiedades digitales y objetivos comerciales. Estas directrices generales pueden ayudarle a saber cuándo utilizar un tipo de gráfico frente a otro. Tenga en cuenta que debe ser miembro de Device Co-op [de](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) Adobe Experience Cloud o tener una relación contractual con un gráfico de dispositivos externo para utilizar estas opciones. Consulte la siguiente tabla para obtener instrucciones generales sobre cuándo elegir una opción de gráfico de dispositivos. Para casos de uso específicos, consulte [Perfil Link Device Graph Casos](profile-link-use-case.md) de uso de Device Graph y Casos [de uso de Device Graph](external-graph-use-cases.md)externos.

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de gráfico de dispositivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Perfil Link Device Graph</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Las reglas de combinación</span> de Perfiles creadas con la opción Vínculo <span class="wintitle"> de</span> Perfil son ideales para: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propiedades digitales que tienen un alto nivel de autenticación de clientes. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">campañas focalizadas y de bajo alcance. El gráfico del dispositivo Vínculo <span class="wintitle"> de</span> Perfil se basa únicamente en datos determinísticos. Este grupo de perfiles de dispositivos siempre será más pequeño en relación con el grupo de usuarios y dispositivos no autenticados. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Casos de uso en los que los clientes necesitan estar en un estado autenticado para poder optar a la segmentación. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opciones de Device Graph externas </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Las reglas de combinación</span> de Perfiles creadas con la cooperación <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> entre dispositivos de</a> Experience Cloud o cualquier gráfico de dispositivos externos integrado con el Administrador <span class="keyword"> de</span> Audiencias son ideales para: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propiedades digitales que tienen un bajo nivel de autenticación de cliente. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">campañas de marca amplias y de gran alcance. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Casos de uso en los que los clientes no necesitan estar autenticados para poder optar a la segmentación. </li> 
     </ul> </p> <p> <p>Sugerencia: Device Co-op <span class="keyword"> es su mejor opción si es cliente de</span> Experience Cloud <span class="keyword"></span> con baja autenticación y sin relación con ningún proveedor de gráficos de dispositivos. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

Vea el siguiente vídeo para obtener una descripción general de los casos de uso posibles de [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Casos de uso de Device Graph de vínculo de Perfil](profile-link-use-case.md)
>* [Ejemplos de uso de los Gráficos de dispositivos externos](external-graph-use-cases.md)
>* [Preguntas más frecuentes sobre las reglas de combinación de Perfiles](../../faq/faq-profile-merge.md)

