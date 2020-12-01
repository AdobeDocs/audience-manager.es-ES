---
description: Describe los campos requeridos, la sintaxis y las convenciones utilizadas para asignar un nombre a un archivo de datos de salida.
seo-description: Describe los campos requeridos, la sintaxis y las convenciones utilizadas para asignar un nombre a un archivo de datos de salida.
seo-title: Sintaxis y ejemplos del nombre del archivo de datos de salida
solution: Audience Manager
title: Sintaxis y ejemplos del nombre del archivo de datos de salida
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 6%

---


# Nombre del archivo de datos de salida: sintaxis y ejemplos{#outbound-data-file-name-syntax-and-examples}

Describe los campos requeridos, la sintaxis y las convenciones utilizadas para asignar un nombre a un archivo de datos de salida.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>Los elementos de estilo (`monospaced text`, *cursiva*, corchetes `[ ]` `( )`, etc.) en este documento, indique los elementos y las opciones del código. Consulte [Convenciones de estilo para elementos de código y texto](../../../reference/code-style-elements.md) para obtener más información.

## Elementos de sintaxis y nombre de archivo {#syntax-file-name}

Los nombres de archivo salientes contienen los siguientes elementos. Todos los elementos siguientes son opcionales.

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### Parámetros

La tabla define los elementos de un nombre de archivo de datos de salida.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento Nombre de archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>Se refiere a los métodos de transferencia de datos. Los métodos de transferencia incluyen: </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - Transferir mediante SFTP </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3  </span> - Transferir a  <span class="keyword"> Amazon AWS  </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>ID de destino. </p> <p>En el Audience Manager <span class="keyword"> </span>, un destino es la instancia de la integración donde puede asignar los segmentos objetivo. Los clientes pueden tener varios destinos, según los requisitos comerciales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>Proveedor de datos o ID de fuente de datos. Este ID identifica el tipo de ID de usuario presente en el contenido del archivo. Las claves de ID de usuario más comunes son: </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">2014 - <span class="keyword"> ID del anunciante de Google </span> (sin procesar, sin hash) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">2015 - <span class="keyword"> ID de Apple para anunciantes </span> (sin procesar, sin hash) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">ID de proveedor: ID de usuario de terceros (web/cookie) </li> 
     </ul> </p> <p>Consulte <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/global-data-sources.html">Fuentes de datos globales</a> para obtener más información.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> El identificador de cliente de la plataforma de terceros. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>El modo de sincronización es un marcador de posición de macro que agrega una etiqueta al nombre del archivo en función del tipo de sincronización. Los tipos de sincronización incluyen total e incremental. Aparecerán en el nombre del archivo como <code> iter </code> o <code> full </code>. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>:: Indica una sincronización "iterativa" o incremental. Un archivo incremental sólo contiene los nuevos datos recopilados desde la última sincronización. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>:: Indica una sincronización "completa". Un archivo completamente sincronizado contiene datos antiguos y cualquier dato nuevo recopilado desde la última sincronización. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>Marca de hora UNIX de 13 dígitos en milisegundos, en la zona horaria UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>Un entero. Identifica parte de un archivo que se ha dividido en varias partes para mejorar los tiempos de procesamiento. El número indica a qué parte del archivo original pertenecen los datos.</p>  <p>El entero debe tener al menos 3 dígitos de longitud, precedido de ceros, si el tamaño de división es inferior a 100 partes.</p>  <p>El archivo original no tendrá ningún número dividido. El primer archivo dividido finalizará con 001. Consulte los ejemplos siguientes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>Compresión GZIP. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplos de nombres de archivo {#file-name-examples}

### Escenario 1

Archivos enviados a una ubicación [!DNL Amazon S3], con *`PID_ALIAS="XYZCustomer"`* y con [!DNL Google Advertiser IDs] en el contenido del archivo.

Por ejemplo, archivos incrementales:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

Por ejemplo, archivos completos:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### Escenario 2

Archivos enviados a la ubicación [!DNL FTP], sin *`PID_ALIAS`* y con [!DNL Apple Advertiser IDs] en el contenido del archivo:

Por ejemplo, archivos incrementales:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Por ejemplo, archivos completos:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**Escenario 3**: Archivos enviados a la  [!DNL FTP] ubicación, con  *`PID_ALIAS="XYZCustomer"`* y con ID de usuario de terceros en el contenido del archivo (  *`Vendor ID=45454`*):

Por ejemplo, archivos incrementales:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Por ejemplo, archivos completos:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## Contenido del archivo de datos de salida: Sintaxis y parámetros {#outbound-contents-syntax}

Describe los campos requeridos, la sintaxis y las convenciones utilizadas para organizar la información en un archivo de datos de salida. Dé formato a los datos según estas especificaciones.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>Los elementos de estilo (`monospaced text`, *cursiva*, corchetes `[ ]` `( )`, etc.) en este documento, indique los elementos y las opciones del código. Consulte [Convenciones de estilo para elementos de código y texto](../../../reference/code-style-elements.md) para obtener más información.

### Sintaxis

Los campos del archivo de datos aparecen en este orden:

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### Parámetros

La tabla lista variables que definen el contenido de un archivo de datos.

<table id="table_109BA747CFDA40108370EFEB208C7E11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>UUID </i></code> </p> </td> 
   <td colname="col2"> <p>ID de usuario único asignado por el Audience Manager <span class="keyword"> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>Separe el UUID y los datos de segmentos con un espacio </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>ID de segmento al que pertenece un visitante. Separe varios segmentos con una coma. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>ID del segmento desde el que se descalificó al usuario. Separe varios segmentos con una coma. Con una sincronización completa, puede ignorar los segmentos eliminados porque el archivo de datos contendrá la lista completa de los segmentos actuales para el usuario. Normalmente, desea conocer los segmentos a los que pertenece un usuario en lugar de aquellos de los que se han eliminado. Consulte también <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Nombre del archivo de datos de salida: Sintaxis y ejemplos </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Ejemplo: Formato de archivo básico

Un archivo de datos formateado correctamente podría tener un aspecto similar al siguiente ejemplo. Esta entrada de archivo indica que un usuario cumple los requisitos para los segmentos 24, 26 y 27. Si es necesario, un espacio separa los `UUID` y los ID de segmento. Otro espacio separa los conjuntos de ID de segmentos. En este ejemplo, un usuario pertenece a los segmentos 24, 26 y 27. Se han eliminado de los segmentos 25 y 28.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
