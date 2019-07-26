---
description: Describe los campos, la sintaxis, las convenciones de nomenclatura y los tamaños de archivo que debe seguir al enviar datos a Audience Manager. Configure los nombres y tamaños de los archivos según estas especificaciones cuando envíe datos a un directorio de Audience Manager/Amazon S 3.
seo-description: Describe los campos, la sintaxis, las convenciones de nomenclatura y los tamaños de archivo que debe seguir al enviar datos a Audience Manager. Configure los nombres y tamaños de los archivos según estas especificaciones cuando envíe datos a un directorio de Audience Manager/Amazon S 3.
seo-title: Requisitos de tamaño de archivo y nombre de Amazon S 3 para archivos de datos de entrada
solution: Audience Manager
title: Requisitos de tamaño de archivo y nombre de Amazon S 3 para archivos de datos de entrada
uuid: 3692 a 122-6 ad 5-468 c -934 e -53067 bd 8 cf 71
translation-type: tm+mt
source-git-commit: ec2d05290874a95e9cc9b8318fcc5e1e1986f5b9

---


# Amazon S3 Name and File Size Requirements for Inbound Data Files{#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Describe los campos, la sintaxis, las convenciones de nomenclatura y los tamaños de archivo que debe seguir al enviar datos a Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / [!DNL Amazon S3] directory.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *cursiva*, paréntesis `[ ]` `( )`, etc.) en este documento indican elementos y opciones de código. Consulte [Convenciones de estilo para elementos de código y texto](../../../reference/code-style-elements.md) para obtener más información.

## File Name Syntax {#file-name-syntax}

[!DNL S3] los nombres de archivo contienen los siguientes elementos opcionales y requeridos:

* **[!DNL S3]prefijo:**`s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Elementos del nombre de archivo:**`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

For other accepted file name formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {important = "high"}
>
>[!DNL Audience Manager] solo procesos y [!DNL ASCII] archivos [!DNL UTF-8] codificados.

### Asignar nombres a elementos

The table defines the elements in an [!DNL S3] file name.

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento Nombre </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>AWS_ directory</i></code> </p> </td> 
   <td colname="col2"> <p>La ruta y el nombre del depósito Amazon S 3. Póngase en contacto con su administrador de cuentas para conocer el nombre del directorio S 3, la ruta y las credenciales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date =<i>aaaa-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Marca de tiempo (basada en hora UTC) de cuando envía los archivos al bloque S 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>The <span class="term"> Data Provider ID</span> (DPID) is an identifier that tells <span class="keyword"> Audience Manager</span> if a data file contains your own user IDs or Android or iOS IDs. Acepta las siguientes opciones: </p> <p> <b>ID del socio de datos</b> </p> <p>Es una ID única de Audience Manager que asigna a su empresa u organización. Utilice este ID asignado en un nombre de archivo al enviar datos que contengan sus propios ID de usuario. For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </p> <p> <b>ID de Android (GAID)</b> </p> <p> Utilice ID 20914 como DPID en un nombre de archivo de datos si el archivo contiene ID de Android. When you use ID 20914 as the DPID, you still need to identify your company to <span class="keyword"> Audience Manager</span>. This means the file name must use the <code><i>_DPID_TARGET_DATA_OWNER</i></code> parameter to hold your company ID. Por ejemplo, supongamos que está pasando archivos con ID de Android y que su ID de proveedor de datos es 21. In this case, the file name would look like <code>...ftp_dpm_20914_21_123456789.sync</code>. This tells <span class="keyword"> Audience Manager</span> the file contains Android IDs and is from a partner identified by ID 21. </p> <p> <b>ID de iOS (IDFA)</b> </p> <p> Utilice ID 20915 como DPID en un nombre de archivo de datos si el archivo contiene ID de iOS. When you use ID 20915 as the DPID, you still need to identify your company to <span class="keyword"> Audience Manager</span>. This means the file name must use the <code><i>_DPID_TARGET_DATA_OWNER</i></code> parameter to hold your company ID. Por ejemplo, supongamos que está pasando archivos con ID de Android y que su ID de proveedor de datos es 21. In this case, the file name would look like <code>...ftp_dpm_20915_21_123456789.sync</code>. This tells <span class="keyword"> Audience Manager</span> the file contains iOS IDs and is from a partner identified by ID 21. </p> 
    <draft-comment> 
     <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
      <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID del socio de datos:</b> Es una ID única de Audience Manager que asigna a su empresa u organización. Utilice este ID asignado en un nombre de archivo al enviar datos que contengan sus propios ID de usuario. For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </li> 
      <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>ID de Android (GAID):</b> Utilice ID 20914 en un nombre de archivo de datos si contiene el ID de Android. For example, <code>...ftp_dpm_20914_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only. Nota: el ID 21 </li> 
      <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID de iOS (IDFA):</b> Utilice ID 20915 en un nombre de archivo de datos si contiene ID de iOS. For example, <code>...ftp_dpm_20915_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only. </li> 
     </ul> 
    </draft-comment> <p> <p>Nota: No combine los tipos de ID en los archivos de datos. Por ejemplo, si el nombre de archivo incluye el identificador de Android, no coloque ID de iOS ni sus propios ID en el archivo de datos. </p> </p> <p>See also the <code><i>_DPID_TARGET_DATA_OWNER</i></code> entry below. </p> </td> 
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
   <td colname="col1"> <p> <code><i>partner_ name</i></code> </p> </td> 
   <td colname="col2"> <p>The company or organization name you use in <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP</i></code> </p> </td> 
   <td colname="col2"> <p>Una marca de tiempo UTC UNIX de 10 dígitos en segundos. La marca de tiempo ayuda a hacer único cada nombre de archivo. </p> 
    <draft-comment> 
     <p> <p>Nota: Audience Manager no utiliza la marca de tiempo durante el procesamiento de archivos de entrada. La marca de tiempo del nombre de archivo se ha desaprobado en Audience Manager, pero sigue siendo necesaria para la compatibilidad con versiones anteriores. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (. sync |. overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opciones de sincronización que incluyen: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sincronizar: Situación normal cuando proveedores de datos de terceros envían características por usuario para añadirlas o eliminarlas en el sistema de Audience Manager.</code> </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> sobrescribir: Permite que los proveedores de datos envíen una lista de características por usuario que debe sobrescribir todas las características de terceros existentes de este usuario para este proveedor de datos en Audience Manager. </code> No es necesario incluir a todos los usuarios en un archivo de sobrescritura. Incluya sólo a los usuarios que desee cambiar. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_ NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un entero. Se utiliza cuando divide archivos de gran tamaño en varias partes para mejorar los tiempos de procesamiento. El número indica qué parte del archivo original está enviando. </p> <p>Para un procesamiento eficaz de archivos, divida los archivos de datos como se indica: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Sin comprimir: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Comprimido: 200 a 300 MB </li> 
    </ul> <p>See the first 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> file name examples</a> below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Cuando envíe archivos a Amazon S 3, utilice solo compresión gzip. When compressed, these files get the <code> .gz</code> extension. No utilice.zip compresión. </p> <p>Los archivos comprimidos deben ser de 3 GB o menos. Si los archivos son más grandes, póngase en contacto con el Servicio de atención al cliente. Aunque Audience Manager puede gestionar archivos de gran tamaño, es posible que podamos ayudarle a reducir el tamaño de los archivos y hacer que las transferencias de datos sean más eficientes. See <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> File Compression for Inbound Data Transfer Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

Los siguientes ejemplos muestran nombres de archivo formateados correctamente. Los nombres de archivos podrían tener un aspecto similar.

<ul class="simplelist"> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_ dpm_ 478_ 1366545717. sync</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_ dpm_ 478_ 1366545717. overwrite</code> </li> 
</ul>

[Puede descargar](assets/ftp_dpm_1234_1445374061.overwrite) el archivo de ejemplo si desea obtener ejemplos adicionales. This file has been saved with the `.overwrite` file extension. Ábrala con un editor de texto sencillo.

## Accepted File Sizes {#accepted-file-sizes}

Consider the figures below for fastest/earliest processing of your files as well as for file size limitations when you send data to an [!DNL Audience Manager] / [!DNL Amazon S3] directory.

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

>[!NOTE]
>
>El proceso de validación de datos entrante marcará los archivos vacíos como no válidos y no los procesará.

>[!MORE_ LIKE_ THIS]
>
>* [Requisitos de nombre de FTP para archivos de datos de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

