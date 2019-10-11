---
description: Envíe o actualice archivos de metadatos enviándolos a un directorio especial de Amazon S3 para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre rutas de entrega/directorio, tiempos de procesamiento de archivos y actualizaciones.
seo-description: Envíe o actualice archivos de metadatos enviándolos a un directorio especial de Amazon S3 para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre rutas de entrega/directorio, tiempos de procesamiento de archivos y actualizaciones.
seo-title: Métodos de envío para archivos de metadatos
solution: Audience Manager
title: Métodos de envío para archivos de metadatos
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: 1ff46970470eae4bc30760468013d994c976e549

---


# Métodos de envío para archivos de metadatos{#delivery-methods-for-metadata-files}

Envíe o actualice archivos de metadatos enviándolos a un directorio especial de Amazon S3 para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre rutas de entrega/directorio, tiempos de procesamiento de archivos y actualizaciones.

## Sintaxis y ejemplos de ruta de entrega {#syntax}

Los datos se almacenan en espacios de nombres separados para cada cliente en un directorio de Amazon S3. La ruta del archivo sigue la sintaxis que se muestra a continuación. Note, *italics* indicates a variable placeholder. Los corchetes `[ ]` indican parámetros opcionales. Los demás elementos son constantes y no cambian.

**Sintaxis:**
<pre><code>.../log_ingestion/pid=<i>AAM ID</i>/dpid= <i>d_src</i>/[meta|status]/ <i>yyyymmdd</i>_ <i>parent ID</i>_ <i>child ID</i></code></pre>

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
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Este par clave-valor que contiene el ID de cliente de <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Este par clave-valor contiene la ID de la fuente de datos que se pasa en una llamada de evento. El ID del origen de datos es el valor que vincula todo el contenido del archivo con los datos reales a los que pertenece. </p> <p>Por ejemplo, supongamos que tiene un elemento creativo con el ID 123 y el nombre "Advertiser Creative A". A medida que una llamada de evento pasa solamente en el ID, debe incluir "Advertiser Creative A" en el archivo de metadatos. La campaña y el elemento creativo pertenecen a un origen de datos. La ID de la fuente de datos es lo que las une y nos permite asociar con precisión el contenido del archivo a un ID enviado en una llamada de evento. Consulte <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> Cómo los ID de llamadas al evento determinan los nombres de archivo, el contenido y las rutas</a>de envío. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>yyyymmdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>Es el nombre del archivo. Consulte <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Convenciones de nomenclatura para archivos</a>de metadatos. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Tiempos y actualizaciones de procesamiento de archivos {#processing-times}

Los archivos de metadatos se procesan cuatro veces al día, a intervalos regulares.

Para actualizar los registros de metadatos, sólo tiene que enviar un archivo que contenga información nueva. No es necesario que envíe actualizaciones completas cada vez.
