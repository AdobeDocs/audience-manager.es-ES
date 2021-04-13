---
description: Un archivo de datos contiene datos de impresión, clics o conversión. Cuando tenga el formato adecuado, puede importar estos datos en el Audience Manager y utilizarlos en los informes del Audience Optimization y en los archivos de registro procesables. Dé formato a los archivos de datos según las especificaciones de esta sección.
seo-description: Un archivo de datos contiene datos de impresión, clics o conversión. Cuando tenga el formato adecuado, puede importar estos datos en el Audience Manager y utilizarlos en los informes del Audience Optimization y en los archivos de registro procesables. Dé formato a los archivos de datos según las especificaciones de esta sección.
seo-title: Archivos de datos para informes de optimización de Audiencia y archivos de registro procesables
solution: Audience Manager
title: Archivos de datos para informes de optimización de Audiencia y archivos de registro procesables
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Archivos de registro
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1044'
ht-degree: 5%

---

# Archivos de datos para informes de optimización de Audiencia y archivos de registro procesables {#data-files-for-audience-optimization-reports}

Un archivo de datos contiene datos de impresión, clics o conversión. Cuando tenga el formato adecuado, puede importar estos datos en el Audience Manager para verlos en los [Informes del Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) y crear rasgos utilizando los datos mediante [Archivos de registro procesables](/help/using/integration/media-data-integration/actionable-log-files.md). Dé formato a los archivos de datos según estas especificaciones en esta sección.

## Información general {#overview}

Un archivo de datos con un nombre y formato adecuados le permite importar datos de impresión, clics o conversiones en los [Informes de Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). Esto resulta útil cuando se trabaja con un socio que no está integrado con [!DNL Audience Manager] y desea trabajar con sus datos en ese grupo de informes. Este proceso requiere archivos independientes para los datos de impresión, clics y conversión. No mezcle estos eventos en un solo archivo.

Un archivo de datos debe ir acompañado de un archivo de metadatos. El contenido del archivo de metadatos coincide con la información del archivo de datos en etiquetas relacionadas y legibles en lenguaje natural de los menús de informes. Para obtener más información, consulte [Información general y asignaciones para archivos de metadatos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Convenciones de nomenclatura para archivos de datos {#naming-conventions}

La siguiente sintaxis define la estructura de un nombre de archivo de datos bien formado. Tenga en cuenta que *la cursiva* indica un marcador de posición de variable que cambia según el contenido del archivo.

**Sintaxis:** <pre><i>tipo</i> de evento_<i>aaaammdd</i></code></pre>

En un nombre de archivo:

* El tipo de evento indica que el archivo contiene impresiones, clics o conversiones. Cree un archivo independiente para cada tipo de evento.
* Un guión bajo separa el tipo de evento y una marca de fecha y mes de año.
* Antes de cargar, comprima sus archivos con gzip y guárdelos con la extensión de archivo `.gz` .

Dados estos requisitos, nombre los archivos de datos en función de su contenido de esta manera:

* Datos de impresión: <pre>impresiones_<i>aaammdd</i>.gz</code></pre>
* Datos de clic: <pre>clicks_<i>aaammdd</i>.gz</code></pre>
* Datos de conversión: <pre>conversiones_<i>aaammdd</i>.gz</code></pre>

## Formato de contenido para archivos de datos {#content-format}

La siguiente sintaxis define la estructura de contenido en un archivo de datos bien formado. Tenga en cuenta que *la cursiva* indica un marcador de posición de variable y se reemplaza con una etiqueta en un archivo de datos real.

**Sintaxis:** <pre><i>etiqueta de encabezado 1</i> | etiqueta de  <i>encabezado 2</i> ... etiqueta de  <i>encabezado n</i> |  <i>versión</i></code></pre>

En el contenido del archivo:

* Las etiquetas de encabezado deben aparecer en el orden indicado en la tabla siguiente. Las impresiones y los clics utilizan las mismas etiquetas. Los archivos de conversión contienen encabezados adicionales.
* Si no tiene datos para una columna en particular, rellene ese campo con un `-1`.

* Los archivos *deben* terminar con un número de versión. La versión actual es 1.1.
* Separe los encabezados y el contenido del archivo con el carácter ASCII 001 no imprimible. Si no puede utilizar ASCII 001, separe los encabezados y datos con un delimitador de tabulación. Como estos son caracteres no imprimibles, el ejemplo de sintaxis anterior muestra una barra vertical `"|"` únicamente con fines de visualización.

**Etiquetas de campos**

En la tabla siguiente se enumeran y describen los encabezados de columna del archivo de datos. Los encabezados distinguen entre mayúsculas y minúsculas y deben aparecer según lo dispuesto en la tabla. Todos los tipos de datos son números enteros (INT) a menos que se indique lo contrario.

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
   <td colname="col2"> <p>Fecha y hora UTC para la impresión, el clic o el evento de conversión. Utilice el formato <code> yyyy-MM-dd HH:mm:ss</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>Su ID para un visitante del sitio, también conocido como ID de usuario único del proveedor de datos <span class="term"> o DPUUID.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID del anunciante </p> </td> 
   <td colname="col2"> <p>El ID de la fuente de datos o el código de integración para el anunciante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>ID de unidad de negocio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de campaña </p> </td> 
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
   <td colname="col2"> <p> ID de colocación numérica del servidor de publicidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>ID del orden de inserción. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>ID táctico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical-ID </p> </td> 
   <td colname="col2"> <p>ID para una categoría o vertical del sector. </p> </td> 
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
   <td colname="col2"> <p>URL de la página de aterrizaje de conversión. Tipo de datos: cadena. </p> <p> <i>Solo para archivos de datos de conversión.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Event-Type </p> </td> 
   <td colname="col2"> <p>Tipo de conversión. Indica si una conversión coincide o no. Las opciones incluyen: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impresión </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Haga clic </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: No atribuido o desconocido </li> 
    </ul> <p> <i>Solo para archivos de datos de conversión.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versión </p> </td> 
   <td colname="col2"> <p>Número de versión requerido que aparece al final de cada fila en un archivo de datos de impresión, clic o conversión. La versión actual es 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Métodos de envío para archivos de datos {#delivery-methods}

Cargue los archivos de datos de impresión, clic o conversión en un directorio Amazon S3 de su cuenta [!DNL Audience Manager]. Consulte esta sección para obtener información sobre las rutas de entrega/directorio, los tiempos de procesamiento de los archivos y las actualizaciones.

>[!IMPORTANT]
>
> Póngase en contacto con su asesor de Audience Manager o con el Servicio de atención al cliente para empezar y configurar un directorio [!DNL Amazon S3] para sus archivos de datos.

**Sintaxis y ejemplos de la ruta de entrega**

Los datos se almacenan en un área de nombres independiente para cada cliente en un directorio [!DNL Amazon S3]. La ruta del archivo sigue la sintaxis que se muestra a continuación. Tenga en cuenta que la *cursiva* indica un marcador de posición de variable. Otros elementos son constantes o claves y no cambian.

**Sintaxis:** <pre>.../log_ingestion/pid= <i>ID de AAM<i>/dpid= <i>d_src</i>/logs/ <i>tipo de archivo</i>_<i>aaammdd</i></code></pre>

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
   <td colname="col2"> <p>Este es el inicio de la ruta de almacenamiento del directorio. Recibirá la ruta completa cuando todo esté configurado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Este par clave-valor contiene su ID de cliente <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Este par clave-valor contiene el ID de fuente de datos transferido en una llamada de evento. Identifica la agencia de la que proceden los datos y los vincula a un archivo de metadatos compatible. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Un directorio de nivel superior para archivos de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Nombre de tipo de archivo que indica qué tipo de datos contiene y una marca de tiempo de entrega. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ruta de carga de muestra y nombre de archivo**

Al cargar un archivo, la ruta será similar a esta:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Tiempos y actualizaciones de procesamiento de archivos**

Los archivos de datos se procesan cuatro veces al día, a intervalos regulares.

Para actualizar los datos, envíe un archivo que contenga todas las impresiones, clics o conversiones de un día concreto. En este caso, un día es el período de 24 horas desde una medianoche hasta la siguiente. Como práctica recomendada, es posible que desee utilizar la hora UTC para definir el intervalo de días.

## Pasos siguientes {#next-steps}

Revise los requisitos para nombrar y crear archivos de metadatos. Para empezar, consulte [Información general y asignaciones para archivos de metadatos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
