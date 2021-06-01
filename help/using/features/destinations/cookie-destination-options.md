---
description: En el Generador de destinos, la sección Configuración contiene los campos Dominio de cookies y Publicar datos en . Permiten crear reglas para determinar si un destino establece una cookie o devuelve una cookie. Dominio de cookies y Publicar datos Para trabajar de forma independiente entre sí y son opcionales. Puede crear un destino de cookie sin usar ninguno de ellos.
seo-description: En el Generador de destinos, la sección Configuración contiene los campos Dominio de cookies y Publicar datos en . Permiten crear reglas para determinar si un destino establece una cookie o devuelve una cookie. Dominio de cookies y Publicar datos Para trabajar de forma independiente entre sí y son opcionales. Puede crear un destino de cookie sin usar ninguno de ellos.
seo-title: Configuración opcional para destinos de cookies
solution: Audience Manager
title: Configuración opcional para destinos de cookies
feature: Conceptos básicos de destino
exl-id: b44f386e-4d43-41c3-b8ce-88b83d5d83c2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 7%

---

# Configuración opcional para destinos de cookies {#optional-settings-cookies}

En [!UICONTROL Destination Builder], el [!UICONTROL Configuration section] contiene los campos [!UICONTROL Cookie Domain] y [!UICONTROL Publish Data To]. Permiten crear reglas para determinar si un destino establece una cookie o devuelve una cookie. [!UICONTROL Cookie Domain] y  [!UICONTROL Publish Data To] trabajan de forma independiente entre sí y son opcionales. Puede crear un destino de cookie sin usar ninguno de ellos.

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
   <td colname="col2"> <p>El campo <span class="wintitle"> Dominio de cookies</span> acepta una cadena de texto simple que permite establecer cookies en un dominio específico o en todos los dominios. Al utilizar esta función: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Establezca solo un dominio para cada destino de cookie. No escriba varios dominios en el campo <span class="wintitle"> Dominio de cookies</span>. Cree otro <span class="wintitle"> destino</span> en su lugar. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">No utilice caracteres comodín. </li> 
     </ul> </p> <p> Deje el campo <span class="wintitle"> Dominio de cookies</span> en blanco para establecer una cookie en todos los dominios. Esta es la configuración predeterminada. </p> <p>Para configurar cookies en un dominio y subdominios específicos: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Escriba el nombre del dominio en el campo <span class="wintitle"> Dominio de cookies</span>. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Inicie el nombre de dominio con un punto. Por ejemplo, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">El prefijo <code> https://www</code> no es obligatorio. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Ejemplo</b> </p> </td> 
   <td colname="col2"> <p>Como ejemplo simple, digamos que tenemos un sitio ficticio llamado deportes.com. Sports.com tiene dominios para golf, béisbol y fútbol. Para establecer una cookie en todos los dominios deportivos, debe escribirla en el cuadro <span class="wintitle"> Dominio de cookies</span> como se muestra a continuación: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Esto indica al <span class="keyword"> Audience Manager</span> que configure una cookie en cualquier dominio que contenga el patrón <code><i>something</i></code>.sport.com. Consulte a continuación un conjunto más complejo de ejemplos. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Ejemplos de dominios de cookies complejos

Estos ejemplos muestran si [!DNL Audience Manager] configurará una cookie en función de cómo se configure la opción [!UICONTROL Cookie Domain].

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sitio web </th> 
   <th colname="col2" class="entry">Dominio de la cookie: .sport.com <p>Conjunto de cookies </p> </th> 
   <th colname="col3" class="entry">Dominio de la cookie: .golf.sport.com <p>Conjunto de cookies </p> </th> 
   <th colname="col4" class="entry">Dominio de la cookie: En blanco <p>Conjunto de cookies </p> </th> 
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
   <td colname="col1"> <p> <b>golf.sport.com</b> </p> </td> 
   <td colname="col2"> Sí </td> 
   <td colname="col3"> Sí </td> 
   <td colname="col4"> Sí </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sport.com</b> </p> </td> 
   <td colname="col2"> Sí </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sí </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sport.golf.com</b> </p> </td> 
   <td colname="col2"> No </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sí </td> 
  </tr> 
 </tbody> 
</table>

## Publicar datos en {#publish-data-to}

La configuración de [!UICONTROL Publish Data To] devuelve una cookie si el dominio cumple los criterios establecidos por las opciones seleccionadas. Las opciones incluyen:

* **[!UICONTROL All of our domains]**: (Predeterminado) Devuelve un valor  [!DNL cookie] para cualquier dominio.
* **[!UICONTROL Only the selected domains]**: Devuelve una cookie solo para los dominios seleccionados en la lista de dominios.
* **[!UICONTROL All of our domains except the selected domains]**: Impide que los dominios seleccionados reciban un  [!DNL cookie]. Todos los demás dominios pueden recibir un [!DNL cookie].

>[!MORELIKETHIS]
>
>* [Crear un destino de cookie](../../features/destinations/create-cookie-destination.md)

