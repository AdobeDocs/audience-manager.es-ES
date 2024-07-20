---
description: Las opciones de reglas de combinación permiten controlar el tipo de datos que utiliza el Audience Manager de datos para la segmentación. Una regla de combinación puede incluir perfiles de dispositivo asignados por el gráfico de dispositivos de enlace de perfil y/u otros proveedores de gráficos de dispositivos de terceros que están integrados con Audience Manager. Puede crear un máximo de 4 reglas de combinación de perfiles.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Opciones definidas de reglas de combinación de perfiles
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 1%

---

# Opciones definidas de [!UICONTROL Profile Merge Rules] {#profile-merge-rule-options-defined}

Las opciones [!UICONTROL profile merge rule] le permiten controlar el tipo de datos que [!DNL Audience Manager] utiliza para la segmentación. Un [!UICONTROL profile merge rule] puede incluir perfiles de dispositivo asignados por el gráfico de dispositivo [!UICONTROL Profile Link] u otros proveedores de gráficos de dispositivos de terceros que están integrados con [!DNL Audience Manager]. Puede crear un máximo de 4 [!UICONTROL Profile Merge Rules]. El cuarto [!UICONTROL Profile Merge Rule] está disponible exclusivamente para los clientes que compraron el complemento [!UICONTROL People-Based Destinations].

Para generar un(a) [!UICONTROL Profile Merge Rule], realice una selección de las opciones que se describen a continuación, en [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Resumen de opciones de [!UICONTROL Profile Merge Rule] {#overview}

[!UICONTROL Profile Merge Rules] permiten una serie de combinaciones de reglas, cada una orientada a casos de uso específicos. Consulte la tabla siguiente para obtener detalles sobre cuándo utilizar cada combinación de reglas.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilidad | Tipo de evaluación | Compatibilidad con [!UICONTROL Audience Lab] | Casos de uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Todos los clientes | Tiempo real y por lotes | Sí | [Segmentación de dispositivo](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Todos los clientes | Tiempo real y por lotes | No | [Segmentación de dispositivos expandida](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Todos los clientes | Solo en tiempo real | No | [Segmentación de dispositivos compartidos](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Todos los clientes | Tiempo real y por lotes | Sí | [Segmentación en línea/sin conexión](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Todos los clientes | Tiempo real y por lotes | Sí | [Segmentación entre dispositivos](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Todos los clientes | Tiempo real y por lotes | No | [Segmentación avanzada entre dispositivos](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/D | Exclusivo para [clientes de destinos basados en personas](../destinations/people-based-destinations-overview.md) | Solo lote | No | [Segmentación para destinos basados en personas](merge-rule-targeting-options.md#all-cross-device) |

## Evaluación de [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] {#segment-evaluation}

Según la configuración de [!UICONTROL Profile Merge Rules], [!DNL Audience Manager] puede realizar la evaluación de [!UICONTROL segment] en tiempo real, por lotes o en ambos.

* La evaluación de [!UICONTROL segment] en tiempo real requiere que [!DNL DCS] vea visitantes que acceden a sus propiedades digitales en tiempo real para poder optar a [!UICONTROL segment].
* La evaluación del lote [!UICONTROL segment] se realizó en relación con [!UICONTROL traits] que se había clasificado previamente.
* [!UICONTROL Profile Merge Rules] que admiten la evaluación en tiempo real y por lotes [!UICONTROL segment] combinan la actividad del visitante en tiempo real con [!UICONTROL traits] que cumplen los requisitos previos.

## [!UICONTROL Profile Merge Rules] latencia de informe {#reporting-latency}

La evaluación [!UICONTROL segment] en tiempo real se refleja inmediatamente en los informes [!UICONTROL Profile Merge Rules].

La evaluación del lote [!UICONTROL segment] puede tardar hasta 24 horas en reflejarse en los [informes de reglas de combinación de perfiles](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

El [!UICONTROL Cross-Device Options] le permite seleccionar usuarios autenticados y no autenticados, así como aprovechar su perfil entre dispositivos para la segmentación. Estas opciones le ayudan a identificar y llegar a usuarios específicos en un dispositivo compartido. Para obtener más información sobre los usuarios anónimos y autenticados, consulte [Estados de autenticación de visitantes en Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción entre dispositivos </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> No hay perfil entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al Audience Manager <span class="keyword"> </span> que no utilice los datos recopilados de los usuarios autenticados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> perfiles autenticados actuales</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al Audience Manager <span class="keyword"> </span> que lea y escriba datos en el perfil autenticado si un visitante ha iniciado sesión en el sitio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> últimos perfiles autenticados</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al Audience Manager <span class="keyword"> </span> que lea los datos del perfil autenticado del usuario que inició sesión por última vez en el dispositivo. </p> <p>Cuando se selecciona, <span class="keyword"> Audience Manager</span> no escribirá nuevos datos de rasgos en el perfil autenticado si el usuario es anónimo. Tras la autenticación, los nuevos datos de rasgos se escriben en el perfil autenticado del usuario. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> todos los perfiles entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al Audience Manager que lea los datos de todos los perfiles entre dispositivos, independientemente del estado de autenticación. Esta opción solo está disponible para clientes de Audience Manager que hayan adquirido el complemento Destinos basados en personas.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

El [!UICONTROL Cross-Device Profile Options] enumera su [!UICONTROL cross-device data sources]. Estas opciones usan los nombres que proporcionaste cuando creaste un [!UICONTROL cross-device] [!UICONTROL data source] (consulta [Crear un Source de datos entre dispositivos](merge-rules-start.md#create-data-source)). Puede seleccionar hasta 3 [!UICONTROL cross-device data sources] para usar con cada regla de perfil. Los [!UICONTROL Authenticated Profile Options] están disponibles cuando elige **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

El [!UICONTROL Device Options] le permite seleccionar el tipo de *`device profile`* que usa un [!UICONTROL Profile Merge Rule]. Se ha creado un perfil de dispositivo a partir de [!UICONTROL traits] recopilado a partir de la actividad de exploración anónima. Como mínimo, [!UICONTROL profile merge rule] incluye [!UICONTROL authenticated option] y [!UICONTROL device option].

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
   <td colname="col2"> <p>Indica al Audience Manager <span class="keyword"> </span> que no use los rasgos contenidos en el perfil anónimo para la segmentación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> perfil de dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al Audience Manager <span class="keyword"> </span> que use el perfil de dispositivo anónimo para la segmentación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> gráfico del dispositivo de enlace de perfil</span></b> </p> </td> 
   <td colname="col2"> <p>Indica al Audience Manager <span class="keyword"> </span> que lea los perfiles del dispositivo actual y de hasta 100 dispositivos desde los cuales el usuario se ha autenticado. Este gráfico de dispositivos se basa en sus propios datos de origen en <span class="keyword"> Audience Manager</span>. Es ideal para clientes que tienen un alto nivel de autenticación en sus propiedades digitales. El gráfico del dispositivo <span class="wintitle"> Profile Link</span> se actualiza en tiempo real. Esta opción está disponible cuando selecciona <b><span class="uicontrol"> Perfil autenticado actual</span></b> o <b><span class="uicontrol"> Último perfil autenticado</span></b>. Al utilizar esta opción, solo puede elegir un único perfil autenticado (<span class="keyword"> Audience Manager</span> atenua automáticamente los demás). Consulte también <a href="profile-link-use-case.md"> casos prácticos de gráficos de dispositivos de vínculos de perfiles</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Opciones de gráfico de dispositivos de terceros</b> (persona y hogar) </p> </td>
   <td colname="col2"> <p>Estas opciones permiten crear reglas de combinación basadas en la tecnología de gráficos de dispositivos proporcionada por un proveedor de terceros. Un gráfico de dispositivos de terceros proporciona lo siguiente: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Datos probabilísticos y/o determinísticos. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Datos a nivel de persona o unidad familiar. </li> 
     </ul> </p> <p>Para utilizar estas opciones, debe ser cliente de un dispositivo que proporcione graph y que ya esté integrado con <span class="keyword"> Audience Manager</span>. Póngase en contacto con su administrador de cuentas para obtener más información o para comenzar. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Los segmentos de audiencia que se crearon automáticamente a partir de otras soluciones de [!DNL Experience Cloud], según las reglas de combinación definidas fuera de [!DNL Audience Manager], se marcan como que utilizan un [!UICONTROL External Merge Policy]. Por ejemplo, vea [Uso compartido de audiencias entre Audience Manager y Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre reglas de combinación de perfiles](../../faq/faq-profile-merge.md)
