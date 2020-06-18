---
description: Información básica sobre archivos de Fuente de datos del cliente (CDF) e instrucciones sobre cómo empezar. Inicio aquí si estás interesado en recibir archivos CDF o solo quieres más información.
keywords: second party data;2nd party;2nd party data;second party
seo-description: Información básica sobre archivos de Fuente de datos del cliente (CDF) e instrucciones sobre cómo empezar. Inicio aquí si estás interesado en recibir archivos CDF o solo quieres más información.
seo-title: Fuentes de datos del cliente
solution: Audience Manager
title: Fuentes de datos del cliente
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1890'
ht-degree: 2%

---


# Fuentes de datos del cliente {#customer-data-feeds}

Información básica sobre [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) archivos e instrucciones sobre cómo empezar. Inicio aquí si estás interesado en recibir [!UICONTROL CDF] archivos o solo quieres más información.

## Contenido y propósito del archivo {#file-contents-purpose}

<!-- cdf-intro.xml -->

Un [!UICONTROL CDF] archivo contiene los mismos datos que una llamada de [!DNL Audience Manager] evento (`/event`) envía a nuestros servidores. Esto incluye datos como ID de usuario, ID de características, ID de segmentos y todos los demás parámetros capturados por una llamada de evento. Los [!DNL Audience Manager] sistemas internos procesan los datos de evento en un [!UICONTROL CDF] archivo con contenido organizado en campos que aparecen en un orden definido. [!DNL Audience Manager] intenta generar [!UICONTROL CDF] archivos por hora y los almacena en un bloque seguro y específico para el cliente en un [!DNL Amazon S3] servidor. Proporcionamos estos archivos para que pueda trabajar con [!DNL Audience Manager] datos fuera de los límites impuestos por nuestra interfaz de usuario.

>[!NOTE]
>
>No debe utilizar [!UICONTROL CDF] los archivos como proxy para supervisar el tráfico de páginas, reconciliar discrepancias en los informes, para facturar, etc.

## Introducción {#getting-started}

No existe un proceso de autoservicio para el envío de archivos [!UICONTROL CDF] de inicio. Contact your [!DNL Audience Manager] consultant or Customer Care to get started. Durante la implementación, su [!DNL Audience Manager] representante:

* Configure el cubo [!DNL Amazon S3] de almacenamiento.
* Proporcione credenciales de autenticación de solo lectura al contenedor de almacenamiento de archivos. [!DNL S3] No podrá ver ni acceder a directorios y archivos que pertenezcan a otros clientes.

Las notificaciones de archivo y [!UICONTROL CDF] los archivos aparecerán en el [!DNL S3] bloque cuando estén listos para la descarga. Usted es el responsable de supervisar y descargar archivos del [!DNL S3] directorio asignado. Consulte Notificaciones [de procesamiento de archivos de fuentes de datos de clientes](#cdf-file-processing-notifications).

## Pasos siguientes {#next-steps}

Las secciones a continuación y las preguntas más frecuentes [sobre fuentes de datos de](../faq/faq-cdf.md) clientes pueden ayudarle a familiarizarse con este servicio.

## Contenido de fuente de datos del cliente definido {#cdf-defined}

Lista y define los elementos de datos y las matrices de un [!UICONTROL CDF] archivo por orden de aspecto. Las definiciones incluyen tipos de datos, pero esta información no forma parte de un [!UICONTROL CDF] archivo.

## Definiciones {#definitions}

<!-- cdf-contents-defined.xml -->

Un [!UICONTROL CDF] archivo incluye algunos o todos los campos definidos a continuación. Para obtener información sobre la organización de archivos internos, consulte Estructura [de archivos de fuentes de datos de](#cdf-file-structure)clientes.

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
   <td colname="col2"> <p>Marca de hora </p> </td> 
   <td colname="col3"> <p>Hora a la que los servidores <span class="wintitle"></span> de recopilación de datos (DCS) procesaron un archivo CDF. La marca de tiempo utiliza el formato <i>aaaa-mm-dd hh:mm:ss</i> y se establece en la zona horaria UTC. </p> <p> <p>Nota: El tiempo de Evento no <i>es</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">La hora del evento de la página o de la llamada del evento, aunque puede estar cerca de esas horas. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Relacionado con la hora de DCS en el nombre del archivo. Consulte también <a href="#different-processing-times"> Tiempos del nombre del archivo de la fuente de datos del cliente y Tiempos del contenido del archivo...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Es el ID <span class="wintitle"> de usuario</span> único (UUID), que es un ID de dispositivo de 38 dígitos para el visitante del sitio. Consulte también <a href="../reference/ids-in-aam.md">Índice de ID en Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numérica </p> </td> 
   <td colname="col3"> <p>ID del contenedor que activa la sincronización de ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Matriz de ID de características que contiene todas las características que un visitante realizó (para las que se calificó) en la llamada de evento. </p> <p>Tenga en cuenta que la matriz puede contener características para las que el visitante ha calificado antes y para las que se vuelven a calificar a través de esta llamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Matriz de ID de segmentos que contiene todos los segmentos que un visitante realizó (para los que se calificó) en la llamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Una cadena que captura todos los parámetros (variables, ID, pares de clave-valor, ID de publicidad de dispositivo, etc.) pasó en la llamada de evento. </p> <p>Ejemplo abreviado: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Dirección URL no codificada de la página de referencia (si existe). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>La dirección IP del visitante capturado en la llamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>El <span class="keyword"> ID de Experience Cloud</span> (MID) asignado al visitante del sitio. Consulte también <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies y el servicio</a>de identidad de Experience Platform de Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Matriz de ID de segmentos que contiene segmentos realizados anteriormente y segmentos nuevos para los que está cualificado el visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Matriz de ID de características de origen y de terceros que contiene características realizadas anteriormente y características nuevas para las que el visitante ha calificado desde la última fuente de datos generada. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Estructura del archivo de fuente de datos del cliente {#cdf-file-structure}

Lista y define la estructura de datos de un [!UICONTROL CDF] archivo. Esto incluye secuencias de datos, delimitadores y separadores de campos, una asignación de archivos de datos y un archivo de muestra.

## Secuencia e identificadores de campo de datos {#identifiers-and-sequence}

<!-- cdf-file-structure.xml -->

[!UICONTROL CDF] los archivos no contienen columnas etiquetadas ni encabezados de campo. En su lugar, un [!UICONTROL CDF] archivo define campos y matrices con [!DNL ASCII] caracteres no imprimibles. Además, el [!UICONTROL CDF] archivo lista cada campo y matriz en un orden específico. El comprender los identificadores de campo y el orden le ayudará a analizar el archivo correctamente.

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
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> o <code> ^A</code>) separa los datos de campos individuales con un indicador de espacio no imprimible. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> o <code> ^B</code>) separa los datos de una matriz y los parámetros de solicitud. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> o <code> ^C</code>) define pares clave-valor. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Secuencia de campos </p> </td> 
   <td colname="col2"> <p> <p>Importante: <span class="keyword"> Audience Manager</span> se reserva el derecho de agregar nuevos campos al final del archivo CDF en futuras versiones. Esto significa que el diseño técnico del sistema de análisis de archivos no debe asumir un número fijo de columnas (aunque puede asumir un orden fijo para las columnas existentes). </p> </p> <p>Los datos del archivo CDF aparecen en el orden que se muestra a continuación. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Tiempo de Evento </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Device </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID de contenedor </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Características realizadas </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segmentos realizados </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Parámetros de solicitud </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Dirección IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">ID del dispositivo Experience Cloud (o MID). Consulte también <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies y el servicio de identidad de Adobe Experience Platform</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Todos los segmentos </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Todas las características </li> 
     </ol> </p> <p>Para ver las descripciones de los campos, consulte <a href="#cdf-defined"> Contenido de fuente de datos del cliente definido</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mapa de archivos CDF {#cdf-file-map}

[!UICONTROL CDF] los datos del archivo aparecen en el orden que se muestra a continuación.

![](assets/sequence-map.png)

## Identificación de matrices

Arreglos en un inicio de [!UICONTROL CDF] archivos y termine con el separador de `Ctrl + a` campos. Esto hace que el primer elemento de una matriz aparezca como un campo de datos independiente. Por ejemplo, la matriz de características realizadas inicio con `^A1234`. El delimitador de matriz y la ID `^B5678` siguen a esta entrada. Como resultado, podría sentir la tentación de pensar que el primer elemento de la matriz de características realizadas es ID 5678 (porque inicio con `^B`). Este no es el caso, por lo que debe estar familiarizado con la secuencia y la estructura de un archivo de datos. Aunque el primer elemento de la matriz de características realizada (o cualquiera de las demás matrices de un [!UICONTROL CDF] archivo) inicio con `^A`, el orden de aspecto o posición del archivo define el inicio de una matriz. Y, el primer elemento de una matriz siempre está separado de la entrada anterior por `^A`.

## Archivo CDF de muestra {#sample-file}

Un [!UICONTROL CDF] archivo de muestra podría tener un aspecto similar al siguiente. Hemos insertado saltos de línea en este ejemplo para ayudarle a ajustar la página.

![](assets/CDF-sample.png)

## Convenciones de nomenclatura de archivos de fuentes de datos de clientes {#cdf-naming-conventions}

Las secciones a continuación lista y definen los elementos en el nombre [!UICONTROL CDF] del archivo.

## Nombre de archivo CDF: Sintaxis y ejemplo {#cdf-file-name}

<!-- cdf-file-name.xml -->

Un nombre [!UICONTROL CDF] de archivo típico contiene los elementos que se enumeran a continuación. Note, *italics* indicates a variable placeholder:

### Sintaxis

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### Ejemplo

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

En el bloque [!DNL S3] almacenamiento, los archivos se ordenan en orden ascendente por ID de socio ([!UICONTROL PID]), día y hora.

## Elementos de nombre de archivo CDF definidos {#cdf-file-name-elements}

La siguiente tabla lista y define los elementos en un nombre de [!UICONTROL CDF] archivo.

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
   <td colname="col2"> <p>Este es el bloque de almacenamiento raíz predeterminado para el archivo CDF en un servidor Amazon S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>Nombre del contenedor S3 de sólo lectura que contiene los archivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>La fecha en que se procesó el archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Un valor de hora expresado en notación de 24 horas y definido en la zona horaria UTC. Consulte también <a href="#different-processing-times"> Tiempos del nombre del archivo de la fuente de datos del cliente y Tiempos del contenido del archivo...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Su ID de socio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Un ID de proceso interno <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Extensión de archivo gzip. Los archivos CDF están comprimidos gzip. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Notificaciones de procesamiento de archivos de fuentes de datos de clientes {#cdf-file-processing-notifications}

[!DNL Audience Manager] escribe un `.info` archivo en su [!DNL S3] directorio para informarle cuando [!UICONTROL Customer Data File] ([!UICONTROL CDF]) esté listo para descargar. El `.info` archivo también incluye metadatos [!DNL JSON] formateados sobre el contenido de [!UICONTROL CDF] los archivos. Consulte esta sección para obtener información sobre la sintaxis y los campos utilizados por este archivo de notificación.

## Archivo de información de muestra {#sample-info-file}

<!-- cdf-notifications.xml -->

Cada `.info` archivo contiene una `Files` sección y `Totals` . La `Files` sección contiene una matriz que contiene métricas específicas para cada archivo por hora. La `Totals` sección contiene métricas agregadas en todos los [!UICONTROL CDF] archivos para un día en particular. El contenido del `.info` archivo podría tener un aspecto similar al del siguiente ejemplo.

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

Las siguientes tablas lista y definen los elementos de un [!UICONTROL CDF] `.info` archivo.

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
   <td colname="col2"> <p>Inicio la matriz que contiene metadatos sobre los archivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Tamaño del archivo en bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag. El número que sigue al guión muestra el número de partes utilizadas para crear el archivo durante la carga de varias partes. El <code> ETag</code> archivo no es idéntico a la suma de comprobación MD5 del archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>El nombre del archivo. Consulte <a href="#cdf-naming-conventions"> Convenciones</a>de nomenclatura de archivos de fuentes de datos de clientes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>Un número de índice para cada archivo. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Totals (objeto)

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
   <td colname="col2"> <p>Inicio el objeto que contiene datos agregados sobre todos los archivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>El día para el que están disponibles los datos. Utiliza el formato <i>aaaa-mm-dd</i> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>La hora para la que están disponibles los datos. Utiliza el formato de 24 horas establecido en la zona horaria UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Tamaño total de todos los archivos CDF para esa fecha en bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Número total de archivos cargados en el directorio S3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Los tiempos del nombre del archivo de la fuente de datos del cliente y del contenido del archivo son diferentes {#different-processing-times}

El [!UICONTROL CDF] archivo contiene marcas de hora en el nombre del archivo y en el contenido del archivo. Estas marcas de hora registran diferentes procesos de evento para el mismo [!UICONTROL CDF] archivo. No es raro ver marcas de hora diferentes en el nombre y el contenido del mismo archivo. El comprender cada marca de tiempo puede ayudarle a evitar errores comunes al trabajar con estos datos o al intentar ordenarlos por tiempo.

## Localización de marcas de hora de archivo CDF {#locating-timestamps}

<!-- cdf-time-differences.xml -->

[!UICONTROL CDF] los archivos registran el tiempo de forma diferente en dos ubicaciones distintas.

![](assets/cdf-timestamp.png)

## Explicación de la diferencia entre marcas de hora {#understanding-timestamps}

En la tabla siguiente se proporcionan detalles adicionales sobre las marcas de hora [!UICONTROL CDF] del archivo, así como información sobre cómo utilizarlas correctamente.

| Ubicación de marca de hora | Descripción |
|--- |--- |
| Nombre del archivo | La marca de tiempo en el nombre [!DNL CDF] del archivo marca la hora en que [!DNL Audience Manager] comenzó a preparar el archivo para su envío. Esta marca de tiempo se establece en la zona [!DNL UTC] horaria. Utiliza el `hour=` parámetro, con el formato de hora de 2 dígitos en notación de 24 horas. Esta hora puede ser diferente a la hora de evento registrada en el contenido del archivo. Al trabajar con [!DNL CDF] archivos, a veces notará que su [!DNL S3] cubo está vacío durante una hora en particular. Un depósito vacío significa cualquiera de los siguientes:<ul><li>No hay datos para esa hora en particular. </li><li> Nuestros servidores están bajo cargas pesadas y no pueden procesar archivos durante una hora en particular. Cuando el servidor se pone al día, coloca los archivos que deberían haber pasado en un bloque de tiempo anterior en un bloque con un valor de tiempo posterior. Por ejemplo, verá esto cuando un archivo que debería estar en el bloque de hora 17 aparezca en el bloque de hora 18 (con `hour=18` el nombre del archivo). En este caso, es probable que el servidor haya empezado a procesar el archivo en la hora 17, pero no pueda completarlo dentro de ese intervalo de tiempo. En su lugar, el archivo se inserta en el siguiente bloque de tiempo por hora.</li></ul><br>**Importante **: No utilice la marca de tiempo del nombre del archivo para agrupar eventos por tiempo. Si necesita agrupar por tiempo, utilice la`EventTime`marca de tiempo en el contenido del archivo. |
| Contenido del archivo | La marca de tiempo en el contenido [!DNL CDF] del archivo marca la hora en que [!DNL Data Collection Servers] comenzó a procesarse el archivo. Esta marca de tiempo se establece en la zona [!DNL UTC] horaria. Utiliza el `EventTime` campo, con el tiempo formateado como *`yyyy-mm-dd hh:mm:ss`*. Esta hora está cerca de la hora real del evento en la página, pero puede ser diferente al indicador de hora en el nombre del archivo. <br> **Sugerencia**: A diferencia de la `hour=` marca de tiempo del nombre del archivo, puede utilizarla `EventTime` para agrupar los datos por tiempo. |

>[!MORELIKETHIS]
>
>* [Preguntas más frecuentes sobre la fuente de datos del cliente](../faq/faq-cdf.md)

