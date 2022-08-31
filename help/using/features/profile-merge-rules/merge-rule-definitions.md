---
description: Las opciones de la regla de combinación le permiten controlar el tipo de datos que utiliza el Audience Manager de datos para la segmentación. Una regla de combinación puede incluir perfiles de dispositivo asignados por el gráfico de dispositivos del vínculo de perfil u otros proveedores de gráficos de dispositivos de terceros que están integrados con el Audience Manager. Puede crear un máximo de 4 reglas de combinación de perfiles.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Definición de las opciones de las reglas de combinación de perfiles.
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 2%

---

# [!UICONTROL Profile Merge Rules] Opciones definidas {#profile-merge-rule-options-defined}

La variable [!UICONTROL profile merge rule] las opciones permiten controlar el tipo de datos [!DNL Audience Manager] utiliza para la segmentación. A [!UICONTROL profile merge rule] puede incluir perfiles de dispositivo asignados por el [!UICONTROL Profile Link] gráficos de dispositivos u otros proveedores de gráficos de dispositivos de terceros que están integrados con [!DNL Audience Manager]. Puede crear un máximo de 4 [!UICONTROL Profile Merge Rules]. El cuarto [!UICONTROL Profile Merge Rule] está disponible exclusivamente para los clientes que compraron el [!UICONTROL People-Based Destinations] complemento.

Si crea un [!UICONTROL Profile Merge Rule] realizando una selección de las opciones que se describen a continuación, en [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Información general de opciones {#overview}

[!UICONTROL Profile Merge Rules] permiten una serie de combinaciones de reglas, cada una orientada a casos de uso específicos. Consulte la siguiente tabla para obtener más información sobre cuándo utilizar cada combinación de reglas.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilidad | Tipo de evaluación | [!UICONTROL Audience Lab] Asistencia | Casos de uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Todos los clientes | Tiempo real y por lotes | Sí | [Segmentación de dispositivos](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Todos los clientes | Tiempo real y por lotes | No | [Segmentación de dispositivos ampliada](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Todos los clientes | Solo en tiempo real | No | [Segmentación de dispositivos compartidos](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Todos los clientes | Tiempo real y por lotes | Sí | [Segmentación en línea/sin conexión](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Todos los clientes | Tiempo real y por lotes | Sí | [Segmentación entre dispositivos](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Todos los clientes | Tiempo real y por lotes | No | [Segmentación avanzada entre dispositivos](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/D | Exclusivo para [Destinos basados en personas](../destinations/people-based-destinations-overview.md) clientes | Sólo por lotes | No | [Segmentación para destinos basados en personas](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Evaluación {#segment-evaluation}

Según el [!UICONTROL Profile Merge Rules] configuración, [!DNL Audience Manager] puede realizar el [!UICONTROL segment] evaluación en tiempo real, en lote o en ambos.

* Tiempo real [!UICONTROL segment] la evaluación requiere que [!DNL DCS] para ver a los visitantes acceder a sus propiedades digitales en tiempo real, para cumplir los requisitos de la función [!UICONTROL segment].
* Lote [!UICONTROL segment] la evaluación se realiza con respecto a los requisitos anteriores [!UICONTROL traits].
* [!UICONTROL Profile Merge Rules] que admiten tanto en tiempo real como por lotes [!UICONTROL segment] combinar la actividad de visitante en tiempo real con las cualificaciones anteriores [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Latencia de los informes {#reporting-latency}

Tiempo real [!UICONTROL segment] la evaluación se refleja inmediatamente en la [!UICONTROL Profile Merge Rules] informes.

Lote [!UICONTROL segment] la evaluación puede tardar hasta 24 horas en reflejarse en la variable [Informes de reglas de combinación de perfiles](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

La variable [!UICONTROL Cross-Device Options] permite seleccionar usuarios autenticados y no autenticados y aprovechar su perfil entre dispositivos para la segmentación. Estas opciones le ayudan a identificar y llegar a usuarios específicos en un dispositivo compartido. Para obtener más información sobre usuarios anónimos y autenticados, consulte [Estados de autenticación de visitante en Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> no utilizar datos recopilados de usuarios autenticados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfiles autenticados actuales</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> para leer y escribir datos en el perfil autenticado si un visitante ha iniciado sesión en su sitio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Últimos perfiles autenticados</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> para leer datos del perfil autenticado del usuario que inició sesión por última vez en el dispositivo. </p> <p>Cuando se selecciona, <span class="keyword"> Audience Manager</span> no escribirá nuevos datos de rasgos en el perfil autenticado si el usuario es anónimo. Tras la autenticación, los nuevos datos de rasgos se escriben en el perfil autenticado del usuario. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Todos los perfiles entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al Audience Manager que lea los datos de todos los perfiles entre dispositivos, independientemente del estado de autenticación. Esta opción solo está disponible para los clientes Audience Manager que hayan comprado el complemento People-Based Destinations .</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

La variable [!UICONTROL Cross-Device Profile Options] enumera las [!UICONTROL cross-device data sources]. Estas opciones utilizan los nombres proporcionados cuando creó un [!UICONTROL cross-device] [!UICONTROL data source] (consulte [Crear una fuente de datos entre dispositivos](merge-rules-start.md#create-data-source)). Puede seleccionar hasta 3 [!UICONTROL cross-device data sources] para usar con cada regla de perfil. La variable [!UICONTROL Authenticated Profile Options] están disponibles cuando elija **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

La variable [!UICONTROL Device Options] permite seleccionar el tipo de *`device profile`* usado por un [!UICONTROL Profile Merge Rule]. Un perfil de dispositivo se crea a partir de [!UICONTROL traits] recopilado de la actividad de navegación anónima. Como mínimo, un [!UICONTROL profile merge rule] incluye un [!UICONTROL authenticated option] y [!UICONTROL device option].

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
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> no utilizar los rasgos contenidos en el perfil anónimo para la segmentación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil del dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> para utilizar el perfil de dispositivo anónimo para la segmentación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos de vínculo de perfil</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> para leer los perfiles del dispositivo actual y hasta 100 dispositivos desde los que el usuario se ha autenticado. Este gráfico de dispositivos se basa en sus propios datos de origen en <span class="keyword"> Audience Manager</span>. Es ideal para clientes que tienen un alto nivel de autenticación en sus propiedades digitales. La variable <span class="wintitle"> Vínculo de perfil</span> el gráfico del dispositivo se actualiza en tiempo real. Esta opción está disponible al seleccionar <b><span class="uicontrol"> Perfil autenticado actual</span></b> o <b><span class="uicontrol"> Último perfil autenticado</span></b>. Al utilizar esta opción, solo puede elegir un perfil autenticado (<span class="keyword"> Audience Manager</span> automáticamente grita los demás). Consulte también <a href="profile-link-use-case.md"> Casos de uso de Device Graph de enlace de perfil</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Opciones de gráfico de dispositivos de terceros</b> (Personas y Hogares) </p> </td>
   <td colname="col2"> <p>Estas opciones permiten crear reglas de combinación basadas en la tecnología de gráficos de dispositivos proporcionada por un proveedor externo. Un gráfico de dispositivos de terceros proporciona: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Datos probabilísticos y/o determinísticos. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Datos a nivel personal o familiar. </li> 
     </ul> </p> <p>Para utilizar estas opciones, debe ser cliente de un gráfico de dispositivos que proporcione quién ya está integrado con <span class="keyword"> Audience Manager</span>. Póngase en contacto con el administrador de cuentas para obtener más información o para empezar. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Segmentos de audiencia que se crearon automáticamente a partir de otros [!DNL Experience Cloud] soluciones, basadas en reglas de combinación definidas fuera de [!DNL Audience Manager], se marcan como si [!UICONTROL External Merge Policy]. Por ejemplo, consulte [Uso compartido de audiencias entre Audience Manager y Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre las reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

