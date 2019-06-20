---
description: Las opciones de regla de combinación permiten controlar el tipo de datos que Audience Manager utiliza para la segmentación. Una regla de combinación puede incluir perfiles de dispositivo asignados por el gráfico de dispositivos Link Link, Device Co-op de Adobe Experience Cloud y/u otros proveedores de gráficos de dispositivos de terceros que se integran con Audience Manager. Puede crear un máximo de 3 reglas de combinación de perfiles.
seo-description: Las opciones de regla de combinación permiten controlar el tipo de datos que Audience Manager utiliza para la segmentación. Una regla de combinación puede incluir perfiles de dispositivo asignados por el gráfico de dispositivos Link Link, Device Co-op de Adobe Experience Cloud y/u otros proveedores de gráficos de dispositivos de terceros que se integran con Audience Manager. Puede crear un máximo de 3 reglas de combinación de perfiles.
seo-title: Opciones de regla de combinación de perfiles definidas
solution: Audience Manager
title: Opciones de regla de combinación de perfiles definidas
uuid: 225 eeaf 7-45 e 9-4 f 21-9360-d 80 a 9 f 90520 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rule Options Defined {#profile-merge-rule-options-defined}

Las opciones de regla de combinación permiten controlar el tipo de datos que Audience Manager utiliza para la segmentación. A merge rule can include device profiles mapped by the [!UICONTROL Profile Link] device graph, the [!UICONTROL Adobe Experience Cloud Device Co-op], and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 3 [!UICONTROL Profile Merge Rules].

You build a [!UICONTROL Profile Merge Rule] by making a selection from these options:

<ul class="simplelist"> 
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#auth-options"> Opciones autenticadas</a> </li>
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#profile-options"> Opciones de perfil autenticado</a> </li>
 <li><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> Opciones de dispositivo</a> </li>
</ul>

## Authenticated Options {#auth-options}

The [!UICONTROL Authenticated Options] let you select un-authenticated and authenticated users and leverage their cross-device profile for segmentation. Estas opciones ayudan a identificar y llegar a usuarios específicos en un dispositivo compartido. For more information on anonymous and authenticated users, see [Visitor Authentication States in Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> not to use data collected from authenticated users. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil autenticado actual</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read and write data to the authenticated profile if a visitor has logged in to your site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Último perfil autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read data from the authenticated profile of the user who last logged in on the device. </p> <p>When selected, <span class="keyword"> Audience Manager</span> will not write new trait data to the authenticated profile if the user is anonymous. Al autenticarse, los nuevos datos de características se escriben en el perfil autenticado del usuario. </p> </td>
  </tr> 
 </tbody>
</table>

## Authenticated Profile Options {#profile-options}

[!UICONTROL Authenticated Profile Options] La lista contiene las fuentes de datos entre dispositivos. These options use the names you provided when you created a cross-device data source (see [Create a Cross-Device Data Source](../../features/profile-merge-rules/merge-rules-start.md#create-data-source)). Puede seleccionar hasta 3 fuentes de datos entre dispositivos para utilizarlas con cada regla de perfil. The [!UICONTROL Authenticated Profile Options] are available when you choose **[!UICONTROL Current Authenticated Profile]** or **[!UICONTROL Last Authenticated Profile]**.

## Device Options {#device-options}

[!UICONTROL Device Options] Permite seleccionar el tipo *`device profile`* de utilizado por [!UICONTROL Profile Merge Rule]un. Un perfil de dispositivo está compuesto de características recopiladas por usuarios cuando navegan de forma anónima por Internet. Como mínimo, una regla de combinación de perfil incluye una opción autenticada y una opción de dispositivo.

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
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> not to use the traits contained in the anonymous profile for segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Perfil de dispositivo actual</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to use the anonymous device profile for segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gráfico de Device Link Device</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read the profiles from the current device and the last 3 devices that the user has authenticated from. This device graph is built on your own, first-party data in <span class="keyword"> Audience Manager</span>. Es ideal para clientes que tienen un alto nivel de autenticación en sus propiedades digitales. The <span class="wintitle"> Profile Link</span> device graph is updated in real time. This option is available when you select <b><span class="uicontrol"> Current Authenticated Profile</span></b> or <b><span class="uicontrol"> Last Authenticated Profile</span></b>. When using this option, you can only choose a single authenticated profile (<span class="keyword"> Audience Manager</span> automatically grays out the others). See also, <a href="../../features/profile-merge-rules/profile-link-use-case.md"> Profile Link Device Graph Use Cases</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Device Graph Co-op</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to merge device profiles using the links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p><span class="keyword"> Device Co-op</span> es una cooperativa digital en la que los clientes participantes comparten información de vínculos de dispositivos. <span class="keyword"> Device Co-op</span> procesa estos datos en un gráfico <span class="term"> de dispositivos</span>. Un gráfico de dispositivo vincula los dispositivos de forma conjunta con los clústeres de dispositivos. These links are built from <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> probabilistic and deterministic data</a>. Los clústeres representan un grupo de dispositivos utilizado por una persona anónima. <span class="keyword">Device Co-op</span> comparte estos clústeres entre sus miembros, lo que los ayuda a ofrecer a sus clientes experiencias valiosas y coherentes entre dispositivos. </p> <p> For more information about the <span class="wintitle"> Device Co-op</span>, see the: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> Información general de Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> Requisitos de participación</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> Device Graph: Procesos internos y resultados</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience Manager y gráficos de dispositivos externos</a> (descarga PDF). </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Opciones de gráfico de dispositivos de terceros</b> (Persona y Hogar) </p> </td>
   <td colname="col2"> <p>Estas opciones permiten generar reglas de combinación basadas en la tecnología gráfica de los dispositivos proporcionada por un proveedor de terceros. Un gráfico de dispositivo de terceros proporciona: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Datos probabilísticos o determinísticos. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Datos a nivel personal o doméstico. </li> 
     </ul> </p> <p>To use these options, you must be a customer of a device graph provides who is already integrated with <span class="keyword"> Audience Manager</span>. Póngase en contacto con su administrador de cuentas para obtener más información o empezar. </p> <p>Consulte también &lt; a href = "../../features/profile-merge-rules/external-graph-use-cases. md). </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Preguntas frecuentes sobre reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

