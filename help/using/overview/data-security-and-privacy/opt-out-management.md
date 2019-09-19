---
description: Adobe cumple con todos los estándares del sector con respecto a la administración de la exclusión. Continúe leyendo para obtener información completa sobre los tipos de exclusión admitidos por Audience Manager.
seo-description: Adobe cumple con todos los estándares del sector con respecto a la administración de la exclusión. Continúe leyendo para obtener información completa sobre los tipos de exclusión admitidos por Audience Manager.
seo-title: Administración de exclusión
solution: Audience Manager
title: Administración de exclusión
uuid: 61b43e0e-bfe3-497e-ade2-6a942a98407e
translation-type: tm+mt
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# Administración de exclusión{#opt-out-management}

Adobe cumple con todos los estándares del sector con respecto a la administración de la exclusión. Continúe leyendo para obtener información completa sobre los tipos de exclusión admitidos por Audience Manager.

## Exclusión global {#global-opt-out}

La exclusión global representa una exclusión en Audience Manager y otras soluciones de Adobe Experience Cloud para todas las marcas. La tabla siguiente enumera los métodos utilizados para la exclusión global:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exclusión para </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>La página <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Opciones de privacidad </a> proporciona funciones de 1 clic que permiten a los usuarios finales controlar y excluir la recopilación de datos mediante las soluciones de publicidad de Adobe Experience Cloud (incluido Audience Manager). Concretamente, consulte la sección <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> cliente comercial </a> de la página Opciones de privacidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Llamadas de API directas a Audience Manager </p> </td> 
   <td colname="col2"> <p>Todas las marcas de Audience Manager pueden desactivar la recopilación de datos haciendo una llamada a la API de DCS a continuación e incluyendo el ID de usuario de <a href="../../reference/ids-in-aam.md"> Audience Manager </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" —cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST 12" </code> </p> <p>Como resultado, estableceremos <code>las cookies demdex=NOTARGET</code> y <code>dextp=NOTARGET</code> para el ID de usuario de Audience Manager enviado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dispositivos móviles </p> </td> 
   <td colname="col2"> <p>Consulte la configuración de exclusión y privacidad para: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Dispositivos Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> Dispositivos iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Los usuarios finales también pueden desactivar la recopilación global de datos visitando los sitios web de nuestros socios de estándares del sector.

* [La Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Iniciativa de publicidad en red (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Siguiendo las solicitudes de exclusión descritas anteriormente:

* Audience Manager dejará de recopilar, segmentar o activar datos en adelante.
* Los datos históricos se eliminan del perfil del usuario pasados 120 días.

## Opción de exclusión de nivel de socio {#partner-opt-out}

La exclusión a nivel de socio permite la exclusión de la recopilación de datos por parte de socios específicos de Audience Manager. La exclusión de nivel de socio funciona con llamadas de ID [](../../features/declared-ids.md) declarados y llamadas de ID de dispositivo, tal como se describe en las secciones siguientes.

### Opción de exclusión de nivel de socio con llamadas de ID declaradas

Después de una exclusión a nivel de socio con una llamada de ID declarada:

* El último ID de dispositivo (ID[de usuario único de](../../reference/ids-in-aam.md)Audience Manager) vinculado al ID [de](../../reference/ids-in-aam.md) CRM se excluye de la recopilación de datos.
* Audience Manager dejará de recopilar, segmentar o activar todos los datos a partir del último ID de dispositivo vinculado al ID de CRM.
* No se eliminan datos históricos.

<br/>

**Llamadas de exclusión**

Cuando Audience Manager recibe una solicitud de exclusión a nivel de socio, el JSON devuelto por el DCS contiene el código de [error 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), con el mensaje [!UICONTROL "Encountered opt out tag"], en lugar del ID de usuario de Audience Manager.

<!-- 

<p> 
 <ul id="ul_65EF2E1ED8F24457A35299E38AFE1DBE"> 
  <li id="li_832D0B507BC64782A5D3662FD5173A37">Audience Manager can pass in a declared ID opt-out alongside an Audience Manager UUID in the URL. </li> 
  <li id="li_D6C41CB385C5401D98156E5A3D79AAEE">The declared ID opt-out is stored in the Profile Cache Server (PCS) on a per-partner basis. There is no platform-level opt-out using declared IDs. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross DCS regions). </li> 
 </ul> </p>

 -->

<!-- 

<p>See <a href="../../overview/data-security-and-privacy/data-privacy.md"> Data Privacy </a> for more information about opting-out of data collection. </p>

 -->



**Ejemplos**

Puede realizar una solicitud de exclusión de ID declarada con los pares `d_cid` y `d_cid_ic` clave-valor. Los parámetros heredados como `d_dpid` y `d_dpuuid` siguen funcionando, pero se consideran obsoletos. Consulte [CID sustituye DPID y DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

**Opciones de exclusión con CID y CID_IC**

Para obtener una descripción y sintaxis, consulte Variables [URL y Sintaxis de los ID](../../features/declared-ids.md#variables-and-syntax)declarados.

| Opción de exclusión mediante | Ejemplo de código |
|--- |--- |
| ID de proveedor de datos e ID de usuario. | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| Código de integración e ID de usuario. | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| Varios pares de clave-valor d_cid y d_cid_ic. | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### Opción de exclusión de nivel de socio con llamadas de ID de dispositivo

Puede desactivar la recopilación de datos en un ID de dispositivo determinado para una marca haciendo las siguientes llamadas a la API [de](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)DCS:

| Opción de exclusión mediante | Ejemplo de código |
|--- |--- |
| Un ID de usuario único (`uuid`) de Audience Manager. | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un ID de Experience Cloud (`mid`) | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Obtenga más información sobre `uuid`los ID `mid` y `imsOrgId` en el [índice de ID de Audience Manager](/help/using/reference/ids-in-aam.md).

Después de una exclusión a nivel de socio con una llamada de ID de dispositivo:

* El ID del dispositivo no se selecciona en la recopilación de datos.
* Audience Manager dejará de recopilar, segmentar o activar todos los datos del socio a partir del ID del dispositivo.
* No se eliminan datos históricos.
