---
description: En el Generador de destino, la sección Configuración contiene los campos Dominio de cookies y Publish Datos para. Permiten crear reglas para determinar si un destino establece un cookie o devuelve un cookie. Dominio de cookies y datos Publish Deben funcionar de forma independiente y son opcionales. Puede crear un destino cookie sin usar ninguno de ellos.
seo-description: In Destination Builder, the Configuration section contains the Cookie Domain and Publish Data To fields. These let you create rules to determine if a destination sets a cookie or returns a cookie. Cookie Domain and Publish Data To work independently of each other and are optional. You can create a cookie destination without using either of them.
seo-title: Optional Settings for Cookie Destinations
solution: Audience Manager
title: Configuración opcional para destinos de cookies
feature: Destination Basics
exl-id: b44f386e-4d43-41c3-b8ce-88b83d5d83c2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 4%

---

# Configuración opcional para destinos de cookies {#optional-settings-cookies}

En [!UICONTROL Destination Builder], contiene [!UICONTROL Configuration section] los [!UICONTROL Cookie Domain] campos and [!UICONTROL Publish Data To] . Permiten crear reglas para determinar si un destino establece un cookie o devuelve un cookie. [!UICONTROL Cookie Domain] y [!UICONTROL Publish Data To] trabajan independientemente el uno del otro y son opcionales. Puede crear un destino cookie sin usar ninguno de ellos.

## Dominio de cookies: sintaxis y ejemplos {#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dominio de la cookie </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Sintaxis</b> </p> </td> 
   <td colname="col2"> <p>El <span class="wintitle"> campo Dominio</span> de cookies acepta una cadena de texto sencilla que le permite configurar cookies en uno o varios dominios específicos. Al utilizar esta función: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Establezca solo un dominio para cada cookie destino. No escriba varios dominios en el <span class="wintitle"> campo Dominio</span> de cookies. Crear otro <span class="wintitle"> destino</span> en su lugar. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">No utilice caracteres comodín. </li> 
     </ul> </p> <p> Deje el campo Dominio<span class="wintitle"> de </span> cookies en blanco para establecer un cookie en todos los dominios. Esta es la configuración predeterminada. </p> <p>Para configurar cookies en un dominio y subdominios específicos: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Escriba el nombre del dominio en el <span class="wintitle"> campo Dominio</span> de cookies. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Inicio el nombre de dominio con un punto. Por ejemplo, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">El <code> https://www</code> prefijo no es obligatorio. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Ejemplo</b> </p> </td> 
   <td colname="col2"> <p>Como un ejemplo simple, digamos que tenemos un sitio ficticio llamado sports.com. Sports.com tiene dominios para golf, béisbol y fútbol. Para establecer un cookie en todos los dominios deportivos, debe escribirlo en el <span class="wintitle"> cuadro Dominio</span> de cookies, como se muestra a continuación: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Esto Audience Manager<span class="keyword"> indica </span> que establezca un cookie en cualquier dominio que contenga el patrón <code><i>something</i></code>.sports.com. Vea a continuación un conjunto más complejo de ejemplos. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Ejemplos complejos de dominios de cookies

En estos ejemplos se indica si [!DNL Audience Manager] se establecerá una cookie en función de cómo esté configurada la [!UICONTROL Cookie Domain] opción.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sitio web </th> 
   <th colname="col2" class="entry">Dominio de cookies: .sports.com <p>Conjunto de cookies </p> </th> 
   <th colname="col3" class="entry">Dominio de cookies: .golf.sports.com <p>Conjunto de cookies </p> </th> 
   <th colname="col4" class="entry">Dominio de cookies: En blanco <p>Conjunto de cookies </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sports.com</b> </p> </td> 
   <td colname="col2"> Sí </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sí </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sports.com</b> </p> </td> 
   <td colname="col2"> Sí </td> 
   <td colname="col3"> Sí </td> 
   <td colname="col4"> Sí </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sports.com</b> </p> </td> 
   <td colname="col2"> Sí </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sí </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sports.golf.com</b> </p> </td> 
   <td colname="col2"> No </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sí </td> 
  </tr> 
 </tbody> 
</table>

## Publish datos a {#publish-data-to}

La [!UICONTROL Publish Data To] configuración devuelve un cookie si el dominio cumple los criterios establecidos por las opciones seleccionadas. Las opciones incluyen:

* **[!UICONTROL All of our domains]**: (Predeterminado) Devuelve a [!DNL cookie] para cualquier dominio.
* **[!UICONTROL Only the selected domains]**: devuelve un cookie solo para los dominios seleccionados en los dominios lista.
* **[!UICONTROL All of our domains except the selected domains]**: Evita que los dominios seleccionados reciban un [!DNL cookie]archivo . Todos los demás dominios pueden recibir un archivo [!DNL cookie].

>[!MORELIKETHIS]
>
>* [Crear destino de cookies](../../features/destinations/create-cookie-destination.md)
