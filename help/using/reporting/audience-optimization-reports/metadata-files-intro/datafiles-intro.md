---
description: Un archivo de datos contiene datos de impresión, clic o conversión. Si el formato es correcto, puede importar estos datos en Audience Manager y utilizarlos en los informes de Optimización de público y en los archivos de registro procesables. Dé formato a los archivos de datos según las especificaciones de esta sección.
seo-description: Un archivo de datos contiene datos de impresión, clic o conversión. Si el formato es correcto, puede importar estos datos en Audience Manager y utilizarlos en los informes de Optimización de público y en los archivos de registro procesables. Dé formato a los archivos de datos según las especificaciones de esta sección.
seo-title: Archivos de datos para informes de optimización de audiencia y archivos de registro procesables
solution: Audience Manager
title: Archivos de datos para informes de optimización de audiencia y archivos de registro procesables
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
translation-type: tm+mt
source-git-commit: 776aaad0c063a870ef804d166292228f83575f48

---


# Archivos de datos para informes de optimización de audiencia y archivos de registro procesables {#data-files-for-audience-optimization-reports}

Un archivo de datos contiene datos de impresión, clic o conversión. Si el formato es correcto, puede importar estos datos en Audience Manager para verlos en los informes [de optimización de](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) público y crear características mediante los datos mediante los archivos [de registro](/help/using/integration/media-data-integration/actionable-log-files.md)procesables. Dé formato a los archivos de datos según estas especificaciones en esta sección.

## Información general {#overview}

Un archivo de datos con nombre y formato adecuados le permite importar datos de impresión, clic o conversión en los informes [de optimización de](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)audiencias. Esto resulta útil cuando se trabaja con un socio que no está integrado con [!DNL Audience Manager] y desea trabajar con sus datos en ese grupo de informes. Este proceso requiere archivos independientes para los datos de impresión, clic y conversión. No mezcle estos eventos en un solo archivo.

Un archivo de datos debe ir acompañado de un archivo de metadatos. El contenido del archivo de metadatos coincide con la información del archivo de datos con etiquetas relacionadas legibles por el usuario en los menús del informe. Para obtener más información, consulte [Información general y asignaciones para archivos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)de metadatos.

## Convenciones de nomenclatura para archivos de datos {#naming-conventions}

La siguiente sintaxis define la estructura de un nombre de archivo de datos bien formado. Tenga en cuenta que la *cursiva* indica un marcador de posición de variable que cambia según el contenido del archivo.

**Sintaxis:** <pre><i>event type</i>_<i>yyyymmdd</i></code></pre>

En un nombre de archivo:

* El tipo de evento indica que el archivo contiene impresiones, clics o conversiones. Cree un archivo independiente para cada tipo de evento.
* Un subrayado separa el tipo de evento y una marca de fecha de año-mes.
* Antes de cargar, comprima los archivos con gzip y guárdelos con la extensión de `.gz` archivo.

Dados estos requisitos, asigne un nombre a los archivos de datos en función de su contenido de la siguiente manera:

* Datos de impresión: <pre>impressions_<i>yyyymmdd</i>.gz</code></pre>
* Haga clic en los datos: <pre>clicks_<i>yyyymmdd</i>.gz</code></pre>
* Datos de conversión: <pre>conversions_<i>yyyymmdd</i>.gz</code></pre>

## Formato de contenido para archivos de datos {#content-format}

La siguiente sintaxis define la estructura de contenido en un archivo de datos bien formado. Tenga en cuenta que la *cursiva* indica un marcador de posición de variable y se sustituye por una etiqueta en un archivo de datos real.

**Sintaxis:** <pre><i>etiqueta de encabezado 1</i> | etiqueta <i>de encabezado 2</i> ... etiqueta de <i>encabezado n</i> | <i>versión</i></code></pre>

En el contenido del archivo:

* Las etiquetas de encabezado deben aparecer en el orden indicado en la tabla siguiente. Las impresiones y los clics utilizan las mismas etiquetas. Los archivos de conversión contienen encabezados adicionales.
* Si no tiene datos para una columna en particular, rellene ese campo con un `-1`.

* Los archivos *deben* terminar con un número de versión. La versión actual es 1.1.
* Separe los encabezados y el contenido de los archivos con el carácter ASCII 001 no imprimible. Si no puede utilizar ASCII 001, separe los encabezados y los datos con un delimitador de tabulación. Dado que se trata de caracteres no imprimibles, el ejemplo de sintaxis anterior muestra una barra vertical `"|"` únicamente para fines de visualización.

**Etiquetas de campo**

La tabla siguiente enumera y describe los encabezados de columna del archivo de datos. Los encabezados distinguen entre mayúsculas y minúsculas y deben aparecer según lo ordenado en la tabla. Todos los tipos de datos son enteros (INT) a menos que se indique lo contrario.

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
   <td colname="col2"> <p>Una fecha y hora UTC para el evento de impresión, clic o conversión. Utilice el <code> yyyy-MM-dd HH:mm:ss</code> formato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>Su ID para un visitante del sitio, también conocido como ID <span class="term"></span> de usuario único del proveedor de datos o DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>El ID de fuente de datos o código de integración del anunciante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>ID de unidad de negocio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Id. de campaña </p> </td> 
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
   <td colname="col1"> <p>Id. de ubicación </p> </td> 
   <td colname="col2"> <p> ID de ubicación numérica desde el servidor de publicidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>ID de orden de inserción. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>ID táctica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical-ID </p> </td> 
   <td colname="col2"> <p>ID para una categoría o sector. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cantidad </p> </td> 
   <td colname="col2"> <p> Número de artículos vendidos en un evento de conversión. </p> <p> <i>Solo para archivos de datos de conversión.</i> </p> </td> 
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
   <td colname="col1"> <p>Event-Type </p> </td> 
   <td colname="col2"> <p>Tipo de conversión. Indica si una conversión coincide o no. Las opciones incluyen: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impresión </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Haga clic </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>:: No atribuido o desconocido </li> 
    </ul> <p> <i>Solo para archivos de datos de conversión.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versión </p> </td> 
   <td colname="col2"> <p>Número de versión requerido que aparece al final de cada fila en un archivo de datos de conversión, de impresión o de clic. La versión actual es 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Métodos de envío para archivos de datos {#delivery-methods}

Cargue los archivos de datos de impresión, clic o conversión en un directorio de Amazon S3 para su [!DNL Audience Manager] cuenta. Consulte esta sección para obtener información sobre rutas de entrega/directorio, tiempos de procesamiento de archivos y actualizaciones.

>[!IMPORTANT]
>
> Póngase en contacto con el consultor de Audience Manager o con el Servicio de atención al cliente para empezar y configurar un [!DNL Amazon S3] directorio para sus archivos de datos.

**Sintaxis y ejemplos de la ruta de entrega**

Los datos se almacenan en un espacio de nombres independiente para cada cliente en un [!DNL Amazon S3] directorio. La ruta del archivo sigue la sintaxis que se muestra a continuación. Note, *italics* indicates a variable placeholder. Otros elementos son constantes o claves y no cambian.

**Sintaxis:** <pre>.../log_ingestion/pid= <i>AAM ID<i>/dpid= <i>d_src</i>/logs/ tipo <i></i>de archivo_<i>yyyymmdd</i></code></pre>

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
   <td colname="col2"> <p>Este par clave-valor contiene el ID de cliente de <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Este par clave-valor contiene la ID de la fuente de datos que se pasa en una llamada de evento. Identifica la agencia de la que provienen los datos y los vincula a un archivo de metadatos compatible. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Un directorio de nivel superior para archivos de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Nombre de tipo de archivo que indica el tipo de datos que contiene y una marca de hora de entrega. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ruta de carga de muestra y nombre de archivo**

Al cargar un archivo, la ruta será similar a esta:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Tiempos y actualizaciones de procesamiento de archivos**

Los archivos de datos se procesan cuatro veces al día, a intervalos regulares.

Para actualizar los datos, envíe un archivo que contenga todas las impresiones, clics o conversiones de un día determinado. En este caso, un día es el período de 24 horas de una medianoche a otra. Se recomienda utilizar la hora UTC para definir el intervalo de días.

## Pasos siguientes {#next-steps}

Revise los requisitos para nombrar y crear archivos de metadatos. Para empezar, consulte [Información general y asignaciones para archivos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)de metadatos.
