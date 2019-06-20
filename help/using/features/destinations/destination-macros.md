---
description: Describe las macros que se pueden agregar a una dirección URL de destino.
seo-description: Describe las macros que se pueden agregar a una dirección URL de destino.
seo-title: Macros de destino definidas
solution: Audience Manager
title: Macros de destino definidas
uuid: 982 cab 05-8 a 3 f -4 f 96-b 4 d 0-291709712 ad 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Destination Macros Defined {#destination-macros-defined}

Describes the macros you can add to a destination [!DNL URL].

<!-- destination-macros.xml -->

When creating a [!DNL URL] destination, you can insert the following macros into the [!DNL URL] string. Check with your data/destination partner about proper macro placement within the destination [!DNL URL].

>[!NOTE]
>
>Las macros son opcionales a menos que se indique lo contrario. La letra en *cursiva* indica un marcador de posición de variable.

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Explicación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> %alias%</code> </p> </td> 
   <td colname="col2"> <p>Requerido. </p> <p>Define la ubicación del valor de segmento asignado en una dirección URL de destino. Usually this is the <i>Segment ID</i>, but could also be the integration code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Inserts the user's <span class="keyword"> Audience Manager</span> ID into the destination URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>% dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>The <i>data source id</i> corresponds to the identifier for a data source passed in to the macro. </p> <p>Veamos cómo funciona en un ejemplo sencillo. In this case, we have an <span class="keyword"> Audience Manager</span> partner with the following IDs and conditions: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">Data source ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">An internal customer ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">Declared ID: The partner wants to pass in these values as the declared ID <code> 1:CustomerABC</code>. </li> 
    </ul> <p>To do this with the <code>%dpid_<i>data source id</i>%</code>, the <span class="keyword"> Audience Manager</span> partner would format the macro like this: </p> 
    <ul class="simplelist"> 
     <li> <code> % dpid_ 1%</code> </li> 
    </ul> <p>The macro will replace <code> 1</code> with <code> CustomerABC</code>. </p> <p> 
     <draft-comment>
       Basado en AAM -22193 https://jira.corp.adobe.com/browse/AAM-22193 
     </draft-comment> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % http_ proto %</code> </p> </td> 
   <td colname="col2"> <p>Detecta el protocolo utilizado en la página Web principal e lo inserta en la dirección URL de destino. Por ejemplo: 
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">if the webpage is <b>https</b>://aam_client.com, this macro will be replaced with <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">if the webpage is <b>http</b>://aam_client.com, this macro will be replaced with <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % mcid %</code> </p> </td> 
   <td colname="col2"> <p>Inserts the <span class="keyword"> Experience Cloud</span> ID into the destination URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % región %</code> </p> </td> 
   <td colname="col2"> <p>Inserts the <span class="wintitle"> Data Collection Server (DCS)</span> region into the destination URL. In order to minimize latency, when the visitor makes an HTTP call to <span class="keyword"> Audience Manager</span>, they are being redirected to the closest <span class="wintitle"> DCS</span> datacenter. Esto se logra a través de DNS, que puede detectar la ubicación del visitante y dirigirlos al conjunto de datos adecuado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> % rnd %</code> </p> </td> 
   <td colname="col2"> <p>Realiza una función de eliminación de caché insertando un número aleatorio en la dirección URL de destino. Esto evita que los exploradores proporcionen contenido almacenado en caché. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Inserta una marca de tiempo UNIX en la dirección URL de destino para evitar que los navegadores proporcionen contenido almacenado en caché. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cache Busting with Destination Macros {#destination-cache-busting}

The `%rnd%` and `%timestamp%` macros insert unique values into a [!DNL URL] string to prevent browser caching.

## Cache Busting with `%rnd%` and `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

Exploradores caché (guardar) el contenido solicitado con frecuencia en la memoria. Cuando se carga una página, el contenido guardado sirve de la caché en lugar de hacerlo desde un servidor remoto. Este proceso ayuda a mantener tiempos de descarga eficientes, ya que los datos se proporcionan localmente en lugar de desde otra ubicación. Sin embargo, debido a que el procesamiento en caché no requiere una llamada al servidor, puede distorsionar los informes reduciendo de forma artificial el número de solicitudes únicas.

La eliminación de caché evita que los navegadores guarden y reutilicen contenido. Esta técnica utiliza código que inserta un número aleatorio o una marca de hora en una cadena URL, lo que hace que parezca único para el navegador. As a result, each `HTTP` call is counted as a separate request to the server. Forzar una nueva llamada al servidor para cada solicitud ayuda a mantener la precisión de los informes y reduce las discrepancias. [!DNL Audience Manager] proporciona dos macros para la eliminación de caché:

* `%rnd%`: Inserta un número aleatorio en una URL.
* `%timestamp%`: Inserta la fecha y hora Unix en una URL.

## Comparing `%rnd%` and `%timestamp%` {#compare-rnd-timestamp}

Both macros prevent caching, but `%rnd%` may be more efficient. For example, with `%timestamp%`, if several users view a page simultaneously they&#39;ll get the same date/time value. As a result, the [!DNL URL] is not unique and multiple calls are counted only once. However, `%rnd%` generates a unique numeric value for each call (even when users see the same page simultaneously). This means the [!DNL URL] string contains different values and is counted as unique.

>[!MORE_ LIKE_ THIS]
>
>* [Macros de destino definidas](../../features/destinations/destination-macros.md#destination-macros-defined)