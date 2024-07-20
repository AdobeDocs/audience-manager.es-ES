---
description: Describe los campos, sintaxis, convenciones de nomenclatura y tamaños de archivo necesarios que debe seguir al enviar datos a Audience Manager. Configure los nombres y tamaños de los archivos según estas especificaciones cuando envíe datos a un directorio FTP de Audience Manager.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager FTP directory.
seo-title: FTP Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: Requisitos de tamaño de archivo y nombre de FTP para archivos de datos de entrada
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
exl-id: 9c889214-7075-4392-9ed5-f07b91e7b50a
source-git-commit: a5506a315a98afdf31f8f52fac09b9179f388f30
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 4%

---

# [!DNL FTP] requisitos de nombre y tamaño de archivo para archivos de datos de entrada {#ftp-name-and-file-size-requirements-for-inbound-data-files}

Describe los campos, sintaxis, convenciones de nomenclatura y tamaños de archivo requeridos que debe seguir al enviar datos a [!DNL Audience Manager]. Establezca los nombres y tamaños de los archivos según estas especificaciones cuando envíe datos a un directorio de Audience Manager [!DNL FTP].

>[!WARNING]
>
>Estamos eliminando gradualmente la compatibilidad con las configuraciones de [!DNL FTP]. Aunque la ingesta de archivos de datos entrantes sigue siendo compatible con las integraciones existentes de [!DNL FTP], recomendamos encarecidamente utilizar [!DNL Amazon S3] para incorporar datos sin conexión en el caso de nuevas integraciones. Consulte [Requisitos de nomenclatura y tamaño de archivo de Amazon S3 para archivos de datos entrantes](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) para obtener más información.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *cursiva*, paréntesis `[ ]` `( )`, etc.) en este documento, indique los elementos y las opciones de código. Consulte [Convenciones de estilo para elementos de código y texto](../../../reference/code-style-elements.md) para obtener más información.

## Sintaxis del nombre del archivo {#file-name-syntax}

[!DNL FTP] nombres de archivo contienen los siguientes elementos obligatorios y opcionales:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Para ver otros formatos de nombre de archivo aceptados, consulte [Integraciones de socios personalizadas](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>[!DNL Audience Manager] solo procesa [!DNL ASCII] y [!DNL UTF-8] archivos codificados.

### Elementos de nombre

La tabla define los elementos en un nombre de archivo de [!DNL FTP].

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
   <td colname="col2"> <p>Ruta de acceso y nombre del directorio FTP del Audience Manager <span class="keyword"> </span>. Póngase en contacto con el Administrador de cuentas para obtener el directorio y las credenciales de FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Un id. que informa al Audience Manager <span class="keyword"></span> si un archivo de datos contiene sus propios id. de usuario, id. de Android, id. de iOS u otros id. que pertenecen a <a href="/help/using/features/global-data-sources.md"> orígenes de datos globales</a>. Acepta las siguientes opciones:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID de Data Source (también conocido como ID de proveedor de datos):</b> Se trata de un ID único que el Audience Manager asigna a un origen de datos (consulte el índice del Audience Manager <a href="/help/using/reference/ids-in-aam.md"> de los ID </a>). Utilice este ID asignado en un nombre de archivo al enviar datos que contengan sus propios ID de usuario. Por ejemplo, <code>...ftp_dpm_21_123456789.sync</code> indica a <span class="keyword"> Audience Manager</span> que incorpore datos a los ID que pertenecen al origen de datos 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID (GAID):</b> Use el ID 20914 en un nombre de archivo de datos si contiene Android ID. Debe usar el campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> cuando use Android ID. Por ejemplo, <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> indica a <span class="keyword"> Audience Manager</span> que el archivo de datos contiene solo Android ID y que los ID deben cumplir los requisitos para los rasgos que pertenecen al origen de datos <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID (IDFA):</b> Use el ID 20915 en un nombre de archivo de datos si contiene iOS ID. Debe usar el campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> cuando use iOS ID. Por ejemplo, <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> indica a <span class="keyword"> Audience Manager</span> que el archivo de datos contiene solo iOS ID y que los ID deben cumplir los requisitos para los rasgos que pertenecen al origen de datos <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li>
     <li> <b>ID que pertenecen a otras fuentes de datos globales</b>: Puede incorporar los ID de Roku para Advertising (RIDA), Microsoft Advertising ID (MAID) y otros ID. Use el identificador correspondiente a cada origen de datos, tal como se describe en el artículo <a href="/help/using/features/global-data-sources.md"> orígenes de datos globales </a>.</li> 
    </ul> <p> <p>Nota: No mezcle tipos de ID en los archivos de datos. Por ejemplo, si el nombre de archivo incluye el identificador de Android, no coloque iOS ID o sus propios ID en el archivo de datos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Este campo indica al Audience Manager a qué fuente de datos incorporar los datos. Este campo es obligatorio si establece el DPID en un Android ID o iOS ID u otro ID que pertenezca a fuentes de datos globales. Esto permite que <span class="keyword"> Audience Manager</span> vincule los datos del archivo a su organización. <br>: este origen de datos de destino debe ser propiedad de su compañía. Para compartir datos de segundo nivel, para introducir datos en una fuente de datos de destino perteneciente a otra empresa, debe tener una asignación de acceso entre su empresa y la fuente de datos de destino. Póngase en contacto con su asesor de Adobe o con Asistencia al cliente para configurar la asignación.</p><p><b>Nota importante:</b> Usted <i>no</i> necesita solicitar una asignación para las relaciones de uso compartido de datos existentes (para orígenes de datos de destino que pertenecen a otras empresas en las que incorporó datos antes del 14 de marzo de 2022). La asignación tampoco es obligatoria al incorporar datos en fuentes de datos de destino que pertenecen a su PID. </p> <p>Por ejemplo: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> indica al Audience Manager que está calificando a los ID de cliente que pertenecen a la fuente de datos 33 para rasgos o señales que pertenecen a la fuente de datos 21. </li> 
     <li> <b>Android ID (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> indica a <span class="keyword"> Audience Manager</span> que el archivo de datos contiene solo Android ID y que los ID deben cumplir los requisitos para los rasgos que pertenecen a la fuente de datos 21.</li> 
     <li> <b>ID de iOS (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> indica al Audience Manager <span class="keyword"></span> que el archivo de datos solo contiene ID de iOS y que los ID deben cumplir los requisitos para los rasgos que pertenecen a la fuente de datos 21.</li>
     <li> <b>ID que pertenecen a otras fuentes de datos globales</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> indica a <span class="keyword"> Audience Manager</span> que el archivo de datos contiene solo ID de Roku y que los ID deben cumplir los requisitos para los rasgos que pertenecen a la fuente de datos 21. Use el identificador correspondiente a cada origen de datos, tal como se describe en el artículo <a href="/help/using/features/global-data-sources.md"> orígenes de datos globales </a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opciones de sincronización que incluyen: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: escenario normal en el que los proveedores de datos de terceros envían características por usuario para que se agreguen o eliminen en el sistema Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: permite a los clientes y proveedores de datos enviar una lista de características por usuario que deben sobrescribir todas las características existentes de este usuario para un origen de datos determinado en Audience Manager. No es necesario incluir a todos los usuarios en un archivo de sobrescritura. Incluya solo a los usuarios que desee cambiar. Las características que no se hayan asignado a la fuente de datos de destino no se borrarán. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un entero. Se utiliza al dividir archivos grandes en varias partes para mejorar los tiempos de procesamiento. El número indica qué parte del archivo original está enviando. </p> <p>Para un procesamiento eficaz de los archivos, divida los archivos de datos como se indica a continuación: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Sin comprimir: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Comprimido: 200-300 MB </li> 
    </ul> <p>Vea los primeros 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> ejemplos de nombre de archivo</a> a continuación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Una marca de tiempo UNIX UTC de 10 dígitos en segundos. La marca de tiempo ayuda a que cada nombre de archivo sea único. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip es el formato de compresión permitido para un nombre de archivo de FTP. Si utiliza la compresión de archivos, asegúrese de que el nombre del archivo tiene la extensión adecuada. </p> <p>Los archivos comprimidos deben tener 3 GB o menos. Si los archivos son más grandes, póngase en contacto con el Servicio de atención al cliente. Aunque Audience Manager puede gestionar archivos grandes, es posible que podamos ayudarle a reducir el tamaño de sus archivos y hacer que las transferencias de datos sean más eficientes. Consulte Compresión de archivos de <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> para archivos de transferencia de datos entrantes</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplos de nombres de archivo {#file-name-examples}

Los siguientes ejemplos muestran nombres de archivo con el formato correcto. Sus nombres de archivo podrían ser similares.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[Descargue](assets/ftp_dpm_1234_1445374061.overwrite) el archivo de muestra si necesita ejemplos adicionales. Este archivo se guardó con la extensión de archivo `.overwrite`. Ábralo con un editor de texto simple.

## Tamaños de archivo admitidos {#accepted-file-sizes}

Tenga en cuenta las figuras siguientes para el procesamiento más rápido/más temprano de sus archivos, así como para las limitaciones de tamaño de archivo al enviar datos a un directorio [!DNL Audience Manager] / [!DNL FTP].

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
