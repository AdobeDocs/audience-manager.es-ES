---
description: En el Generador de destino, la sección Configuración contiene los campos Dominio de cookie y Publicar datos en. Permiten crear reglas para determinar si un destino configura una cookie o devuelve una cookie. Dominio de la cookie y Publicar datos para trabajar de forma independiente y son opcionales. Puede crear un destino de cookie sin utilizar ninguno de ellos.
seo-description: En el Generador de destino, la sección Configuración contiene los campos Dominio de cookie y Publicar datos en. Permiten crear reglas para determinar si un destino configura una cookie o devuelve una cookie. Dominio de la cookie y Publicar datos para trabajar de forma independiente y son opcionales. Puede crear un destino de cookie sin utilizar ninguno de ellos.
seo-title: Configuración opcional para destinos de cookie
solution: Audience Manager
title: Configuración opcional para destinos de cookie
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Configuración opcional para destinos de cookie {#optional-settings-cookies}

En [!UICONTROL Destination Builder], [!UICONTROL Configuration section] la contiene los campos [!UICONTROL Cookie Domain] y los [!UICONTROL Publish Data To] campos. Permiten crear reglas para determinar si un destino configura una cookie o devuelve una cookie. [!UICONTROL Cookie Domain] y [!UICONTROL Publish Data To] funcionan de forma independiente y son opcionales. Puede crear un destino de cookie sin utilizar ninguno de ellos.

## Dominio de la cookie: Sintaxis y ejemplos {#cookie-domain-syntax}

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
   <td colname="col2"> <p>El campo <span class="wintitle"> Dominio</span> de cookie acepta una cadena de texto simple que permite establecer cookies en un dominio específico o en todos los dominios. Al utilizar esta función: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Establezca sólo un dominio para cada destino de cookie. No escriba varios dominios en el campo <span class="wintitle"> Dominio</span> de cookie. Cree otro <span class="wintitle"> destino en</span> su lugar. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">No utilice caracteres comodín. </li> 
     </ul> </p> <p> Deje en blanco <span class="wintitle"> el campo Dominio</span> de la cookie para establecer una cookie en todos los dominios. Ésta es la configuración predeterminada. </p> <p>Para configurar cookies en un dominio y subdominio específicos: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Escriba el nombre del dominio en el campo <span class="wintitle"> Dominio</span> de cookie. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Inicie el nombre de dominio con un período. Por ejemplo <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Ejemplo</b> </p> </td> 
   <td colname="col2"> <p>Como ejemplo simple, supongamos que tenemos un sitio ficticio llamado sports. com. Sports.com tiene dominios para golf, béisbol y fútbol. Para configurar una cookie en todos los dominios de deportes, debe escribirla en el cuadro Dominio <span class="wintitle"> de cookie, como</span> se muestra a continuación: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Esto indica <span class="keyword"> a Audience Manager</span> que establezca una cookie en cualquier dominio que contenga el patrón <code><i>algo</i></code>. sports. com. Consulte a continuación un conjunto de ejemplos más complejo. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Ejemplos de dominios de cookies complejas

Estos ejemplos muestran si [!DNL Audience Manager] configurará una cookie según cómo se configure la [!UICONTROL Cookie Domain] opción.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sitio Web </th> 
   <th colname="col2" class="entry">Dominio de la cookie: .sports.com <p>Conjunto de cookies </p> </th> 
   <th colname="col3" class="entry">Dominio de la cookie: .golf.sports.com <p>Conjunto de cookies </p> </th> 
   <th colname="col4" class="entry">Dominio de la cookie: En blanco <p>Conjunto de cookies </p> </th> 
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

[!UICONTROL Publish Data To] La configuración devuelve una cookie si el dominio cumple los criterios establecidos por las opciones seleccionadas. Las opciones incluyen:

* **[!UICONTROL All of our domains]**: (Predeterminado) Devuelve un [!DNL cookie] para cualquier dominio.
* **[!UICONTROL Only the selected domains]**: Devuelve una cookie solo para los dominios seleccionados en la lista de dominios.
* **[!UICONTROL All of our domains except the selected domains]**: Impide que los dominios seleccionados reciban una [!DNL cookie]. Todos los demás dominios pueden recibir [!DNL cookie]un.

>[!MORE_ LIKE_ THIS]
>
>* [Crear un destino de cookie](../../features/destinations/create-cookie-destination.md)