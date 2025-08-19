---
description: Un archivo de metadatos vincula los ID numéricos con nombres que puede leer y comprender. Los informes de Audience Optimization muestran nombres legibles en los distintos menús de opciones de informes.
seo-description: A metadata file links numeric IDs with names you can read and understand. The Audience Optimization reports display readable names in the various report options menus.
seo-title: Overview and Mappings for Metadata Files
solution: Audience Manager
title: Información general y asignaciones para archivos de metadatos
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: Log Files
exl-id: 8c59ab80-f04a-42df-891e-a187ecd0219f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 2%

---

# Información general y asignaciones para archivos de metadatos{#overview-and-mappings-for-metadata-files}

Un archivo de metadatos vincula los ID numéricos con nombres que puede leer y comprender. Los informes de Audience Optimization muestran nombres legibles en los distintos menús de opciones de informes.

## Información general {#overview}

Una revisión de los metadatos y cómo se utilizan. Un archivo de metadatos debe ir acompañado de un archivo de datos. El contenido del archivo de metadatos hace coincidir la información del archivo de datos con las etiquetas relacionadas legibles en lenguaje natural en los menús del informe. Para obtener más información, vea [Archivos de datos para informes de Audience Optimization y archivos de registro procesables](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### Los Archivos De Metadatos Contienen Datos Sobre Otros Datos

Un archivo de metadatos contiene información sobre otros tipos de datos. Para ayudarle a comprender cómo funciona, vamos a revisar cómo [!DNL Audience Manager] recibe los datos.

Durante un evento de impresión o clic, [!DNL Audience Manager] recibe datos en una cadena URL conocida como *llamada de evento*.

La llamada de evento organiza la información en conjuntos de pares clave-valor definidos. Los valores de un par clave-valor contienen datos numéricos. El archivo de metadatos contiene nombres y otra información legible correspondiente al ID en cada par clave-valor.

### Los metadatos vinculan los ID a nombres legibles

El archivo de metadatos es necesario para asociar un ID numérico a un nombre legible. Por ejemplo, supongamos que una llamada de evento contiene un ID creativo en un par clave-valor como el siguiente: `d_creative:1234`. Sin un archivo de metadatos, este elemento creativo aparecería como 1234 en un menú de opciones.

Sin embargo, un archivo de metadatos con el formato correcto puede vincular este elemento creativo con un nombre real como &quot;Anunciante Creative A&quot;, que es un nombre que se puede leer y reconocer en un informe.

### ¿Cuándo se necesita un archivo de metadatos?

En primer lugar, se requiere un archivo de metadatos, y todos los parámetros que se enumeran a continuación, en una llamada de evento cuando desee usar los [informes de Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

Segundo, necesita un archivo de metadatos si está enviando sus propios datos a [!DNL Audience Manager] o si desea ver datos en los informes de otros proveedores con los que no estamos integrados. Por ejemplo, [!DNL Audience Manager] tiene una integración con el [Administrador de campañas](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM) de Google que hace doble clic. Debido a esta relación, [!DNL Audience Manager] puede asociar identificadores con nombres y descripciones usados por las opciones del informe. Sin una integración, aún podemos introducir datos, pero las opciones del informe mostrarán ID numéricos en lugar de nombres descriptivos.

![imagen de menú de metadatos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## Asignaciones de archivos {#file-mappings}

En la tabla siguiente se enumeran los pares de clave-valor que contienen datos utilizados por los informes [!UICONTROL Audience Optimization]. Si necesita utilizar un archivo de metadatos, contendría información legible en lenguaje natural que corresponde a los valores de estos pares clave-valor. Los valores de estas claves solo aceptan números enteros (tipo de datos INT). Tenga en cuenta que *cursiva* indica un marcador de posición de variable. Otros elementos son constantes o claves y no cambian.

>[!IMPORTANT]
>
>Si usa los informes de [!UICONTROL Audience Optimization], se requieren *todos* de estos valores en la llamada de evento.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción de informe </th> 
   <th colname="col2" class="entry"> Pares de clave-valor de metadatos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Anunciante </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>Es el ID de fuente de datos del anunciante o el código de integración que se proporciona al crear una fuente de datos. Ver <a href="../../../features/manage-datasources.md#create-data-source"> Crear un Source de datos</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Unidad de Negocio (BU) </p> </td> 
   <td colname="col2"> <p> <code>d_bu = <i>business unit ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign </p> </td> 
   <td colname="col2"> <p> <code>d_campaign = <i>campaign ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative </p> </td> 
   <td colname="col2"> <p> <code>d_creative = <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>Acepta dos pares clave-valor diferentes: </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_exchange = <i>ID for the exchange that served the ad</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_site = <i>ID for the site an ad served on</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Orden de inserción (IO) </p> </td> 
   <td colname="col2"> <p> <code>d_io = <i>insertion order ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plataforma </p> </td> 
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>Este es el ID <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> de la fuente de datos </a> de la plataforma que proporciona información de metadatos (por ejemplo, DFA, Atlas, GBM, MediaMath, etc.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Táctico </p> </td> 
   <td colname="col2"> <p> <code>d_tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical </p> </td> 
   <td colname="col2"> <p> <code>d_vert = <i>vertical ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Identificadores de llamadas de evento: nombres de archivos de formas, contenido y rutas de envío {#how-ids-shape-file-names}

Los ID pasados por estos pares clave-valor ayudan a crear el nombre del archivo de metadatos y su contenido. Las siguientes secciones e ilustraciones muestran cómo funciona esto. Estos ejemplos generan un archivo que contiene el nombre de un creativo en una campaña, pero otras combinaciones son posibles.

### Llamada de evento

En este ejemplo crearemos un archivo de metadatos que incluya nombres creativos en un informe de [!UICONTROL Audience Optimization]. Para ello, es necesario extraer los ID creativos, de campaña y de fuente de datos de una llamada de evento.

![imagen de llamada de evento](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### Nombre del archivo

El nombre del archivo se basa en los ID de creativo, de campaña y de fuente de datos. En este caso, compare aquí las diferencias entre los datos clave-valor de una llamada de evento y cómo se utilizan en un nombre de archivo.

En un nombre de archivo:

* La clave del origen de datos cambia a `dpid` desde `d_src`.

* Los ID de creativo y de campaña representan una categoría, no un identificador real.

![cómo se crea un nombre de archivo](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

Consulte [Convenciones de nomenclatura para archivos de metadatos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Contenido de archivo

En este ejemplo, el contenido del archivo refleja los ID de creativo y de campaña pasados en la llamada de evento. El nuevo elemento es un nombre legible. Una vez procesado, el nombre de este archivo aparecerá como una opción en el menú Creative de un informe [!UICONTROL Audience Optimization].

![contenido de un archivo de metadatos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

Consulte [Formato de contenido para archivos de metadatos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Entrega de archivos

Después de asignar un nombre y agregar datos a un archivo, los envía a un directorio de almacenamiento de Amazon S3 proporcionado por [!DNL Audience Manager]. Consulte [Métodos de envío para archivos de metadatos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORELIKETHIS]
>
>* [Archivos de datos para informes de Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Captura de los datos de campaña por clic a través de Pixel Calls](../../../integration/media-data-integration/click-data-pixels.md)
>* [Captura de los datos de impresión de campaña a través de Pixel Calls](../../../integration/media-data-integration/impression-data-pixels.md)
