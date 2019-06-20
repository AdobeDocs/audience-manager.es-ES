---
description: Información básica sobre archivos de Fuente de datos de clientes (CDF) e instrucciones sobre cómo empezar. Comience aquí si le interesa recibir archivos CDF o solo desea obtener más información.
keywords: datos de terceros; Segundo nivel; Datos de segundo nivel; segundo nivel
seo-description: Información básica sobre archivos de Fuente de datos de clientes (CDF) e instrucciones sobre cómo empezar. Comience aquí si le interesa recibir archivos CDF o solo desea obtener más información.
seo-title: Fuentes de datos de clientes
solution: Audience Manager
title: Fuentes de datos de clientes
uuid: a 5 de 1630-2 c 7 a -4862-9 ba 0-f 8343 cdd 2782
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feeds {#customer-data-feeds}

Basic information about [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) files and instructions on how to get started. Start here if you&#39;re interested in receiving [!UICONTROL CDF] files or just want more information.

## File Contents and Purpose {#file-contents-purpose}

<!-- cdf-intro.xml -->

[!UICONTROL CDF] Un archivo contiene los mismos datos que envía una [!DNL Audience Manager] llamada de evento a `/event`nuestros servidores. Esto incluye datos como ID de usuario, ID de características, ID de segmento y todos los demás parámetros capturados por una llamada de evento. Internal [!DNL Audience Manager] systems processes event data into a [!UICONTROL CDF] file with content organized into fields that appear in a set order. [!DNL Audience Manager] intenta generar [!UICONTROL CDF] archivos por hora y almacenarlos en un bloque seguro y específico para el cliente en un [!DNL Amazon S3] servidor. We provide these files so you can work with [!DNL Audience Manager] data outside of the limits imposed by our user interface.

>[!NOTE]
>
>You should not use [!UICONTROL CDF] files as a proxy to monitor page traffic, reconcile report discrepancies, or for billing, etc.

## Introducción {#getting-started}

There is no self-service process to start [!UICONTROL CDF] file delivery. Contact your [!DNL Audience Manager] consultant or Customer Care to get started. During implementation, your [!DNL Audience Manager] representative will:

* Set up your [!DNL Amazon S3] storage bucket.
* Provide read-only [!DNL S3] authentication credentials to your file storage bucket. No podrá ver ni acceder a directorios ni archivos que pertenecen a otros clientes.

File notifications and [!UICONTROL CDF] files will appear in your [!DNL S3] bucket when they&#39;re ready for download. You&#39;re responsible for monitoring and downloading files from your assigned [!DNL S3] directory. See [Customer Data Feed File Processing Notifications](#cdf-file-processing-notifications).

## Pasos siguientes {#next-steps}

The sections below and the [Customer Data Feed FAQ](../faq/faq-cdf.md) can help you become more familiar with this service.

## Customer Data Feed Contents Defined {#cdf-defined}

Lists and defines the data elements and arrays in a [!UICONTROL CDF] file, by order of appearance. Definitions include data types, but this information is not part of a [!UICONTROL CDF] file.

## Definiciones {#definitions}

<!-- cdf-contents-defined.xml -->

[!UICONTROL CDF] Un archivo incluye algunos o todos los campos definidos a continuación. For information about internal file organization, see [Customer Data Feed File Structure](#cdf-file-structure).

<table id="table_46BC897A30C2469AB5911F5B85A3FAA7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Tipo de datos </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> Hora del evento</code> </p> </td> 
   <td colname="col2"> <p>Marca de tiempo </p> </td> 
   <td colname="col3"> <p>The time a CDF file was processed by the <span class="wintitle"> Data Collection Servers</span> (DCS). The timestamp uses the <i>yyyy-mm-dd hh:mm:ss</i> format and is set in the UTC time zone. </p> <p> <p>Note: The Event Time <i>is not</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">Hora del evento de página o la propia llamada del evento, aunque puede ser cercana a esas horas. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Relacionado con la hora DCS en el nombre del archivo. See also, <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>This is the <span class="wintitle"> Unique User ID</span> (UUID), which is a 38-digit device ID for your site visitor. Consulte también <a href="../reference/ids-in-aam.md">Índice de ID en Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> ID de contenedor</code> </p> </td> 
   <td colname="col2"> <p>Numérica </p> </td> 
   <td colname="col3"> <p>ID del contenedor que activa sincronizaciones de ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Características obtenidas</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Matriz de ID de características que contiene todas las características que un visitante cumplió (calificado para) en la llamada de evento. </p> <p>Tenga en cuenta que la matriz puede contener características para las que el visitante ha calificado antes y para las que vuelve a calificar mediante esta llamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Segmentos conseguidos</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Matriz de ID de segmento que contiene todos los segmentos que un visitante cumplió (calificado para) en la llamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Parámetros de solicitud</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Una cadena que captura todos los parámetros (variables, ID, pares clave-valor, etc.) se pasó en la llamada de evento. </p> <p>Ejemplo abreviado: </p> <p> <code> d_ rtbd: json, c_ contextdata. a. carriername: mobile, c_ contextdata. a. adid: 92 D 56353-49 C 5-431 E-B 474-FC 528 D 585810, c_ contextdata. a, runmode: Aplicación, c_ contextdata. a. dayssincelastupgrade: 61, d_ cid_ ic: xid % 01 EACB 6 E 40-AC 65-4012-9 FE 9-ABD 59965 E 9 C 4% 011, c_ contextdata. a. prevsessionlength: 583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Tipo de datos de referente</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>La dirección URL sin codificar de la página de referencia (si existe). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Tipo de datos IP</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>La dirección IP del visitante capturado en la llamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Mcdevice </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>The <span class="keyword"> Experience Cloud</span> ID (MID) assigned to the site visitor. See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and theExperience Cloud ID service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Todos los segmentos</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Matriz de ID de segmento que contiene segmentos previamente conseguidos y segmentos nuevos para los que el visitante está cualificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Todas las características</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Matriz de ID de características individuales y de terceros que contiene características previamente obtenidas y nuevas características que el visitante ha calificado desde la última fuente de datos generada. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Structure {#cdf-file-structure}

Lists and defines the data structure of a [!UICONTROL CDF] file. Esto incluye la secuencia de datos, delimitadores de campo y separadores, un mapa de archivos de datos y un archivo de muestra.

## Data Field Identifiers and Sequence {#identifiers-and-sequence}

<!-- cdf-file-structure.xml -->

[!UICONTROL CDF] los archivos no contienen columnas ni encabezados de campo etiquetados. Instead, a [!UICONTROL CDF] file defines fields and arrays with non-printing [!DNL ASCII] characters. Also, the [!UICONTROL CDF] file lists each field and array in a specific order. El comprender los identificadores y el orden de los campos le ayudará a analizar el archivo correctamente.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de archivo CDF </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Separadores y delimitadores de campo </p> </td> 
   <td colname="col2"> <p>Estos caracteres no imprimibles definen los elementos y la estructura del archivo CDF: </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> or <code> ^A</code>) separates data in individual fields with a non-printing space indicator. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> or <code> ^B</code>) separates data an array and request parameters. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> or <code> ^C</code>) defines key-value pairs. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Secuencia de campos </p> </td> 
   <td colname="col2"> <p> <p>Important: <span class="keyword"> Audience Manager</span> reserves the right to add new fields to the end of the CDF file in future releases. Esto significa que el diseño técnico del sistema de análisis de archivos no debe suponer un número fijo de columnas (aunque puede suponer un orden fijo para las columnas existentes). </p> </p> <p>Los datos del archivo CDF aparecen en el orden que se muestra a continuación. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Hora del evento </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Device </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID de contenedor </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Características obtenidas </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segmentos conseguidos </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Parámetros de solicitud </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Dirección IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">ID de dispositivo de Experience Cloud (o MID). See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Todos los segmentos </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Todas las características </li> 
     </ol> </p> <p>For field descriptions, see <a href="#cdf-defined"> Customer Data Feed Contents Defined</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## CDF File Map {#cdf-file-map}

[!UICONTROL CDF] los datos del archivo aparecen en el orden que se muestra a continuación.

![](assets/sequence-map.png)

## Identificación de matrices

Arrays in a [!UICONTROL CDF] file start and end with the `Ctrl + a` field separator. Esto hace que el primer elemento de una matriz aparezca como un campo de datos independiente. For example, the realized traits array starts with `^A1234`. The array delimiter and ID `^B5678` follows this entry. As a result, you might be tempted to think that the first element in the realized traits array is ID 5678 (because it starts with `^B`). Este no es el caso, por eso es necesario estar familiarizado con la secuencia y la estructura de un archivo de datos. Even though the first element in the realized trait array (or any of the other arrays in a [!UICONTROL CDF] file) starts with `^A`, the order of appearance or position in the file defines the start of an array. And, the first element in an array is always separated from the preceding entry by `^A`.

## Sample CDF File {#sample-file}

A sample [!UICONTROL CDF] file could look similar to the following. Hemos insertado saltos de línea en este ejemplo para ayudarle a ajustar la página.

![](assets/CDF-sample.png)

## Customer Data Feed File Naming Conventions {#cdf-naming-conventions}

The sections below list and define the elements in your [!UICONTROL CDF] file name.

## CDF File Name: Syntax and Example {#cdf-file-name}

<!-- cdf-file-name.xml -->

A typical [!UICONTROL CDF] file name contains the elements listed below. Note, *italics* indicates a variable placeholder:

* **Sintaxis**

<pre><code>s 3: //aam-cdf/your<i>s 3 bucket name</i>/day =<i>aaaa-mm-dd</i>/hour =<i>hh</i>/<i>AAM_ CDF_ partner ID_ AAM process ID</i>_0.gz</code>
</pre>

* **Ejemplo**

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

In your [!DNL S3] storage bucket, files are sorted in ascending order by Partner ID ([!UICONTROL PID]), day, and hour.

## CDF File Name Elements Defined {#cdf-file-name-elements}

The following table lists and defines the elements in a [!UICONTROL CDF] file name.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento Nombre de archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s 3: //aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Bloque de almacenamiento raíz predeterminado para su archivo CDF en un servidor Amazon S 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>su nombre de bucket S 3</i></code> </p> </td> 
   <td colname="col2"> <p>El nombre del bloque de solo lectura S 3 que contiene sus archivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day =<i>aaaa-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Fecha en la que se procesó el archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour =<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Valor de hora expresado en notación de 24 horas y establecido en la zona horaria UTC. See also, <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>ID del socio</i></code> </p> </td> 
   <td colname="col2"> <p>Su ID de socio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>ID del proceso AAM</i>_ 0</code> </p> </td> 
   <td colname="col2"> <p>An internal, <span class="keyword"> Audience Manager</span> process ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Extensión de archivo gzip. Los archivos CDF son comprimidos. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Processing Notifications {#cdf-file-processing-notifications}

[!DNL Audience Manager] escribe un `.info` archivo en [!DNL S3] el directorio para saber cuándo está listo para descargar el [!UICONTROL Customer Data File] ([!UICONTROL CDF]). `.info` El archivo también incluye [!DNL JSON] metadatos formateados sobre el contenido de [!UICONTROL CDF] los archivos. Revise esta sección para obtener información sobre la sintaxis y los campos utilizados por este archivo de notificación.

## Sample Info File {#sample-info-file}

<!-- cdf-notifications.xml -->

Each `.info` file contains a `Files` and `Totals` section. The `Files` section contains an array that holds specific metrics for each hourly file. The `Totals` section contains metrics aggregated across all your [!UICONTROL CDF] files for a particular day. The contents of your `.info` file could look similar to the following example.

```js
{
    "Files": [
        {
            "FileByteSize": 2709730,
            "FileChecksumMD5": "a9ea418e79511642cff11c2a898037dc-1",
            "FileName": "AAM_CDF_1109_000000_0.gz",
            "FileSequenceNumber": 1
        },
        {
            "FileByteSize": 2783351,
            "FileChecksumMD5": "7b469485d60274b6991acd0817855840-3",
            "FileName": "AAM_CDF_1109_000001_0.gz",
            "FileSequenceNumber": 2
        }
    ],
    "Totals": {
        "Day": "2017-09-26",
        "Hour": "18",
        "TotalByteSize": 150092997,
        "TotalNumberFiles": 2
    }
}
```

## Info File Fields Defined {#info-file-fields-defined}

The following tables list and define the elements in a [!UICONTROL CDF] `.info` file.

### Objeto de archivos

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Archivos</code> </p> </td> 
   <td colname="col2"> <p>Inicia la matriz que contiene metadatos sobre los archivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filebytesize</code> </p> </td> 
   <td colname="col2"> <p>Tamaño del archivo en bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S 3 etag. El número que sigue al guión muestra el número de partes utilizadas para crear el archivo durante la carga de varias partes. <code> Etag</code> no es idéntica a la suma de comprobación MD 5 del archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filename</code> </p> </td> 
   <td colname="col2"> <p>El nombre del archivo. See <a href="#cdf-naming-conventions"> Customer Data Feed File Naming Conventions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filesequencenumber</code> </p> </td> 
   <td colname="col2"> <p>Un número de índice para cada archivo. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Objeto Totales

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Totales</code> </p> </td> 
   <td colname="col2"> <p>Inicia el objeto que contiene datos agregados sobre todos los archivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Día</code> </p> </td> 
   <td colname="col2"> <p>Día para el cual están disponibles los datos. Uses <i>yyyy-mm-dd</i> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hora</code> </p> </td> 
   <td colname="col2"> <p>Hora para la cual están disponibles los datos. Utiliza formato de 24 horas establecido en la zona horaria UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalbytesize</code> </p> </td> 
   <td colname="col2"> <p>Tamaño total de todos los archivos CDF para esa fecha en bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalnumberfiles</code> </p> </td> 
   <td colname="col2"> <p>Número total de archivos cargados en su directorio S 3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Name Times and File Content Times are Different {#different-processing-times}

[!UICONTROL CDF] El archivo contiene marcas de hora en el nombre del archivo y en el contenido del archivo. These timestamps record different event processes for the same [!UICONTROL CDF] file. No es raro ver las diferentes marcas de hora en el nombre y el contenido del mismo archivo. Comprender cada marca de tiempo puede ayudarle a evitar errores comunes al trabajar con estos datos o al intentar ordenarlos por tiempo.

## Locating CDF File Timestamps {#locating-timestamps}

<!-- cdf-time-differences.xml -->

[!UICONTROL CDF] los archivos registran el tiempo de forma diferente en dos ubicaciones independientes.

![](assets/cdf-timestamp.png)

## Understanding the Difference Between Timestamps {#understanding-timestamps}

The following table provides additional details about your [!UICONTROL CDF] file timestamps along with information about how to use them properly.

| Ubicación de marca de hora | Descripción |
|--- |--- |
| Nombre del archivo | The timestamp in your CDF file name marks the time when [!DNL Audience Manager] started preparing your file for delivery. Esta marca de tiempo se establece en la zona horaria UTC. It uses the `hour=` parameter, with time formatted as a 2-digit hour in 24-hour notation. Este tiempo puede ser distinto al tiempo de evento registrado en el contenido del archivo. Breakwhen trabaja con archivos CDF, a veces observará que el bucket S 3 está vacío para una hora en particular. Un bloque vacío significa una de las siguientes opciones:<ul><li>No hay datos para esa hora en particular. </li><li> Nuestros servidores están bajo cargas pesadas y no pueden procesar archivos para una hora en particular. Cuando el servidor se detecte, pone los archivos que deberían haber pasado de un bloque de tiempo anterior a un bloque con un valor de hora posterior. For example, you&#39;ll see this when a file that should have been in the hour 17 bucket appear in the hour 18 bucket (with `hour=18` in the file name). En este caso, el servidor probablemente comenzó a procesar el archivo en la hora 17 pero no lo pudo completar dentro de ese intervalo de tiempo. En su lugar, el archivo se inserta en el siguiente bloque de hora por hora.</li></ul><br>**Importante**: No utilice la marca de fecha y hora del nombre de archivo para agrupar los eventos por hora. If you need to group by time, use the `EventTime` timestamp in the file contents. |
| Contenido del archivo | La marca de tiempo del contenido del archivo CDF marca el momento en que los servidores de recopilación de datos comenzaron a procesar el archivo. Esta marca de tiempo se establece en la zona horaria UTC. It uses the `EventTime` field, with time formatted as *`yyyy-mm-dd hh:mm:ss`*. This time is close to the actual time of the event on the page, but it can be different than the hour indicator in the file name. <br> **Sugerencia**: A diferencia de `hour=` la marca de tiempo en el nombre del archivo, puede utilizar `EventTime` para agrupar los datos por tiempo. |

>[!MORE_ LIKE_ THIS]
>
>* [Preguntas frecuentes sobre fuentes de datos de clientes](../faq/faq-cdf.md)

