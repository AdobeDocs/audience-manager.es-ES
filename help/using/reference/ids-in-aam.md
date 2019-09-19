---
description: Consulte este documento para obtener la lista completa de los ID de Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuuid
seo-description: Consulte este documento para obtener la lista completa de los ID de Adobe Audience Manager.
seo-title: Índice de ID en Audience Manager
solution: Audience Manager
title: Índice de ID en Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Índice de ID en Audience Manager{#index-of-ids-in-audience-manager}

Consulte este documento para obtener la lista completa de los ID de Adobe Audience Manager.

<table frame="all" id="table_6727BA8BBF2C40E48768126B4EC9984E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> Nombre y descripción </th> 
   <th colname="col3" class="entry"> Ejemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>UUID de AAM </p> </td> 
   <td colname="col2"> <p> <b><span class="keyword"> ID de usuario único de Audience Manager</span></b> </p> <p> Un ID de dispositivo numérico de 38 dígitos que Audience Manager <span class="keyword"></span> asocia a cada dispositivo con el que interactúa. Considere este ID siempre que vea una mención de usuarios únicos en la interfaz de usuario de Audience Manager.<p><span class="keyword"> Audience Manager</span> intenta guardar este ID como una cookie en el dominio de terceros "demdex.net".</p> </p> <p>El UUID de Audience Manager se envía en llamadas de evento como señal d_uuid. </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ImsOrgId </p> </td> 
   <td colname="col2"> <p> <b>Identificador de organización</b> </p> <p>ID con el que se proporciona una empresa al registrarse en Experience Cloud. Para saber cómo puede encontrar el identificador de organización de su empresa, lea <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> Organizaciones y vinculación</a> de cuentas y desplácese hacia abajo para encontrar el identificador de su organización.</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>ID del socio</b> </p> <p> El PID es un ID de empresa en <span class="keyword"> Audience Manager</span>. <span class="keyword"> Audience Manager</span> asocia un imsOrgId a un PID. </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID, MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>El ID de Experience Cloud (ECID, abreviaturas heredadas MID o MCID) se deriva matemáticamente de su ID de organización y del ID de usuario único de Audience Manager <span class="keyword"></span> . Mientras estos ID permanezcan constantes, generar el ECID adecuado para un usuario específico es simplemente un problema matemático. Con el mismo ID de organización y UUID de Audience Manager, obtiene el mismo valor ECID cada vez. Puede obtener más información sobre el ECID en el documento <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies y Experience Cloud ID</a> . </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SID </p> </td> 
   <td colname="col2"> <p> <b>ID de característica</b> </p> <p>El ID de característica identifica de forma exclusiva las características del entorno de <span class="keyword"> Audience Manager</span> . Se asigna un ID de característica a cada característica de la interfaz de usuario (IU). </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SID </p> </td> 
   <td colname="col2"> <p> <b>ID del segmento </b> </p> <p>El ID de segmento identifica de forma exclusiva los segmentos en el entorno de <span class="keyword"> Audience Manager</span> . Se asigna un ID de segmento a cada segmento en la interfaz de usuario. </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>csegID </p> </td> 
   <td colname="col2"> <p> <b>ID de segmento heredado </b> </p> <p>Este ID identifica de forma exclusiva los segmentos en el entorno de <span class="keyword"> Audience Manager</span> . Se asigna un ID de segmento heredado a cada segmento de la interfaz de usuario. </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>destID </p> </td> 
   <td colname="col2"> <p> <b>ID de destino </b> </p> <p>El ID de destino identifica de forma exclusiva los destinos en el entorno de <span class="keyword"> Audience Manager</span> . Se asigna un ID a cada destino en la interfaz de usuario. </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>ID de fuente de datos (también denominada ID del proveedor de datos)</b> </p> <p>El ID de fuente de datos es un espacio de nombres para ID o características. Se asigna un ID a cada origen de datos (proveedor de datos) en la interfaz de usuario. </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>ID de usuario único del proveedor de datos </b> <b>(también denominado ID de CRM)</b> </p> <p>ID de terceros. Es el ID mediante el cual se identifican los usuarios finales en su propio sistema CRM. Puede sincronizar DPUUID con <span class="keyword"> UUID de Audience Manager</span> y DPUUID de diferentes fuentes <span class="wintitle"> de datos (DPID) en el proceso</span> de sincronización de <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"></a>ID. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de CRM </p> </td> 
   <td colname="col2"> <p>Consulte DPUUID más arriba. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID, CID_IC </p> </td>
   <td colname="col2"> <p> <b>ID de cliente, código de integración de ID de cliente</b> </p> <p> <b>Los pares de clave-valor CID y CID_IC <a href="../reference/cid.md"> reemplazan DPID y DPUUID</a>.</b> Proporcionan las mismas funciones que el DPID y el DPUUID, pero son más eficientes porque incluyen el ID del proveedor de datos y el ID del usuario (o código de integración) en un solo par de clave-valor. </p> </td> 
   <td colname="col3"> <p><code> 81841%013ad2948b1570a7e408a7cfb7ff4879e4 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="2"> <p>DAID </p> <p> 
     <ul id="ul_4EA61BDD0C9140C894162F50300BA9DB"> 
      <li id="li_16148BDD80194F509FF7935364B77F7A">IDFA </li> 
      <li id="li_DF7FEEF2D46A42C5B9FECD6377758B1A">GAID </li>
      <li>RIDA</li>
      <li>MAID</li>
      <li>DUID</li>
     </ul> </p> </td> 
   <td colname="col2"> <p> <b>ID de publicidad del dispositivo</b> </p> <p>Un ID exclusivo de cada dispositivo hardware y que se utiliza con propósitos publicitarios. Normalmente lo proporciona el fabricante del dispositivo o del sistema operativo del dispositivo. </p> </td> 
   <td colname="col3"> <p>IDFA, GAID, Roku ID, Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID de publicidad del dispositivo - IDFA - Dispositivos iOS</b> </p> <p> <b>Los ID de IDFA</b> son identificadores de dispositivos móviles, proporcionados por el fabricante del dispositivo. Estos ID representan dispositivos que ejecutan el sistema operativo iOS. </p> </td> 
   <td colname="col3"> <p> El formato consiste estrictamente en 32 dígitos hexadecimales <i>en mayúsculas</i> , mostrados en cinco grupos y separados por guiones, en el formato 8-4-4-4-12, con un total de 36 caracteres. </p> <p><code> AEBE52E7-03EE-455A-B3C4-E5728396239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID de publicidad del dispositivo - GAID - Dispositivos Android</b> </p> <p><b>Los ID de GAID</b> son identificadores de dispositivos móviles, proporcionados por el fabricante del dispositivo. Estos ID representan dispositivos que ejecutan el sistema operativo Android. </p> </td> 
   <td colname="col3"> <p>El formato consiste estrictamente en 32 dígitos hexadecimales en <i>minúsculas</i> , mostrados en cinco grupos y separados por guiones, en el formato 8-4-4-4-12, con un total de 36 caracteres. </p> <p> <code> e4fe9bde-caa0-47b6-908d-ffba3fa184f2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Dispositivos de transmisión de Roku</b> </p> <p><b>Los ID de GAID</b> RIDA son identificadores de dispositivo de flujo continuo proporcionados por el fabricante de dispositivos Roku.</p> </td>
   <td colname="col3"> <p>El formato consiste estrictamente en 32 dígitos hexadecimales en <i>minúsculas</i> , mostrados en cinco grupos y separados por guiones, en el formato 8-4-4-4-12, con un total de 36 caracteres. </p> <p> <code> fcb2a29c-315a-5e6b-bcfd-d889ba19aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>ID de publicidad de Microsoft - MAID - Dispositivos Windows 10</b> </p> <p><b>Los ID de MAID</b> son identificadores de dispositivo generados por Windows 10 por dispositivo y por usuario.</p> </td>
   <td colname="col3"> <p>Los MAID tienen el formato de cadenas alfanuméricas.</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID - Dispositivos Samsung</b> </p> Los DUID de Samsung son identificadores de dispositivo proporcionados por los televisores Samsung.</p> </td>
   <td colname="col3"> <p>Los DUID de Samsung tienen el formato de cadenas alfanuméricas.</p></td>
  </tr>
 </tbody> 
</table>