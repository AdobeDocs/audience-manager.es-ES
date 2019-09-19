---
description: Envíe o actualice archivos de metadatos enviándolos a un directorio especial de Amazon S3 para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre rutas de entrega/directorio, tiempos de procesamiento de archivos y actualizaciones.
seo-description: Envíe o actualice archivos de metadatos enviándolos a un directorio especial de Amazon S3 para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre rutas de entrega/directorio, tiempos de procesamiento de archivos y actualizaciones.
seo-title: Métodos de envío para archivos de metadatos
solution: Audience Manager
title: Métodos de envío para archivos de metadatos
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Métodos de envío para archivos de metadatos{#delivery-methods-for-metadata-files}

Envíe o actualice archivos de metadatos enviándolos a un directorio especial de Amazon S3 para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre rutas de entrega/directorio, tiempos de procesamiento de archivos y actualizaciones.

## Sintaxis y ejemplos de ruta de entrega {#syntax}

Los datos se almacenan en espacios de nombres separados para cada cliente en un directorio de Amazon S3. La ruta del archivo sigue la sintaxis que se muestra a continuación. Note, *italics* indicates a variable placeholder. Los corchetes `[ ]` indican parámetros opcionales. Los demás elementos son constantes y no cambian.

**Sintaxis:**
<pre><code>.../log_ingestion/pid=<i>AAM ID</i>/dpid= <i>d_src</i>/[meta|status]/ <i>aaaammdd</i>_ ID <i></i>principal_ <i>secundario</i></code></pre>

La siguiente tabla define cada uno de estos elementos en una ruta de entrega de archivos.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro de archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>Este es el inicio de la ruta de almacenamiento del directorio. Recibirás la ruta completa cuando todo esté configurado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=ID de<i>AAM</i></code> </p> </td> 
   <td colname="col2"> <p>Este par clave-valor que contiene el ID de cliente de <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Este par clave-valor contiene la ID de la fuente de datos que se pasa en una llamada de evento. El ID del origen de datos es el valor que vincula todo el contenido del archivo con los datos reales a los que pertenece. </p> <p>Por ejemplo, supongamos que tiene un elemento creativo con el ID 123 y el nombre "Advertiser Creative A". A medida que una llamada de evento pasa solamente en el ID, debe incluir "Advertiser Creative A" en el archivo de metadatos. La campaña y el elemento creativo pertenecen a un origen de datos. La ID de la fuente de datos es lo que las une y nos permite asociar con precisión el contenido del archivo a un ID enviado en una llamada de evento. Consulte <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> Cómo los ID de llamadas al evento determinan los nombres de archivo, el contenido y las rutas</a>de envío. </p> </td> 
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
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> status</code> es una ruta a un directorio que contiene información de éxito o error sobre los archivos procesados. Una vez procesado el archivo, verá un archivo <code> .info</code> con el título de la marca de tiempo <code> yyyymmdd</code> . Los archivos de estado contienen datos en un objeto JSON. Consulte <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> Actualizaciones de estado para archivos</a>de metadatos. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ID <i>aaaammdd</i>_<i>parent ID</i>_<i>child</i></code> </p> </td> 
   <td colname="col2"> <p>Es el nombre del archivo. Consulte <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Convenciones de nomenclatura para archivos</a>de metadatos. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Rutas de carga y estado de muestra**

Para cargar un archivo de metadatos o [comprobar su estado](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md), las rutas de archivo tendrán un aspecto similar a este:

* Ruta de carga: `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* Ruta de estado de procesamiento: `/log_ingestion/pid=1234/dpid=567/status/20150827.info`.

## Tiempos y actualizaciones de procesamiento de archivos {#processing-times}

Los archivos de metadatos se procesan cuatro veces al día, a intervalos regulares.

Para actualizar los registros de metadatos, sólo tiene que enviar un archivo que contenga información nueva. No es necesario que envíe actualizaciones completas cada vez.
