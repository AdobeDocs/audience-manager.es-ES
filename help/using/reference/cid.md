---
description: Actualice el código para utilizar d_cid o d_cid_ic en lugar de d_dpid y d_dpuuid. Las variables DPID y DPUUID seguirán funcionando, pero debe considerarlas obsoletas. Esto incluye las variantes DPID y DPUUID sin el prefijo d_.
seo-description: Update your code to use d_cid or d_cid_ic instead of d_dpid and d_dpuuid. The DPID and DPUUID variables will continue to work, but you should consider them deprecated. This includes DPID and DPUUID variants without the d_ prefix.
seo-title: CID Replaces DPID and DPUUID
solution: Audience Manager
title: CID sustituye DPID y DPUUID
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
feature: Reference
exl-id: 18e6b1db-fe51-4560-9458-8d65474d2506
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 1%

---

# CID sustituye DPID y DPUUID{#cid-replaces-dpid-and-dpuuid}

Actualice el código para que use `d_cid` o `d_cid_ic` en lugar de `d_dpid` y `d_dpuuid`. Las variables DPID y DPUUID seguirán funcionando, pero debe considerarlas obsoletas. Esto incluye variantes DPID y DPUUID sin el `d_ prefix`.

## DPID y DPUUID: una revisión {#dpid-dpuuid-review}

El DPID y el DPUUID son pares clave-valor que contienen un ID de proveedor de datos y un ID de usuario. Estos pares clave-valor vinculan los ID de proveedor con los ID de usuario. Envían datos durante llamadas de evento, para eventos de sincronización entrantes y para llamadas de ID. Sin ellos, [!DNL Audience Manager], y otros servicios o características, no tendrían una forma de coincidir y sincronizar los ID. Estas variables a veces se expresan con o sin el prefijo `d_`, como se muestra a continuación. Tenga en cuenta que, en el código, *cursiva* indica un marcador de posición de variable.

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
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_dpid=<i>data provider ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>data provider ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID único de usuario del proveedor de datos (DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_dpuuid=<i>data provider unique user ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=<i>data provider unique user ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Estos pares clave-valor siguen funcionando, pero están en desuso. Debe actualizar el código para que utilice CID o CID_IC en su lugar.

## CID y CID_IC: Acerca de {#cid-cidic-about}

Los pares clave-valor CID y CID_IC reemplazan a DPID y DPUUID. Proporcionan las mismas funciones que el DPID y el DPUUID, pero son más eficientes porque incluyen el ID del proveedor de datos (o código de integración) y el ID de usuario en un único par clave-valor. En cada par clave-valor:

* El símbolo = separa la clave de sus valores relacionados.
* El carácter ASCII no imprimible %01 separa los valores.

`d_cid` y `d_cid_ic` utilizan la sintaxis que se muestra a continuación. Tenga en cuenta que, en el código, *cursiva* indica un marcador de posición de variable.

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
   <td colname="col2"> <p> <code>d_cid=<i>data provider ID</i>%01<i>user ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código de integración de ID de cliente (CID_IC) </p> </td> 
   <td colname="col2"> <p> <code>d_cid_ic=<i>integration code</i>%01<i>user ID</i></code> </p> <p> Un código de integración <span class="term"> </span> es un identificador alternativo que puede usar en lugar del ID de Data Source, asignado por el Audience Manager <span class="keyword"> </span>. Consulte <a href="../features/manage-datasources.md#create-data-source"> Crear un Source de datos</a> si necesita configurar un código de integración. </p> </td> 
  </tr> 
 </tbody> 
</table>

Vea también [Variables de URL y Sintaxis para ID declarados](../features/declared-ids.md#variables-and-syntax).

>[!NOTE]
>
>Puede usar códigos de integración para sus propias fuentes de datos y para las [fuentes de datos compartidas](../features/datasources-list-and-settings.md#settings-menu-options) globales a las que tiene acceso. Por ejemplo, puede utilizar códigos de integración al trabajar con fuentes de datos de identificadores móviles. Utilice los siguientes códigos de integración, exactamente como se especifica a continuación:

* **DSID_20914** para GAID, que representa dispositivos que ejecutan el sistema operativo Android.
* **DSID_20915** para IDFA, que representa dispositivos que ejecutan el sistema operativo iOS.

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
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">Nuevo: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">Obsoleto: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sincronización entrante (IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">Nuevo: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">Obsoleto: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Generar UUID de Audience Manager (ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">Nuevo: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">Obsoleto: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Cada llamada también puede incluir varios pares de valor clave `d_cid` y `d_cid_ic` de esta manera:

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## Consideraciones importantes para los equipos de desarrollo {#dev-considerations}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Elemento </p> </th> 
   <th colname="col2" class="entry"> <p>Descripción </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Codificación de URL </p> </td> 
   <td colname="col2"> <p>Sus equipos de desarrollo <i>deben</i> aplicar la codificación de URL a las siguientes variables en el par clave-valor de CID: </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> user ID</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>Nota: debe codificar mediante URL el identificador de usuario y el código de integración <i>antes de</i> concatenarlos en una cadena. Esto se debe a que el carácter ASCII %01 que separa las dos variables no debe capturarse en la codificación de la dirección URL. </p> </p> <p>La codificación de URL garantiza que los ID de usuario y los códigos de integración que contienen caracteres reservados o no seguros, como, entre otros, + o =, se transmitan correctamente a nuestros servidores. </p> <p>Use la tabla de codificación ASCII <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> </a> como referencia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uso de códigos de integración para fuentes de datos compartidos globales </p> </td> 
   <td colname="col2"> <p>Puede usar códigos de integración para sus propios orígenes de datos y para los orígenes de datos compartidos <a href="../features/datasources-list-and-settings.md#settings-menu-options"> globales</a>, a los que tiene acceso. Por ejemplo, puede utilizar códigos de integración al trabajar con fuentes de datos de identificadores móviles. Utilice los siguientes códigos de integración, exactamente como se especifica a continuación: </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>DSID_20914</b> para GAID, que representa dispositivos que ejecutan el sistema operativo Android. </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_20915</b> para IDFA, que representa dispositivos que ejecutan el sistema operativo iOS. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>
