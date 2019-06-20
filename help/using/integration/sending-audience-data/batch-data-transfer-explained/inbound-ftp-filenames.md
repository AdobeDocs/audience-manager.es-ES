---
description: Describe los campos, la sintaxis, las convenciones de nomenclatura y los tamaños de archivo que debe seguir al enviar datos a Audience Manager. Defina los nombres y tamaños de los archivos según estas especificaciones cuando envíe datos a un directorio de FTP de Audience Manager.
seo-description: Describe los campos, la sintaxis, las convenciones de nomenclatura y los tamaños de archivo que debe seguir al enviar datos a Audience Manager. Defina los nombres y tamaños de los archivos según estas especificaciones cuando envíe datos a un directorio de FTP de Audience Manager.
seo-title: Requisitos de nombre de archivo y nombre de FTP para archivos de datos de entrada
solution: Audience Manager
title: Requisitos de nombre de archivo y nombre de FTP para archivos de datos de entrada
uuid: 49 eaafac -5 cb 0-482 f -872 a -84 c 056016 bdb
translation-type: tm+mt
source-git-commit: ec2d05290874a95e9cc9b8318fcc5e1e1986f5b9

---


# FTP Name and File Size Requirements for Inbound Data Files{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Describe los campos, la sintaxis, las convenciones de nomenclatura y los tamaños de archivo que debe seguir al enviar datos a Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager [!DNL FTP] directory.

>[!WARNING]
>
>Ya no se admite la transferencia FTP para archivos de datos entrantes. Utilice Amazon S 3 en los datos sin conexión. See [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) for details.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *cursiva*, paréntesis `[ ]` `( )`, etc.) en este documento indican elementos y opciones de código. Consulte [Convenciones de estilo para elementos de código y texto](../../../reference/code-style-elements.md) para obtener más información.

## File Name Syntax {#file-name-syntax}

[!DNL FTP] los nombres de archivo contienen los siguientes elementos opcionales y requeridos:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

For other accepted file name formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {important = &quot;high&quot;}
>
>[!DNL Audience Manager] solo procesos y [!DNL ASCII] archivos [!DNL UTF-8] codificados.

### Asignar nombres a elementos

The table defines the elements in an [!DNL FTP] file name.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento Nombre de archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_ dpm_</code> </p> </td> 
   <td colname="col2"> <p>The path to and name of your <span class="keyword"> Audience Manager</span> FTP directory. Póngase en contacto con su administrador de cuentas para conocer el directorio y las credenciales del FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>An lD that tells <span class="keyword"> Audience Manager</span> if a data file contains your own user IDs or Android or iOS IDs. Acepta las siguientes opciones: </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID del socio de datos:</b> Es una ID única de Audience Manager que asigna a su empresa u organización. Utilice este ID asignado en un nombre de archivo al enviar datos que contengan sus propios ID de usuario. For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>ID de Android (GAID):</b> Utilice ID 20914 en un nombre de archivo de datos si contiene el ID de Android. For example, <code>...ftp_dpm_20914_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID de iOS (IDFA):</b> Utilice ID 20915 en un nombre de archivo de datos si contiene ID de iOS. For example, <code>...ftp_dpm_20915_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only. </li> 
    </ul> <p> <p>Nota: No combine los tipos de ID en los archivos de datos. Por ejemplo, si el nombre de archivo incluye el identificador de Android, no coloque ID de iOS ni sus propios ID en el archivo de datos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>_ DPID_ TARGET_ DATA_ OWNER</i></code> </p> </td> 
   <td colname="col2"> <p>Marcador de posición para un ID. For example, you could set it to your <span class="keyword"> Audience Manager</span> ID if you set the DPID to a data source ID or an Android or iOS ID. This lets <span class="keyword"> Audience Manager</span> link the file data back to your organization. </p> <p>Por ejemplo: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>… ftp_ dpm_ 33_ 21_ 1234567890. sync</code> muestra un socio con ID 21 enviado en datos desde un origen de datos que utiliza ID 33. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>… ftp_ dpm_ 20914_ 21_ 1234567890. sync</code> muestra un socio con ID 21 enviado en datos que contienen ID de Android. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>… ftp_ dpm_ 20915_ 21_ 1234567890. sync</code> muestra un socio con ID 21 enviado en datos que contienen ID de iOS. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (. sync |. overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opciones de sincronización que incluyen: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sincronizar: Situación normal cuando proveedores de datos de terceros envían características por usuario para añadirlas o eliminarlas en el sistema de Audience Manager.</code> </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> sobrescribir: Permite a los clientes y proveedores de datos enviar una lista de características por usuario que debe sobrescribir todas las características existentes de este usuario para una fuente de datos determinada en Audience Manager. </code> No es necesario incluir a todos los usuarios en un archivo de sobrescritura. Incluya sólo a los usuarios que desee cambiar. No se borrarán las características que no estén asignadas a la fuente de datos objetivo. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_ NUMBER</i></code>] </p> </td> 
   <td colname="col2"> <p>Un entero. Se utiliza cuando divide archivos de gran tamaño en varias partes para mejorar los tiempos de procesamiento. El número indica qué parte del archivo original está enviando. </p> <p>Para un procesamiento eficaz de archivos, divida los archivos de datos como se indica: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Sin comprimir: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Comprimido: 200 a 300 MB </li> 
    </ul> <p>See the first 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> file name examples</a> below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP</i></code> </p> </td> 
   <td colname="col2"> <p>Una marca de tiempo UTC UNIX de 10 dígitos en segundos. La marca de tiempo ayuda a hacer único cada nombre de archivo. </p> 
    <draft-comment> 
     <p> <p>Nota: Audience Manager no utiliza la marca de tiempo durante el procesamiento de archivos de entrada. La marca de tiempo del nombre de archivo se ha desaprobado en Audience Manager, pero sigue siendo necesaria para la compatibilidad con versiones anteriores. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip es el formato de compresión permitido para un nombre de archivo FTP. Si utiliza la compresión de archivos, asegúrese de que el nombre del archivo tenga la extensión correcta. </p> <p>Los archivos comprimidos deben ser de 3 GB o menos. Si los archivos de archivos son más grandes, póngase en contacto con el Servicio de atención al cliente. Aunque Audience Manager puede gestionar archivos de gran tamaño, es posible que podamos ayudarle a reducir el tamaño de los archivos y hacer que las transferencias de datos sean más eficientes. See <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> File Compression for Inbound Data Transfer Files</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

Los siguientes ejemplos muestran nombres de archivo formateados correctamente. Los nombres de archivos podrían tener un aspecto similar.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_ dpm_ 478_ 1366545717. overwrite</code> </li> 
</ul>

[Descargue](assets/ftp_dpm_1234_1445374061.overwrite) el archivo de ejemplo si necesita ejemplos adicionales. This file is saved with the `.overwrite` file extension. Ábrala con un editor de texto sencillo.

## Accepted File Sizes {#accepted-file-sizes}

Consider the figures below for fastest/earliest processing of your files as well as for file size limitations when you send data to an [!DNL Audience Manager] / [!DNL FTP] directory.

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
   <td colname="col2"> <p>200 a 300 MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Sin comprimir</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

