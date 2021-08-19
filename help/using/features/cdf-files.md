---
description: Información básica sobre archivos de Fuente de datos de clientes (CDF) e instrucciones sobre cómo empezar. Comience aquí si está interesado en recibir archivos CDF o solo desea más información.
keywords: datos de segundo nivel;datos de segundo nivel;datos de segundo nivel;datos de segundo nivel
seo-description: Información básica sobre archivos de Fuente de datos de clientes (CDF) e instrucciones sobre cómo empezar. Comience aquí si está interesado en recibir archivos CDF o solo desea más información.
seo-title: Fuentes de datos de clientes
solution: Audience Manager
title: Fuentes de datos de clientes
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Fuentes de datos de clientes
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1930'
ht-degree: 3%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

Información básica sobre archivos [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) e instrucciones sobre cómo empezar. Comience aquí si está interesado en recibir archivos [!UICONTROL CDF] o solo desea más información.

## Contenido del archivo y propósito {#file-contents-purpose}

Un archivo [!UICONTROL CDF] contiene los mismos datos que una llamada de evento de [!DNL Audience Manager] (`/event`) envía a nuestros servidores. Esto incluye datos como ID de usuario, [!UICONTROL trait IDs], [!UICONTROL segment IDs] y todos los demás parámetros capturados por una llamada de evento. Los sistemas internos [!DNL Audience Manager] procesan los datos de evento en un archivo [!UICONTROL CDF] con contenido organizado en campos que aparecen en un orden establecido. [!DNL Audience Manager] intenta generar  [!UICONTROL CDF] archivos cada hora y los almacena en un bloque seguro específico del cliente en un  [!DNL Amazon S3] servidor. Proporcionamos estos archivos para que pueda trabajar con datos [!DNL Audience Manager] fuera de los límites impuestos por nuestra interfaz de usuario.

>[!IMPORTANT]
>
>Tenga en cuenta las restricciones siguientes al trabajar con archivos CDF:
>
>* Antes de configurar la entrega de archivos CDF, asegúrese de que tiene los permisos adecuados de proveedores de datos de terceros para la exportación de características de terceros. Actualmente, el Audience Manager no admite la funcionalidad en la interfaz de usuario para solicitar el permiso de exportación de envío de archivos CDF de proveedores de datos de terceros, por lo que debe ponerse en contacto con ellos de forma independiente.
>* No debe utilizar [!UICONTROL CDF] archivos como proxy para supervisar el tráfico de la página, reconciliar discrepancias en los informes, o para la facturación, etc.


## Introducción {#getting-started}

No hay ningún proceso de autoservicio para iniciar la entrega de archivos [!UICONTROL CDF]. Póngase en contacto con su asesor de [!DNL Audience Manager] o con el Servicio de atención al cliente para empezar. Durante la implementación, su representante de [!DNL Audience Manager]:

* Configure su espacio de almacenamiento [!DNL Amazon S3].
* Proporcione credenciales de autenticación [!DNL S3] de solo lectura al espacio de almacenamiento de archivos. No podrá ver ni acceder a directorios y archivos que pertenezcan a otros clientes.

Las notificaciones de archivos y los archivos [!UICONTROL CDF] aparecerán en el bloque [!DNL S3] cuando estén listos para la descarga. Usted es el responsable de supervisar y descargar archivos del directorio [!DNL S3] asignado. Consulte [Notificaciones sobre procesamiento de archivos de fuentes de datos de clientes](#cdf-file-processing-notifications).

## Pasos siguientes {#next-steps}

Las secciones siguientes y las [Preguntas frecuentes sobre la fuente de datos del cliente](../faq/faq-cdf.md) pueden ayudarle a familiarizarse con este servicio.

## [!UICONTROL Customer Data Feed] Contenido definido {#cdf-defined}

Enumera y define los elementos de datos y las matrices de un archivo [!UICONTROL CDF] por orden de aspecto. Las definiciones incluyen tipos de datos, pero esta información no forma parte de un archivo [!UICONTROL CDF].

## Definiciones {#definitions}

Un archivo [!UICONTROL CDF] incluye algunos o todos los campos definidos a continuación. Para obtener información sobre la organización de archivos internos, consulte [Estructura de archivos de fuentes de datos de clientes](#cdf-file-structure).

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
   <td colname="col1"> <p><code> Event Time</code> </p> </td> 
   <td colname="col2"> <p>Marca de tiempo </p> </td> 
   <td colname="col3"> <p>La hora en que los <span class="wintitle"> Servidores de recopilación de datos</span> (DCS) procesaron un archivo CDF. La marca de tiempo utiliza el formato <i>yyyy-mm-dd hh:mm:ss</i> y se establece en la zona horaria UTC. </p> <p> <p>Nota: El Tiempo de evento <i>no es</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">La hora del evento de página o de la llamada del evento en sí, aunque puede estar cerca de esas horas. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Relacionado con la hora de DCS en el nombre del archivo. Consulte también <a href="#different-processing-times"> Tiempos del nombre de archivo de la fuente de datos del cliente y Tiempos de contenido del archivo...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Este es el <span class="wintitle"> ID de usuario único</span> (UUID), que es un ID de dispositivo de 38 dígitos para el visitante del sitio. Consulte también <a href="../reference/ids-in-aam.md">Índice de ID en Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numérica </p> </td> 
   <td colname="col3"> <p>ID del contenedor que activa la sincronización de ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Matriz de ID de rasgos que contiene todos los rasgos que un visitante realizó (para los que se calificó) en la llamada de evento. </p> <p>Tenga en cuenta que la matriz puede contener rasgos para los que el visitante se haya clasificado antes y para los que se vuelve a calificar mediante esta llamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Matriz de ID de segmento que contiene todos los segmentos que realizó un visitante (para los que cumple los requisitos) en la llamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Una cadena que captura todos los parámetros (variables, ID, pares de clave-valor, ID de publicidad de dispositivo, etc.) se transfiere en la llamada de evento. </p> <p>Ejemplo abreviado: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>La dirección URL no codificada de la página de referencia (si existe). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>La dirección IP del visitante capturada en la llamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>El <span class="keyword"> ID de Experience Cloud</span> (MID) asignado al visitante del sitio. Consulte también la información relativa a las cookies <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> y el servicio de identidad del Experience Platform de Adobe</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Matriz de ID de segmento que contiene segmentos realizados anteriormente y segmentos nuevos para los que el visitante está cualificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Matriz de ID de rasgos de origen y de terceros que contiene características realizadas anteriormente y nuevas características para las que el visitante ha calificado desde la última fuente de datos generada. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Estructura del archivo {#cdf-file-structure}

Enumera y define la estructura de datos de un archivo [!UICONTROL CDF]. Esto incluye secuencia de datos, delimitadores y separadores de campos, un mapa de archivos de datos y un archivo de muestra.

## Identificadores y secuencia de campos de datos {#identifiers-and-sequence}

[!UICONTROL CDF] los archivos no contienen columnas etiquetadas ni encabezados de campo. En su lugar, un archivo [!UICONTROL CDF] define campos y matrices con caracteres no imprimibles [!DNL ASCII]. Además, el archivo [!UICONTROL CDF] enumera cada campo y matriz en un orden específico. La comprensión de los identificadores de campo y el orden le ayudará a analizar el archivo correctamente.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento Archivo CDF </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Separadores y delimitadores de campo </p> </td> 
   <td colname="col2"> <p>Estos caracteres no imprimibles definen los elementos y la estructura del archivo CDF: </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> o <code> ^A</code>) separa los datos de campos individuales con un indicador de espacio no imprimible. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> o <code> ^B</code>) separa los datos, la matriz y los parámetros de solicitud. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> o <code> ^C</code>) define pares clave-valor. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Secuencia de campo </p> </td> 
   <td colname="col2"> <p> <p>Importante: El <span class="keyword"> Audience Manager</span> se reserva el derecho de agregar nuevos campos al final del archivo CDF en futuras versiones. Esto significa que el diseño técnico del sistema de análisis de archivos no debe asumir un número fijo de columnas (aunque puede suponer un orden fijo para las columnas existentes). </p> </p> <p>Los datos del archivo CDF aparecen en el orden que se muestra a continuación. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Hora del evento </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Device </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID de contenedor </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Rasgos reales </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segmentos hechos </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Parámetros de solicitud </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Dirección IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">ID del dispositivo Experience Cloud (o MID). Consulte también la información relativa a las cookies <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> y el servicio de identidad de Adobe Experience Platform</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Todos los segmentos </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Todos los rasgos </li> 
     </ol> </p> <p>Para obtener descripciones de los campos, consulte <a href="#cdf-defined"> Contenido definido de la fuente de datos del cliente</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] Mapa del archivo {#cdf-file-map}

[!UICONTROL CDF] los datos del archivo aparecen en el orden que se muestra a continuación.

![](assets/sequence-map.png)

## Identificación de matrices

Las matrices de un archivo [!UICONTROL CDF] comienzan y finalizan con el separador de campos `Ctrl + a`. Esto hace que el primer elemento de una matriz aparezca como un campo de datos independiente. Por ejemplo, la matriz [!UICONTROL traits] realizada comienza con `^A1234`. El delimitador de matriz y el ID `^B5678` siguen esta entrada. Como resultado, es posible que esté tentado a pensar que el primer elemento de la matriz [!UICONTROL traits] realizada es el ID 5678 (porque comienza con `^B`). Este no es el caso, por lo que debe estar familiarizado con la secuencia y la estructura de un archivo de datos. Aunque el primer elemento de la matriz [!UICONTROL trait] existente (o cualquiera de las otras matrices de un archivo [!UICONTROL CDF]) comience por `^A`, el orden de aspecto o posición del archivo define el inicio de una matriz. Además, el primer elemento de una matriz siempre se separa de la entrada anterior por `^A`.

## Archivo [!UICONTROL CDF] de muestra {#sample-file}

Un archivo [!UICONTROL CDF] de muestra podría tener un aspecto similar al siguiente. Hemos insertado saltos de línea en este ejemplo para ayudarle a ajustar la página.

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] Convenciones de nomenclatura de archivos {#cdf-naming-conventions}

Las secciones siguientes enumeran y definen los elementos en su nombre de archivo [!UICONTROL CDF].

## [!UICONTROL CDF] Nombre del archivo: Sintaxis y ejemplo {#cdf-file-name}

Un nombre de archivo [!UICONTROL CDF] típico contiene los elementos que se enumeran a continuación. Tenga en cuenta que *cursiva* indica un marcador de posición de variable:

### Sintaxis

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### Ejemplo

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

En el espacio de almacenamiento [!DNL S3], los archivos se ordenan en orden ascendente por ID de socio ([!UICONTROL PID]), día y hora.

## [!UICONTROL CDF] Elementos de nombre de archivo definidos {#cdf-file-name-elements}

En la tabla siguiente se enumeran y definen los elementos de un nombre de archivo [!UICONTROL CDF].

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento Nombre de archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3://aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Este es el espacio de almacenamiento raíz predeterminado para su archivo CDF en un servidor Amazon S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>El nombre del contenedor S3 de solo lectura que contiene sus archivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>La fecha en la que se procesó el archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Un valor de hora expresado en notación de 24 horas y establecido en la zona horaria UTC. Consulte también <a href="#different-processing-times"> Tiempos del nombre de archivo de la fuente de datos del cliente y Tiempos de contenido del archivo...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Su ID de socio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Un ID de proceso <span class="keyword"> Audience Manager</span> interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Extensión de archivo gzip. Los archivos CDF están comprimidos en gzip. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Notificaciones de procesamiento de archivos {#cdf-file-processing-notifications}

[!DNL Audience Manager] escribe un  `.info` archivo en su  [!DNL S3] directorio para informarle cuando su  [!UICONTROL Customer Data File] ([!UICONTROL CDF]) esté listo para la descarga. El archivo `.info` también incluye metadatos con formato [!DNL JSON] sobre el contenido de sus archivos [!UICONTROL CDF]. Consulte esta sección para obtener información sobre la sintaxis y los campos utilizados por este archivo de notificación.

## Archivo de información de muestra {#sample-info-file}

Cada archivo `.info` contiene una sección `Files` y `Totals`. La sección `Files` contiene una matriz que contiene métricas específicas para cada archivo por hora. La sección `Totals` contiene métricas agregadas en todos los archivos [!UICONTROL CDF] de un día en particular. El contenido del archivo `.info` puede tener un aspecto similar al del siguiente ejemplo.

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

## Campos del archivo de información definidos {#info-file-fields-defined}

Las siguientes tablas enumeran y definen los elementos de un archivo [!UICONTROL CDF] `.info`.

### Objeto Files

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Files</code> </p> </td> 
   <td colname="col2"> <p>Inicia la matriz que contiene metadatos sobre los archivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Tamaño del archivo en bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag. El número que sigue al guión muestra el número de partes utilizadas para crear el archivo durante la carga multiparte. El <code> ETag</code> no es idéntico a la suma de comprobación MD5 del archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>El nombre del archivo. Consulte <a href="#cdf-naming-conventions"> Convenciones de nomenclatura de archivos de fuentes de datos de clientes</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>Un número de índice para cada archivo. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Objeto Totals

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Totals</code> </p> </td> 
   <td colname="col2"> <p>Inicia el objeto que contiene datos acumulados sobre todos los archivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>El día durante el cual están disponibles los datos. Utiliza el formato <i>yyyy-mm-dd</i> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>Hora a la que están disponibles los datos. Utiliza el formato de 24 horas configurado en la zona horaria UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Tamaño total de todos sus archivos CDF para esa fecha en bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Número total de archivos cargados en el directorio S3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Los tiempos de los nombres de archivo y los tiempos de contenido de archivo son diferentes {#different-processing-times}

El archivo [!UICONTROL CDF] contiene marcas de hora en el nombre del archivo y en el contenido del archivo. Estas marcas de tiempo registran diferentes procesos de evento para el mismo archivo [!UICONTROL CDF]. No es raro ver diferentes marcas de tiempo en el nombre y contenido del mismo archivo. Comprender cada marca de tiempo puede ayudarle a evitar errores comunes al trabajar con estos datos o al intentar ordenarlos por tiempo.

## Localización de [!UICONTROL CDF] Marcas de hora de archivo {#locating-timestamps}

[!UICONTROL CDF] los archivos registran el tiempo de forma diferente en dos ubicaciones independientes.

![](assets/cdf-timestamp.png)

## Explicación de la diferencia entre marcas de hora {#understanding-timestamps}

La siguiente tabla proporciona detalles adicionales sobre las marcas de tiempo del archivo [!UICONTROL CDF] junto con información sobre cómo utilizarlas correctamente.

| Ubicación de la marca de tiempo | Descripción |
|--- |--- |
| Nombre del archivo | La marca de tiempo del nombre del archivo [!DNL CDF] marca la hora en que [!DNL Audience Manager] comenzó a preparar el archivo para su envío. Esta marca de tiempo se establece en el huso horario [!DNL UTC]. Utiliza el parámetro `hour=`, con el formato de hora de 2 dígitos en notación de 24 horas. Esta vez puede ser diferente a la hora del evento registrada en el contenido del archivo. Al trabajar con archivos [!DNL CDF], a veces notará que su contenedor [!DNL S3] está vacío durante una hora en particular. Un espacio vacío significa que puede ser cualquiera de los siguientes:<ul><li>No hay datos para esa hora en particular. </li><li> Nuestros servidores están bajo cargas pesadas y no pueden procesar archivos durante una hora en particular. Cuando el servidor se pone al día, coloca los archivos que deberían haber pasado en archivos de bloque de tiempo anteriores en un bloque con un valor de tiempo posterior. Por ejemplo, verá esto cuando un archivo que debería estar en el bloque de la hora 17 aparezca en el bloque de la hora 18 (con `hour=18` en el nombre del archivo). En este caso, el servidor probablemente comenzó a procesar su archivo en la hora 17, pero no pudo completarlo en ese intervalo de tiempo. En su lugar, el archivo se inserta en el siguiente espacio de tiempo por hora.</li></ul><br>**Importante**: No utilice la marca de tiempo del nombre del archivo para agrupar eventos por tiempo. Si necesita agrupar por tiempo, use la marca de tiempo `EventTime` en el contenido del archivo. |
| Contenido del archivo | La marca de tiempo del contenido del archivo [!DNL CDF] marca la hora en que [!DNL Data Collection Servers] comenzó a procesar el archivo. Esta marca de tiempo se establece en el huso horario [!DNL UTC]. Utiliza el campo `EventTime`, con el formato de tiempo *`yyyy-mm-dd hh:mm:ss`*. Esta hora está cerca de la hora real del evento en la página, pero puede ser diferente del indicador de hora del nombre del archivo. <br> **Sugerencia**: A diferencia de la  `hour=` marca de tiempo del nombre del archivo, puede utilizar  `EventTime` para agrupar los datos por hora. |

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre la Fuente de datos de clientes](../faq/faq-cdf.md)

