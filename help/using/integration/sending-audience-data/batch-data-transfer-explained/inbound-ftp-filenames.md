---
description: Describe los campos obligatorios, la sintaxis, las convenciones de nomenclatura y los tamaños de archivo que debe seguir al enviar datos a Audience Manager. Defina los nombres y tamaños de los archivos según estas especificaciones cuando envíe datos a un directorio FTP de Audience Manager.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager FTP directory.
seo-title: FTP Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: Nombre de FTP y requisitos de tamaño Archivo para el Archivos de datos de entrada
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
exl-id: 9c889214-7075-4392-9ed5-f07b91e7b50a
source-git-commit: a5506a315a98afdf31f8f52fac09b9179f388f30
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 3%

---

# [!DNL FTP] Requisitos de nombre y tamaño Archivo aplicables a los datos de entrada Archivos {#ftp-name-and-file-size-requirements-for-inbound-data-files}

Describe los campos obligatorios, la sintaxis, las convenciones de nomenclatura y los tamaños de archivo que debe seguir al enviar datos a [!DNL Audience Manager]. Defina los nombres y tamaños de los archivos según estas especificaciones cuando envíe datos a un directorio Audience Manager [!DNL FTP] .

>[!WARNING]
>
>Estamos eliminando gradualmente el soporte para [!DNL FTP] las configuraciones. Aunque la ingesta de archivos de datos de entrada todavía se admite en las integraciones existentes [!DNL FTP] , recomendamos encarecidamente su uso [!DNL Amazon S3] para incorporar datos de sin conexión para nuevas integraciones. Consulte [Requisitos de nomenclatura y tamaño de archivo de Amazon S3 para archivos de datos entrantes](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) para obtener más información.

>[!NOTE]
>
>Los estilos de texto (`monospaced text`, cursiva *, corchetes , etc.) de esta documento indican elementos y opciones de* `[ ]` `( )`código. Consulte [Convenciones de estilo para elementos de código y texto](../../../reference/code-style-elements.md) para obtener más información.

## Sintaxis del nombre Archivo {#file-name-syntax}

[!DNL FTP] Los nombres de archivo contienen los siguientes elementos opcionales y obligatorios:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Para conocer otros formatos de nombre de archivo aceptados[, consulte &#x200B;](/help/using/integration/sending-audience-data/custom-partner-integrations.md)Integraciones personalizadas de socios.

>[!NOTE]
>
>[!DNL Audience Manager] solo procesos [!DNL ASCII] y [!DNL UTF-8] archivos codificados.

### Nombrar elementos

La tabla define los elementos de un [!DNL FTP] nombre de archivo.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Archivo elemento Name </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>La ruta y el nombre de su <span class="keyword"> directorio FTP del Audience Manager</span> . Póngase en contacto con el administrador de cuentas para obtener el directorio FTP y las credenciales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Un LD que Audience Manager<span class="keyword"> indica </span> si un archivo de datos contiene sus propios ID de usuario, ID de Android, ID de iOS u otros ID que pertenecen a <a href="/help/using/features/global-data-sources.md"> orígenes</a> de datos globales. Acepta las siguientes opciones:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID de Origen de datos (también conocido como ID de proveedor de datos):</b> es un ID único que Audience Manager asigna a un fuente de datos (consulte el índice Audience Manager <a href="/help/using/reference/ids-in-aam.md"> de ID).</a> Utilice este ID asignado en un nombre de archivo cuando envíe datos que contengan sus propios ID de usuario. Por ejemplo, <code>...ftp_dpm_21_123456789.sync</code> indica <span class="keyword"> a los Audience Manager</span> que incorporen datos a identificadores pertenecientes al fuente de datos 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>ID de Android (GAID):</b> use el ID 20914 en el nombre de un archivo de datos si contiene ID de Android. Debe utilizar este campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> cuando utilice ID de Android. Por ejemplo, <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> indica <span class="keyword"> a Audience Manager</span> que el archivo de datos contiene solo ID de Android y que los ID deben calificar para las características pertenecientes al <code><i>_DPID_TARGET_DATA_OWNER</i></code> fuente de datos.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID de iOS (IDFA):</b> use el ID 20915 en el nombre de un archivo de datos si contiene ID de iOS. Debe usar el campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> cuando use ID de iOS. Por ejemplo, <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> indica <span class="keyword"> a Audience Manager</span> que el archivo de datos contiene solo ID de iOS y que los ID deben cumplir los requisitos para las características pertenecientes al <code><i>_DPID_TARGET_DATA_OWNER</i></code> fuente de datos.</li>
     <li> <b>ID pertenecientes a otras fuentes</b> de datos globales: puede incorporar ID de Roku para publicidad (RIDA), ID de Microsoft Advertising (MAID) y otros ID. Utilice el ID correspondiente a cada fuente de datos, tal y como se describe en el artículo<a href="/help/using/features/global-data-sources.md"> Fuentes </a> de datos globales.</li> 
    </ul> <p> <p>Nota: No mezcle tipos de ID en los archivos de datos. Por ejemplo, si su nombre de archivo incluye el identificador de Android, no coloque ID de iOS o sus propios ID en el archivo de datos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Este campo Audience Manager indica a qué fuente de datos incorporar los datos. Este campo es obligatorio si establece el DPID en un ID de Android o iOS ID u otro ID que pertenezca a fuentes de datos globales. Esto Audience Manager permite <span class="keyword"> vincular</span> los datos del archivo a su organización. <br> Este destino fuente de datos debe ser propiedad de su compañía. Para fines de intercambio de datos de segunda parte, para ingerir datos en una destino fuente de datos perteneciente a otra compañía, debe tener una asignación de acceso entre su compañía y la fuente de datos destino. Para configurar la asignación, póngase en contacto con su consultor Adobe Systems o con Asistencia al cliente.</p><p><b>Nota importante:</b> <i>No</i> es necesario solicitud una asignación para las relaciones de uso compartido de datos existentes (para destino fuentes de datos pertenecientes a otras empresas en las que incorporó datos antes del 14 de marzo de 2022). La asignación tampoco es necesaria cuando se incorporan datos a fuentes de datos destino que pertenecen a su PID. </p> <p>Por ejemplo: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> Audience Manager indica que reúne los requisitos para los ID de cliente pertenecientes al fuente de datos 33 para rasgos o señales pertenecientes al fuente de datos 21. </li> 
     <li> <b>ID de Android (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> Audience Manager<span class="keyword"> indica </span> que el archivo de datos contiene solo ID de Android y que los ID deben calificar para los rasgos pertenecientes a fuente de datos 21.</li> 
     <li> <b>ID de iOS (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> Audience Manager<span class="keyword"> indica </span> que el archivo de datos contiene solo ID de iOS y que los ID deben calificar para los rasgos pertenecientes a fuente de datos 21.</li>
     <li> <b>ID pertenecientes a otras fuentes</b> de datos globales: <code>...ftp_dpm_121963_21_1234567890.sync</code> Audience Manager<span class="keyword"> indica </span> que el archivo de datos contiene solo ID de Roku y que los ID deben calificar para los rasgos pertenecientes al fuente de datos 21. Utilice el ID correspondiente a cada fuente de datos, tal y como se describe en el artículo<a href="/help/using/features/global-data-sources.md"> Fuentes </a> de datos globales.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opciones de sincronización que incluyen: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Situación normal en la que los proveedores de datos de terceros envían características por usuario para añadirlas o eliminarlas en el sistema Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: permite a los clientes y proveedores de datos enviar un lista de características por usuario que debería sobrescribir todas las características existentes de este usuario para un fuente de datos determinado en Audience Manager. No es necesario incluir a todos los usuarios en un archivo de sobrescritura. Incluya solo aquellos usuarios que desee cambiar. Las características que no estén asignadas al fuente de datos destino no se borrarán. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un entero. Se utiliza al dividir archivos de gran tamaño en varias partes con el fin de mejorar los tiempos de procesamiento. El número indica qué parte del archivo original está enviando. </p> <p>Para un procesamiento de archivos eficiente, divida sus archivos de datos como se indica: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Sin comprimir: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Comprimido: 200-300 MB </li> 
    </ul> <p>Vea los primeros 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> ejemplos</a> de nombres de archivo a continuación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Una marca de tiempo UTC UNIX de 10 dígitos en segundos. La marca de fecha y hora ayuda a que cada nombre de archivo sea único. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip es el formato de compresión permitido para un nombre de archivo FTP. Si utiliza la compresión de archivos, asegúrese de que el nombre del archivo tenga la extensión adecuada. </p> <p>Los archivos comprimidos deben tener 3 GB o menos. Si los archivos son más grandes, póngase en contacto con el Servicio de atención al cliente. Aunque Audience Manager puede manejar archivos grandes, es posible que podamos ayudarlo a reducir el tamaño de sus archivos y hacer que las transferencias de datos sean más eficientes. Consulte <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> Archivo Compresión para la transferencia de datos de entrada Archivos</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplos de nombres Archivo {#file-name-examples}

Los ejemplos siguientes muestran nombres de archivo con el formato correcto. Los nombres de archivo pueden tener un aspecto similar.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[Descargue](assets/ftp_dpm_1234_1445374061.overwrite) el archivo de muestra si necesita ejemplos adicionales. Este archivo se guarda con la extensión de `.overwrite` archivo. Ábralo con un simple texto editor.

## Tamaños de Archivo aceptados {#accepted-file-sizes}

Tenga en cuenta las cifras a continuación para el procesamiento más rápido / temprano de sus archivos, así como para las limitaciones de tamaño de archivo cuando envía datos a un [!DNL Audience Manager] directorio / [!DNL FTP] .

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
