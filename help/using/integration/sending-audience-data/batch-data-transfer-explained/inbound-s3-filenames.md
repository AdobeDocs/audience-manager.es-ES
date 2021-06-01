---
description: Describe los campos requeridos, la sintaxis, las convenciones de nomenclatura y los tamaños de archivo que debe seguir al enviar datos al Audience Manager. Configure los nombres y tamaños de sus archivos según estas especificaciones cuando envíe datos a un directorio Audience Manager/Amazon S3.
seo-description: Describe los campos requeridos, la sintaxis, las convenciones de nomenclatura y los tamaños de archivo que debe seguir al enviar datos al Audience Manager. Configure los nombres y tamaños de sus archivos según estas especificaciones cuando envíe datos a un directorio Audience Manager/Amazon S3.
seo-title: Requisitos de tamaño de archivo y nomenclatura de Amazon S3 para archivos de datos entrantes
solution: Audience Manager
title: Requisitos de tamaño de archivo y nomenclatura de Amazon S3 para archivos de datos entrantes
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Transferencias de datos de entrada
exl-id: 428acdb5-fff0-4b70-b15a-e384aed9cc2d
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 6%

---

# [!DNL Amazon S3] requisitos de tamaño de archivo y nombre para archivos de datos entrantes  {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Describe los campos requeridos, la sintaxis, las convenciones de nomenclatura y los tamaños de archivo que debe seguir al enviar datos a [!DNL Audience Manager]. Configure los nombres y tamaños de sus archivos según estas especificaciones cuando envíe datos a un directorio [!DNL Audience Manager] / [!DNL Amazon S3].

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *cursiva*, paréntesis `[ ]` `( )`, etc.) en este documento, indique los elementos de código y las opciones. Consulte [Convenciones de estilo para elementos de código y texto](../../../reference/code-style-elements.md) para obtener más información.

## Sintaxis del nombre de archivo {#file-name-syntax}

[!DNL S3] los nombres de archivo contienen los siguientes elementos opcionales y requeridos:

* **[!DNL S3]prefijo:**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Elementos de nombre de archivo:**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Para ver otros formatos de nombre de archivo aceptados, consulte [Integraciones de socio personalizadas](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager] solo procesa  [!DNL ASCII] y  [!DNL UTF-8] codifica archivos.

### Elementos de nombre

La tabla define los elementos de un nombre de archivo [!DNL S3].

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento Nombre </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>La ruta y el nombre del espacio de Amazon S3. Póngase en contacto con el administrador de su cuenta para obtener el nombre, la ruta y las credenciales de su directorio S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Marca de fecha y hora (según la hora UTC) del momento en el que se envían los archivos al compartimento S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Un lD que indica al <span class="keyword"> Audience Manager</span> si un archivo de datos contiene sus propios ID de usuario, ID de Android, ID de iOS u otros ID pertenecientes a <a href="/help/using/features/global-data-sources.md"> fuentes de datos globales</a>. Acepta las siguientes opciones:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID de fuente de datos (también conocido como ID de proveedor de datos): </b> se trata de un ID exclusivo que el Audience Manager asigna a una fuente de datos (consulte el  <a href="/help/using/reference/ids-in-aam.md"> índice de ID del Audience Manager  </a>). Utilice este ID asignado en un nombre de archivo al enviar datos que contengan sus propios ID de usuario. Por ejemplo, <code>...ftp_dpm_21_123456789.sync</code> indica al <span class="keyword"> Audience Manager</span> que incorpore datos a los ID que pertenecen a la fuente de datos 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID (GAID): </b> utilice el ID 20914 en un nombre de archivo de datos si contiene Android ID. Debe utilizar el campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> cuando utilice Android ID. Por ejemplo, <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> indica al <span class="keyword"> Audience Manager</span> que el archivo de datos contiene solo ID de Android y que los ID deben cumplir los requisitos para los rasgos pertenecientes a la fuente de datos <code><i>_DPID_TARGET_DATA_OWNER</i></code> .</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID de iOS (IDFA): </b> utilice el ID 20915 en un nombre de archivo de datos si contiene ID de iOS. Debe utilizar el campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> cuando utilice ID de iOS. Por ejemplo, <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> indica al Audience Manager <span class="keyword"></span> que el archivo de datos contiene solo ID de iOS y que los ID deben cumplir los requisitos para los rasgos pertenecientes a la fuente de datos <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li>
     <li> <b>ID que pertenecen a otras fuentes</b> de datos globales: Puede incorporar ID de Roku para publicidad (RIDA), ID de publicidad de Microsoft (MAID) y otros ID. Utilice el ID correspondiente a cada fuente de datos, tal como se describe en el artículo <a href="/help/using/features/global-data-sources.md"> de fuentes de datos globales</a>.</li> 
    </ul> <p> <p>Nota:  No mezcle los tipos de ID en los archivos de datos. Por ejemplo, si el nombre de archivo incluye el identificador de Android, no inserte ID de iOS o ID propios en el archivo de datos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Este campo indica al Audience Manager a qué fuente de datos debe incorporar los datos. Este campo es obligatorio si se establece el DPID en un ID de Android o un ID de iOS u otro ID que pertenezca a fuentes de datos globales. Esto permite que el <span class="keyword"> Audience Manager</span> vuelva a vincular los datos del archivo a su organización. </p> <p>Por ejemplo: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> indica al Audience Manager que está calificando los ID de cliente pertenecientes a la fuente de datos 33 para características o señales pertenecientes a la fuente de datos 21. </li> 
     <li> <b>ID de Android (GAID): </b> <code>...ftp_dpm_20914_21_1234567890.sync</code> indica a  <span class="keyword"> Audience </span> Manager que el archivo de datos contiene solo ID de Android y que los ID deben cumplir los requisitos para los rasgos pertenecientes a la fuente de datos 21.</li> 
     <li> <b>ID de iOS (IDFA): </b> <code>...ftp_dpm_20915_21_1234567890.sync</code> indica a  <span class="keyword"> Audience </span> Manager que el archivo de datos contiene solo ID de iOS y que los ID deben cumplir los requisitos para los rasgos pertenecientes a la fuente de datos 21.</li>
     <li> <b>ID que pertenecen a otras fuentes</b> de datos globales:  <code>...ftp_dpm_121963_21_1234567890.sync</code> indica a  <span class="keyword"> Audience </span> Manager que el archivo de datos contiene solo ID de Roku y que los ID deben cumplir los requisitos para los rasgos pertenecientes a la fuente de datos 21. Utilice el ID correspondiente a cada fuente de datos, tal como se describe en el artículo <a href="/help/using/features/global-data-sources.md"> de fuentes de datos globales</a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>El nombre de empresa u organización que utiliza en el Audience Manager <span class="keyword"></span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Marca de tiempo UNIX UTC de 10 dígitos en segundos. La marca de tiempo ayuda a que cada nombre de archivo sea único. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opciones de sincronización que incluyen: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Caso normal cuando proveedores de datos de terceros envían rasgos por usuario para agregarlos o eliminarlos en el sistema de Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Permite que los proveedores de datos envíen una lista de características por usuario que debe sobrescribir todos los rasgos de terceros de este usuario para este proveedor de datos en el Audience Manager. No es necesario incluir a todos los usuarios en un archivo de sobrescritura. Incluir solo los usuarios que desee cambiar. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un entero. Se utiliza cuando se dividen archivos grandes en varias partes para mejorar los tiempos de procesamiento. El número indica qué parte del archivo original está enviando. </p> <p>Para un procesamiento eficaz de los archivos, divida los archivos de datos como se indica: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Sin comprimir: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Comprimido: 200-300 MB </li> 
    </ul> <p>Consulte los dos primeros ejemplos de nombres de archivo <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"></a> a continuación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Cuando envíe archivos a Amazon S3, utilice solo compresión gzip. Cuando se comprime, estos archivos obtienen la extensión <code> .gz</code>. No utilice la compresión .zip. </p> <p>Los archivos comprimidos deben tener 3 GB o menos. Si sus archivos son más grandes, póngase en contacto con el Servicio de atención al cliente. Aunque el Audience Manager puede gestionar archivos de gran tamaño, es posible que podamos ayudarle a reducir el tamaño de sus archivos y aumentar la eficacia de las transferencias de datos. Consulte <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">Compresión de archivos de transferencia de datos entrantes</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplos de nombres de archivo {#file-name-examples}

Los siguientes ejemplos muestran nombres de archivo con el formato correcto. Sus nombres de archivo podrían tener un aspecto similar.

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

Puede [descargar](assets/ftp_dpm_1234_1445374061.overwrite) el archivo de muestra si desea ver más ejemplos. Este archivo se ha guardado con la extensión de archivo `.overwrite`. Ábrala con un editor de texto sencillo.

## Tamaños de archivo aceptados {#accepted-file-sizes}

Tenga en cuenta las siguientes cifras para un procesamiento más rápido/temprano de los archivos, así como para las limitaciones de tamaño de los archivos, al enviar datos a un directorio [!DNL Audience Manager] / [!DNL Amazon S3].

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


>[!NOTE]
>
>El proceso de validación de datos de entrada marcará los archivos vacíos como no válidos y no los procesará.

## Límites de longitud de línea {#line-limits}

Los archivos de datos de entrada tienen un límite de longitud de línea de 102400 bytes. Las líneas que superen este límite se excluyen de la transferencia.

>[!MORELIKETHIS]
>
>* [Requisitos de nombre de FTP para archivos de datos de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

