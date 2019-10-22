---
description: Las opciones de regla de combinación le permiten controlar el tipo de datos que Audience Manager utiliza para la segmentación. Una regla de combinación puede incluir perfiles de dispositivo asignados por el gráfico del dispositivo Vínculo de perfil, la cooperación entre dispositivos de Adobe Experience Cloud y otros proveedores de gráficos de dispositivos de terceros que estén integrados en Audience Manager. Puede crear un máximo de 4 reglas de combinación de perfiles.
seo-description: Las opciones de regla de combinación le permiten controlar el tipo de datos que Audience Manager utiliza para la segmentación. Una regla de combinación puede incluir perfiles de dispositivo asignados por el gráfico del dispositivo Vínculo de perfil, la cooperación entre dispositivos de Adobe Experience Cloud y otros proveedores de gráficos de dispositivos de terceros que estén integrados en Audience Manager. Puede crear un máximo de 4 reglas de combinación de perfiles.
seo-title: Opciones de regla de combinación de perfiles definidas
solution: Audience Manager
title: Opciones de regla de combinación de perfiles definidas
uuid: 225eaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: 532c69981ebc082bd411a9232e9ef207b59dace5

---


# Profile Merge Rules Options Defined {#profile-merge-rule-options-defined}

Las opciones de regla de combinación le permiten controlar el tipo de datos que Audience Manager utiliza para la segmentación. Una regla de combinación puede incluir perfiles de dispositivo asignados por el gráfico del [!UICONTROL Profile Link] dispositivo, los proveedores de gráficos de dispositivos de terceros [!UICONTROL Adobe Experience Cloud Device Co-op]o ambos que estén integrados en Audience Manager. Puede crear un máximo de 4 [!UICONTROL Profile Merge Rules]. El cuarto [!UICONTROL Profile Merge Rule] está disponible exclusivamente para los clientes que compraron el [!UICONTROL People-Based Destinations] complemento.

Para crear un [!UICONTROL Profile Merge Rule] formulario, realice una selección de las opciones que se describen a continuación, en [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Profile Merge Rule Options Overview {#overview}

Las reglas de combinación de perfiles permiten una serie de combinaciones de reglas, cada una orientada a casos de uso específicos. Consulte la tabla siguiente para obtener más información sobre cuándo utilizar cada combinación de reglas.

| Opción entre dispositivos | Opción de dispositivo | Disponibilidad | Tipo de evaluación | Compatibilidad con Audience Lab | Casos de uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| Sin perfil entre dispositivos | Perfil del dispositivo | Todos los clientes | Tiempo real y lote | Sí | [Segmentación de dispositivos](merge-rule-targeting-options.md#device-personalization) |
| Sin perfil entre dispositivos | Gráfico de dispositivos externos (incluye Device Graph de cooperación) | Todos los clientes | Tiempo real y lote | No | [Targeting ampliado de dispositivos](external-graph-use-cases.md#audience-expansion) |
| Perfiles autenticados actuales | Sin perfil de dispositivo | Todos los clientes | Solo en tiempo real | No | [Segmentación de dispositivos compartidos](merge-rule-targeting-options.md#target-shared-devices) |
| Últimos perfiles autenticados | Perfil del dispositivo | Todos los clientes | Tiempo real y lote | Sí | [Objetivo en línea/sin conexión](merge-rule-targeting-options.md#device-household-targeting) |
| Últimos perfiles autenticados |  Gráfico de dispositivo de vínculo de perfil | Solo Norteamérica y Canadá | Tiempo real y lote | Sí | [Targeting entre dispositivos](profile-link-use-case.md#cross-device-personalization) |
| Últimos perfiles autenticados | Gráfico de dispositivos externos (incluye Device Graph de cooperación) | Todos los clientes | Tiempo real y lote | No | [Targeting cruzado de dispositivos avanzado](external-graph-use-cases.md#advanced-graph-expansion) |
|  Todos los perfiles entre dispositivos | N/D | Exclusivo para clientes de destinos [basados en](../destinations/people-based-destinations-overview.md) personas | Sólo lote | No | [Objetivo para destinos basados en personas](merge-rule-targeting-options.md#all-cross-device) |

## Evaluación del segmento de regla de combinación de perfiles {#segment-evaluation}

En función de su [!UICONTROL Profile Merge Rules] configuración, Audience Manager puede realizar la evaluación del segmento en tiempo real, en lote o en ambos.

* La evaluación de segmentos en tiempo real requiere [!DNL DCS] que los visitantes accedan a sus propiedades digitales en tiempo real para poder acceder al segmento.
* La evaluación de segmentos por lotes se realiza con respecto a características previamente calificadas.
* [!UICONTROL Profile Merge Rules] que admiten tanto la evaluación de segmentos por lotes como en tiempo real combinan la actividad de los visitantes en tiempo real con características previamente calificadas.

## Latencia de informes de reglas de combinación de perfiles {#reporting-latency}

La evaluación de segmentos en tiempo real se refleja inmediatamente en los [!UICONTROL Profile Merge Rules] informes.

La evaluación de segmentos por lotes puede tardar hasta 24 horas en reflejarse en los informes [Reglas de combinación de](profile-link-metrics.md)perfiles.

## Opciones entre dispositivos {#auth-options}

Permite [!UICONTROL Cross-Device Options] seleccionar usuarios autenticados y no autenticados y aprovechar su perfil entre dispositivos para la segmentación. Estas opciones le ayudan a identificar y llegar a usuarios específicos en un dispositivo compartido. Para obtener más información sobre los usuarios anónimos y autenticados, consulte Estados de autenticación de [visitantes en Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Indica a Audience Manager <span class="keyword"></span> que no utilice los datos recopilados de los usuarios autenticados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfiles autenticados actuales</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a Audience Manager <span class="keyword"></span> que lea y escriba datos en el perfil autenticado si un visitante ha iniciado sesión en el sitio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Últimos perfiles autenticados</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a Audience Manager <span class="keyword"></span> que lea datos del perfil autenticado del usuario que inició sesión por última vez en el dispositivo. </p> <p>Cuando está seleccionada, Audience Manager <span class="keyword"></span> no escribirá nuevos datos de características en el perfil autenticado si el usuario es anónimo. Tras la autenticación, los nuevos datos de características se escriben en el perfil autenticado del usuario. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Todos los perfiles entre dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a Audience Manager que lea datos de todos los perfiles entre dispositivos, independientemente del estado de autenticación. Esta opción solo está disponible para los clientes de Audience Manager que han adquirido el complemento Destinos basados en personas.</p> </td>
  </tr>
 </tbody>
</table>

## Opciones de perfil entre dispositivos {#profile-options}

La [!UICONTROL Cross-Device Profile Options] lista muestra las fuentes de datos entre dispositivos. Estas opciones utilizan los nombres proporcionados cuando se crea una fuente de datos entre dispositivos (consulte [Creación de una fuente](merge-rules-start.md#create-data-source)de datos entre dispositivos). Puede seleccionar hasta 3 fuentes de datos entre dispositivos para utilizarlas con cada regla de perfil. Los [!UICONTROL Authenticated Profile Options] están disponibles cuando usted elija **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]**.

## Opciones de dispositivo {#device-options}

Permite [!UICONTROL Device Options] seleccionar el tipo de *`device profile`* uso por parte de un [!UICONTROL Profile Merge Rule]. Un perfil de dispositivo se crea a partir de características recopiladas de la actividad de exploración anónima. Como mínimo, una regla de combinación de perfiles incluye una opción autenticada y una opción de dispositivo.

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
   <td colname="col2"> <p>Indica a Audience Manager <span class="keyword"></span> que no utilice las características contenidas en el perfil anónimo para la segmentación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil del dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a Audience Manager <span class="keyword"></span> que utilice el perfil de dispositivo anónimo para la segmentación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivo de vínculo de perfil</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a Audience Manager <span class="keyword"></span> que lea los perfiles del dispositivo actual y hasta 100 dispositivos desde los que el usuario se ha autenticado. Este gráfico de dispositivos se crea con sus propios datos de origen en <span class="keyword"> Audience Manager</span>. Es ideal para clientes que tienen un alto nivel de autenticación en sus propiedades digitales. El gráfico del dispositivo Vínculo <span class="wintitle"></span> de perfil se actualiza en tiempo real. Esta opción está disponible cuando selecciona <b><span class="uicontrol"> Perfil</span></b> autenticado actual o <b><span class="uicontrol"> Último perfil</span></b>autenticado. Al utilizar esta opción, solo se puede elegir un perfil autenticado único (<span class="keyword"> Audience Manager</span> mostrará automáticamente el gris entre los demás). Consulte también <a href="profile-link-use-case.md"> Casos</a>de uso de Device Graph Device Link Profile. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos de cooperación</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a Audience Manager <span class="keyword"> que lea los perfiles del dispositivo actual y hasta 100 otros dispositivos mediante los vínculos proporcionados por</span> Experience Cloud Device Co-op <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"></a>. </p> <p><span class="keyword"> Device Co-op</span> es una cooperativa digital en la que los clientes participantes comparten información de vínculos de dispositivos. Device Co-op <span class="keyword"> procesa estos datos en un</span> gráfico <span class="term"></span>de dispositivo. Un gráfico de dispositivo vincula dispositivos de forma conjunta con clústeres de dispositivos. Estos vínculos se crean a partir de <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> datos</a>probabilísticos y determinísticos. Los clústeres representan un grupo de dispositivos utilizados por una persona desconocida. <span class="keyword">Device Co-op</span> comparte estos clústeres entre sus miembros, lo que los ayuda a ofrecer a sus clientes experiencias valiosas y coherentes entre dispositivos. </p> <p> Para obtener más información acerca de <span class="wintitle"> Device Co-op</span>, consulte: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> Información general de Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> Requisitos de participación</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> Device Graph: Procesos internos y resultados</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience Manager y gráficos</a> de dispositivos externos (descarga de PDF). </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Opciones</b> de gráfico de dispositivos de terceros (persona y hogar) </p> </td>
   <td colname="col2"> <p>Estas opciones le permiten crear reglas de combinación basadas en la tecnología de gráficos de dispositivos proporcionada por un proveedor externo. Un gráfico de dispositivos de terceros proporciona: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Datos probabilísticos y/o determinísticos. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Datos a nivel personal o familiar. </li> 
     </ul> </p> <p>Para utilizar estas opciones, debe ser cliente de un gráfico de dispositivos que ya esté integrado con <span class="keyword"> Audience Manager</span>. Póngase en contacto con el administrador de cuentas para obtener más información o para empezar. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_LIKE_THIS]
>
>* [Preguntas más frecuentes sobre las reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

