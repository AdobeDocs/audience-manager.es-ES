---
description: Las opciones de regla de combinación le permiten controlar el tipo de datos que Audience Manager utiliza para segmentación. Una regla de combinación puede incluir dispositivos perfiles asignados por el gráfico de dispositivos vínculo de perfil u otros proveedores de gráficos terceros dispositivos que estén integrados con Audience Manager. Puede crear un máximo de 4 reglas de combinación de perfiles.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Definir regla de combinación de perfiles Opciones
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 1%

---

# [!UICONTROL Profile Merge Rules] Opciones definido {#profile-merge-rule-options-defined}

Las [!UICONTROL profile merge rule] opciones le permiten controlar el tipo de uso de datos [!DNL Audience Manager] para segmentación. Un [!UICONTROL profile merge rule] puede incluir perfiles de dispositivo asignados por el gráfico de dispositivo [!UICONTROL Profile Link] u otros proveedores de gráficos de dispositivos de terceros que están integrados con [!DNL Audience Manager]. Puede crear un máximo de 4 [!UICONTROL Profile Merge Rules]. El cuarto [!UICONTROL Profile Merge Rule] está disponible exclusivamente para los clientes que compraron el complemento [!UICONTROL People-Based Destinations].

Para generar un(a) [!UICONTROL Profile Merge Rule], realice una selección de las opciones que se describen a continuación, en [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Resumen de opciones de [!UICONTROL Profile Merge Rule] {#overview}

[!UICONTROL Profile Merge Rules] permiten una serie de combinaciones de reglas, cada una orientada a casos de uso específicos. Consulte la tabla siguiente para obtener detalles sobre cuándo utilizar cada combinación regla.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilidad | Tipo de evaluación | [!UICONTROL Audience Lab] Apoyo | Casos de uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Todos los clientes | Tiempo real y por lotes | Sí | [Segmentación por dispositivo](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Todos los clientes | Tiempo real y por lotes | No | [Segmentación por dispositivo ampliada](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Todos los clientes | Solo en tiempo real | No | [Segmentación por dispositivo compartido](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Todos los clientes | Tiempo real y por lotes | Sí | [Segmentación en línea/sin conexión](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Todos los clientes | Tiempo real y por lotes | Sí | [Segmentación dispositivos cruzada](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Todos los clientes | Tiempo real y por lotes | No | [Avanzadas Segmentación entre dispositivos](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/D | Exclusivo para [clientes de destinos](../destinations/people-based-destinations-overview.md) basados en personas | Solo Lote | No | [Segmentación para destinos basados en personas](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule]&#x200B;[!UICONTROL Segment] Evaluación {#segment-evaluation}

Dependiendo de su [!UICONTROL Profile Merge Rules] configuración, [!DNL Audience Manager] puede realizar la [!UICONTROL segment] evaluación en tiempo real, en lote, o en ambos.

* La evaluación en tiempo [!UICONTROL segment] real requiere que los [!DNL DCS] visitantes accedan a sus propiedades digitales en tiempo real, para calificar para el [!UICONTROL segment].
* [!UICONTROL segment] Lote evaluación se realiza en comparación con los calificados [!UICONTROL traits]previamente.
* [!UICONTROL Profile Merge Rules] que admiten tanto la evaluación en tiempo real como la evaluación por lotes [!UICONTROL segment] , combinan el actividad de visitante en tiempo real con los calificados [!UICONTROL traits]previamente.

## [!UICONTROL Profile Merge Rules] Informes de latencia {#reporting-latency}

La evaluación en tiempo [!UICONTROL segment] real se refleja inmediatamente en los [!UICONTROL Profile Merge Rules] informes.

[!UICONTROL segment] Lote evaluación puede tardar hasta 24 horas en reflejarse en los informes de reglas de [combinación de perfiles](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

Permiten [!UICONTROL Cross-Device Options] seleccionar usuarios autenticados y no autenticados y impulsar sus perfil dispositivos para segmentación. Estas opciones le ayudan a identificar y llegar a usuarios específicos en un dispositivos compartido. Para obtener más información acerca de los usuarios anónimos y autenticados, consulte [Estados de Authentication de visitantes en Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Indica <span class="keyword"> a Audience Manager</span> que no utilice datos recopilados de usuarios autenticados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfiles autenticados actuales</span></b> </p> </td> 
   <td colname="col2"> <p>Indica <span class="keyword"> a Audience Manager</span> que lean y escriban datos en el perfil autenticado si un visitante ha iniciado sesión en el sitio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> últimos perfiles autenticados</span></b> </p> </td> 
   <td colname="col2"> <p>Indica <span class="keyword"> a Audience Manager</span> que lea datos del perfil autenticado del usuario que inició sesión por última vez en el dispositivos. </p> <p>Cuando se selecciona, <span class="keyword"> Audience Manager</span> no escribirá nuevos datos de características en el perfil autenticado si el usuario es anónimo. Tras la autenticación, los nuevos datos de características se escriben en el perfil autenticado del usuario. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Todos los perfiles entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a los Audience Manager que lean datos de todos los perfiles dispositivos cruzados, independientemente del estado de autenticación. Esta opción solo está disponible para los clientes de Audience Manager que hayan adquirido el complemento Destinos basados en personas.</p> </td>
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
   <td colname="col2"> <p>Indica <span class="keyword"> a Audience Manager</span> que no use las características contenidas en el perfil anónimo para segmentación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil del dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica <span class="keyword"> a Audience Manager</span> que utilice el perfil de dispositivos anónimo para segmentación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Vínculo de perfil Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Indica <span class="keyword"> a Audience Manager</span> que lea los perfiles del dispositivos actual y hasta otros 100 dispositivos desde los que el usuario se haya autenticado. Este gráfico de dispositivos se basa en sus propios datos propios y de origen en <span class="keyword"> Audience Manager</span>. Es ideal para clientes que tienen un alto nivel de autenticación en todas sus propiedades digitales. El <span class="wintitle"> gráfico de dispositivos de vínculo de perfil</span> se actualiza en tiempo real. Esta opción está disponible cuando selecciona <b><span class="uicontrol"> Perfil</span></b> autenticado actual o <b><span class="uicontrol"> Perfil autenticado</span></b> por última vez. Al utilizar esta opción, solo puede elegir un único perfil autenticado (<span class="keyword"> Audience Manager</span> automáticamente tacha las demás). Consulte también <a href="profile-link-use-case.md"> Casos</a> de uso de Device Graph de vínculo de perfil. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Opciones de gráfico de dispositivos de terceros</b> (persona y hogar) </p> </td>
   <td colname="col2"> <p>Estas opciones le permiten versión reglas de combinación basadas en dispositivos tecnología de gráficos proporcionada por un proveedor de terceros. Un gráfico de dispositivos de terceros proporciona: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Datos probabilísticos y/o determinísticos. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Datos a nivel de persona o de hogar. </li> 
     </ul> </p> <p>Para utilizar estas opciones, debe ser cliente de un dispositivos que proporciona el gráfico que ya está integrado con <span class="keyword"> Audience Manager</span>. Póngase en contacto con su Administrador de cuentas para obtener más información o para empezar. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Los segmentos de audiencia que se crearon automáticamente a partir de otras soluciones de [!DNL Experience Cloud], según las reglas de combinación definidas fuera de [!DNL Audience Manager], se marcan como que utilizan un [!UICONTROL External Merge Policy]. Por ejemplo, vea [Uso compartido de audiencias entre Audience Manager y Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre reglas de combinación de perfiles](../../faq/faq-profile-merge.md)
