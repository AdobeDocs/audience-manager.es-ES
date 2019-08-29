---
description: Describe los campos, la sintaxis y las convenciones requeridos para nombrar un archivo de datos saliente.
seo-description: Describe los campos, la sintaxis y las convenciones requeridos para nombrar un archivo de datos saliente.
seo-title: Sintaxis y ejemplos del nombre de archivo de datos salientes
solution: Audience Manager
title: Sintaxis y ejemplos del nombre de archivo de datos salientes
uuid: effdcaf 6-c 37 c -45 f 3-9 d 2 f-a 938 a 9 da 47 a 6
translation-type: tm+mt
source-git-commit: e6f1a3b86658a882ebe927cefe55be6ddd40b906

---


# Nombre del archivo de datos saliente: Sintaxis y ejemplos{#outbound-data-file-name-syntax-and-examples}

Describe los campos, la sintaxis y las convenciones requeridos para nombrar un archivo de datos saliente.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>Los elementos style (`monospaced text`, *cursiva*, corchetes `[ ]``( )`, etc.) en este documento indican elementos y opciones de código. Consulte [Convenciones de estilo para elementos de código y texto](../../../reference/code-style-elements.md) para obtener más información.

## Elementos de sintaxis y nombre de archivo {#syntax-file-name}

Los nombres de archivos salientes contienen los siguientes elementos. Todos los elementos siguientes son opcionales.

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### Parámetros

La tabla define los elementos en un nombre de archivo de datos saliente.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento Nombre de archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_ TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>Se refiere a los métodos de transferencia de datos. Los métodos de transferencia incluyen: </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - Transferencia mediante SFTP </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S 3 </span> - Transferencia a <span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>ID de destino. </p> <p><span class="keyword"> En Audience Manager </span>, un destino es la instancia de la integración donde puede asignar sus segmentos objetivo. Los clientes pueden tener múltiples destinos, según el requisito comercial. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_ DPID </i></code> </p> </td> 
   <td colname="col2"> <p>ID de datos o proveedor de datos. Este ID identifica el tipo de ID de usuario presente en el contenido del archivo. Las claves de ID de usuario más comunes son: </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> ID del anunciante de Google </span> (sin procesar, sin límite) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - ID <span class="keyword"> de Apple para anunciantes </span> (sin procesar, sin límite) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">ID de proveedor: ID de usuario de terceros (web/cookie) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ ALIAS </i></code> </p> </td> 
   <td colname="col2"> Identificador de cliente de la plataforma de terceros. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_ MODE </i></code> </p> </td> 
   <td colname="col2"> <p>El modo de sincronización es un marcador de posición de macro que agrega una etiqueta al nombre del archivo en función del tipo de sincronización. Los tipos de sincronización son completos e incrementales. Aparecerá en el nombre del archivo como <code> iter </code> o <code> lleno </code>. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>: Indica una sincronización «iterativa» o incremental. Un archivo incremental contiene solamente los nuevos datos recopilados desde la última sincronización. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>: Indica una sincronización "completa". Un archivo completamente sincronizado contiene datos antiguos y cualquier dato nuevo recopilado desde la última sincronización. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>Una marca de tiempo UNIX de 13 dígitos en milisegundos, en la zona horaria UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>Un entero. Identifica parte de un archivo que se divide en varias partes para mejorar los tiempos de procesamiento. El número indica a qué parte del archivo original pertenece los datos.</p>  <p>El número entero debe tener al menos 3 dígitos, precedido por ceros, si el tamaño dividido es inferior a 100 partes.</p>  <p>El archivo original no tendrá ningún número dividido. El primer archivo dividido terminará con 001. Consulte los ejemplos siguientes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (opcional) </i></code> </p> </td> 
   <td colname="col2"> <p>Compresión GZIP. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplos de nombres de archivos {#file-name-examples}

### Escenario 1

Archivos enviados a una [!DNL Amazon S3] ubicación, con *`PID_ALIAS="XYZCustomer"`* y con [!DNL Google Advertiser IDs] contenido del archivo.

P. ej. archivos incremental:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

P. ej. archivos completos:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### Escenario 2

Archivos enviados a [!DNL FTP] la ubicación, sin *`PID_ALIAS`* y con [!DNL Apple Advertiser IDs] el contenido del archivo:

P. ej. archivos incremental:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

P. ej. archivos completos:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**Escenario 3**: Archivos enviados a [!DNL FTP] la ubicación, con *`PID_ALIAS="XYZCustomer"`* y con ID de usuario de terceros en el contenido del archivo ( *`Vendor ID=45454`*):

P. ej. archivos incremental:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

P. ej. archivos completos:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## Contenido del archivo de datos saliente: Sintaxis y parámetros {#outbound-contents-syntax}

Describe los campos, la sintaxis y las convenciones necesarios para organizar la información en un archivo de datos saliente. Dé formato a los datos según estas especificaciones.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>Los elementos style (`monospaced text`, *cursiva*, corchetes `[ ]``( )`, etc.) en este documento indican elementos y opciones de código. Consulte [Convenciones de estilo para elementos de código y texto](../../../reference/code-style-elements.md) para obtener más información.

### Sintaxis

Los campos del archivo de datos aparecen en este orden:

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### Parámetros

La tabla enumera las variables que definen el contenido de un archivo de datos.

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
   <td colname="col2"> <p>ID de usuario exclusivo asignado por <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt; ESPACIO &gt; </i></code> </p> </td> 
   <td colname="col2"> <p>Separe el UUID y los datos de segmentos con un espacio </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_ N </i></code> </p> </td> 
   <td colname="col2"> <p>ID del segmento al que pertenece un visitante. Separe varios segmentos con una coma. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_ SEGMENT_ N </i></code> </p> </td> 
   <td colname="col2"> <p>ID del segmento desde el que se descalifica al usuario. Separe varios segmentos con una coma. Con una sincronización completa, puede ignorar los segmentos eliminados, ya que el archivo de datos contendrá la lista completa de segmentos actuales para el usuario. Normalmente, desea saber de segmentos a los que pertenece un usuario en lugar de hacerlo de los que se han eliminado. Consulte también <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Nombre del archivo de datos saliente: Sintaxis y ejemplos </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Ejemplo: Formato de archivo básico

Un archivo de datos con formato correcto podría tener un aspecto similar al siguiente ejemplo. Esta entrada de archivo indica que un usuario cumple los requisitos para los segmentos 24, 26 y 27. Si es necesario, un espacio separa los ID `UUID` y los segmentos de segmento. Otro espacio separa los conjuntos de ID de segmento. En este ejemplo, un usuario pertenece a los segmentos 24, 26 y 27. Se han eliminado de los segmentos 25 y 28.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
