---
description: Enumera las macros que puede utilizar para crear plantillas salientes. Estas incluyen macros de nombre de archivo, macros de encabezado y macros de contenido.
seo-description: Lists the macros you can use to create outbound templates. These include file name macros, header macros, and content macros.
seo-title: Outbound Template Macros
solution: Audience Manager
title: Macros de plantillas de salida
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
feature: Outbound Data Transfers
exl-id: 6988d0e5-7a99-4291-91d3-bcd3a15630fd
source-git-commit: d76505fda1ba448a1aaa3a756ef3bcf193a2718a
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 1%

---

# Macros de plantillas de salida {#outbound-template-macros}

Enumera las macros que puede utilizar para crear plantillas salientes. Estas incluyen macros de nombre de archivo, macros de encabezado y macros de contenido.

## Nombre de archivo y macros de encabezado de archivo {#file-name-header-macros}

En la tabla se enumeran y describen las macros que se pueden utilizar en el nombre de archivo y para definir los campos de encabezado. Para obtener ejemplos de código, vea [Ejemplos de macros de salida](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_SOH </code> </p> </td> 
   <td colname="col2"> <p>Un carácter ASCII no imprimible. Indica el inicio de una fila o una sección de contenido. También se puede utilizar para separar columnas de datos en un archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID del proveedor de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>ID de usuario ID de proveedor de datos clave. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NEW_LINE </code> </p> </td> 
   <td colname="col2"> <p> Permite la creación de encabezados de varias líneas para pedidos salientes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>ID de pedido/destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ALIAS </code> </p> </td> 
   <td colname="col2"> <p>Un alias para un ID de pedido/destino. </p> <p>El alias se establece en la interfaz de usuario de administración. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>Indica la división de los archivos salientes en varias partes. Reemplace la sección SPLITNUM del nombre del fichero por el número de pieza precedido por ceros, asegurándose de un mínimo de tres caracteres para la sección SPLITNUM.</p>
   <p>No es necesario que la macro SPLITNUM esté rodeada por caracteres &lt;&gt;.</p><p>Ejemplo: <code>&lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;SPLITNUM.csv</code>
<p>s3_123456_9999_full_1566906141001.csv</p> 
<p>s3_123456_9999_full_1566906141002.csv</p> 
<p>s3_123456_9999_full_1566906141003.csv</p> 
<p>Los tres últimos dígitos (001 002 003) de los ejemplos anteriores son los identificadores SPLITNUM.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Indica el tipo de sincronización e incluye: </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>: sincronización completa. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>: sincronización incremental. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indica el método de transferencia de datos e incluye: </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Utilizada como separador, esta macro inserta una tabulación entre los campos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Una marca de tiempo Unix, UTC y de 10 dígitos. </p> <p>También se le puede aplicar el formato <code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code> según las reglas de formato de fecha y hora de Java. </p> </td> 
  </tr>

</tbody> 
</table>

## Macros de contenido {#content-macros}

Macros utilizadas para dar formato al contenido de un archivo de datos. Para obtener ejemplos de código, vea [Ejemplos de macros de salida](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Inserta un carácter de cierre de llaves <code>&rbrace;</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Identificador De Usuario Único Del Proveedor De Datos </span>. </p> <p>Este es el ID del socio de datos al que envía los datos en un archivo saliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>Devuelve una lista que contiene varios ID de un socio de datos. Esto resulta útil si tiene una organización grande con varias subdivisiones u otros grupos organizativos con los que puede compartir datos. Esta macro devuelve una lista de los identificadores de esos grupos subordinados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID del proveedor de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>El resultado de esta macro asigna el ID del proveedor de datos (DPID) a los ID de usuario únicos relacionados (DPUUID). Esta macro debe tener una cadena de formato para controlar su resultado. El resultado de la muestra sería similar al siguiente: </p> <p> <code> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </code> </p> <p>La configuración <code> maxMappings </code> determina cuántas asignaciones desea que devuelva la macro. Cuando <code> maxMappings=0 </code>, esta macro devuelve todas las asignaciones para cada DPID especificado. Los datos se ordenan por marca de tiempo (más reciente primero) y devuelve los resultados con la marca de tiempo más grande primero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p>Esta combinación de macros crea una instrucción condicional que enumera los segmentos a los que pertenecen los usuarios y de los que se han eliminado. Devuelve una cadena vacía si no se cumplen ambas condiciones o si no hay datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> ID. </span> de Adobe Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Inserta un carácter de llave <code>&lbrace;</code> abierto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_OUT </code> </p> </td> 
   <td colname="col2"> <p>Obsoleta. No utilice. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>ID de pedido o destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Obsoleta. No utilice. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_VALUE </code> </p> </td> 
   <td colname="col2"> <p>Devuelve <code> 1 </code> como un valor estático codificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>ID de socio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>Un alias para un ID de pedido/destino. </p> <p>El alias se establece en la interfaz de usuario de administración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Devuelve una lista de los segmentos que se han eliminado, si los hay. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Devuelve una lista de segmentos de una lista. Acepta los siguientes argumentos opcionales: </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> segmentId </code>: ID de segmento. Obsoleta. Usar <code> sid </code>. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>: ID de segmento de cliente. Obsoleta. Usar <code> sid </code>. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>: ID de segmento </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>: devuelve <code> 5 </code>, un valor estático codificado que identifica los datos como datos de segmento. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: obsoleto. No utilice. </li>
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> lastUpdateTime </code>: una marca de tiempo Unix que indica la última vez que se actualizó el estado de pertenencia a un segmento. </li>
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD28"> <code> lastRealizationTime </code>: una marca de tiempo Unix que indica la última vez que se realizó un segmento. </li>
    </ul> <p>Coloque estas variables entre llaves después de la macro. Por ejemplo, este código separa los resultados con una barra vertical "|": <code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Devuelve <code> 1 </code> como un valor estático codificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Indica el tipo de sincronización e incluye: </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>: sincronización completa. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>: sincronización incremental. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indica el método de transferencia de datos e incluye: </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Utilizada como separador, esta macro inserta una tabulación entre los campos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Devuelve una lista de características. Acepta los siguientes argumentos opcionales: </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>: identifica los tipos de rasgos por identificador numérico. Devuelve: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> que identifica un rasgo de DPM (sin conexión, incorporado por un trabajo entrante). </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> que identifica un rasgo basado en reglas (en tiempo real, incorporado a través del DCS). </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> traitId </code>: ID de rasgo. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastRealized </code>: la última vez que se realizó el rasgo. Marca de tiempo Unix. </li> 
    </ul> <p>Coloque estas variables entre llaves después de la macro. Por ejemplo, este código separa los resultados con una barra vertical "|": <code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> ID de usuario </span> de Audience Manager. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Ejemplos de macros de salida](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)
