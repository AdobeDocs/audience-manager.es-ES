---
description: Un archivo de datos contiene datos de impresión, clics o conversión. Cuando se le aplica el formato adecuado, puede importar estos datos en Audience Manager y utilizarlos en los informes de Audience Optimization y en los archivos de registro procesables. Dé formato a sus archivos de datos según las especificaciones de esta sección.
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and use it in the Audience Optimization reports and for Actionable Log Files. Format your data files according to the specifications in this section.
seo-title: Data Files for Audience Optimization Reports and Actionable Log Files
solution: Audience Manager
title: Archivos de datos para informes de Audience Optimization y archivos de registro procesables
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
source-git-commit: db90a6f1aaf85b10e31e93e316c257b7c3a904aa
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 1%

---

# Archivos de datos para informes de Audience Optimization y archivos de registro procesables {#data-files-for-audience-optimization-reports}

Un archivo de datos contiene datos de impresión, clics o conversión. Cuando tenga el formato correcto, puede importar estos datos en el Audience Manager para verlos en los [informes del Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) y crear características con los datos a través de [archivos de registro procesables](/help/using/integration/media-data-integration/actionable-log-files.md). Dé formato a los archivos de datos según las especificaciones de esta sección.

## Información general {#overview}

Un archivo de datos con nombre y formato adecuados le permite importar datos de impresión, clics o conversiones en [Informes de Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). Esto resulta útil cuando se trabaja con un socio que no está integrado con [!DNL Audience Manager] y se desea trabajar con sus datos en ese grupo de informes. Este proceso requiere archivos independientes para los datos de impresión, clics y conversión. No mezcle estos eventos en un solo archivo.

Un archivo de datos debe ir acompañado de un archivo de metadatos. El contenido del archivo de metadatos hace coincidir la información del archivo de datos con las etiquetas relacionadas legibles en lenguaje natural en los menús del informe. Para obtener más información, vea [Información general y asignaciones para archivos de metadatos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Convenciones de nomenclatura para archivos de datos {#naming-conventions}

La siguiente sintaxis define la estructura de un nombre de archivo de datos bien formado. Tenga en cuenta que *cursiva* indica un marcador de posición variable que cambia según el contenido del archivo.

**Sintaxis:** <pre><code><i>tipo de evento</i>_<i>aaaammdd</i></code></pre>

En un nombre de archivo:

* El tipo de evento indica que el archivo contiene impresiones, clics o conversiones. Cree un archivo independiente para cada tipo de evento.
* Un guion bajo separa el tipo de evento y una marca de tiempo de año-mes-fecha.
* Antes de cargar, comprima los archivos con gzip y guárdelos con la extensión de archivo `.gz`.

Dados estos requisitos, asigne un nombre a los archivos de datos en función de su contenido de esta manera:

* Datos de impresión: <pre><code>impresiones_<i>aaaammdd</i>.gz</code></pre>
* Datos de clics: <pre><code>clicks_<i>yyyymmdd</i>.gz</code></pre>
* Datos de conversión: <pre><code>conversiones_<i>aaaammdd</i>.gz</code></pre>

## Formato de contenido para archivos de datos {#content-format}

La siguiente sintaxis define la estructura de contenido en un archivo de datos bien formado. Tenga en cuenta que *cursiva* indica un marcador de posición de variable y se reemplaza con una etiqueta en un archivo de datos real.

**Sintaxis:** <pre><code><i>etiqueta de encabezado 1</i> | <i>etiqueta de encabezado 2</i>... <i>etiqueta de encabezado n</i> | <i>versión</i></code></pre>

En el contenido del archivo:

* Las etiquetas de encabezado deben aparecer en el orden indicado en la tabla siguiente. Las impresiones y los clics utilizan las mismas etiquetas. Los archivos de conversión contienen encabezados adicionales.
* Si no tiene datos para una columna en particular, rellene ese campo con un `-1`.

* Los archivos *deben* finalizar con un número de versión. La versión actual es 1.1.
* Separe los encabezados y el contenido del archivo con el carácter ASCII 001 no imprimible. Si no puede utilizar ASCII 001, separe los encabezados y los datos con un delimitador de tabulación. Como se trata de caracteres no imprimibles, el ejemplo de sintaxis anterior muestra una barra vertical `"|"` únicamente con fines de presentación.

**Etiquetas de campo**

En la tabla siguiente se enumeran y describen los encabezados de columna del archivo de datos. Los encabezados distinguen entre mayúsculas y minúsculas y deben aparecer según se han ordenado en la tabla. Todos los tipos de datos son enteros (INT) a menos que se indique lo contrario.

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etiqueta </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Marca de tiempo </p> </td> 
   <td colname="col2"> <p>Una fecha y hora UTC para el evento de impresión, clic o conversión. Usar el formato <code> yyyy-MM-dd HH:mm:ss</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>Su ID para un visitante del sitio, también conocido como ID de usuario único </span> o DPUUID del proveedor de datos <span class="term">. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID del anunciante </p> </td> 
   <td colname="col2"> <p>El ID de la fuente de datos o el código de integración de su anunciante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>ID de unidad de negocio. </p> </td> 
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
   <td colname="col1"> <p>Site-ID </p> </td> 
   <td colname="col2"> <p>ID del sitio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> ID de ubicación numérica del servidor de publicidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>ID de orden de inserción. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>ID táctico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical-ID </p> </td> 
   <td colname="col2"> <p>ID de un sector o categoría. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cantidad </p> </td> 
   <td colname="col2"> <p> El número de artículos vendidos en un evento de conversión. </p> <p> <i>Solo para archivos de datos de conversión.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ingresos </p> </td> 
   <td colname="col2"> <p>Importe de compra u otro importe de conversión. Tipo de datos: Flotante. </p> <p> <i>Solo para archivos de datos de conversión.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Other-Data </p> </td> 
   <td colname="col2"> <p>URL de la página de aterrizaje de conversión. Tipo de datos: String. </p> <p> <i>Solo para archivos de datos de conversión.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Event-Type </p> </td> 
   <td colname="col2"> <p>Tipo de conversión. Indica si una conversión coincide o no. Las opciones incluyen: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: impresión </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: clic </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: sin atribuir o desconocido </li> 
    </ul> <p> <i>Solo para archivos de datos de conversión.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versión </p> </td> 
   <td colname="col2"> <p>Un número de versión requerido que aparece al final de cada fila en un archivo de datos de impresión, clic o conversión. La versión actual es 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Métodos de envío para archivos de datos {#delivery-methods}

Cargue los archivos de datos de impresión, clics o conversión en un directorio de Amazon S3 para la cuenta de [!DNL Audience Manager]. Consulte esta sección para obtener información sobre las rutas de entrega/directorio, los tiempos de procesamiento de archivos y las actualizaciones.

>[!IMPORTANT]
>
> Póngase en contacto con el consultor del Audience Manager o con el Servicio de atención al cliente para empezar y configurar un directorio [!DNL Amazon S3] para los archivos de datos.

**Sintaxis de la ruta de envío y ejemplos**

Los datos se almacenan en un área de nombres independiente para cada cliente en un directorio [!DNL Amazon S3]. La ruta del archivo sigue la sintaxis que se muestra a continuación. Tenga en cuenta que *cursiva* indica un marcador de posición de variable. Otros elementos son constantes o claves y no cambian.

**Sintaxis:** <pre>AAM <code>.../log_ingestion/pid= <i>ID</i>/dpid= <i>d_src</i>/logs/ <i>tipo de archivo</i>_<i>aaaammdd</i></code></pre>

La siguiente tabla define cada uno de estos elementos en una ruta de envío de archivos.

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
   <td colname="col2"> <p>Este es el inicio de la ruta de almacenamiento del directorio. Recibirá la ruta de acceso completa cuando todo esté configurado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Este par clave-valor contiene su ID de cliente <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Este par clave-valor contiene el ID de fuente de datos pasado en una llamada de evento. Identifica la agencia de la que proceden los datos y los vincula a un archivo de metadatos de soporte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Un directorio de nivel superior para archivos de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Nombre de tipo de archivo que indica el tipo de datos que contiene y una marca de tiempo de envío. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ruta de carga de muestra y nombre de archivo**

Al cargar un archivo, la ruta será similar a la siguiente:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Actualizaciones y tiempos de procesamiento de archivos**

Los archivos de datos se procesan cuatro veces al día, a intervalos regulares.

Para actualizar los datos, envíe un archivo que contenga todas las impresiones, clics o conversiones de un día en particular. En este caso, un día es el periodo de 24 horas entre una medianoche y la siguiente. Como práctica recomendada, es posible que desee utilizar la hora UTC para definir el intervalo de día.

## Pasos siguientes {#next-steps}

Revise los requisitos para nombrar y crear archivos de metadatos. Para empezar, consulte [Información general y asignaciones para archivos de metadatos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
