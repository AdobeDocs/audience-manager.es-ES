---
description: Consulte este documento para ver la lista completa de los ID de Audience Manager de Adobe.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid
seo-description: Consulte este documento para ver la lista completa de los ID de Audience Manager de Adobe.
seo-title: Índice de ID en Audience Manager
solution: Audience Manager
title: Índice de ID en Audience Manager
uuid: 292185 ec -7 c 6 a -414 b-ab 17-800 c 21 cb 1 f 01
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Index of IDs in Audience Manager{#index-of-ids-in-audience-manager}

Consulte este documento para ver la lista completa de los ID de Audience Manager de Adobe.

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
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID de característica</b> </p> <p>The Trait ID uniquely identifies traits in the <span class="keyword"> Audience Manager</span> environment. Se asigna un ID de característica a cada característica de la interfaz de usuario (interfaz de usuario). </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID de segmento </b> </p> <p>The Segment ID uniquely identifies segments in the <span class="keyword"> Audience Manager</span> environment. Se asigna un ID de segmento a cada segmento de la interfaz de usuario. </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Csegid </p> </td> 
   <td colname="col2"> <p> <b>ID de segmento heredado </b> </p> <p>This ID uniquely identifies segments in the <span class="keyword"> Audience Manager</span> environment. Se asigna un ID de segmento heredado a cada segmento de la interfaz de usuario. </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Destid </p> </td> 
   <td colname="col2"> <p> <b>ID de destino </b> </p> <p>The Destination ID uniquely identifies destinations in the <span class="keyword"> Audience Manager</span> environment. Se asigna un ID a cada destino en la interfaz de usuario. </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>ID de fuente de datos (también denominado ID de proveedor de datos)</b> </p> <p>El ID de fuente de datos es un espacio de nombres para ID o características. Se asigna un ID a cada fuente de datos (proveedor de datos) en la interfaz de usuario. </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>ID de usuario único del proveedor de datos </b><b>(también denominado ID CRM)</b> </p> <p>Un ID de terceros. Este es el ID por el que se identifica a los usuarios finales en su propio sistema CRM. You can sync DPUUIDs with <span class="keyword"> Audience Manager</span> UUIDs and you can sync DPUUIDs from your different <span class="wintitle"> Data Sources</span> (DPIDs) in the <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"> ID synchronization process</a>. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423 vn -343 fds -3432 r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de CRM </p> </td> 
   <td colname="col2"> <p>Consulte DPUUID arriba. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423 vn -343 fds -3432 r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID, CID_ IC </p> </td>
   <td colname="col2"> <p> <b>ID de cliente, código de integración de ID de cliente</b> </p> <p> <b>Los pares CID y CID_ IC-value <a href="../reference/cid.md"> reemplazan DPID y DPUUID</a>.</b> Proporcionan las mismas funciones que el DPID y el DPUUID, pero son más eficientes porque incluyen el ID del proveedor de datos y el ID de usuario (o código de integración) en un solo par clave-valor. </p> </td> 
   <td colname="col3"> <p><code> 81841% 013 ad 2948 b 1570 a 7 e 408 a 7 cfb 7 ff 4879 e 4 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AAM UUID </p> </td> 
   <td colname="col2"> <p> <b><span class="keyword"> ID de usuario único de</span> Audience Manager </b> </p> <p> A numerical, 38-digit device ID that <span class="keyword"> Audience Manager</span> associates to each device it interacts with. <span class="keyword"> Audience Manager</span> intenta guardar este ID como una cookie en el dominio de terceros "demdex. net". </p> <p>El UUID de Audience Manager se envía en llamadas de evento como la señal d_ uuid. </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imsorgid </p> </td> 
   <td colname="col2"> <p> <b>Identificador de organización</b> </p> <p>Este es el ID con el que se proporciona una empresa al registrarse para Experience Cloud. To learn how you can find your company's Organization ID, read <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> Organizations and Account Linking</a> and scroll down to Find your Organization ID.</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>ID del socio</b> </p> <p> The PID is a company's ID in <span class="keyword"> Audience Manager</span>. <span class="keyword"> Audience Manager</span> asocia un imsorgid a un PID. </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID, MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>The Experience Cloud ID (ECID, legacy abbreviations MID or MCID) is derived mathematically from your Organization ID and the <span class="keyword"> Audience Manager</span> Unique User ID. Siempre que estos ID sean constantes, la generación de la ECID derecha para un usuario específico es simplemente un problema matemático. Con el mismo ID de organización y Audience Manager UUID obtiene el mismo valor ECID siempre. You can read more about the ECID in the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and Experience Cloud ID</a> document. </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
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
   <td colname="col2"> <p> <b>ID de publicidad de dispositivo</b> </p> <p>Un ID exclusivo de cada dispositivo hardware y que se utiliza con propósitos publicitarios. Normalmente lo proporciona el fabricante del dispositivo o del sistema operativo del dispositivo. </p> </td> 
   <td colname="col3"> <p>IDFA, GAID, Roku ID, Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID de publicidad de dispositivo - IDFA - Dispositivos iOS</b> </p> <p> <b>Los ID IDFA</b> son identificadores de dispositivo móvil proporcionados por el fabricante del dispositivo. Estos ID representan dispositivos que ejecutan el sistema operativo iOS. </p> </td> 
   <td colname="col3"> <p> The format strictly consists of 32 <i>uppercase</i> hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. </p> <p><code> AEBE 52 E 7-03 EE -455 A-B 3 C 4-E 57283966239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID de publicidad de dispositivo: GAID - Dispositivos Android</b> </p> <p><b>Los ID de GAID</b> son identificadores de dispositivo móvil proporcionados por el fabricante del dispositivo. Estos ID representan dispositivos que ejecutan el sistema operativo Android. </p> </td> 
   <td colname="col3"> <p>The format strictly consists of 32 <i>lowercase</i> hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. </p> <p> <code> e 4 fe 9 bde-caa 0-47 b 6-908 d-ffba 3 fa 184 f 2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Dispositivos de flujo Roku</b> </p> <p><b>Los ID</b> RAID RIDES son identificadores de dispositivos de flujo continuo proporcionados por el fabricante de dispositivos Roku.</p> </td>
   <td colname="col3"> <p>The format strictly consists of 32 <i>lowercase</i> hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. </p> <p> <code> fcb 2 a 29 c -315 a -5 e 6 b-bcfd-d 889 ba 19 aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>ID de publicidad de Microsoft: MAID - Dispositivos Windows 10</b> </p> <p><b>Los ID de MAID</b> son identificadores de dispositivo generados por Windows 10 en cada dispositivo por usuario.</p> </td>
   <td colname="col3"> <p>Los ID se formatean como cadenas alfanuméricas.</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID - Dispositivos Samsung</b> </p> Los ID de Samsung son identificadores de dispositivo proporcionados por Samsung TV.</p> </td>
   <td colname="col3"> <p>Los Samsung duids tienen formato como cadenas alfanuméricas.</p></td>
  </tr>
 </tbody> 
</table>