---
description: Un archivo de datos contiene datos impresión, de clics o Conversión. Cuando se formatean correctamente, puede importar estos datos a Audience Manager y utilizarlos en los informes de Audience Optimization y para el Archivos de registro procesable. Formatee sus archivos de datos de acuerdo con las especificaciones de esta sección.
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and use it in the Audience Optimization reports and for Actionable Log Files. Format your data files according to the specifications in this section.
seo-title: Data Files for Audience Optimization Reports and Actionable Log Files
solution: Audience Manager
title: Archivos de datos para informes Audience Optimization y Archivos de registro procesables
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
source-git-commit: db90a6f1aaf85b10e31e93e316c257b7c3a904aa
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 1%

---

# Archivos de datos para informes Audience Optimization y Archivos de registro procesables {#data-files-for-audience-optimization-reports}

Un archivo de datos contiene datos impresión, de clics o Conversión. Cuando se formatean correctamente, puede importar estos datos a Audience Manager para vista en los informes[&#x200B; de Audience Optimization y crear características utilizando los datos a través &#x200B;](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)del [Archivos](/help/using/integration/media-data-integration/actionable-log-files.md) de registro procesable. Dé formato a los archivos de datos según las especificaciones de esta sección.

## Información general {#overview}

Un archivo de datos con el formato y el nombre correcto permite importar datos impresión, hacer clic o Conversión a los [informes](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) Audience Optimization. Esto resulta útil cuando se trabaja con una socio que no está integrada y [!DNL Audience Manager] se desea trabajar con sus datos de esa grupo de informes. Este proceso requiere archivos separados para impresión, clic y Conversión datos. No mezcle estos eventos en un solo archivo.

El archivo de datos debe ir acompañado de un archivo metadatos. El contenido del archivo de metadatos hace coincidir la información del archivo de datos con las etiquetas relacionadas legibles en lenguaje humano de los menús de informes. Para obtener más información, consulte [Información general y asignaciones para Archivos metadatos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Convenciones de nomenclatura para Archivos de datos {#naming-conventions}

La siguiente sintaxis define la estructura de un nombre de archivo de datos bien formado. Tenga en cuenta que *la* cursiva indica un marcador de posición de variable que cambia según el contenido del archivo.

**Sintaxis:** <pre><code><i>tipo de evento</i>_<i>aaaammdd</i></code></pre>

En un nombre de archivo:

* El tipo de evento indica que el archivo contiene impresiones, clics o conversiones. Crear un archivo separado para cada tipo de evento.
* Un guión bajo separa la tipo de evento y una marca de tiempo año-mes-fecha.
* Antes de cargar, comprima sus archivos usando gzip y guárdelos con la extensión de `.gz` archivo.

Dados estos requisitos, asigne un nombre a sus archivos de datos en función de su contenido gustar la siguiente manera:

* Datos de impresión: <pre><code>impressions_<i>aaaammdd</i>.gz</code></pre>
* Datos de clics: <pre><code>clicks_<i>aaaammdd</i>.gz</code></pre>
* Datos de conversión: <pre><code>conversions_<i>aaaammdd</i>.gz</code></pre>

## Formato de contenido para datos Archivos {#content-format}

La siguiente sintaxis define la estructura contenido en un archivo de datos bien formado. Tenga en cuenta que *la* cursiva indica un marcador de posición variable y se sustituye por una etiqueta en un archivo de datos real.

**Sintaxis:** <pre><code><i>Etiqueta de encabezado 1</i> | <i>etiqueta de encabezado 2</i> ... <i>Etiqueta de encabezado n</i> | <i>Versión</i></code></pre>

En el contenido del archivo:

* Las etiquetas de encabezado deben aparecer en el orden que se muestra en la tabla siguiente. Las impresiones y los clics utilizan las mismas etiquetas. Los archivos de conversión contienen encabezados adicionales.
* Si no tiene datos para una columna concreta, rellene ese campo con un `-1`archivo .

* *Archivos debe* finalizar con un número de versión. La versión actual es la 1.1.
* Separe los encabezados y contenidos de archivo con el carácter ASCII 001 de no impresión. Si no puede utilizar ASCII 001, separe los encabezados y los datos con un delimitador pestaña. Dado que se trata de caracteres de no impresión, el ejemplo de sintaxis anterior muestra una barra vertical `"|"` únicamente con fines de visualización.

**Etiquetas de campo**

La tabla siguiente enumera y describe los encabezados de columna del archivo de datos. Los encabezados distinguen mayúsculas de minúsculas y deben aparecer como están ordenados en la tabla. Todos los tipos de datos son enteros (INT) a menos que se indique lo contrario.

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etiqueta </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Stamp tiempo </p> </td> 
   <td colname="col2"> <p>Fecha y hora UTC para la evento, de clic o de impresión, clic o Conversión. Utilice el <code> yyyy-MM-dd HH:mm:ss</code> formato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de usuario </p> </td> 
   <td colname="col2"> <p>Su ID para una visitante del sitio, también conocida como ID de <span class="term"> usuario exclusivo del proveedor de datos o DPUUID</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID del anunciante </p> </td> 
   <td colname="col2"> <p>ID de fuente de datos o código de integración de su anunciante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>Empresa ID de la unidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID Campaign </p> </td> 
   <td colname="col2"> <p>Campaign ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID Creative </p> </td> 
   <td colname="col2"> <p>Creative ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID del sitio </p> </td> 
   <td colname="col2"> <p>ID del sitio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de colocación </p> </td> 
   <td colname="col2"> <p> ID de ubicación numérico del servidor de anuncios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inserción-Orden-ID </p> </td> 
   <td colname="col2"> <p>ID de pedido de inserción. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de táctica </p> </td> 
   <td colname="col2"> <p>ID de táctica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID vertical </p> </td> 
   <td colname="col2"> <p>ID para un sector o categoría. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cantidad </p> </td> 
   <td colname="col2"> <p> Número de elementos vendidos en un Conversión evento. </p> <p> <i>Solo para Conversión archivos de datos.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ingresos </p> </td> 
   <td colname="col2"> <p>Compra u otra cantidad Conversión. Tipo de datos: flotante. </p> <p> <i>Solo para Conversión archivos de datos.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Otros datos </p> </td> 
   <td colname="col2"> <p>URL del Conversión página de aterrizaje. Tipo de datos: cadena. </p> <p> <i>Solo para Conversión archivos de datos.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tipo de evento </p> </td> 
   <td colname="col2"> <p>Tipo de conversión. Indica si una Conversión coincide o no. Las opciones incluyen: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>:Impresión </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>:Clic </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Sin atribuir o desconocido </li> 
    </ul> <p> <i>Solo para Conversión archivos de datos.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versión </p> </td> 
   <td colname="col2"> <p>Número de versión requerido que aparece al final de cada fila de un archivo de datos de impresión, clic o Conversión. La versión actual es la 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Métodos de envío de datos Archivos {#delivery-methods}

Cargue sus archivos de datos de impresión, haga clic o Conversión en un directorio de Amazon S3 para su [!DNL Audience Manager] cuenta. Consulte esta sección para obtener información sobre rutas de directorio/envío, tiempos de procesamiento de archivos y actualizaciones.

>[!IMPORTANT]
>
> Póngase en contacto con su consultor Audience Manager o con el Servicio de atención al cliente para comenzar y configurar un [!DNL Amazon S3] directorio para sus archivos de datos.

**Sintaxis y ejemplos de la ruta de entrega**

Los datos se almacenan en un espacio de nombres separado para cada cliente en un [!DNL Amazon S3] directorio. La ruta del archivo sigue la sintaxis que se muestra a continuación. Tenga en cuenta que *la* cursiva indica un marcador de posición variable. Otros elementos son constantes o claves y no cambian.

**Sintaxis:** <pre><code>.../log_ingestion/pid= <i>AAM ID/</i>dpid= <i>d_src</i>/logs/ <i>tipo</i> de archivo_<i>yyyymmdd</i></code></pre>

La tabla siguiente define cada uno de estos elementos en una ruta de envío de archivo.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro Archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>Este es el inicio del directorio almacenamiento ruta. Recibirá la ruta completa cuando todo esté configurado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Este par clave-valor contiene su <span class="keyword"> Audience Manager</span> ID de cliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Este par clave-valor contiene el ID de fuente de datos transferido en una llamada de evento. Identifica la agencia de la que provienen los datos y vincula esos datos a un archivo de metadatos de apoyo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Un directorio de nivel superior para archivos de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Nombre de tipo de archivo que indica la clase de datos que contiene y una marca de tiempo envío. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ejemplo de ruta de carga y nombre Archivo**

Cuando cargar un archivo, la ruta de acceso tendrá un aspecto similar al siguiente:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Tiempos de procesamiento y actualizaciones de Archivo**

Los archivos de datos se procesan cuatro veces al día, a intervalos regulares.

Para actualizar los datos, envíe un archivo que contenga todas las impresiones, clics o conversiones de un día determinado. En este caso, un día es el período de 24 horas desde una medianoche hasta la siguiente. Como práctica recomendada, puede que desee utilizar la hora UTC para definir el intervalo de días.

## Pasos siguientes {#next-steps}

Revise los requisitos para nombrar y crear metadatos archivos. Para empezar, consulte [Información general y asignaciones para Archivos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) de metadatos.
