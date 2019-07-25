---
description: Puede solicitar un archivo .csv para un Informe superpuesto cuando ese informe alcance su límite de 1 millón de registros. Es posible que un informe haya alcanzado este límite cuando aparezca el mensaje "Error inesperado". Póngase en contacto con el Servicio de atención al cliente para solicitar un archivo. csv comprimido, que puede importar y trabajar con su propio sistema de bases de datos. Los archivos están disponibles para los informes superpuestos de segmento a segmento, segmento a rasgo y rasgo a rasgo.
seo-description: Puede solicitar un archivo .csv para un Informe superpuesto cuando ese informe alcance su límite de 1 millón de registros. Es posible que un informe haya alcanzado este límite cuando aparezca el mensaje "Error inesperado". Póngase en contacto con el Servicio de atención al cliente para solicitar un archivo. csv comprimido, que puede importar y trabajar con su propio sistema de bases de datos. Los archivos están disponibles para los informes superpuestos de segmento a segmento, segmento a rasgo y rasgo a rasgo.
seo-title: Archivos CSV para informes superpuestos
solution: Audience Manager
title: Archivos CSV para informes superpuestos
uuid: 047 e 440 e -00 c 5-4 d 06-a 809-51 d 776326 cd 6
translation-type: tm+mt
source-git-commit: d13b32999c5af4d20f33a92dfa805d7fe0babb2d

---


# Archivos CSV para informes superpuestos{#csv-files-for-overlap-reports}

Puede solicitar un archivo .csv para un Informe superpuesto cuando ese informe alcance su límite de 1 millón de registros. Es posible que un informe haya alcanzado este límite cuando aparezca el mensaje "Error inesperado". Póngase en contacto con el Servicio de atención al cliente para solicitar un archivo. csv comprimido, que puede importar y trabajar con su propio sistema de bases de datos. Los archivos están disponibles para los informes superpuestos de segmento a segmento, segmento a rasgo y rasgo a rasgo.

## File Name Metadata {#file-name-metadata}

En la siguiente lista de tablas se describen las convenciones de nomenclatura de archivos y las extensiones de archivo que se utilizan en un archivo superpuesto. csv. In the examples, *italics* indicates a variable placeholder.

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
   <td colname="col2"> <p>Overlap report files are gzip compressed and have a <code> .gz</code> file extension. You must add the <code> .csv</code> extension to the file after decompression. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre del archivo </p> </td> 
   <td colname="col2"> <p>Sintaxis del nombre de archivo: </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">Segment-to-segment files: <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">Segment-to-trait files: <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">Trait-to-trait files: <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
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
   <td colname="col2"> <p>Se incrementa el último dígito del nombre del archivo si un informe contiene varios archivos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ejemplos </p> </td> 
   <td colname="col2"> <p>Ejemplos de nombres de archivos para un solo informe: </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">Single, 7-day file: <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">Single, 30-day file: <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>Ejemplos de nombres de archivos para un informe con varios archivos: </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Contents {#file-contents}

En el archivo, los datos de cadena se encierran entre comillas dobles. Consulte los datos mck a continuación. Esto se ha truncado para la brevedad y se ajustará a la pantalla.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Segment-to-Segment Report Records {#segment-segment-records}

A data file for your [Segment-to-Segment Overlap Report](segment-segment-overlap-report.md) contains the following records.

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etiqueta </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ id 1</code> </p> </td> 
   <td colname="col2"> <p>ID del segmento que está comparando con el segmento de línea base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ name 1</code> </p> </td> 
   <td colname="col2"> <p>El nombre del segmento que está comparando con los segmentos de línea de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ id 2</code> </p> </td> 
   <td colname="col2"> <p>ID del segmento de base. El segmento de línea base es el segmento que desea comparar con otros segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ name 2</code> </p> </td> 
   <td colname="col2"> <p>El nombre del segmento de base que está comparando con otros segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Puede obtener informes para intervalos retrospectivos de 7 y 30 días. <code> rangeid</code> corresponde a los intervalos de tiempo que se muestran a continuación. </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>: 7 días </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>: 30 días </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Fecha de procesamiento de un informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ absolute backs 1</code> </p> </td> 
   <td colname="col2"> <p>Número de usuarios únicos en el segmento que está comparando con el segmento de línea base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ absolute backs 2</code> </p> </td> 
   <td colname="col2"> <p>Número de usuarios únicos en el segmento de línea base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> duplicate_ absolute</code> </p> </td> 
   <td colname="col2"> <p>Recuento total de la superposición de usuarios únicos entre el segmento de línea base y los demás segmentos seleccionados para la comparación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Superponer_ perc</code> </p> </td> 
   <td colname="col2"> <p>El porcentaje de superposición de usuarios únicos entre el segmento de línea base y los otros segmentos seleccionados para la comparación. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment-to-Trait Report Records {#segment-trait-records}

A data file for your [Segment-to-Trait Overlap Report](segment-trait-overlap-report.md) contains the following records.

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etiqueta </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> trait_ id</code> </p> </td> 
   <td colname="col2"> <p>ID de característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_ name</code> </p> </td> 
   <td colname="col2"> <p>Nombre de característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_ type</code> </p> </td> 
   <td colname="col2"> <p>ID del proveedor de datos. Los ID incluyen: </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> Personal</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> Terceros</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Nombre del proveedor de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Puede obtener informes para intervalos retrospectivos de 7 y 30 días. <code> rangeid</code> corresponde a los intervalos de tiempo que se muestran a continuación. </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>: 7 días </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>: 30 días </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Fecha de procesamiento de un informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ absolute</code> </p> </td> 
   <td colname="col2"> <p>Número de usuarios únicos en el segmento seleccionado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_ absolute</code> </p> </td> 
   <td colname="col2"> <p>Número de usuarios únicos en un rasgo. En el informe de interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> duplicate_ absolute</code> </p> </td> 
   <td colname="col2"> <p>El número de usuarios únicos compartidos entre los segmentos y las características seleccionados. En el informe de interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_ utases_ overlap_ perc</code> </p> </td> 
   <td colname="col2"> <p>% de usuarios únicos que se superponen entre el rasgo y el segmento. En el informe de interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ absolute backs_ overlap_ perc</code> </p> </td> 
   <td colname="col2"> <p>% de usuarios únicos que se superponen entre el segmento y el rasgo. En el informe de interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait-to-Trait Report Records {#trait-trait-records}

A data file for your [Trait-to-Trait Overlap Report](trait-trait-overlap-report.md) contains the following records.

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etiqueta </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> duplicate_ trait_ id</code> </p> </td> 
   <td colname="col2"> <p>El ID de la característica que está comparando con el rasgo de línea base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> duplicate_ trait_ name</code> </p> </td> 
   <td colname="col2"> <p>El nombre de la característica que está comparando con el rasgo de línea base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ id</code> </p> </td> 
   <td colname="col2"> <p>ID del rasgo base. El rasgo de línea base es la característica que desea comparar con otras características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ name</code> </p> </td> 
   <td colname="col2"> <p>El nombre de la característica de línea base que está comparando con otras características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_ type</code> </p> </td> 
   <td colname="col2"> <p>ID del proveedor de datos. Los ID incluyen: </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> Personal</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> Terceros</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Nombre del proveedor de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Puede obtener informes para intervalos retrospectivos de 7 y 30 días. <code> rangeid</code> corresponde a los intervalos de tiempo que se muestran a continuación. </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>: 7 días </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>: 30 días </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Fecha de procesamiento de un informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> duplicate_ trait_ absolute</code> </p> </td> 
   <td colname="col2"> <p>El número de usuarios únicos compartidos entre las características seleccionadas. En el informe de interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ únicos</code> </p> </td> 
   <td colname="col2"> <p>Número de usuarios únicos en un rasgo base. En el informe de interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> duplicate_ absolute</code> </p> </td> 
   <td colname="col2"> <p>El número de usuarios únicos compartidos entre las características seleccionadas. En el informe de interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> duplicate_ trait_ utases_ overlap_ perc</code> </p> </td> 
   <td colname="col2"> <p>% de usuarios únicos que se superponen entre las características seleccionadas. En el informe de interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ utases_ overlap_ perc</code> </p> </td> 
   <td colname="col2"> <p>% de usuarios únicos que se superponen entre las características seleccionadas. En el informe de interfaz de usuario, este número aparece en la ventana emergente cuando pasa el ratón por encima de un rasgo en los resultados del mapa de calor. </p> </td> 
  </tr> 
 </tbody> 
</table>
