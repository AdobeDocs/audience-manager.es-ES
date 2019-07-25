---
description: Un archivo de datos contiene impresión, clic o datos de conversión. Cuando se formatee correctamente, puede importar estos datos en Audience Manager y verlos en los informes de Optimización de audiencias. Dé formato a los archivos de datos según estas especificaciones en esta sección.
seo-description: Un archivo de datos contiene impresión, clic o datos de conversión. Cuando se formatee correctamente, puede importar estos datos en Audience Manager y verlos en los informes de Optimización de audiencias. Dé formato a los archivos de datos según estas especificaciones en esta sección.
seo-title: Archivos de datos para informes de optimización de audiencias
solution: Audience Manager
title: Archivos de datos para informes de optimización de audiencias
uuid: c 19 eb 0 c 7-47 c 1-4 cdf -8 a 6 c-cd 15 fe 04 c 379
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Files for Audience Optimization Reports{#data-files-for-audience-optimization-reports}

Un archivo de datos contiene impresión, clic o datos de conversión. Cuando se formatee correctamente, puede importar estos datos en Audience Manager y verlos en los informes de Optimización de audiencias. Dé formato a los archivos de datos según estas especificaciones en esta sección.

## Información general {#overview}

A properly named and formatted data file lets you import impression, click, or conversion data into the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). This is useful when working with a partner who is not integrated with [!DNL Audience Manager] and you want to work with their data in that report suite. Este proceso requiere archivos separados para impresión, clic y datos de conversión. No combine estos eventos en un solo archivo.

Un archivo de datos debe estar acompañado de un archivo de metadatos. El contenido del archivo de metadatos coincide con la información del archivo de datos a etiquetas relacionadas con humanos en los menús del informe. For more information, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Naming Conventions for Data Files {#naming-conventions}

La siguiente sintaxis define la estructura de un nombre de archivo de datos bien formado. Note, *italics* indicates a variable placeholder that changes depending on the file contents.

**Sintaxis:** <pre><code><i>event type</i>_<i>aaaammdd</i></code></pre>

En un nombre de archivo:

* El tipo de evento indica que el archivo contiene impresiones, clics o conversiones. Cree un archivo independiente para cada tipo de evento.
* Un guión bajo separa el tipo de evento y la marca de fecha y hora del mes.
* Before uploading, compress your files using gzip and save them with the `.gz` file extension.

Dados estos requisitos, asigne a los archivos de datos un nombre basado en su contenido de la siguiente manera:

* Datos de impresión: <pre><code>impresiones_<i>aaaammdd<i>.gz</code></pre>
* Haga clic en datos: <pre><code>clicks_<i>aaaammdd</i>.gz</code></pre>
* Datos de conversión: <pre><code>conversions_<i>aaaammdd</i>.gz</code></pre>

## Content Format for Data Files {#content-format}

La siguiente sintaxis define la estructura de contenido en el archivo de datos bien formado. Note, *italics* indicates a variable placeholder and is replaced with an label in an actual data file.

**Sintaxis:** <pre><code><i>etiqueta de encabezado 1</i> | <i>etiqueta de encabezado 2</i> … <i>etiqueta de encabezado n</i> | <i>version</i></code></pre>

En el contenido del archivo:

* Las etiquetas de encabezado deben aparecer en el orden, como se muestra en la siguiente tabla. Las impresiones y los clics utilizan las mismas etiquetas. Los archivos de conversión contienen encabezados adicionales.
* If you don't have data for a particular column, populate that field with a `NULL` object or `-1`.

* Files *must* end with a version number. La versión actual es 1.1.
* Separe los encabezados y los contenidos de archivos con el carácter ASCII 001 no imprimible. Si no puede utilizar ASCII 001, separe los encabezados y los datos con un delimitador de tabuladores. As these are non-printing characters, the syntax example above shows a pipe `"|"` for display purposes only.

**Etiquetas de campo**

La tabla siguiente enumera y describe los encabezados de columna para el archivo de datos. Los encabezados distinguen entre mayúsculas y minúsculas y deben aparecer como se ordenan en la tabla. Todos los tipos de datos son enteros (INT) a menos que se indique lo contrario.

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etiqueta </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Marca de hora </p> </td> 
   <td colname="col2"> <p>Una fecha y hora UTC para la impresión, el clic o el evento de conversión. Use the <code> yyyy-dd-mm hh:mm:ss</code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>Your ID for a site visitor, also known as the <span class="term"> data provider unique user ID</span> or DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anunciante-ID </p> </td> 
   <td colname="col2"> <p>El ID de fuente de datos o el código de integración del anunciante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>ID de unidad comercial. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign-ID </p> </td> 
   <td colname="col2"> <p>ID de campaña. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>ID del creativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID del sitio </p> </td> 
   <td colname="col2"> <p>ID del sitio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> ID de ubicación numérica del servidor de publicidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>ID de pedido de inserción. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>ID de táctica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID vertical </p> </td> 
   <td colname="col2"> <p>ID para un sector o categoría. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cantidad </p> </td> 
   <td colname="col2"> <p> Número de elementos vendidos en un evento de conversión. </p> <p> <i>Solo para archivos de datos de conversión.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ingresos </p> </td> 
   <td colname="col2"> <p>Compra u otra cantidad de conversión. Tipo de datos: Flotante. </p> <p> <i>Solo para archivos de datos de conversión.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Otros datos </p> </td> 
   <td colname="col2"> <p>Dirección URL de la página de aterrizaje de conversión. Tipo de datos: cadena. </p> <p> <i>Solo para archivos de datos de conversión.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tipo de evento </p> </td> 
   <td colname="col2"> <p>Tipo de conversión. Indica si una conversión coincide o no. Las opciones incluyen: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impresión </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Haga clic </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: No atribuido o desconocido </li> 
    </ul> <p> <i>Solo para archivos de datos de conversión.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versión </p> </td> 
   <td colname="col2"> <p>Un número de versión obligatorio que aparece al final de cada fila en un archivo de datos de impresión, clic o conversión. La versión actual es 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Delivery Methods for Data Files {#delivery-methods}

Upload your impression, click, or conversion data files to an Amazon S3 directory for your [!DNL Audience Manager] account. Consulte esta sección para obtener información sobre las rutas de envío y directorio, los tiempos de procesamiento de archivos y las actualizaciones.

**Sintaxis y ejemplos de ruta de entrega**

Los datos se almacenan en un espacio de nombres independiente para cada cliente en un directorio de Amazon S 3. La ruta de archivo sigue la sintaxis que se muestra a continuación. Note, *italics* indicates a variable placeholder. Otros elementos son constantes o claves y no cambian.

**Sintaxis:** <pre><code>…/log_ ingestion/pid = <i>AAM ID<i>/dpid = <i>d_ src</i>/logs/ <i>file type</i>_<i>aaaammdd</i></code></pre>

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
   <td colname="col2"> <p>Este par clave-valor contiene el ID de fuente de datos que se pasa en una llamada de evento. Identifica a la agencia desde la que provienen los datos y vincula esos datos a un archivo de metadatos compatible. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> registros</code> </p> </td> 
   <td colname="col2"> <p> Directorio de nivel superior para archivos de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>file type</i>_<i>yyyammdd</i></code> </p> </td> 
   <td colname="col2"> <p>Un nombre de tipo de archivo que indica qué tipo de datos contiene y una marca de hora de entrega. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ruta de carga de ejemplo y nombre de archivo**

Al cargar un archivo, la ruta tendrá un aspecto similar al siguiente:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Tiempos y actualizaciones de procesamiento de archivos**

Los archivos de datos se procesan cuatro veces al día, a intervalos regulares.

Para actualizar los datos, envíe un archivo que contenga todas las impresiones, clics o conversiones de un día concreto. En este caso, un día es el período de 24 horas de una medianoche al siguiente. Es recomendable utilizar la hora UTC para definir el intervalo de día.

## Pasos siguientes {#next-steps}

Revise los requisitos para nombrar y crear archivos de metadatos. To get started, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
