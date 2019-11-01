---
description: Un archivo de metadatos vincula los ID numéricos con nombres que puede leer y comprender. Los informes Optimización de audiencias muestran nombres legibles en los distintos menús de opciones de informes.
seo-description: Un archivo de metadatos vincula los ID numéricos con nombres que puede leer y comprender. Los informes Optimización de audiencias muestran nombres legibles en los distintos menús de opciones de informes.
seo-title: Información general y asignaciones para archivos de metadatos
solution: Audience Manager
title: Información general y asignaciones para archivos de metadatos
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Información general y asignaciones para archivos de metadatos{#overview-and-mappings-for-metadata-files}

Un archivo de metadatos vincula los ID numéricos con nombres que puede leer y comprender. Los informes Optimización de audiencias muestran nombres legibles en los distintos menús de opciones de informes.

## Información general {#overview}

Una revisión de los metadatos y cómo se utilizan. Un archivo de metadatos debe ir acompañado de un archivo de datos. El contenido del archivo de metadatos coincide con la información del archivo de datos con etiquetas relacionadas legibles por el usuario en los menús del informe. Para obtener más información, consulte Archivos [de datos para informes](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)de optimización de audiencia.

### Los archivos de metadatos contienen datos sobre otros datos

Un archivo de metadatos contiene información sobre otros tipos de datos. Para ayudarle a comprender cómo funciona esto, vamos a revisar cómo [!DNL Audience Manager] recibe los datos.

Durante un evento de impresión o clic, [!DNL Audience Manager] recibe datos en una cadena URL conocida como llamada *de* evento.

La llamada al evento organiza la información en conjuntos de pares de clave-valor definidos. Los valores de un par clave-valor contienen datos numéricos. El archivo de metadatos contiene nombres y otra información legible que corresponde al ID en cada par clave-valor.

### ID de vínculos de metadatos a nombres legibles

El archivo de metadatos es necesario para asociar un ID numérico a un nombre legible. Por ejemplo, supongamos que una llamada de evento contiene un ID creativo en un par de valor clave como este: `d_creative:1234`. Sin un archivo de metadatos, este elemento creativo se mostraría como 1234 en un menú de opciones.

Sin embargo, un archivo de metadatos correctamente formateado puede enlazar este elemento creativo a un nombre real como "Anunciante creativo A", que es un nombre que puede leer y reconocer en un informe.

### Cuándo se necesita un archivo de metadatos

En primer lugar, se requiere un archivo de metadatos y todos los parámetros enumerados a continuación en una llamada de evento cuando se desea utilizar los informes [de optimización de](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)audiencia.

En segundo lugar, necesita un archivo de metadatos si va a enviar sus propios datos a [!DNL Audience Manager] o si desea ver los datos en los informes de otros proveedores con los que no estamos integrados. Por ejemplo, [!DNL Audience Manager] tiene una integración con el Administrador [de campañas (DCM) de](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) doble clic de Google. Debido a esta relación, [!DNL Audience Manager] puede asociar ID con nombres y descripciones utilizados por las opciones del informe. Sin una integración, aún podemos ingerir datos, pero las opciones del informe mostrarán ID numéricos en lugar de nombres descriptivos.

![](assets/metadata_menu.png)

## Asignaciones de archivos {#file-mappings}

En la tabla siguiente se muestran los pares clave-valor que contienen los datos utilizados por los [!UICONTROL Audience Optimization] informes. Si necesita utilizar un archivo de metadatos, contendrá información legible en lenguaje natural que corresponda a los valores de estos pares de clave-valor. Los valores de estas claves sólo aceptan enteros (tipo de datos INT). Note, *italics* indicates a variable placeholder. Otros elementos son constantes o claves y no cambian.

>[!IMPORTANT]
>
>Si utiliza los [!UICONTROL Audience Optimization] informes, *todos* estos valores se requieren en la llamada de evento.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción de informe </th> 
   <th colname="col2" class="entry"> Par clave-valor de metadatos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Anunciante </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>Constituye el ID de fuente de datos del anunciante o el código de integración proporcionado al crear una fuente de datos. Consulte <a href="../../../features/manage-datasources.md#create-data-source"> Creación de una fuente</a>de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Unidad de negocio (BU) </p> </td> 
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
   <td colname="col1"> <p>Orden de inserción (E/S) </p> </td> 
   <td colname="col2"> <p> <code>d_io = <i>insertion order ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plataforma </p> </td> 
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>Es el ID de fuente <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"></a> de datos de la plataforma que proporciona información de metadatos (por ejemplo, DFA, Atlas, GBM, MediaMath, etc.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Táctica </p> </td> 
   <td colname="col2"> <p> <code>d_tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical </p> </td> 
   <td colname="col2"> <p> <code>d_vert = <i>vertical ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cómo los ID de llamadas de evento definen los nombres de los archivos, el contenido y las rutas de entrega {#how-ids-shape-file-names}

Los ID pasados por estos pares clave-valor ayudan a crear el nombre del archivo de metadatos y su contenido. Las siguientes secciones e ilustraciones muestran cómo funciona. En estos ejemplos se crea un archivo que contiene el nombre de un elemento creativo de una campaña, pero se pueden usar otras combinaciones.

### Llamada al evento

En este ejemplo crearemos un archivo de metadatos que incluya nombres creativos en un [!UICONTROL Audience Optimization] informe. Para ello, debemos extraer los ID de fuentes de datos, campañas y elementos creativos de una llamada de evento.

![](assets/metadata_file_event.png)

### Nombre del archivo

El nombre del archivo se basa en los ID de creativo, campaña y fuente de datos. En este caso, compare las diferencias entre los datos clave-valor de una llamada de evento y cómo se utilizan en un nombre de archivo.

En un nombre de archivo:

* La clave de origen de datos cambia a `dpid` de `d_src`.

* Los ID de campaña y creativo representan una categoría en lugar de un identificador real.

![](assets/metadata_file_name.png)

Consulte Convenciones [de nomenclatura para archivos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)de metadatos.

### Contenido del archivo

En este ejemplo, el contenido del archivo refleja los ID de campaña y creativo pasados en la llamada de evento. El nuevo elemento aquí es un nombre legible. Una vez procesado, el nombre de este archivo aparecerá como una opción en el menú Creative de un [!UICONTROL Audience Optimization] informe.

![](assets/metadata_file_contents.png)

Consulte Formato [de contenido para archivos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md)de metadatos.

### Envío de archivos

Después de nombrar y agregar datos a un archivo, se lo envía a un directorio de almacenamiento de Amazon S3 proporcionado por [!DNL Audience Manager]. Consulte Métodos [de envío para archivos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md)de metadatos.

>[!MORELIKETHIS]
>
>* [Archivos de datos para informes de optimización de audiencia](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Captura de datos de clics de campaña mediante llamadas de píxel](../../../integration/media-data-integration/click-data-pixels.md)
>* [Capturación de los datos de impresión de campaña a través de Pixel Calls](../../../integration/media-data-integration/impression-data-pixels.md)

