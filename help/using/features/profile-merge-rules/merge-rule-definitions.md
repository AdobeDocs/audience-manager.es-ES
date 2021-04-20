---
description: Las opciones de la regla de combinación le permiten controlar el tipo de datos que utiliza el Audience Manager de datos para la segmentación. Una regla de combinación puede incluir perfiles de dispositivo asignados por el gráfico de dispositivos del vínculo de perfil, Adobe Experience Cloud Device Co-op u otros proveedores de gráficos de dispositivos de terceros que están integrados con Audience Manager. Puede crear un máximo de 4 reglas de combinación de perfiles.
seo-description: Las opciones de la regla de combinación le permiten controlar el tipo de datos que utiliza el Audience Manager de datos para la segmentación. Una regla de combinación puede incluir perfiles de dispositivo asignados por el gráfico de dispositivos del vínculo de perfil, Adobe Experience Cloud Device Co-op u otros proveedores de gráficos de dispositivos de terceros que están integrados con Audience Manager. Puede crear un máximo de 4 reglas de combinación de perfiles.
seo-title: Definición de las opciones de las reglas de combinación de perfiles.
solution: Audience Manager
title: Definición de las opciones de las reglas de combinación de perfiles.
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 6%

---

# [!UICONTROL Profile Merge Rules] Opciones definidas  {#profile-merge-rule-options-defined}

Las opciones de [!UICONTROL profile merge rule] permiten controlar el tipo de datos que [!DNL Audience Manager] utiliza para la segmentación. Un [!UICONTROL profile merge rule] puede incluir perfiles de dispositivo asignados por el gráfico de dispositivos [!UICONTROL Profile Link], el [!UICONTROL Adobe Experience Cloud Device Co-op] y/u otros proveedores de gráficos de dispositivos de terceros que están integrados con [!DNL Audience Manager]. Puede crear un máximo de 4 [!UICONTROL Profile Merge Rules]. El cuarto [!UICONTROL Profile Merge Rule] está disponible exclusivamente para los clientes que compraron el complemento [!UICONTROL People-Based Destinations].

Para crear un [!UICONTROL Profile Merge Rule], realice una selección entre las opciones que se describen a continuación, en [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Información general de opciones  {#overview}

[!UICONTROL Profile Merge Rules] permiten una serie de combinaciones de reglas, cada una orientada a casos de uso específicos. Consulte la siguiente tabla para obtener más información sobre cuándo utilizar cada combinación de reglas.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilidad | Tipo de evaluación | [!UICONTROL Audience Lab] Asistencia | Casos de uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Todos los clientes | Tiempo real y por lotes | Sí | [Segmentación de dispositivos](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (incluye  [!UICONTROL Co-op Device Graph]) | Todos los clientes | Tiempo real y por lotes | No | [Segmentación de dispositivos ampliada](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Todos los clientes | Solo en tiempo real | No | [Segmentación de dispositivos compartidos](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Todos los clientes | Tiempo real y por lotes | Sí | [Segmentación en línea/sin conexión](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Todos los clientes | Tiempo real y por lotes | Sí | [Segmentación entre dispositivos](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (incluye  [!UICONTROL Co-op Device Graph]) | Todos los clientes | Tiempo real y por lotes | No | [Segmentación avanzada entre dispositivos](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/D | Exclusivo para clientes de [People-Based Destinations](../destinations/people-based-destinations-overview.md) | Sólo por lotes | No | [Segmentación para destinos basados en personas](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Evaluación  {#segment-evaluation}

Según la configuración de [!UICONTROL Profile Merge Rules], [!DNL Audience Manager] puede realizar la evaluación [!UICONTROL segment] en tiempo real, en lote o ambas cosas.

* La evaluación en tiempo real [!UICONTROL segment] requiere [!DNL DCS] para ver a los visitantes acceder a sus propiedades digitales en tiempo real y cumplir los requisitos para [!UICONTROL segment].
* La evaluación del lote [!UICONTROL segment] se realiza frente a [!UICONTROL traits] previamente cualificados.
* [!UICONTROL Profile Merge Rules] que admiten tanto la  [!UICONTROL segment] evaluación en tiempo real como la por lotes combinan la actividad del visitante en tiempo real con cualificaciones anteriores  [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Latencia de los informes  {#reporting-latency}

La evaluación en tiempo real [!UICONTROL segment] se refleja inmediatamente en los informes [!UICONTROL Profile Merge Rules].

La evaluación por lotes [!UICONTROL segment] puede tardar hasta 24 horas en reflejarse en los informes [Reglas de combinación de perfiles](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

El [!UICONTROL Cross-Device Options] permite seleccionar usuarios autenticados y no autenticados y aprovechar su perfil entre dispositivos para la segmentación. Estas opciones le ayudan a identificar y llegar a usuarios específicos en un dispositivo compartido. Para obtener más información sobre usuarios anónimos y autenticados, consulte [Estados de autenticación de visitantes en Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción entre dispositivos </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Sin perfil entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al <span class="keyword"> Audience Manager</span> que no utilice los datos recopilados de los usuarios autenticados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfiles autenticados actuales</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al <span class="keyword"> Audience Manager</span> que lea y escriba datos en el perfil autenticado si un visitante ha iniciado sesión en su sitio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Últimos perfiles autenticados</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al <span class="keyword"> Audience Manager</span> que lea los datos del perfil autenticado del usuario que inició sesión por última vez en el dispositivo. </p> <p>Cuando se selecciona, el <span class="keyword"> Audience Manager</span> no escribirá nuevos datos de rasgos en el perfil autenticado si el usuario es anónimo. Tras la autenticación, los nuevos datos de rasgos se escriben en el perfil autenticado del usuario. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Todos los perfiles entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al Audience Manager que lea los datos de todos los perfiles entre dispositivos, independientemente del estado de autenticación. Esta opción solo está disponible para los clientes Audience Manager que hayan comprado el complemento People-Based Destinations .</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

El [!UICONTROL Cross-Device Profile Options] enumera su [!UICONTROL cross-device data sources]. Estas opciones utilizan los nombres que proporcionó al crear una [!UICONTROL cross-device] [!UICONTROL data source] (consulte [Crear una fuente de datos entre dispositivos](merge-rules-start.md#create-data-source)). Puede seleccionar hasta 3 [!UICONTROL cross-device data sources] para usar con cada regla de perfil. Los [!UICONTROL Authenticated Profile Options] están disponibles cuando elige **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

El [!UICONTROL Device Options] permite seleccionar el tipo de *`device profile`* que utiliza un [!UICONTROL Profile Merge Rule]. Un perfil de dispositivo se crea a partir de [!UICONTROL traits] recopilado a partir de la actividad de navegación anónima. Como mínimo, un [!UICONTROL profile merge rule] incluye un [!UICONTROL authenticated option] y un [!UICONTROL device option].

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción de dispositivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Sin perfil de dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al <span class="keyword"> Audience Manager</span> que no utilice los rasgos contenidos en el perfil anónimo para la segmentación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil del dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al <span class="keyword"> Audience Manager</span> que utilice el perfil anónimo del dispositivo para la segmentación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos de vínculo de perfil</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al <span class="keyword"> Audience Manager</span> que lea los perfiles del dispositivo actual y hasta 100 dispositivos desde los que el usuario se ha autenticado. Este gráfico de dispositivos se crea sobre sus propios datos de origen en <span class="keyword"> Audience Manager</span>. Es ideal para clientes que tienen un alto nivel de autenticación en sus propiedades digitales. El gráfico del dispositivo <span class="wintitle"> Vínculo de perfil</span> se actualiza en tiempo real. Esta opción está disponible cuando selecciona <b><span class="uicontrol"> Perfil autenticado actual</span></b> o <b><span class="uicontrol"> Último perfil autenticado</span></b>. Al utilizar esta opción, solo puede elegir un perfil autenticado único (<span class="keyword"> Audience Manager</span> gris automáticamente los demás). Consulte también <a href="profile-link-use-case.md"> Casos de uso de Device Graph de enlace de perfil</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos de cooperación</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al <span class="keyword"> Audience Manager</span> que lea los perfiles del dispositivo actual y hasta 100 dispositivos más utilizando los vínculos proporcionados por el <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p><span class="keyword"> Device Co-op</span> es una cooperativa digital en la que los clientes participantes comparten información de vínculos de dispositivos. El <span class="keyword"> Device Co-op</span> procesa estos datos en un <span class="term"> gráfico de dispositivos</span>. Un gráfico de dispositivos vincula dispositivos de clústeres de dispositivos. Estos vínculos se crean a partir de <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> datos probabilísticos y determinísticos</a>. Los clústeres representan un grupo de dispositivos utilizados por una persona desconocida. <span class="keyword">Device Co-op</span> comparte estos clústeres entre sus miembros, lo que los ayuda a ofrecer a sus clientes experiencias valiosas y coherentes entre dispositivos. </p> <p> Para obtener más información acerca de <span class="wintitle"> Device Co-op</span>, consulte: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Información general de Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Requisitos de participación</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Device Graph: Procesos internos y resultados</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Opciones de gráfico de dispositivos de terceros</b>  (persona y hogar) </p> </td>
   <td colname="col2"> <p>Estas opciones permiten crear reglas de combinación basadas en la tecnología de gráficos de dispositivos proporcionada por un proveedor externo. Un gráfico de dispositivos de terceros proporciona: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Datos probabilísticos y/o determinísticos. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Datos a nivel personal o familiar. </li> 
     </ul> </p> <p>Para utilizar estas opciones, debe ser cliente de un gráfico de dispositivos que proporcione quién ya está integrado con <span class="keyword"> Audience Manager</span>. Póngase en contacto con el administrador de cuentas para obtener más información o para empezar. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Los segmentos de audiencia que se crearon automáticamente a partir de otras [!DNL Experience Cloud] soluciones, en función de reglas de combinación definidas fuera de [!DNL Audience Manager], se marcan como utilizando [!UICONTROL External Merge Policy]. Por ejemplo, consulte [Uso compartido de audiencias entre Audience Manager y Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre las reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

