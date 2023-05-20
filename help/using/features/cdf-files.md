---
description: Información básica sobre los archivos de Fuente de datos del cliente (CDF) e instrucciones sobre cómo empezar. Comience aquí si está interesado en recibir archivos CDF o simplemente desea más información.
keywords: datos de segundo nivel;segundo nivel;datos de segundo nivel;segundo nivel
seo-description: Basic information about Customer Data Feed (CDF) files and instructions on how to get started. Start here if you're interested in receiving CDF files or just want more information.
seo-title: Customer Data Feeds
solution: Audience Manager
title: Fuentes de datos de clientes
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Customer Data Feeds
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 89137248aa47573f5b65e387a152f651419da827
workflow-type: tm+mt
source-wordcount: '1989'
ht-degree: 3%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

Información básica sobre [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) archivos e instrucciones sobre cómo empezar. Comience aquí si está interesado en recibir [!UICONTROL CDF] archivos o simplemente desea obtener más información.

## Contenido y propósito del archivo {#file-contents-purpose}

Un archivo [!UICONTROL CDF] contiene los mismos datos que una llamada de evento de [!DNL Audience Manager] (`/event`) envía a nuestros servidores. Esto incluye datos como ID de usuario, [!UICONTROL trait IDs], [!UICONTROL segment IDs]y todos los demás parámetros capturados por una llamada de evento. Interno [!DNL Audience Manager] procesa los datos de evento en una [!UICONTROL CDF] archivo con contenido organizado en campos que aparecen en un orden definido. [!DNL Audience Manager] intenta generar [!UICONTROL CDF] archivos por hora y los almacena en un espacio seguro y específico del cliente en un [!DNL Amazon S3] servidor. Proporcionamos estos archivos para que pueda trabajar con [!DNL Audience Manager] datos fuera de los límites impuestos por nuestra interfaz de usuario.

>[!IMPORTANT]
>
>Tenga en cuenta las siguientes restricciones al trabajar con archivos CDF:
>
>* Antes de configurar la entrega de archivos CDF, asegúrese de que dispone de los permisos adecuados de los proveedores de datos de terceros para la exportación de características de terceros. Actualmente, Audience Manager no admite la funcionalidad en la interfaz de usuario para solicitar a los proveedores de datos de terceros el permiso de exportación de entrega de archivos CDF, por lo que debe ponerse en contacto con ellos de forma independiente.
>* No debe utilizar [!UICONTROL CDF] archivos como proxy para controlar el tráfico de la página, reconciliar discrepancias de informes, o para facturación, etc.


## Introducción {#getting-started}

No hay ningún proceso de autoservicio para iniciar [!UICONTROL CDF] envío de archivos. Póngase en contacto con su [!DNL Audience Manager] consultor o con el Servicio de atención al cliente para empezar. Durante la implementación, su [!DNL Audience Manager] el representante:

* Configure su [!DNL Amazon S3] cubo de almacenamiento.
* Proporcionar solo lectura [!DNL S3] credenciales de autenticación en el contenedor de almacenamiento de archivos. No podrá ver ni acceder a directorios y archivos que pertenezcan a otros clientes.

Notificaciones de archivos y [!UICONTROL CDF] Los archivos aparecerán en su [!DNL S3] cubos cuando estén listos para descargar. Usted es responsable de supervisar y descargar archivos de su asignado [!DNL S3] directorio. Consulte [Notificaciones sobre procesamiento de archivos de fuentes de datos de clientes](#cdf-file-processing-notifications).

## Pasos siguientes {#next-steps}

Las secciones siguientes y la [Preguntas frecuentes sobre fuentes de datos de clientes](../faq/faq-cdf.md) puede ayudarle a familiarizarse con este servicio.

## [!UICONTROL Customer Data Feed] Contenido definido {#cdf-defined}

Enumera y define los elementos de datos y las matrices de una [!UICONTROL CDF] archivo, por orden de aparición. Las definiciones incluyen tipos de datos, pero esta información no forma parte de un [!UICONTROL CDF] archivo.

>[!IMPORTANT]
>
>Los píxeles de evento se excluyen de forma predeterminada en las configuraciones de CDF. Asegúrese de especificar en la solicitud al servicio de atención al cliente si desea que los píxeles de evento se incluyan en los archivos CDF. Cada píxel de evento se rellenará como una fila única en los archivos CDF.

## Definiciones {#definitions}

A [!UICONTROL CDF] incluye algunos o todos los campos definidos a continuación. Para obtener información sobre la organización interna de archivos, consulte [Estructura de archivo de fuente de datos del cliente](#cdf-file-structure).

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
   <td colname="col3"> <p>Hora a la que el administrador procesó un archivo CDF <span class="wintitle"> Servidores de recopilación de datos</span> (DCS). La marca de tiempo utiliza el <i>yyyy-mm-dd hh:mm:ss</i> y se establece en la zona horaria UTC. </p> <p> <p>Nota: La Hora Del Evento <i>no es</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">La hora del evento de página o la propia llamada de evento, aunque puede estar cerca de esas horas. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Relacionado con la hora DCS en el nombre de archivo. Consulte también. <a href="#different-processing-times"> Fuentes de datos del cliente Nombre de archivo Horas y Contenido de archivo Horas...</a>. </li> 
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
   <td colname="col3"> <p>El ID del contenedor que activa la sincronización de ID. Este campo solo se rellena si establece el ID de contenedor en la variable <i>d_nsid</i> dentro de la implementación del sitio. De lo contrario, el valor predeterminado de 0 no se incluirá en los archivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Una matriz de ID de rasgos que contiene todos los rasgos para los que un visitante se dio cuenta (cualificado) en la llamada de evento. </p> <p>Tenga en cuenta que la matriz puede contener características para las que el visitante había cumplido los requisitos antes y para las que volvió a clasificarse a través de esta llamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Matriz de ID de segmento que contiene todos los segmentos para los que el visitante se dio cuenta (para los que cumple los requisitos) en la llamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Una cadena que captura todos los parámetros (variables, ID, pares clave-valor, ID de publicidad de dispositivo, etc.) pasado en la llamada de evento. </p> <p>Ejemplo abreviado: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>La dirección URL sin codificar de la página de referencia (si la hay). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>La dirección IP del visitante capturada en la llamada de evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>El <span class="keyword"> Experience Cloud</span> ID asignado al visitante del sitio. Consulte también. <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies y el servicio de ID del Experience Platform de Adobe</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Matriz de ID de segmento que contiene segmentos para los que se ha realizado anteriormente y nuevos segmentos para los que el visitante está cualificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Matriz numérica </p> </td> 
   <td colname="col3"> <p>Una matriz de ID de rasgos de origen y de terceros que contiene rasgos realizados anteriormente y nuevos rasgos para los que el visitante ha cumplido los requisitos desde la última fuente de datos generada. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Estructura de archivos {#cdf-file-structure}

Enumera y define la estructura de datos de un [!UICONTROL CDF] archivo. Esto incluye la secuencia de datos, los delimitadores y separadores de campo, un mapa del archivo de datos y un archivo de muestra.

## Identificadores y secuencia de campos de datos {#identifiers-and-sequence}

[!UICONTROL CDF] los archivos no contienen columnas etiquetadas ni encabezados de campo. En su lugar, un [!UICONTROL CDF] define campos y matrices con elementos no imprimibles [!DNL ASCII] caracteres. Además, la variable [!UICONTROL CDF] El archivo enumera cada campo y matriz en un orden específico. Comprender los identificadores de campo y el orden le ayudará a analizar el archivo correctamente.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de archivo CDF </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Separadores y delimitadores de campos </p> </td> 
   <td colname="col2"> <p>Estos caracteres no imprimibles definen los elementos y la estructura del archivo CDF: </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII) <code> 001</code> o <code> ^A</code>) separa los datos de campos individuales con un indicador de espacio no imprimible. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII) <code> 002</code> o <code> ^B</code>) separa los datos de una matriz y los parámetros de solicitud. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII) <code> 003</code> o <code> ^C</code>) define pares clave-valor. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Secuencia de campos </p> </td> 
   <td colname="col2"> <p> <p>Importante: <span class="keyword"> Audience Manager</span> se reserva el derecho de añadir nuevos campos al final del archivo CDF en futuras versiones. Esto significa que el diseño técnico del sistema de análisis de archivos no debe suponer un número fijo de columnas (aunque puede suponer un orden fijo para las columnas existentes).</p> </p> <p>Los datos del archivo CDF aparecen en el orden indicado a continuación. /N puede aparecer en lugar de cualquiera de estos campos, lo que indica un valor nulo.</p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Hora del evento </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Device </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID de contenedor </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Características realizadas </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segmentos realizados </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Parámetros de solicitud </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Dirección IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">ID del dispositivo del Experience Cloud (o MID). Consulte también. <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies y el servicio de Adobe Experience Platform ID</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Todos los segmentos </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Todas las características </li> 
     </ol> </p> <p>Para ver las descripciones de los campos, consulte <a href="#cdf-defined"> Contenido de fuente de datos de cliente definido</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] Mapa de archivos {#cdf-file-map}

[!UICONTROL CDF] los datos del archivo aparecen en el orden mostrado a continuación.

![](assets/sequence-map.png)

## Identificación de matrices

Matrices en una [!UICONTROL CDF] inicio y final del archivo con `Ctrl + a` separador de campos. Esto hace que el primer elemento de una matriz parezca un campo de datos independiente. Por ejemplo, la cuenta [!UICONTROL traits] la matriz empieza por `^A1234`. El delimitador de matriz y el ID `^B5678` sigue esta entrada. Como resultado, puede sentirse tentado a pensar que el primer elemento de la imagen realizada [!UICONTROL traits] La matriz es el ID 5678 (porque comienza con `^B`). Este no es el caso, por lo que debe estar familiarizado con la secuencia y estructura de un archivo de datos. A pesar de que el primer elemento en el realizado [!UICONTROL trait] matriz (o cualquiera de las otras matrices de una [!UICONTROL CDF] file) empieza por `^A`, el orden de aparición o posición en el archivo define el inicio de una matriz. Y, el primer elemento de una matriz siempre se separa de la entrada anterior por `^A`.

## Muestra [!UICONTROL CDF] Archivo {#sample-file}

Una muestra [!UICONTROL CDF] podría tener un aspecto similar al siguiente. Hemos insertado saltos de línea en este ejemplo para que se ajuste a la página.

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] Convenciones de nomenclatura de archivos {#cdf-naming-conventions}

Las secciones siguientes enumeran y definen los elementos de su [!UICONTROL CDF] nombre de archivo.

## [!UICONTROL CDF] Nombre del archivo: sintaxis y ejemplo {#cdf-file-name}

Un típico [!UICONTROL CDF] file name contiene los elementos que se enumeran a continuación. Nota, *cursiva* indica un marcador de posición variable:

### Sintaxis

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF_PARTNER-ID_FILE-SEQUENCE_0.gz
```

### Ejemplo

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_0_0_0.gz
```

En su [!DNL S3] , los archivos se ordenan en orden ascendente por ID de socio ([!UICONTROL PID]), día y hora.

## [!UICONTROL CDF] Elementos de nombre de archivo definidos {#cdf-file-name-elements}

En la tabla siguiente se enumeran y definen los elementos de una [!UICONTROL CDF] nombre de archivo.

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
   <td colname="col2"> <p>Nombre del contenedor S3 de solo lectura que contiene los archivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>La fecha en la que se procesó el archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Un valor de hora expresado en notación de 24 horas y establecido en la zona horaria UTC. Consulte también. <a href="#different-processing-times"> Fuentes de datos del cliente Nombre de archivo Horas y Contenido de archivo Horas...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Su ID de socio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>File Sequence</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Valores que identifican la secuencia de archivos. La secuencia se incrementa de la siguiente manera: 0_0_0 , 0_1_0, 0_2_0....1_0_0</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Extensión de archivo gzip. Los archivos CDF están comprimidos en gzip. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Notificaciones de procesamiento de archivos {#cdf-file-processing-notifications}

[!DNL Audience Manager] escribe un `.info` archivo a su [!DNL S3] directorio para que sepa cuándo [!UICONTROL Customer Data File] ([!UICONTROL CDF]) está listo para descargar. El `.info` el archivo también incluye [!DNL JSON] metadatos con formato sobre el contenido de su [!UICONTROL CDF] archivos. Revise esta sección para obtener información sobre la sintaxis y los campos utilizados por este archivo de notificación.

## Archivo de información de muestra {#sample-info-file}

Cada `.info` el archivo contiene un `Files` y `Totals` sección. El `Files` contiene una matriz que contiene métricas específicas para cada archivo por hora. El `Totals` contiene métricas agregadas en todas sus [!UICONTROL CDF] archivos de un día en particular. El contenido de su `.info` podría ser similar al siguiente ejemplo.

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

## Campos de archivo de información definidos {#info-file-fields-defined}

Las siguientes tablas enumeran y definen los elementos de una [!UICONTROL CDF] `.info` archivo.

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
   <td colname="col2"> <p>Tamaño de archivo en bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>La Amazon S3 ETag. El número que sigue al guión muestra el número de partes utilizadas para crear el archivo durante la carga de varias partes. El <code> ETag</code> no es idéntico a la suma de comprobación MD5 del archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>El nombre del archivo. Consulte <a href="#cdf-naming-conventions"> Convenciones sobre nombres de archivos en fuentes de datos de clientes</a>. </p> </td> 
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
   <td colname="col2"> <p>Inicia el objeto que contiene los datos agregados de todos los archivos CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>El día para el cual los datos están disponibles. Usos <i>aaaa-mm-dd</i> formato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>La hora para la que los datos están disponibles. Utiliza el formato de 24 horas establecido en la zona horaria UTC. </p> </td> 
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

## [!UICONTROL Customer Data Feed] Las horas del nombre del archivo y las horas del contenido del archivo son diferentes {#different-processing-times}

Su [!UICONTROL CDF] el archivo contiene marcas de hora en su nombre y contenido. Estas marcas de tiempo registran diferentes procesos de evento para el mismo [!UICONTROL CDF] archivo. No es raro ver marcas de tiempo diferentes en el nombre y el contenido del mismo archivo. Comprender cada marca de tiempo puede ayudarle a evitar errores comunes al trabajar con estos datos o al intentar ordenarlos por tiempo.

## Localización [!UICONTROL CDF] Marcas horarias de archivo {#locating-timestamps}

[!UICONTROL CDF] Los archivos registran el tiempo de forma diferente en dos ubicaciones independientes.

![](assets/cdf-timestamp.png)

## Explicación de la diferencia entre marcas de tiempo {#understanding-timestamps}

La siguiente tabla proporciona detalles adicionales sobre su [!UICONTROL CDF] las marcas de tiempo de los archivos, junto con información sobre cómo utilizarlas correctamente.

| Ubicación de marca de tiempo | Descripción |
|--- |--- |
| Nombre del archivo | La marca de tiempo de su [!DNL CDF] nombre de archivo marca la hora en que [!DNL Audience Manager] comenzó a preparar el archivo para su envío. Esta marca de tiempo se establece en [!DNL UTC] zona horaria. Utiliza el `hour=` , con el formato de hora de 2 dígitos en notación de 24 horas. Esta hora puede ser diferente a la hora del evento registrada en el contenido del archivo. Al trabajar con [!DNL CDF] archivos, a veces notará que su [!DNL S3] el bloque está vacío durante una hora en particular. Un bloque vacío significa que puede significar cualquiera de las siguientes opciones:<ul><li>No hay datos para esa hora en particular. </li><li> Nuestros servidores están bajo cargas pesadas y no pueden procesar archivos durante una hora en particular. Cuando el servidor se pone al día, coloca los archivos que deberían haber estado en un bloque de tiempo anterior en un bloque con un valor de tiempo posterior. Por ejemplo, verá esto cuando aparezca un archivo que debería haber estado en el bloque de horas 17 en el bloque de horas 18 (con `hour=18` en el nombre del archivo). En este caso, es probable que el servidor haya empezado a procesar el archivo en la hora 17, pero no haya podido completarlo en ese intervalo de tiempo. En su lugar, el archivo se inserta en el siguiente bloque de tiempo por hora.</li></ul><br>**Importante**: no utilice la marca de tiempo del nombre de archivo para agrupar eventos por tiempo. Si necesita agrupar por tiempo, utilice el `EventTime` marca de tiempo en el contenido del archivo. |
| Contenido de archivo | La marca de tiempo de su [!DNL CDF] el contenido del archivo marca la hora en que [!DNL Data Collection Servers] comenzó a procesar el archivo. Esta marca de tiempo se establece en [!DNL UTC] zona horaria. Utiliza el `EventTime` , con el formato de hora *`yyyy-mm-dd hh:mm:ss`*. Esta hora está cerca de la hora real del evento en la página, pero puede ser diferente al indicador de hora del nombre del archivo. <br> **Sugerencia**: A diferencia del `hour=` marca de tiempo en el nombre del archivo, puede utilizar `EventTime` para agrupar los datos por tiempo. |

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre la Fuente de datos de clientes](../faq/faq-cdf.md)

