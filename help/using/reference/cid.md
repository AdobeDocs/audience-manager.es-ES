---
description: Actualice su código para utilizar d_ cid o d_ cid_ ic en lugar de d_ dpid y d_ dpuuid. Las variables DPID y DPUUID seguirán funcionando, pero debe considerarlas obsoletas. Esto incluye las variantes DPID y DPUUID sin el prefijo d_ prefijo.
seo-description: Actualice su código para utilizar d_ cid o d_ cid_ ic en lugar de d_ dpid y d_ dpuuid. Las variables DPID y DPUUID seguirán funcionando, pero debe considerarlas obsoletas. Esto incluye las variantes DPID y DPUUID sin el prefijo d_ prefijo.
seo-title: CID sustituye DPID y DPUUID
solution: Audience Manager
title: CID sustituye DPID y DPUUID
uuid: 3641 eac 5-b 19 e -45 d 5-bc 1 c -35 a 23 b 4 bab 8 c
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# CID Replaces DPID and DPUUID{#cid-replaces-dpid-and-dpuuid}

Update your code to use `d_cid` or `d_cid_ic` instead of `d_dpid` and `d_dpuuid`. Las variables DPID y DPUUID seguirán funcionando, pero debe considerarlas obsoletas. This includes DPID and DPUUID variants without the `d_ prefix`.

## DPID and DPUUID: A Review {#dpid-dpuuid-review}

El DPID y el DPUUID son pares de clave-valor que contienen un ID de proveedor de datos y un ID de usuario. Estos pares de clave-valor vinculan ID de proveedor de vínculos a ID de usuario. Envían datos durante las llamadas de evento, para eventos de sincronización entrantes y para llamadas de ID. Without them, [!DNL Audience Manager], and other services or features, would not have a way to match and synchronize IDs. These variables are sometimes expressed with or without the `d_` prefix as shown below. Note, in the code, *italics* indicates a variable placeholder.

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Sintaxis </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID del proveedor de datos (DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_ dpid =<i>ID del proveedor de datos</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid =<i>ID del proveedor de datos</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de usuario único del proveedor de datos (DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_ dpuuid =<i>ID de usuario único del proveedor de datos</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid =<i>ID de usuario único del proveedor de datos</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Estos pares clave-valor siguen funcionando, pero están obsoletos. Debe actualizar su código para utilizar CID o CID_ IC en su lugar.

## CID and CID_IC: About {#cid-cidic-about}

Los pares CID y CID_ IC-value reemplazan DPID y DPUUID. Proporcionan las mismas funciones que el DPID y el DPUUID, pero son más eficientes porque incluyen el ID del proveedor de datos (o código de integración) y el ID de usuario en un solo par clave-valor. En cada par clave-valor:

* El símbolo = separa la clave de sus valores relacionados.
* El carácter ASCII de no impresión % 01 separa los valores.

`d_cid` y `d_cid_ic` utilice la sintaxis que se muestra a continuación. Note, in the code, *italics* indicates a variable placeholder.

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Sintaxis </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID de cliente (CID) </p> </td> 
   <td colname="col2"> <p> <code>d_ cid =<i>ID del proveedor de datos</i>% 01 ID<i>de usuario</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código de integración de ID de cliente (CID_ IC) </p> </td> 
   <td colname="col2"> <p> <code>d_ cid_ ic =<i>código de integración</i>% 01<i>ID de usuario</i></code> </p> <p> An <span class="term"> integration code</span> is an alternate ID you can use instead of the Data Source ID, assigned by <span class="keyword"> Audience Manager</span>. See <a href="../features/manage-datasources.md#create-data-source"> Create a Data Source</a> if you need to configure an integration code. </p> </td> 
  </tr> 
 </tbody> 
</table>

See also, [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

>[!NOTE]
>
>You can use integration codes for your own data sources and for global [shared data sources](../features/datasources-list-and-settings.md#settings-menu-options), which you have access to. Por ejemplo, puede utilizar los códigos de integración al trabajar con fuentes de datos de identificadores móviles. Utilice los siguientes códigos de integración, tal como se especifica a continuación:

* **DSID_ 20914** para GAID, que representa dispositivos que ejecutan el sistema operativo Android.
* **DSID_ 20915** para IDFA, que representa dispositivos que ejecutan el sistema operativo iOS.

**Ejemplos**

En la tabla siguiente se proporcionan ejemplos por tipo de evento.

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de evento </th> 
   <th colname="col2" class="entry"> Ejemplo </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Evento </p> </td> 
   <td colname="col2"> 
    <ul id="ul_6EAB4188C6954512A28D1A8328794BCB"> 
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">New: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">Deprecated: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sincronización de entrada (IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">New: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">Deprecated: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Generar UUID de Audience Manager (ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">New: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">Deprecated: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Each call can also include multiple `d_cid` and `d_cid_ic` key value pairs like this:

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## Important Considerations for Development Teams {#dev-considerations}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Elemento </p> </th> 
   <th colname="col2" class="entry"> <p>Descripción </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Codificación URL </p> </td> 
   <td colname="col2"> <p>Your development teams <i>must</i> apply URL encoding to the following variables in the CID key-value pair: </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> user ID</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>Note: You must URL encode the user ID and integration code <i>before</i> concatenating them into a string. Esto se debe a que el carácter ASCII % 01 que separa las dos variables no debe capturarse en la codificación de URL. </p> </p> <p>La codificación URL garantiza que los ID de usuario y los códigos de integración que contienen caracteres reservados o no seguros, como, pero no limitados, + o = se transmitan correctamente a nuestros servidores. </p> <p>Use the <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> ASCII encoding table</a> for reference. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uso de los códigos de integración para fuentes de datos compartidas globales </p> </td> 
   <td colname="col2"> <p>You can use integration codes for your own data sources and for global <a href="../features/datasources-list-and-settings.md#settings-menu-options"> shared data sources</a>, which you have access to. Por ejemplo, puede utilizar los códigos de integración al trabajar con fuentes de datos de identificadores móviles. Utilice los siguientes códigos de integración, tal como se especifica a continuación: </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>DSID_ 20914</b> para GAID, que representa dispositivos que ejecutan el sistema operativo Android. </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_ 20915</b> para IDFA, que representa dispositivos que ejecutan el sistema operativo iOS. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

