---
description: Describe los campos requeridos, la sintaxis, las convenciones de nomenclatura y los tamaños de archivo que debe seguir al enviar datos al Audience Manager. Configure los nombres y tamaños de los archivos según estas especificaciones cuando envíe datos a un directorio FTP de Audience Manager.
seo-description: Describe los campos requeridos, la sintaxis, las convenciones de nomenclatura y los tamaños de archivo que debe seguir al enviar datos al Audience Manager. Configure los nombres y tamaños de los archivos según estas especificaciones cuando envíe datos a un directorio FTP de Audience Manager.
seo-title: Requisitos de tamaño de archivo y nombre de FTP para archivos de datos de entrada
solution: Audience Manager
title: Requisitos de tamaño de archivo y nombre de FTP para archivos de datos de entrada
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 9%

---


# [!DNL FTP]Requisitos de tamaño de archivo y nombre de para archivos de datos de entrada{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Describe los campos requeridos, la sintaxis, las convenciones de nomenclatura y los tamaños de archivo que debe seguir al enviar datos a [!DNL Audience Manager]. Configure los nombres y tamaños de los archivos según estas especificaciones cuando envíe datos a un directorio de Audience Manager [!DNL FTP] .

>[!WARNING]
>
>We are gradually phasing out support for [!DNL FTP] configurations. While inbound data file ingestion is still supported in existing [!DNL FTP] integrations, we strongly recommend using [!DNL Amazon S3] to onboard offline data for new integrations. Consulte [Requisitos de nomenclatura y tamaño de archivo de Amazon S3 para archivos de datos entrantes](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) para obtener más información.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *cursiva*, paréntesis `[ ]` `( )`, etc.) en este documento, indique los elementos y las opciones del código. Consulte [Convenciones de estilo para elementos de código y texto](../../../reference/code-style-elements.md) para obtener más información.

## Sintaxis del nombre del archivo {#file-name-syntax}

[!DNL FTP] los nombres de archivo contienen los siguientes elementos opcionales y requeridos:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Para ver otros formatos de nombre de archivo aceptados, consulte Integraciones [de socio](/help/using/integration/sending-audience-data/custom-partner-integrations.md)personalizadas.

>[!NOTE] {important=&quot;high&quot;}
>
>[!DNL Audience Manager] solo procesa [!DNL ASCII] y [!DNL UTF-8] codifica archivos.

### Asignar nombres a los elementos

La tabla define los elementos de un nombre de [!DNL FTP] archivo.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento Nombre de archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>La ruta y el nombre del directorio FTP del <span class="keyword"> Audience Manager</span> . Póngase en contacto con el administrador de cuentas para obtener el directorio FTP y las credenciales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Un ID que indica al <span class="keyword"> Audience Manager</span> si un archivo de datos contiene sus propios ID de usuario o Android o iOS. Acepta las siguientes opciones: </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID del socio de datos:</b> Es un Audience Manager de ID exclusivo que se asigna a su compañía u organización. Utilice este ID asignado en un nombre de archivo cuando envíe datos que contengan sus propios ID de usuario. Por ejemplo, <code>...ftp_dpm_21_123456789.sync</code> indica al <span class="keyword"> Audience Manager</span> que un socio con ID 21 envió el archivo y contiene ID de usuario asignados por dicho socio. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>ID de Android (GAID):</b> Utilice el ID 20914 en un nombre de archivo de datos si contiene el ID de Android. Por ejemplo, <code>...ftp_dpm_20914_123456789.sync</code> indica al <span class="keyword"> Audience Manager</span> que el archivo de datos solo contiene ID de Android. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID de iOS (IDFA):</b> Utilice el ID 20915 en un nombre de archivo de datos si contiene ID de iOS. Por ejemplo, <code>...ftp_dpm_20915_123456789.sync</code> indica al <span class="keyword"> Audience Manager</span> que el archivo de datos solo contiene ID de iOS. </li> 
    </ul> <p> <p>Nota:  No mezcle los tipos de ID en los archivos de datos. Por ejemplo, si el nombre de archivo incluye el identificador de Android, no incluya los ID de iOS ni los propios ID en el archivo de datos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Marcador de posición para un ID. Por ejemplo, puede configurarlo en su ID de <span class="keyword"> Audience Manager</span> si establece el DPID en un ID de origen de datos o un ID de Android o iOS. Esto permite al <span class="keyword"> Audience Manager</span> volver a vincular los datos del archivo a su organización. </p> <p>Por ejemplo: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>...ftp_dpm_33_21_1234567890.sync</code> La muestra un socio con ID 21 que ha enviado datos desde un origen de datos que utiliza ID 33. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>...ftp_dpm_20914_21_1234567890.sync</code> La muestra un socio con ID 21 enviado en datos que contienen ID de Android. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>...ftp_dpm_20915_21_1234567890.sync</code> La muestra un socio con ID 21 enviado en datos que contienen ID de iOS. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opciones de sincronización que incluyen: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>:: escenario normal cuando proveedores de datos de terceros envían características por usuario para agregarlas o eliminarlas en el sistema de Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>:: Permite a los clientes y proveedores de datos enviar una lista de características por usuario que debe sobrescribir todas las características existentes de este usuario para una fuente de datos determinada en Audience Manager. No es necesario incluir todos los usuarios en un archivo de sobrescritura. Incluya solo los usuarios que desee cambiar. Las características que no están asignadas al origen de datos de destinatario no se borran. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i></code>] </p> </td> 
   <td colname="col2"> <p>Un entero. Se utiliza cuando se dividen archivos grandes en varias partes para mejorar los tiempos de procesamiento. El número indica qué parte del archivo original está enviando. </p> <p>Para un procesamiento eficaz de archivos, divida los archivos de datos como se indica: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Sin comprimir: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Comprimido: 200-300 MB </li> 
    </ul> <p>Consulte los dos primeros ejemplos <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"></a> de nombres de archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Marca de hora UNIX de 10 dígitos en segundos. La marca de tiempo ayuda a hacer que cada nombre de archivo sea único. </p> 
    <draft-comment> 
     <p> <p>Nota:  Audience Manager no utiliza la marca de tiempo durante el procesamiento de archivos entrantes. La marca de tiempo del nombre de archivo se ha desaprobado en Audience Manager, pero sigue siendo necesaria para la compatibilidad con versiones anteriores. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip es el formato de compresión permitido para un nombre de archivo FTP. Si utiliza compresión de archivos, asegúrese de que el nombre del archivo tenga la extensión adecuada. </p> <p>Los archivos comprimidos deben tener 3 GB o menos. Si los archivos son más grandes, póngase en contacto con el Servicio de atención al cliente. Aunque el Audience Manager puede gestionar archivos de gran tamaño, es posible que podamos ayudarle a reducir el tamaño de los archivos y aumentar la eficacia de las transferencias de datos. Consulte <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">Compresión de archivos de transferencia de datos entrantes</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplos de nombres de archivo {#file-name-examples}

Los siguientes ejemplos muestran nombres de archivo con el formato correcto. Los nombres de archivo podrían ser similares.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[Descargue](assets/ftp_dpm_1234_1445374061.overwrite) el archivo de muestra si necesita ejemplos adicionales. Este archivo se guarda con la extensión `.overwrite` de archivo. Ábralo con un editor de texto sencillo.

## Tamaños de archivo aceptados {#accepted-file-sizes}

Tenga en cuenta las siguientes cifras para un procesamiento más rápido y más temprano de sus archivos, así como para las limitaciones de tamaño de los archivos al enviar datos a un directorio [!DNL Audience Manager] / [!DNL FTP] .

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de archivo </th> 
   <th colname="col2" class="entry"> Tamaño óptimo </th> 
   <th colname="col3" class="entry"> Tamaño máximo </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Comprimido</b> </td> 
   <td colname="col2"> <p>200-300 MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Sin comprimir</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

