---
description: El directorio de estado de S3 contiene un archivo .info con información de éxito y error sobre los archivos cargados. El archivo contiene datos con formato JSON con los resultados de estado en una matriz.
seo-description: The S3 status directory holds a .info file with success and failure information about your uploaded files. The file contains JSON-formatted data with status results in an array.
seo-title: Status Updates for Metadata Files
solution: Audience Manager
title: Actualizaciones de estado para archivos de metadatos
uuid: 56a1e88a-41da-4d51-a21e-2be98cca7fa2
feature: Log Files
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---


# Actualizaciones de estado para archivos de metadatos{#status-updates-for-metadata-files}

El directorio de estado S3 contiene un archivo `.info` con información de éxito y error acerca de los archivos cargados. El archivo contiene datos con formato JSON con los resultados de estado en una matriz.

El contenido del archivo `.info` será similar al de este ejemplo.

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

## Pares de clave-valor de metadatos definidos {#key-value-pairs}

Las siguientes tablas enumeran y definen las claves en las secciones `Files` y `Summary` de un archivo de estado de metadatos.

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
   <td colname="col1"> <p> <code> Description</code> </p> </td> 
   <td colname="col2"> <p>Contiene una breve descripción de por qué falló el procesamiento. Este campo está vacío cuando el procesamiento se realiza correctamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Tamaño de archivo en bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Suma de comprobación MD 5 para el archivo de metadatos cargado en el directorio <code> meta</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Nombre del archivo de metadatos cargado en el directorio <code> meta</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MetadataType</code> </p> </td> 
   <td colname="col2"> <p>El nombre legible en lenguaje natural para el tipo de datos que contiene su archivo. Se basa en el ID secundario del nombre de archivo. </p> <p>Consulte <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> convenciones de nomenclatura para archivos de metadatos</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Parent</code> </p> </td> 
   <td colname="col2"> <p>El nombre legible en lenguaje natural para el tipo de datos que contiene su archivo. Se basa en el ID principal del nombre de archivo. </p> <p>Consulte <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> convenciones de nomenclatura para archivos de metadatos</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Status</code> </p> </td> 
   <td colname="col2"> <p>Devuelve dos valores de texto que describen el estado de procesamiento del archivo de metadatos: </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> SUCCESS</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Claves en el objeto de resumen**

<table id="table_C765A0CDBAA14A2FB5E0D38BDD1D292A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Clave </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>Fecha de procesamiento de archivo en formato <code><i>yyyy-mm-dd</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> GlobalStatus</code> </p> </td> 
   <td colname="col2"> <p>Devuelve dos valores de texto que describen el estado de procesamiento de todos los archivos para un día completo: </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> SUCCESS</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberFailure</code> </p> </td> 
   <td colname="col2"> <p>Número de archivos que no se procesaron correctamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberSuccess</code> </p> </td> 
   <td colname="col2"> <p>El número de archivos procesados correctamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>Devuelve una marca de tiempo legible en lenguaje natural para las horas de inicio de procesamiento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimePOSIX</code> </p> </td> 
   <td colname="col2"> <p>Una marca de tiempo UNIX para procesar las horas de inicio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Número total de bytes de todos los archivos de metadatos del día. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Número total de todos los archivos procesados durante el día. </p> </td> 
  </tr> 
 </tbody> 
</table>
