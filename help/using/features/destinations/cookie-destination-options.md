---
description: En Destination Builder, la sección Configuración contiene los campos Dominio de cookies y Destino de datos de Publish. Permiten crear reglas para determinar si un destino establece una cookie o la devuelve. Dominio de cookies y Datos de Publish Para trabajar de forma independiente entre sí y son opcionales. Puede crear un destino de cookie sin utilizar ninguno de ellos.
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

En [!UICONTROL Destination Builder], [!UICONTROL Configuration section] contiene los campos [!UICONTROL Cookie Domain] y [!UICONTROL Publish Data To]. Permiten crear reglas para determinar si un destino establece una cookie o la devuelve. [!UICONTROL Cookie Domain] y [!UICONTROL Publish Data To] trabajan de forma independiente entre sí y son opcionales. Puede crear un destino de cookie sin utilizar ninguno de ellos.

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
   <td colname="col2"> <p>El campo <span class="wintitle"> Dominio de cookies</span> acepta una cadena de texto simple que le permite establecer cookies en un dominio especificado o en todos los dominios. Al utilizar esta función: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Establezca solo un dominio para cada destino de cookie. No escriba varios dominios en el campo Dominio de cookies <span class="wintitle"></span>. Cree otro <span class="wintitle"> destino</span> en su lugar. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">No utilice caracteres comodín. </li> 
     </ul> </p> <p> Deje el campo Dominio de cookie <span class="wintitle"></span> en blanco para establecer una cookie en todos los dominios. Esta es la configuración predeterminada. </p> <p>Para establecer cookies en un dominio y subdominios específicos: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Escriba el nombre del dominio en el campo Dominio de cookie <span class="wintitle"></span>. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Inicie el nombre de dominio con un punto. Por ejemplo, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">El prefijo <code> https://www</code> no es obligatorio. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Ejemplo</b> </p> </td> 
   <td colname="col2"> <p>Como ejemplo sencillo, supongamos que tenemos un sitio ficticio llamado sports.com. Sports.com tiene dominios para el golf, el béisbol y el fútbol. Para establecer una cookie en todos los dominios deportivos, debe escribirla en el cuadro Dominio de cookies <span class="wintitle"></span>, tal como se muestra a continuación: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Esto indica al Audience Manager <span class="keyword"></span> que establezca una cookie en cualquier dominio que contenga el patrón <code><i>something</i></code>.sports.com. Consulte a continuación un conjunto de ejemplos más complejo. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Ejemplos de dominios de cookies complejos

Estos ejemplos muestran si [!DNL Audience Manager] configurará una cookie en función de cómo esté configurada la opción [!UICONTROL Cookie Domain].

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
   <td colname="col1"> <p> <b>deportes.com</b> </p> </td> 
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
   <td colname="col1"> <p> <b>béisbol.sports.com</b> </p> </td> 
   <td colname="col2"> Sí </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sí </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>deportes.golf.com</b> </p> </td> 
   <td colname="col2"> No </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sí </td> 
  </tr> 
 </tbody> 
</table>

## Datos De Publish Para {#publish-data-to}

La configuración de [!UICONTROL Publish Data To] devuelve una cookie si el dominio cumple los criterios establecidos por las opciones seleccionadas. Las opciones incluyen:

* **[!UICONTROL All of our domains]**: (Predeterminado) Devuelve un [!DNL cookie] para cualquier dominio.
* **[!UICONTROL Only the selected domains]**: devuelve una cookie solo para los dominios seleccionados en la lista de dominios.
* **[!UICONTROL All of our domains except the selected domains]**: impide que los dominios seleccionados reciban [!DNL cookie]. Todos los demás dominios pueden recibir un [!DNL cookie].

>[!MORELIKETHIS]
>
>* [Crear un destino de cookie](../../features/destinations/create-cookie-destination.md)
