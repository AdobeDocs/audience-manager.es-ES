---
description: Las opciones de regla de combinación le permiten controlar el tipo de datos que Audience Manager utiliza para la segmentación. Una regla de combinación puede incluir perfiles de dispositivo asignados por el gráfico del dispositivo Vínculo de perfil, la cooperación entre dispositivos de Adobe Experience Cloud y otros proveedores de gráficos de dispositivos de terceros que estén integrados en Audience Manager. Puede crear un máximo de 3 reglas de combinación de perfiles.
seo-description: Las opciones de regla de combinación le permiten controlar el tipo de datos que Audience Manager utiliza para la segmentación. Una regla de combinación puede incluir perfiles de dispositivo asignados por el gráfico del dispositivo Vínculo de perfil, la cooperación entre dispositivos de Adobe Experience Cloud y otros proveedores de gráficos de dispositivos de terceros que estén integrados en Audience Manager. Puede crear un máximo de 3 reglas de combinación de perfiles.
seo-title: Opciones de regla de combinación de perfiles definidas
solution: Audience Manager
title: Opciones de regla de combinación de perfiles definidas
uuid: 225eaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rule Options Defined {#profile-merge-rule-options-defined}

Las opciones de regla de combinación le permiten controlar el tipo de datos que Audience Manager utiliza para la segmentación. Una regla de combinación puede incluir perfiles de dispositivo asignados por el gráfico del [!UICONTROL Profile Link] dispositivo, los proveedores de gráficos de dispositivos de terceros [!UICONTROL Adobe Experience Cloud Device Co-op]o ambos que estén integrados en Audience Manager. Puede crear un máximo de 3 [!UICONTROL Profile Merge Rules].

Para crear un [!UICONTROL Profile Merge Rule] archivo, realice una selección de estas opciones:

<ul class="simplelist"> 
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#auth-options"> Opciones autenticadas</a> </li>
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#profile-options"> Opciones de perfil autenticadas</a> </li>
 <li><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> Opciones de dispositivo</a> </li>
</ul>

## Opciones autenticadas {#auth-options}

Permite [!UICONTROL Authenticated Options] seleccionar usuarios no autenticados y autenticados y aprovechar su perfil entre dispositivos para la segmentación. Estas opciones le ayudan a identificar y llegar a usuarios específicos en un dispositivo compartido. Para obtener más información sobre los usuarios anónimos y autenticados, consulte Estados de autenticación de [visitantes en Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción autenticada </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ningún perfil autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a Audience Manager <span class="keyword"></span> que no utilice los datos recopilados de los usuarios autenticados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil autenticado actual</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a Audience Manager <span class="keyword"></span> que lea y escriba datos en el perfil autenticado si un visitante ha iniciado sesión en el sitio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Último perfil autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a Audience Manager <span class="keyword"></span> que lea datos del perfil autenticado del usuario que inició sesión por última vez en el dispositivo. </p> <p>Cuando está seleccionada, Audience Manager <span class="keyword"></span> no escribirá nuevos datos de características en el perfil autenticado si el usuario es anónimo. Tras la autenticación, los nuevos datos de características se escriben en el perfil autenticado del usuario. </p> </td>
  </tr> 
 </tbody>
</table>

## Opciones de perfil autenticadas {#profile-options}

La [!UICONTROL Authenticated Profile Options] lista muestra las fuentes de datos entre dispositivos. Estas opciones utilizan los nombres proporcionados cuando se crea una fuente de datos entre dispositivos (consulte [Creación de una fuente](../../features/profile-merge-rules/merge-rules-start.md#create-data-source)de datos entre dispositivos). Puede seleccionar hasta 3 fuentes de datos entre dispositivos para utilizarlas con cada regla de perfil. Los [!UICONTROL Authenticated Profile Options] están disponibles cuando usted elija **[!UICONTROL Current Authenticated Profile]** o **[!UICONTROL Last Authenticated Profile]**.

## Opciones de dispositivo {#device-options}

Permite [!UICONTROL Device Options] seleccionar el tipo de *`device profile`* uso por parte de un [!UICONTROL Profile Merge Rule]. Un perfil de dispositivo se compone de características recopiladas por los usuarios cuando navegan por la web de forma anónima. Como mínimo, una regla de combinación de perfiles incluye una opción autenticada y una opción de dispositivo.

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
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil del dispositivo actual</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a Audience Manager <span class="keyword"></span> que utilice el perfil de dispositivo anónimo para la segmentación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivo de vínculo de perfil</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a Audience Manager <span class="keyword"></span> que lea los perfiles del dispositivo actual y los últimos 3 dispositivos desde los que el usuario se ha autenticado. Este gráfico de dispositivos se crea con sus propios datos de origen en <span class="keyword"> Audience Manager</span>. Es ideal para clientes que tienen un alto nivel de autenticación en sus propiedades digitales. El gráfico del dispositivo Vínculo <span class="wintitle"></span> de perfil se actualiza en tiempo real. Esta opción está disponible cuando selecciona <b><span class="uicontrol"> Perfil</span></b> autenticado actual o <b><span class="uicontrol"> Último perfil</span></b>autenticado. Al utilizar esta opción, solo se puede elegir un perfil autenticado único (<span class="keyword"> Audience Manager</span> mostrará automáticamente el gris entre los demás). Consulte también <a href="../../features/profile-merge-rules/profile-link-use-case.md"> Casos</a>de uso de Device Graph Device Link Profile. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de dispositivos de cooperación</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a Audience Manager <span class="keyword"> que combine perfiles de dispositivo mediante los vínculos proporcionados por</span> Experience Cloud Device Co-op <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"></a>. </p> <p><span class="keyword"> Device Co-op</span> es una cooperativa digital en la que los clientes participantes comparten información de vínculos de dispositivos. Device Co-op <span class="keyword"> procesa estos datos en un</span> gráfico <span class="term"></span>de dispositivo. Un gráfico de dispositivo vincula dispositivos de forma conjunta con clústeres de dispositivos. Estos vínculos se crean a partir de <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> datos</a>probabilísticos y determinísticos. Los clústeres representan un grupo de dispositivos utilizados por una persona desconocida. <span class="keyword">Device Co-op</span> comparte estos clústeres entre sus miembros, lo que los ayuda a ofrecer a sus clientes experiencias valiosas y coherentes entre dispositivos. </p> <p> Para obtener más información acerca de <span class="wintitle"> Device Co-op</span>, consulte: </p> <p> 
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
     </ul> </p> <p>Para utilizar estas opciones, debe ser cliente de un gráfico de dispositivos que ya esté integrado con <span class="keyword"> Audience Manager</span>. Póngase en contacto con el administrador de cuentas para obtener más información o para empezar. </p> <p>Consulte también &lt;a href="../../features/profile-merge-rules/external-graph-use-cases.md). </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_LIKE_THIS]
>
>* [Preguntas más frecuentes sobre las reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

