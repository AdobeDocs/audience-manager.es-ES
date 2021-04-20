---
description: Puede solicitar un archivo .csv para un Informe superpuesto cuando ese informe alcance su límite de 1 millón de registros. Es posible que un informe haya alcanzado este límite cuando aparece el mensaje "Se ha producido un error inesperado". Póngase en contacto con el Servicio de atención al cliente para solicitar un archivo .csv comprimido, que puede importar y usar en su propio sistema de bases de datos. Los archivos están disponibles para informes de segmento a segmento, segmento a rasgo y superposición de rasgo a rasgo.
seo-description: Puede solicitar un archivo .csv para un Informe superpuesto cuando ese informe alcance su límite de 1 millón de registros. Es posible que un informe haya alcanzado este límite cuando aparece el mensaje "Se ha producido un error inesperado". Póngase en contacto con el Servicio de atención al cliente para solicitar un archivo .csv comprimido, que puede importar y usar en su propio sistema de bases de datos. Los archivos están disponibles para informes de segmento a segmento, segmento a rasgo y superposición de rasgo a rasgo.
seo-title: Archivos CSV para informes superpuestos
solution: Audience Manager
title: Archivos CSV para informes superpuestos
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
feature: Overlap Reports
exl-id: 759c39cb-64ec-47dd-a3a4-027408aa6b5e
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 9%

---

# Archivos CSV para informes superpuestos{#csv-files-for-overlap-reports}

Puede solicitar un archivo .csv para un Informe superpuesto cuando ese informe alcance su límite de 1 millón de registros. Es posible que un informe haya alcanzado este límite cuando aparece el mensaje &quot;Se ha producido un error inesperado&quot;. Póngase en contacto con el Servicio de atención al cliente para solicitar un archivo .csv comprimido, que puede importar y usar en su propio sistema de bases de datos. Los archivos están disponibles para informes de segmento a segmento, segmento a rasgo y superposición de rasgo a rasgo.

## Metadatos de nombre de archivo {#file-name-metadata}

En la tabla siguiente se describen las convenciones de nomenclatura de archivos y las extensiones de archivo que se utilizan en un archivo .csv superpuesto. En los ejemplos, la *cursiva* indica un marcador de posición para una variable.

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento Metadatos </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Archivo Extensión </p> </td> 
   <td colname="col2"> <p>Los archivos de informe de superposición se comprimen con gzip y tienen una extensión de archivo <code> .gz</code>. Debe añadir la extensión <code> .csv</code> al archivo después de la descompresión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre del archivo </p> </td> 
   <td colname="col2"> <p>Sintaxis del nombre del archivo: </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">Archivos de segmento a segmento: <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">Archivos de segmento a rasgo: <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">Archivos entre rasgos: <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervalo de fechas </p> </td> 
   <td colname="col2"> <p>El intervalo de fechas de un informe es un ID de 5 dígitos que incluye: </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 70000</code> para un informe de 7 días. </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code> para un informe de 30 días. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Varios archivos </p> </td> 
   <td colname="col2"> <p>Incrementamos el último dígito del nombre del archivo si un informe contiene varios archivos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ejemplos </p> </td> 
   <td colname="col2"> <p>Ejemplos de nombres de archivo para un solo informe: </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">Archivo único de 7 días: <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">Archivo único de 30 días: <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>Ejemplos de nombres de archivo para un informe con varios archivos: </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Contenido del archivo {#file-contents}

En el archivo, los datos de cadena se incluyen entre comillas dobles. Consulte los datos de prueba a continuación. Esto se ha truncado para que sea más breve y se ajuste a la pantalla.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Registros de informes de segmento a segmento {#segment-segment-records}

Un archivo de datos para su [Informe de solapamiento entre segmentos](segment-segment-overlap-report.md) contiene los siguientes registros.

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etiqueta </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id1</code> </p> </td> 
   <td colname="col2"> <p>ID del segmento que está comparando con el segmento de línea de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name1</code> </p> </td> 
   <td colname="col2"> <p>Nombre del segmento que está comparando con los segmentos de línea de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id2</code> </p> </td> 
   <td colname="col2"> <p>El ID del segmento de línea de base. El segmento de línea de base es el segmento que desea comparar con otros segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name2</code> </p> </td> 
   <td colname="col2"> <p>Nombre del segmento de línea de base que está comparando con otros segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Puede obtener informes para intervalos retrospectivos de 7 y 30 días. El <code> rangeid</code> corresponde a los intervalos de tiempo que se muestran a continuación. </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>: 7 días </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>: 30 días </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>La fecha de procesamiento de un informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques1</code> </p> </td> 
   <td colname="col2"> <p>Número de usuarios únicos en el segmento que está comparando con el segmento de línea de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques2</code> </p> </td> 
   <td colname="col2"> <p>Número de usuarios únicos en el segmento de línea de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Recuento total de la superposición de usuarios únicos entre el segmento de línea de base y los demás segmentos seleccionados para la comparación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>La superposición de % de usuarios únicos entre el segmento de línea de base y los demás segmentos seleccionados para la comparación. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Registros de informes de segmento a característica {#segment-trait-records}

Un archivo de datos para su [Informe de solapamiento entre segmento y característica](segment-trait-overlap-report.md) contiene los siguientes registros.

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etiqueta </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> trait_id</code> </p> </td> 
   <td colname="col2"> <p>ID de rasgo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_name</code> </p> </td> 
   <td colname="col2"> <p>Nombre del rasgo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>El ID del proveedor de datos. Los ID incluyen: </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 1st Party</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Nombre del proveedor de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Puede obtener informes para intervalos retrospectivos de 7 y 30 días. El <code> rangeid</code> corresponde a los intervalos de tiempo que se muestran a continuación. </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>: 7 días </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>: 30 días </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>La fecha de procesamiento de un informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques</code> </p> </td> 
   <td colname="col2"> <p>El número de usuarios únicos en el segmento seleccionado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Número de usuarios únicos en una característica. En el informe Interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Número de usuarios únicos compartidos entre los segmentos y las características seleccionados. En el informe Interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% de usuarios únicos que se superponen entre el rasgo y el segmento. En el informe Interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% de usuarios únicos que se superponen entre el segmento y la característica. En el informe Interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Registros de informes de características {#trait-trait-records}

Un archivo de datos para su [Informe de solapamiento entre rasgos](trait-trait-overlap-report.md) contiene los siguientes registros.

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etiqueta </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_id</code> </p> </td> 
   <td colname="col2"> <p>El ID del rasgo que se compara con el rasgo de línea de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_name</code> </p> </td> 
   <td colname="col2"> <p>El nombre del rasgo que se compara con el rasgo de línea base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_id</code> </p> </td> 
   <td colname="col2"> <p>El ID de su rasgo de línea de base. El rasgo de línea de base es el rasgo que desea comparar con otros rasgos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_name</code> </p> </td> 
   <td colname="col2"> <p>Nombre del rasgo de línea base que se compara con otros rasgos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>El ID del proveedor de datos. Los ID incluyen: </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 1st Party</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Nombre del proveedor de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Puede obtener informes para intervalos retrospectivos de 7 y 30 días. El <code> rangeid</code> corresponde a los intervalos de tiempo que se muestran a continuación. </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>: 7 días </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>: 30 días </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>La fecha de procesamiento de un informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Número de usuarios únicos compartidos entre los rasgos seleccionados. En el informe Interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Número de usuarios únicos en un rasgo base. En el informe Interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Número de usuarios únicos compartidos entre los rasgos seleccionados. En el informe Interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% de usuarios únicos que se superponen entre los rasgos seleccionados. En el informe Interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% de usuarios únicos que se superponen entre los rasgos seleccionados. En el informe Interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
 </tbody> 
</table>
