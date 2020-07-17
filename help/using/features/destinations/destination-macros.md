---
description: Describe las macros que se pueden agregar a una dirección URL de destino.
seo-description: Describe las macros que se pueden agregar a una dirección URL de destino.
seo-title: Macros de destino definidas
solution: Audience Manager
title: Macros de destino definidas
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 3%

---


# Macros de destino definidas {#destination-macros-defined}

Describe las macros que se pueden agregar a un destino [!DNL URL].

<!-- destination-macros.xml -->

Al crear un [!DNL URL] destino, puede insertar las siguientes macros en la [!DNL URL] cadena. Consulte con el socio de datos/destino la ubicación correcta de la macro dentro del destino [!DNL URL].

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
   <td colname="col2"> <p>Requerido. </p> <p>Define la ubicación del valor del segmento asignado en una dirección URL de destino. Generalmente es el ID <i></i>del segmento, pero también puede ser el código de integración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Inserta el ID de <span class="keyword"> Audience Manager</span> del usuario en la dirección URL de destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>La ID <i>del origen de</i> datos corresponde al identificador de un origen de datos que se pasa a la macro. </p> <p>Veamos cómo funciona esto en un ejemplo sencillo. En este caso, tenemos un socio <span class="keyword"> Audience Manager</span> con las siguientes ID y condiciones: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">ID de fuente de datos: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Un ID de cliente interno: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">ID declarado: El socio desea pasar estos valores como ID declarado <code> 1:CustomerABC</code>. </li> 
    </ul> <p>Para hacerlo con el <code>%dpid_<i>data source id</i>%</code>, el <span class="keyword"> socio Audience Manager</span> aplicaría este formato a la macro: </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>La macro se reemplazará <code> 1</code> por <code> CustomerABC</code>. </p> <p> 
     <draft-comment>
       Basado en AAM-22193 https://jira.corp.adobe.com/browse/AAM-22193 
     </draft-comment> </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>Indica si las regulaciones del RGPD se aplican al visitante o no. Utilice esta macro para incluir el consentimiento en segmentos enviados a destinos URL integrados con IAB. Consulte el complemento <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager para TCF</a> de IAB para obtener más información.</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>La cadena de consentimiento (incluida la ID del proveedor de IAB) recopilada cuando los visitantes proporcionan o niegan el consentimiento en el sitio. Utilice esta macro para incluir la cadena de consentimiento en segmentos enviados a destinos URL integrados con IAB. Reemplazar <code>XXXX</code> por el ID del socio de destino. Consulte el complemento <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager para TCF</a> de IAB para obtener más información. </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>Detecta el protocolo utilizado en la página web principal y lo inserta en la dirección URL de destino. Por ejemplo:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">si la página web es <b>https</b>://aam_client.com, esta macro se reemplazará por <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">si la página web es <b>http</b>://aam_client.com, esta macro se reemplazará por <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Inserta el ID de <span class="keyword"> Experience Cloud</span> en la dirección URL de destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>Inserta la región del servidor de recopilación de datos (DCS) <span class="wintitle"></span> en la dirección URL de destino. Para minimizar la latencia, cuando el visitante realiza una llamada HTTP al <span class="keyword"> Audience Manager</span>, se les redirige al centro de datos DCS <span class="wintitle"></span> más cercano. Esto se logra a través de DNS, que puede detectar la ubicación del visitante y dirigirlo al centro de datos apropiado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>Realiza una función de eliminación de caché insertando un número aleatorio en la dirección URL de destino. Esto evita que los navegadores proporcionen contenido en caché. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Inserta una marca de tiempo UNIX en la dirección URL de destino para evitar que los navegadores proporcionen contenido en caché. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Descarga de caché con macros de destino {#destination-cache-busting}

Las `%rnd%` y `%timestamp%` las macros insertan valores únicos en una [!DNL URL] cadena para evitar el almacenamiento en caché del explorador.

## Descarga de caché con `%rnd%` y `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

Los navegadores guardan (guardan) en la memoria el contenido solicitado con frecuencia. Cuando se carga una página, el contenido guardado se suministra desde la caché en lugar de desde un servidor remoto. Este proceso ayuda a mantener tiempos de descarga eficientes, ya que los datos sirven localmente en lugar de hacerlo desde otra ubicación. Sin embargo, como el almacenamiento en caché no requiere una llamada al servidor, puede distorsionar el sistema de informes reduciendo artificialmente el número de solicitudes únicas.

La eliminación de caché evita que los navegadores guarden y reutilicen el contenido. Esta técnica utiliza código que inserta un número o una marca de hora aleatorios en una cadena URL, lo que hace que parezca único para el explorador. Como resultado, cada `HTTP` llamada se cuenta como una solicitud separada al servidor. Forzar una nueva llamada al servidor para cada solicitud ayuda a mantener la precisión del sistema de informes y a reducir las discrepancias. [!DNL Audience Manager] proporciona dos macros para la eliminación de caché:

* `%rnd%`:: Inserta un número aleatorio en una dirección URL.
* `%timestamp%`:: Inserta la fecha y hora Unix en una dirección URL.

## Comparación `%rnd%` y `%timestamp%` {#compare-rnd-timestamp}

Ambas macros impiden el almacenamiento en caché, pero `%rnd%` pueden ser más eficientes. Por ejemplo, con `%timestamp%`, si varios usuarios vista una página simultáneamente, obtendrán el mismo valor de fecha y hora. Como resultado, el [!DNL URL] informe no es único y las llamadas múltiples se cuentan una sola vez. Sin embargo, `%rnd%` genera un valor numérico único para cada llamada (incluso cuando los usuarios ven la misma página simultáneamente). Esto significa que la [!DNL URL] cadena contiene valores diferentes y se cuenta como única.

>[!MORELIKETHIS]
>
>* [Macros de destino definidas](../../features/destinations/destination-macros.md#destination-macros-defined)