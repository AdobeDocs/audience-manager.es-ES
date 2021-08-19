---
description: Enumera y describe la sintaxis y los atributos admitidos (o pares clave-valor) que puede pasar a los Servidores de recopilación de datos (DCS). Esta información puede ayudarle a dar formato a sus solicitudes de DCS y a comprender los parámetros que devuelve este sistema.
seo-description: Enumera y describe la sintaxis y los atributos admitidos (o pares clave-valor) que puede pasar a los Servidores de recopilación de datos (DCS). Esta información puede ayudarle a dar formato a sus solicitudes de DCS y a comprender los parámetros que devuelve este sistema.
seo-title: Atributos admitidos para llamadas a la API DCS
solution: Audience Manager
title: Atributos admitidos para llamadas a la API DCS
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid
uuid: 0b98ed11-314b-4500-afde-45a041112150
feature: DCS
exl-id: 1bdd7dcd-9411-4b0a-a236-059eb5faf00d
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 4%

---

# Atributos admitidos para llamadas [!DNL DCS] [!DNL API] {#supported-attributes-for-dcs-api-calls}

Enumera y describe la sintaxis y los atributos admitidos (o pares clave-valor) que puede pasar a [!UICONTROL Data Collection Servers] ([!DNL DCS]). Esta información puede ayudarle a dar formato a sus solicitudes [!DNL DCS] y comprender los parámetros que devuelve este sistema.

## Prefijos de atributos {#attribute-prefixes}

El [!DNL DCS] se basa en prefijos específicos agregados a las claves en pares clave-valor para clasificar el tipo de datos que está pasando.

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefijo de clave </th> 
   <th colname="col2" class="entry"> Reservado para </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>Atributos definidos por el cliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Atributos de Audience </span> Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>Datos del encabezado HTTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>Atributos privados definidos por el cliente. </p> <p> El DCS acepta sus propios datos privados cuando la clave tiene un prefijo <code> p_</code>. Los datos privados se utilizan para la evaluación de características, pero no se registran ni almacenan en nuestro sistema. Por ejemplo, supongamos que tiene un rasgo definido como <code> customers = p_age&lt;25</code> y pasa <code> p_age=23</code> en una llamada de evento. Dadas estas condiciones, el usuario que cumple los criterios de calificación basados en la edad se califica para el rasgo, pero el par clave-valor se abandona después de que <span class="keyword"> Audience Manager</span> reciba la solicitud y no se registre. </p> </td>
  </tr> 
 </tbody> 
</table>

## [!DNL d_] Atributos {#d-attributes}

Todos estos son opcionales, a menos que desee una respuesta de [!DNL DCS]. Si desea que el [!DNL DCS] devuelva una respuesta, se requiere `d_rtbd=json`.

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Atributo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_caller</code> </p> </td> 
   <td colname="col2"> <p>Se utiliza para identificar el llamador que realiza la llamada a la API <span class="wintitle"> DCS</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>Especifica una función de JavaScript que se desea ejecutar utilizando la respuesta <span class="wintitle"> DCS</span> como parámetro de función de la función de llamada de retorno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Contiene uno o más pares de ID del proveedor de datos (<code> DPID</code>) e ID de usuario del proveedor de datos (<code> DPUUID</code>) asignados por el <span class="keyword"> Audience Manager</span>. Si utiliza varios pares de <code> DPID</code>s y <code> DPUUID</code>s, separe cada par con el carácter no imprimible <code> %01</code>. Por ejemplo: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_cid</code> reemplaza <code> d_dpid</code> y <code> d_dpuuid</code>, que están en desuso pero siguen siendo compatibles. Consulte <a href="../../../reference/cid.md">CID reemplaza DPID y DPUUID</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>Contiene un código de integración y un ID de usuario único asociado en un único par clave-valor. </p> <p><code> d_cid_ic</code> reemplaza <code> d_dpid</code> y <code> d_dpuuid</code>, que están en desuso pero siguen siendo compatibles. Consulte <a href="../../../reference/cid.md">CID reemplaza DPID y DPUUID</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>Deshabilite el uso de cookies de terceros para cumplir con las regulaciones de protección infantil. El servicio de identidad de Adobe Experience Platform de Adobe establece dinámicamente este parámetro y depende de la configuración <code> idSyncDisable3rdPartySyncing</code>. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/coppa.html" format="https" scope="external"> Compatibilidad con COPPA en el servicio de identidad de Adobe Experience Platform</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>Opcional. Habilitado en la solicitud del cliente. Póngase en contacto con su asesor de Adobe Audience Manager o con el Servicio de atención al cliente. </p> <p>Indica que los rasgos y segmentos deben devolverse dentro de la respuesta <code> JSON</code>. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> devuelve <a href="../../../reference/ids-in-aam.md"> ID de segmento heredados</a> para los segmentos. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> devuelve ID de segmento para los segmentos. </p> </li>
     </ul> </p> <p>Una respuesta de ejemplo podría parecerse a la de abajo: </p> <p>
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"07955261652886032950143702505894272138",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"traits":&nbsp;[420020,&nbsp;5421506],
      &nbsp;&nbsp;&nbsp;&nbsp;"segments":&nbsp;[984263,&nbsp;985264],
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpid</code> </p> </td> 
   <td colname="col2"> <p>Obsoleta. Consulte <code> d_cid</code> y <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>Obsoleta. Consulte <code> d_cid</code> y <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>Devuelve los datos de destino de la URL en la respuesta <code> JSON</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> es un atributo reservado que se utiliza en la integración entre Adobe Analytics y Audience Manager. </p> <p>No se recomienda crear características que usen atributos reservados. El Adobe puede cambiar los atributos reservados en cualquier momento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>Indica la versión <code> JSON</code> que se utilizará en la respuesta. Normalmente, debe establecerlo en <code> d_jsonv=1</code>. Al establecer <code> d_jsonv=0</code> se deshabilitan las sincronizaciones de ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Especifica el ID de Experience Cloud definido y utilizado por el servicio de ID <span class="keyword"> Experience Cloud</span>. Para obtener más información sobre el ECID, consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies y el servicio de identidad del Experience Cloud</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>Asigne un nombre al ID de espacio. Indica qué contenedor de JavaScript se utiliza. Utilizado por el DIL <span class="wintitle"></span> para la sincronización de id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>Permite que el Audience Manager distinga las solicitudes móviles de las solicitudes de escritorio. Los valores admitidos son: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>Obsoleta. <code> d_rs</code> es un atributo reservado que se utiliza en la integración heredada entre  <span class="keyword"> Adobe </span> Analytics y  <span class="keyword"> Audience Manager</span>. </p> <p>No se recomienda crear características que usen atributos reservados. El Adobe puede cambiar los atributos reservados en cualquier momento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>Requerido si desea una respuesta <code> JSON</code> del <span class="wintitle"> DCS</span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">Si omite esto, el <span class="wintitle"> DCS</span> devuelve un píxel en el encabezado. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">Si lo incluye, el <span class="wintitle"> DCS</span> devuelve un objeto <code> JSON</code> en el cuerpo de la respuesta. Consulte el ejemplo siguiente. Su respuesta podría ser más compleja. </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"22920112968019678612904394744954398990",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> es <span class="term"> score ID</span>. Se trata de un ID exclusivo para un rasgo o un segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>Pasa una fuente de datos para la evaluación de características. Solo se evalúan los rasgos de esta fuente de datos. </p> <p>Por ejemplo, supongamos que tiene: </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>Rasgo T1</b> con: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Regla de rasgos: "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Fuente de datos (<a href="../../../reference/ids-in-aam.md"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">Código de integración de DPID: ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>Rasgo T2</b> con: </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Regla de rasgos: "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">Fuente de datos (DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">Código de integración de DPID: ic2 </li> 
     </ul> </p> <p>En una llamada de ejemplo, <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>, solo se devuelve el rasgo T1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>El propósito es idéntico al parámetro <code> d_tdpid</code> descrito anteriormente. Sin embargo, en este caso, la fuente de datos se pasa mediante el código de integración. </p> <p>Para mantener los rasgos descritos anteriormente, considere la llamada de ejemplo: </p> <p>Para <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>, solo se devuelve el rasgo T2. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>ID de usuario único. Identifica a un visitante cuando este valor no está disponible desde una cookie. </p> </td> 
  </tr>
 </tbody>
</table>
