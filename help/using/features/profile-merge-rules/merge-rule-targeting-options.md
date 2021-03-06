---
description: Las opciones de Reglas de combinación de perfil le permiten ampliar o ajustar el enfoque de audiencia en audiencias específicas basadas en necesidades u objetivos empresariales. En estos casos de uso general se explica cómo utilizar las opciones disponibles y crear reglas de combinación para la segmentación individual, doméstica y entre dispositivos.
seo-description: Las opciones de Reglas de combinación de perfil le permiten ampliar o ajustar el enfoque de audiencia en audiencias específicas basadas en necesidades u objetivos empresariales. En estos casos de uso general se explica cómo utilizar las opciones disponibles y crear reglas de combinación para la segmentación individual, doméstica y entre dispositivos.
seo-title: Casos generales de uso de las reglas de combinación de Perfiles
solution: Audience Manager
title: Casos generales de uso de las reglas de combinación de Perfiles
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Combinación de perfiles
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 3%

---

# Casos generales de uso de las reglas de combinación de Perfiles {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] las opciones permiten ampliar o ajustar el enfoque de audiencia en audiencias específicas según las necesidades o objetivos del negocio. En estos casos de uso general se explica cómo utilizar las opciones disponibles y crear reglas de combinación para la segmentación individual, doméstica y entre dispositivos. [!UICONTROL Profile Merge Rules] trabajar con destinos de lote y en tiempo real.

>[!TIP]
>
>Para obtener definiciones y descripciones de estas [!UICONTROL Merge Rule] configuraciones, consulte [Opciones definidas de reglas de combinación de perfiles](merge-rule-definitions.md).

## Segmentación de dispositivos {#device-personalization}

Este escenario se aplica a los especialistas en marketing que deseen evaluar un perfil de dispositivo único para un segmento de audiencia definido en Audience Manager, con el fin de ofrecer una experiencia coherente al dispositivo mediante plataformas de segmentación que admitan ID de dispositivo (DSP, plataformas de personalización en el sitio y otras plataformas de segmentación basadas en dispositivos), sin tener en cuenta la autenticación de usuarios.

Para crear una regla que tenga como objetivo solo perfiles de dispositivo, seleccione **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![solo dispositivo](assets/device-only.png)

Digamos que John posee tres teléfonos inteligentes. Dos de ellos son iPhone 7s en el Plan de datos A, y uno de ellos es un Samsung en el Plan de datos B. Al no tener en cuenta su estado autenticado en ninguno de los tres dispositivos, el operador de telefonía móvil de John desea ofrecerle una actualización del plan de datos, pero solo para los dispositivos iPhone 7 que se ejecutan en el Plan de datos A.

Al usar la regla **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**, [!DNL Device 1] y [!DNL Device 3] se califican para el segmento, mientras que el Dispositivo 2 se ignora.

![solo dispositivo](assets/device-management.png)

## Segmentación de dispositivos compartidos {#target-shared-devices}

Digamos que John y su esposa, Jane, usan el mismo portátil para visitar una tienda en línea y pedir varios artículos.

John utiliza su propia cuenta para reservar entradas para viajes y ofertas especiales, mientras que Jane utiliza su propia cuenta para comprar música y películas.

El equipo de marketing de la tienda puede utilizar la regla **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** para dirigirse a John y Jane con ofertas específicas, basadas únicamente en su actividad autenticada.

![current-no-device](assets/current-no-device.png)

Al utilizar esta regla, el Audience Manager ignora completamente el perfil del dispositivo, califica el ID de CRM de John para el segmento y no califica el ID de CRM de Jane.

![shared-device-targeting](assets/shared-device-targeting.png)

## Segmentación en línea/sin conexión {#device-household-targeting}

Este caso de uso cubre la administración de identidades domésticas. Una empresa puede combinar un perfil de dispositivo único con el último perfil autenticado en ese dispositivo mediante la regla **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]**.

![last-device-profile](assets/last-device-profile.png)

Consideremos un segmento hecho de hogares con ingresos buenos a más de $100.000 al año, que contiene al menos un dispositivo que es [!DNL iPhone 7] en [!DNL Data Plan B]. Tenemos dos perfiles domésticos (perfiles entre dispositivos), cada uno conectado a dos perfiles de dispositivo diferentes. Los rasgos necesarios para calificar para el segmento se distribuyen entre los perfiles de dispositivo y entre dispositivos.

El Audience Manager combina cada dispositivo + par de perfiles entre dispositivos para ver si el conjunto combinado de características cumple los requisitos para el segmento. Dado que el Audience Manager evalúa todos los perfiles incluidos en la combinación, se pueden segmentar tanto un perfil de dispositivo como un perfil doméstico.

El vínculo entre el dispositivo y el perfil del hogar permite que el Audience Manager clasifique [!DNL Household 2] para el segmento, pero no [!DNL Household 1]. Desde [!DNL Household 2], solo [!DNL Device 3] califica para el segmento. Esto [!UICONTROL Profile Merge Rule] ha permitido que el especialista en marketing envíe un mensaje de marketing coherente a un dispositivo individual ([!DNL Device 3]) y a un hogar más amplio ([!DNL Household 2]).

![administración del hogar](assets/household-management.png)

## Segmentación para destinos basados en personas {#all-cross-device}

>[!IMPORTANT]
>
>Este artículo contiene documentación del producto pensada para guiarle en la configuración y uso de esta función. Nada de lo contenido en este documento es asesoramiento jurídico. Consulte a su propio asesor jurídico para obtener asesoramiento jurídico.

Este escenario de objetivo solo está disponible para los clientes que han comprado el complemento [!DNL People-Based Destinations]. Esta regla permite que los especialistas en marketing lleguen a los clientes en función de sus propios datos autenticados.

Supongamos que un comerciante en línea desea llegar a los clientes existentes a través de plataformas sociales y mostrarles ofertas personalizadas basadas en sus pedidos anteriores. Con [!UICONTROL People-Based Destinations], pueden ingerir direcciones de correo electrónico con hash desde su propio [!DNL CRM] Audience Manager, generar segmentos a partir de los datos sin conexión y enviar estos segmentos a las plataformas sociales en las que quieran publicitar, utilizando ese identificador con hash, optimizando así su gasto en publicidad.

Para obtener más información sobre esta opción, consulte [People-Based Destinations](../destinations/people-based-destinations-overview.md).

![todos los dispositivos](assets/all-cross-device.png)

## Opciones de gráfico de dispositivos {#device-graph-options}

La selección de una opción [!UICONTROL device graph] para una regla [!UICONTROL Profile Merge] depende de condiciones exclusivas de sus propiedades digitales y objetivos comerciales. Estas directrices generales pueden ayudarle a comprender cuándo utilizar un tipo de gráfico frente a otro. Tenga en cuenta que debe ser miembro de [Adobe Experience Cloud Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/home.html) o tener una relación contractual con un gráfico de dispositivos externos para utilizar estas opciones. Consulte la siguiente tabla para obtener instrucciones generales sobre cuándo elegir una opción de gráfico de dispositivos. Para casos de uso específicos, consulte [Casos de uso del gráfico de dispositivos de enlace de perfil](profile-link-use-case.md) y [Casos de uso del gráfico de dispositivos externos](external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de gráfico de dispositivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Gráfico de dispositivos de vínculo de perfil</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Las </span> reglas de combinación de perfiles creadas con la  <span class="wintitle"> opción </span> Vinculación de perfiles son ideales para: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Propiedades digitales con un alto nivel de autenticación de clientes. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Campañas centradas de bajo alcance. El gráfico de dispositivos <span class="wintitle"> Vínculo de perfil</span> se basa únicamente en datos determinísticos. Este grupo de perfiles de dispositivo siempre será más pequeño en relación con el grupo de usuarios y dispositivos no autenticados. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Casos de uso en los que los clientes necesitan estar en un estado autenticado para poder optar a la segmentación. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opciones de gráfico de dispositivos externos </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Las </span> reglas de combinación de perfiles creadas con Device Co- <a href="https://experienceleague.adobe.com/docs/device-co-op/using/about/overview.html" format="https" scope="external"> or de </a> Experience Cloud y cualquier gráfico de dispositivos externos integrado con  <span class="keyword"> Audience </span> Manager son perfectas para: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Propiedades digitales con un bajo nivel de autenticación de clientes. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Campañas de marca amplias y de gran alcance. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Casos de uso en los que los clientes no necesitan estar en un estado autenticado para poder optar a la segmentación. </li> 
     </ul> </p> <p> <p>Sugerencia: <span class="keyword"> Device Co-op</span> es su mejor opción si es cliente <span class="keyword"> de </span> con poca autenticación y sin relación con ningún proveedor de gráficos de dispositivos. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

Vea el siguiente vídeo para obtener una descripción general de los posibles casos de uso de [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Casos de uso de Device Graph de enlace de Perfil](profile-link-use-case.md)
* [Ejemplos de uso de los Gráficos de dispositivos externos](external-graph-use-cases.md)
* [Preguntas frecuentes sobre las reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

