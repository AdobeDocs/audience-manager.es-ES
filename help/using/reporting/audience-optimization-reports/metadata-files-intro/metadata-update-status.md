---
description: El directorio de estado S 3 contiene un archivo.info con información de éxito y errores sobre los archivos cargados. El archivo contiene datos con formato JSON con resultados de estado en una matriz.
seo-description: El directorio de estado S 3 contiene un archivo.info con información de éxito y errores sobre los archivos cargados. El archivo contiene datos con formato JSON con resultados de estado en una matriz.
seo-title: Actualizaciones de estado para archivos de metadatos
solution: Audience Manager
title: Actualizaciones de estado para archivos de metadatos
uuid: 56 a 1 e 88 a -41 da -4 d 51-a 21 e -2 be 98 cca 7 fa 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Status Updates for Metadata Files{#status-updates-for-metadata-files}

The S3 status directory holds a `.info` file with success and failure information about your uploaded files. El archivo contiene datos con formato JSON con resultados de estado en una matriz.

The contents of your `.info` file will look similar to this example.

```js
//sample file path
/log_ingestion/pid=1234/dpid=567/status/20150827.info

//sample contents
{
    "Files": [
        {
            "FileByteSize": 488900,
            "FileChecksumMD5": "94b821082daff242e452c0d8796b08f0",
            "FileName": "20141112_4_2",
            "MetadataType": "Creative",
            "Parent": "Site",
            "Status": "SUCCESS",
            "Description": ""
        },
        {
            "FileByteSize": 58812,
            "FileChecksumMD5": "db79f148e6a635629701c13a7bcc8db0",
            "FileName": "20141112_0_4",
            "MetadataType": "Site",
            "Parent": "None",
            "Status": "FAILURE",
            "Description": "Invalid format."
        }
    ],
    "Summary": {
        "Day": "2014-11-12",
        "ProcessingTimeRFC2822": "Wed, 10 Dec 2014 21:07:58 -0000",
        "ProcessingTimestampPOSIX": 1418263678,
        "TotalByteSize": 547712,
        "TotalNumberFiles": 2,
        "NumberSuccess": 1,
        "NumberFailure": 1,
        "GlobalStatus": "FAILURE"
    }
}
```

## Metadata Key-Value Pairs Defined {#key-value-pairs}

The following tables list and define the keys in the `Files` and `Summary` sections of a metadata status file.

**Claves en la matriz de archivos**

<table id="table_BF23C032FEFA446282E9364E85BE8C9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Clave </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Descripción</code> </p> </td> 
   <td colname="col2"> <p>Contiene una breve descripción de por qué falló el procesamiento. Este campo está vacío cuando el procesamiento se realiza correctamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filebytesize</code> </p> </td> 
   <td colname="col2"> <p>Tamaño del archivo en bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>The MD 5 checksum for the metadata file uploaded to your <code> meta</code> directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filename</code> </p> </td> 
   <td colname="col2"> <p>The name of the metadata file uploaded to your <code> meta</code> directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Metadatatype</code> </p> </td> 
   <td colname="col2"> <p>Nombre legible en lenguaje natural para el tipo de datos que contiene el archivo. Se basa en el ID secundario del nombre de archivo. </p> <p>See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Principal</code> </p> </td> 
   <td colname="col2"> <p>Nombre legible en lenguaje natural para el tipo de datos que contiene el archivo. Se basa en el ID principal del nombre de archivo. </p> <p>See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Estado</code> </p> </td> 
   <td colname="col2"> <p>Devuelve 2 valores de texto que describen el estado de procesamiento del archivo de metadatos: </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> SUCCESS</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> ERROR</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Claves del objeto Resumen**

<table id="table_C765A0CDBAA14A2FB5E0D38BDD1D292A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Clave </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Día</code> </p> </td> 
   <td colname="col2"> <p>File processing date in <code><i>yyyy-mm-dd</i></code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Globalstatus</code> </p> </td> 
   <td colname="col2"> <p>Devuelve 2 valores de texto que describen el estado de procesamiento de todos los archivos para un día completo: </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> SUCCESS</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> ERROR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Numberfailure</code> </p> </td> 
   <td colname="col2"> <p>Número de archivos que se procesaron de forma incorrecta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Numbersuccess</code> </p> </td> 
   <td colname="col2"> <p>El número de archivos se procesó correctamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>Devuelve una marca de hora legible en lenguaje natural para el procesamiento de los tiempos de inicio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Processingtimeposix</code> </p> </td> 
   <td colname="col2"> <p>Marca de hora UNIX para el procesamiento de los tiempos de inicio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalbytesize</code> </p> </td> 
   <td colname="col2"> <p>Número total de bytes para todos los archivos de metadatos del día. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalnumberfiles</code> </p> </td> 
   <td colname="col2"> <p>La cantidad total de todos los archivos procesados para el día. </p> </td> 
  </tr> 
 </tbody> 
</table>
