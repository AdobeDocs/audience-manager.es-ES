---
description: En Destination Builder, la sección Configuración contiene los campos Dominio de cookies y Publicar datos en. Permiten crear reglas para determinar si un destino establece una cookie o la devuelve. Cookie Domain y Publish Data Para trabajar de forma independiente entre sí y son opcionales. Puede crear un destino de cookie sin utilizar ninguno de ellos.
seo-description: In Destination Builder, the Configuration section contains the Cookie Domain and Publish Data To fields. These let you create rules to determine if a destination sets a cookie or returns a cookie. Cookie Domain and Publish Data To work independently of each other and are optional. You can create a cookie destination without using either of them.
seo-title: Optional Settings for Cookie Destinations
solution: Audience Manager
title: Configuración opcional para destinos de cookies
feature: Destination Basics
exl-id: b44f386e-4d43-41c3-b8ce-88b83d5d83c2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 7%

---

# Configuración opcional para destinos de cookies {#optional-settings-cookies}

Entrada [!UICONTROL Destination Builder], el [!UICONTROL Configuration section] contiene el [!UICONTROL Cookie Domain] y [!UICONTROL Publish Data To] campos. Permiten crear reglas para determinar si un destino establece una cookie o la devuelve. [!UICONTROL Cookie Domain] y [!UICONTROL Publish Data To] trabajan de forma independiente entre sí y son opcionales. Puede crear un destino de cookie sin utilizar ninguno de ellos.

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
   <td colname="col2"> <p>El <span class="wintitle"> Dominio de cookie</span> Este campo acepta una cadena de texto simple que permite establecer cookies en un dominio especificado o en todos los dominios. Al utilizar esta función: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Establezca solo un dominio para cada destino de cookie. No escriba varios dominios en <span class="wintitle"> Dominio de cookie</span> field. Crear otro <span class="wintitle"> Destino</span> en su lugar. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">No utilice caracteres comodín. </li> 
     </ul> </p> <p> Deje el <span class="wintitle"> Dominio de cookie</span> para establecer una cookie en todos los dominios. Esta es la configuración predeterminada. </p> <p>Para establecer cookies en un dominio y subdominios específicos: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Escriba el nombre del dominio en la <span class="wintitle"> Dominio de cookie</span> field. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Inicie el nombre de dominio con un punto. Por ejemplo, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">El <code> https://www</code> El prefijo no es obligatorio. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Ejemplo</b> </p> </td> 
   <td colname="col2"> <p>Como ejemplo sencillo, supongamos que tenemos un sitio ficticio llamado sports.com. Sports.com tiene dominios para el golf, el béisbol y el fútbol. Para establecer una cookie en todos los dominios deportivos, debe escribirla en la variable <span class="wintitle"> Dominio de cookie</span> como se muestra a continuación: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Esto indica <span class="keyword"> Audience Manager</span> para establecer una cookie en cualquier dominio que contenga el patrón <code><i>something</i></code>.sports.com. Consulte a continuación un conjunto de ejemplos más complejo. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Ejemplos de dominios de cookies complejos

Estos ejemplos muestran si [!DNL Audience Manager] establecerá una cookie en función de cómo [!UICONTROL Cookie Domain] está configurada.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sitio web </th> 
   <th colname="col2" class="entry">Dominio de cookies: .sports.com <p>Conjunto de cookies </p> </th> 
   <th colname="col3" class="entry">Dominio de cookies: .golf.sports.com <p>Conjunto de cookies </p> </th> 
   <th colname="col4" class="entry">Dominio de cookie: en blanco <p>Conjunto de cookies </p> </th> 
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

## Publicar datos en {#publish-data-to}

El [!UICONTROL Publish Data To] La configuración de devuelve una cookie si el dominio cumple los criterios establecidos por las opciones seleccionadas. Las opciones incluyen:

* **[!UICONTROL All of our domains]**: (Predeterminado) Devuelve un [!DNL cookie] para cualquier dominio.
* **[!UICONTROL Only the selected domains]**: Devuelve una cookie solo para los dominios seleccionados en la lista de dominios.
* **[!UICONTROL All of our domains except the selected domains]**: evita que los dominios seleccionados reciban una [!DNL cookie]. Todos los demás dominios pueden recibir una [!DNL cookie].

>[!MORELIKETHIS]
>
>* [Crear un destino de cookie](../../features/destinations/create-cookie-destination.md)

