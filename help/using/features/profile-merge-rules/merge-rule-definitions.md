---
description: Las opciones de regla de combinación le permiten controlar el tipo de uso que el Audience Manager de datos utiliza para la segmentación. Una regla de combinación puede incluir perfiles de dispositivos asignados por el gráfico de dispositivos de vínculo de Perfil, Adobe Experience Cloud Device Co-op y otros proveedores de gráficos de dispositivos de terceros que estén integrados con Audience Manager. Puede crear un máximo de 4 reglas de combinación de Perfiles.
seo-description: Las opciones de regla de combinación le permiten controlar el tipo de uso que el Audience Manager de datos utiliza para la segmentación. Una regla de combinación puede incluir perfiles de dispositivos asignados por el gráfico de dispositivos de vínculo de Perfil, Adobe Experience Cloud Device Co-op y otros proveedores de gráficos de dispositivos de terceros que estén integrados con Audience Manager. Puede crear un máximo de 4 reglas de combinación de Perfiles.
seo-title: Definición de las opciones de las reglas de combinación de perfiles.
solution: Audience Manager
title: Definición de las opciones de las reglas de combinación de perfiles.
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 6%

---


# [!UICONTROL Profile Merge Rules] Opciones definidas  {#profile-merge-rule-options-defined}

Las opciones [!UICONTROL profile merge rule] le permiten controlar el tipo de datos [!DNL Audience Manager] que utiliza para la segmentación. Un [!UICONTROL profile merge rule] puede incluir perfiles de dispositivos asignados por el gráfico de dispositivos [!UICONTROL Profile Link], los [!UICONTROL Adobe Experience Cloud Device Co-op] y/u otros proveedores de gráficos de dispositivos de terceros que están integrados con [!DNL Audience Manager]. Puede crear un máximo de 4 [!UICONTROL Profile Merge Rules]. El cuarto [!UICONTROL Profile Merge Rule] está disponible exclusivamente para los clientes que compraron el complemento [!UICONTROL People-Based Destinations].

Para crear un [!UICONTROL Profile Merge Rule], realice una selección de las opciones que se describen a continuación, en [!UICONTROL Profile Merge Rule Setup].

![perfil-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Información general de opciones  {#overview}

[!UICONTROL Profile Merge Rules] permiten una serie de combinaciones de reglas, cada una orientada a casos de uso específicos. Consulte la tabla siguiente para obtener más información sobre cuándo utilizar cada combinación de reglas.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilidad | Tipo de evaluación | [!UICONTROL Audience Lab] Asistencia | Casos de uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Todos los clientes | Tiempo real y lote | Sí | [Segmentación de dispositivos](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (incluye  [!UICONTROL Co-op Device Graph]) | Todos los clientes | Tiempo real y lote | No | [Targeting ampliado de dispositivos](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Todos los clientes | Solo en tiempo real | No | [Segmentación de dispositivos compartidos](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Todos los clientes | Tiempo real y lote | Sí | [Objetivo en línea/sin conexión](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Todos los clientes | Tiempo real y lote | Sí | [Targeting entre dispositivos](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (incluye  [!UICONTROL Co-op Device Graph]) | Todos los clientes | Tiempo real y lote | No | [Targeting cruzado de dispositivos avanzado](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/D | Exclusivo para [Clientes de destinos basados en personas](../destinations/people-based-destinations-overview.md) | Sólo lote | No | [Objetivo para destinos basados en personas](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Evaluación  {#segment-evaluation}

Según la configuración [!UICONTROL Profile Merge Rules], [!DNL Audience Manager] puede realizar la evaluación [!UICONTROL segment] en tiempo real, en lote o en ambos.

* La evaluación en tiempo real [!UICONTROL segment] requiere que [!DNL DCS] vea que los visitantes acceden a sus propiedades digitales en tiempo real, para cumplir con los requisitos de [!UICONTROL segment].
* La evaluación del lote [!UICONTROL segment] se realiza con respecto a [!UICONTROL traits] previamente cualificados.
* [!UICONTROL Profile Merge Rules] que admiten tanto la  [!UICONTROL segment] evaluación en tiempo real como la  [!UICONTROL traits]evaluación por lotes combinan la actividad de visitantes en tiempo real con las cualificaciones anteriores.

## [!UICONTROL Profile Merge Rules] Latencia de sistema de informes  {#reporting-latency}

La evaluación [!UICONTROL segment] en tiempo real se refleja inmediatamente en los informes [!UICONTROL Profile Merge Rules].

La evaluación del lote [!UICONTROL segment] puede tardar hasta 24 horas en reflejarse en los informes [Reglas de combinación de Perfiles](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

El [!UICONTROL Cross-Device Options] permite seleccionar usuarios autenticados y no autenticados y aprovechar su perfil entre dispositivos para la segmentación. Estas opciones le ayudan a identificar y llegar a usuarios específicos en un dispositivo compartido. Para obtener más información sobre los usuarios anónimos y autenticados, consulte [Estados de autenticación de Visitante en Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción entre dispositivos </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Sin Perfil entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al <span class="keyword"> Audience Manager</span> que no utilice los datos recopilados de los usuarios autenticados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfiles autenticados actuales</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al <span class="keyword"> Audience Manager</span> que lea y escriba datos en el perfil autenticado si un visitante ha iniciado sesión en el sitio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Últimos Perfiles autenticados</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al <span class="keyword"> Audience Manager</span> que lea los datos del perfil autenticado del usuario que inició sesión por última vez en el dispositivo. </p> <p>Cuando se selecciona, <span class="keyword"> Audience Manager</span> no escribirá nuevos datos de características en el perfil autenticado si el usuario es anónimo. Tras la autenticación, los nuevos datos de características se escriben en el perfil autenticado del usuario. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Todos los Perfiles entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al Audience Manager que lea datos de todos los perfiles entre dispositivos, independientemente del estado de autenticación. Esta opción solo está disponible para los clientes Audience Manager que han adquirido el complemento Destinos basados en personas.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

La [!UICONTROL Cross-Device Profile Options] lista su [!UICONTROL cross-device data sources]. Estas opciones utilizan los nombres proporcionados cuando creó un [!UICONTROL cross-device] [!UICONTROL data source] (consulte [Creación de una fuente de datos entre dispositivos](merge-rules-start.md#create-data-source)). Puede seleccionar hasta 3 [!UICONTROL cross-device data sources] para usar con cada regla de perfil. Los [!UICONTROL Authenticated Profile Options] están disponibles al elegir **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

El [!UICONTROL Device Options] permite seleccionar el tipo de *`device profile`* que utiliza un [!UICONTROL Profile Merge Rule]. Un perfil de dispositivo se crea a partir de [!UICONTROL traits] recopilado a partir de una actividad de exploración anónima. Como mínimo, un [!UICONTROL profile merge rule] incluye un [!UICONTROL authenticated option] y un [!UICONTROL device option].

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción de dispositivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Sin Perfil de dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al <span class="keyword"> Audience Manager</span> que no utilice las características contenidas en el perfil anónimo para la segmentación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil del dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al <span class="keyword"> Audience Manager</span> que utilice el perfil de dispositivo anónimo para la segmentación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil Link Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al <span class="keyword"> Audience Manager</span> que lea los perfiles del dispositivo actual y hasta 100 dispositivos desde los que el usuario se ha autenticado. Este gráfico de dispositivos se crea sobre sus propios datos de origen en <span class="keyword"> Audience Manager</span>. Es ideal para clientes que tienen un alto nivel de autenticación en sus propiedades digitales. El gráfico del dispositivo <span class="wintitle"> Vínculo de Perfil</span> se actualiza en tiempo real. Esta opción está disponible cuando selecciona <b><span class="uicontrol"> Perfil autenticado actual</span></b> o <b><span class="uicontrol"> Último Perfil autenticado</span></b>. Al utilizar esta opción, solo puede elegir un único perfil autenticado (<span class="keyword"> Audience Manager</span> automáticamente elimina el gris de los demás). Consulte también <a href="profile-link-use-case.md"> Casos de uso de Device Graph de Perfil Link</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos de cooperación</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al <span class="keyword"> Audience Manager</span> que lea los perfiles del dispositivo actual y hasta 100 dispositivos más utilizando los vínculos proporcionados por la cooperación <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> entre dispositivos Experience Cloud</a>. </p> <p><span class="keyword"> Device Co-op</span> es una cooperativa digital en la que los clientes participantes comparten información de vínculos de dispositivos. Device Co-op<span class="keyword"> procesa estos datos en un <span class="term"> gráfico de dispositivos</span>. </span> Un gráfico de dispositivo vincula dispositivos de forma conjunta con clústeres de dispositivos. Estos vínculos se crean a partir de <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> datos probabilísticos y determinísticos</a>. Los clústeres representan un grupo de dispositivos utilizados por una persona desconocida. <span class="keyword">Device Co-op</span> comparte estos clústeres entre sus miembros, lo que los ayuda a ofrecer a sus clientes experiencias valiosas y coherentes entre dispositivos. </p> <p> Para obtener más información acerca de Device Co-op<span class="wintitle"></span>, consulte: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Información general de Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Requisitos de participación</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Device Graph: Procesos internos y resultados</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Opciones</b>  de gráficos de dispositivos de terceros (persona y hogar) </p> </td>
   <td colname="col2"> <p>Estas opciones le permiten crear reglas de combinación basadas en la tecnología de gráficos de dispositivos proporcionada por un proveedor externo. Un gráfico de dispositivos de terceros proporciona: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Datos probabilísticos y/o determinísticos. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Datos a nivel personal o familiar. </li> 
     </ul> </p> <p>Para utilizar estas opciones, debe ser cliente de un gráfico de dispositivos que proporcione quién ya está integrado con <span class="keyword"> Audience Manager</span>. Póngase en contacto con el administrador de cuentas para obtener más información o para empezar. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Los segmentos de audiencia que se crearon automáticamente a partir de otras [!DNL Experience Cloud] soluciones, en base a reglas de combinación definidas fuera de [!DNL Audience Manager], se marcan como si utilizaran [!UICONTROL External Merge Policy]. Por ejemplo, consulte [Uso compartido de Audiencias entre Audience Manager y Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Preguntas más frecuentes sobre las reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

