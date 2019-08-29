---
description: Enumera las macros que puede utilizar para crear plantillas salientes. Estas incluyen macros de nombre de archivo, macros de encabezado y macros de contenido.
seo-description: Enumera las macros que puede utilizar para crear plantillas salientes. Estas incluyen macros de nombre de archivo, macros de encabezado y macros de contenido.
seo-title: Macros de plantillas de salida
solution: Audience Manager
title: Macros de plantillas de salida
uuid: dec 082 d 3-306 b -4 ff 5-afb 2-418 bd 543 d 8 d 0
translation-type: tm+mt
source-git-commit: 11663e962254bbcab90105d72af003b2a7056744

---


# Macros de plantillas de salida {#outbound-template-macros}

Enumera las macros que puede utilizar para crear plantillas salientes. Estas incluyen macros de nombre de archivo, macros de encabezado y macros de contenido.

## Nombre de archivo y macros de encabezado de archivo {#file-name-header-macros}

En la tabla se enumeran y describen las macros que se pueden utilizar en el nombre del archivo y para definir los campos del encabezado. Para obtener ejemplos de código, consulte [Ejemplos de macro de salida](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_ SOH </code> </p> </td> 
   <td colname="col2"> <p>Carácter ASCII no imprimible. Indica el inicio de una fila o una sección de contenido. También se puede utilizar para separar las columnas de datos en un archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID del proveedor de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_ DPID </code> </p> </td> 
   <td colname="col2"> <p>ID del proveedor de datos clave de ID de usuario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>ID de pedido/destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ ALIAS </code> </p> </td> 
   <td colname="col2"> <p>Alias para un ID de pedido/destino. </p> <p>El alias se establece en la interfaz de usuario de administración. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>Indica la división de los archivos salientes en varias partes. Sustituya la sección SPLITNUM en el nombre del archivo por el número de pieza precedido por ceros, garantizando un mínimo de tres caracteres para la sección SPLITNUM.</p>
   <p>La macro SPLITNUM no necesita estar encerrada por &lt; &gt; caracteres.</p><p>Ejemplo: <code>&lt; SYNC_ TYPE &gt;_ &lt; ORDER_ ID &gt;_ &lt; DPID &gt;_ &lt; SYNC_ MODE &gt;_ &lt; TIMESTAMP &gt; SPLITNUM. csv</code>
<p>s 3_ 123456_ 9999_ full_ 1566906141001. csv</p> 
<p>s 3_ 123456_ 9999_ full_ 1566906141002. csv</p> 
<p>s 3_ 123456_ 9999_ full_ 1566906141003. csv</p> 
<p>Los últimos tres dígitos (001.002.003) en los ejemplos anteriores son los identificadores SPLITNUM.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ MODE </code> </p> </td> 
   <td colname="col2"> <p>Indica el tipo de sincronización e incluye: </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>: Sincronización completa. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>: Incrementa la sincronización. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indica el método de transferencia de datos e incluye: </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s 3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Esta macro, utilizada como separador, inserta una ficha entre campos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Marca de tiempo de 10 dígitos, UTC y Unix. </p> <p>También se puede formatear como <code> &lt; TIMESTAMP; format = "aaaammddhhmmss" &gt; </code> después de las reglas de formato de fecha y hora de Java. </p> </td> 
  </tr>

</tbody> 
</table>

## Macros de contenido {#content-macros}

Macros utilizadas para dar formato al contenido de un archivo de datos. Para obtener ejemplos de código, consulte [Ejemplos de macro de salida](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_ CURLY_ BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Inserta un carácter de llave. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Identificador de usuario único del proveedor de datos </span>. </p> <p>Es el ID del socio de datos al que se envían los datos en un archivo saliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Devuelve una lista que contiene varios ID para un socio de datos. Esto resulta útil si tiene una gran organización con varias subdivisiones u otros grupos organizativos con los que puede compartir datos. Esta macro devuelve una lista de los ID de esos grupos subordinados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID del proveedor de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>El resultado de esta macro asigna el ID de proveedor de datos (DPID) a ID de usuarios únicos relacionados (DPUUID). Esta macro debe tener una cadena de formato para controlar su salida. El resultado de la muestra tendría un aspecto similar al siguiente: </p> <p> <code> " dpids = dpid 1, dpid 2,… dpid n | maxmappings = n | format = json " </code> </p> <p>La configuración <code> maxmappings </code> determina cuántas asignaciones desea que devuelvan la macro. Cuando <code> maxmappings = 0 </code>, esta macro devuelve todas las asignaciones de cada DPID especificado. Los datos se ordenan por marca de tiempo (primero más reciente) y devuelven primero los resultados con la marca de fecha y hora más grande. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if (SEGMENT_ LIST &amp; &amp; REMOVED_ SEGMENT_ LIST) endif </code> </p> </td> 
   <td colname="col2"> <p>Esta combinación de macros crea una afirmación condicional que enumera los segmentos a los que pertenecen los usuarios y que se han eliminado de. Devuelve una cadena vacía si no se cumplen ambas condiciones o si no hay datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud </span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_ CURLY_ BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Inserta un corchete abierto {carácter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_ OUT </code> </p> </td> 
   <td colname="col2"> <p>Obsoleta. No utilice. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>ID o ID de destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ ATTRIBUTE_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Obsoleta. No utilice. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ ATTRIBUTE_ VALUE </code> </p> </td> 
   <td colname="col2"> <p>Devuelve <code> 1 </code> como valor estático y estático. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>ID del socio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>Alias para un ID de pedido/destino. </p> <p>El alias se establece en la interfaz de usuario de administración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_ SEGMENT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Devuelve una lista de segmentos que se han eliminado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Devuelve una lista de segmentos en una lista. Acepta los siguientes argumentos opcionales: </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> Segmentid </code>: ID de segmento. Obsoleta. Utilice <code> sid </code>. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>: ID del segmento del cliente. Obsoleta. Utilice <code> sid </code>. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>: ID de segmento </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>: Devuelve <code> 5 </code>, un valor estático y estático que identifica los datos como datos de segmento. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: Obsoleto. No utilice. </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> Lastupdatetime </code>: Marca de hora Unix que indica la última vez que se ha realizado un segmento. </li> 
    </ul> <p>Coloque estas variables entre llaves después de la macro. Por ejemplo, este código separa los resultados con una barra vertical "|" character: <code> &lt; SEGMENT_ LIST: {seg|&lt; seg. type &gt;, &lt; seg. sid &gt;}; separator = "," &gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Devuelve <code> 1 </code>, como un valor estático y estático. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ MODE </code> </p> </td> 
   <td colname="col2"> <p>Indica el tipo de sincronización e incluye: </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>: Sincronización completa. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>: Incrementa la sincronización. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indica el método de transferencia de datos e incluye: </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s 3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Esta macro, utilizada como separador, inserta una ficha entre campos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Devuelve una lista de características. Acepta los siguientes argumentos opcionales: </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>: Identifica los tipos de características por ID numérico. Devuelve: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> que identifica un rasgo DPM (sin conexión, onquecado por un trabajo entrante). </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> , que identifica un rasgo basado en reglas (en tiempo real, incorporado a través del DCS). </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> Traitid </code>: ID de característica. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> Lastended </code>: La última vez que se realizó la característica. Marca de hora Unix. </li> 
    </ul> <p>Coloque estas variables entre llaves después de la macro. Por ejemplo, este código separa los resultados con una barra vertical "|" character: <code> &lt; TRAIT_ LIST: {trait|&lt; trait. Id &gt;, &lt; trait. lastdone &gt;}; separator = "," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> ID </span> de usuario de Audience Manager. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Ejemplos de macros de salida](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

