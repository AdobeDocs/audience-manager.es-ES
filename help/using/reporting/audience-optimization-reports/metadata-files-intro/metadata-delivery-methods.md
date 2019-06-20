---
description: Envíe o actualice archivos de metadatos enviándolos a un directorio especial de Amazon S 3 para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre las rutas de envío y directorio, los tiempos de procesamiento de archivos y las actualizaciones.
seo-description: Envíe o actualice archivos de metadatos enviándolos a un directorio especial de Amazon S 3 para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre las rutas de envío y directorio, los tiempos de procesamiento de archivos y las actualizaciones.
seo-title: Métodos de envío para archivos de metadatos
solution: Audience Manager
title: Métodos de envío para archivos de metadatos
uuid: 5199 ee 9 b -920 d -423 d -8070-05 a 017 ecd 562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Delivery Methods for Metadata Files{#delivery-methods-for-metadata-files}

Envíe o actualice archivos de metadatos enviándolos a un directorio especial de Amazon S 3 para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre las rutas de envío y directorio, los tiempos de procesamiento de archivos y las actualizaciones.

## Delivery Path Syntax and Examples {#syntax}

Los datos se almacenan en espacios de nombres separados para cada cliente en un directorio de Amazon S 3. La ruta de archivo sigue la sintaxis que se muestra a continuación. Note, *italics* indicates a variable placeholder. Brackets `[ ]` indicate optional parameters. Los demás elementos son constantes y no cambian.

**Sintaxis:**
<pre><code>…/log_ ingestion/pid =<i>AAM ID</i>/dpid = <i>d_ src</i>/[meta | status]/ <i>aaaammdd</i>_ <i>parent ID</i>_ <i>child ID</i></code></pre>

La tabla siguiente define cada uno de estos elementos en una ruta de entrega de archivo.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro de archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> …/log_ ingestion/</code> </p> </td> 
   <td colname="col2"> <p>Es el inicio de la ruta de almacenamiento del directorio. Recibirá la ruta completa cuando esté configurada todo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid =<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>This key-value pair that contains your <span class="keyword"> Audience Manager</span> customer ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid =<i>d_ src</i></code> </p> </td> 
   <td colname="col2"> <p>Este par clave-valor contiene el ID de fuente de datos que se pasa en una llamada de evento. El ID de fuente de datos es el valor que asocia todo el contenido del archivo con los datos reales a los que pertenece. </p> <p>Por ejemplo, supongamos que tiene un elemento creativo con el ID 123 y el nombre "Creador de publicidades A". Como una llamada de evento solo pasa al ID, debe incluir el "Elemento creativo del anunciante A" en el archivo de metadatos. La campaña y el elemento creativo pertenecen a un origen de datos. El ID de fuente de datos es lo que vincula estos datos y permite asociar con precisión el contenido del archivo a un ID enviado en una llamada de evento. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> How Event Call IDs Determine File Names, Contents, and Delivery Paths</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> meta</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> status</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code> meta</code> es un directorio de carga/almacenamiento de archivos. </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> es</code> una ruta a un directorio que contiene información de éxito o error sobre los archivos procesados. After your file is processed, you'll see a <code> .info</code> file with <code> yyyymmdd</code> timestamp title. Los archivos de estado contienen datos en un objeto JSON. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> Status Updates for Metadata Files</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>aaaammdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>Este es el nombre del archivo. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Rutas de carga y estado de muestra**

To upload a metadata file or to [check its status](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md), the file paths will look similar to these:

* Upload path: `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* Processing status path: `/log_ingestion/pid=1234/dpid=567/status/20150827.info`.

## File Processing Times and Updates {#processing-times}

Los archivos de metadatos se procesan cuatro veces al día, a intervalos regulares.

Para actualizar los registros de metadatos, simplemente envíe un archivo que contenga información nueva. No es necesario que envíe actualizaciones completas cada vez.
