---
description: Describe los métodos en el espacio de nombres DIL. tools. Estas funciones de utilidad le ayudan a realizar tareas específicas.
seo-description: Describe los métodos en el espacio de nombres DIL. tools. Estas funciones de utilidad le ayudan a realizar tareas específicas.
seo-title: Herramientas DIL
solution: Audience Manager
title: Herramientas DIL
uuid: 2 bc 62 ce 2-16 bd -4 e 80-b 493-c 816 ba 643 b 59
translation-type: tm+mt
source-git-commit: ac9e4f24a896ecae2ebf36dcf34a4ac8fab00cd8

---


# Herramientas DIL

Describes methods in the `DIL.tools` namespace. Estas funciones de utilidad le ayudan a realizar tareas específicas.

<!-- 

c_dil_functions.xml

 -->

## Getsearchreferrer

Devuelve los términos de búsqueda utilizados para llegar a la página actual.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Purpose of `getSearchReferrer`

In DIL, `getSearchReferrer` returns search results (names and key words) used to reach your site. You can pass in specific search terms to this function or let it search the supported search engines ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google], and [!DNL Yahoo]) against `document.referrer` by default.

### Firma de función

Function signature: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Parámetros de función

`getSearchReferrer` acepta:

* *`{string}`*: *(Opcional)* Una cadena que contiene la dirección URL de búsqueda (utiliza `document.referrer` si no está definida).
* *`{object}`*: *(Opcional)* Un objeto que contiene la configuración de `hostPattern`, `queryParam`o `queryPattern`.

Y devuelve:

* `{object}` Objeto que contiene nombres y palabras clave válidos.

### Ejemplos

<table id="table_D035276601EC428295E4D619F05BB8D0"> 
 <thead> 
  <tr> 
   <th> Tipo de búsqueda </th> 
   <th> Descripción </th> 
   <th> Ejemplo de código </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Búsqueda predeterminada</td> 
   <td> Devuelve los términos de búsqueda de palabras clave utilizados por los motores de búsqueda AOL, Ask, Bing, Google y Yahoo. </td> 
   <td>
      <code>var &amp; amp; nbsp; results &amp; amp; nbsp; = &amp; amp; nbsp; DIL. tools. getsearchreferrer ();</code> 
  </td>
  </tr> 
  <tr> 
   <td>Pasar una URL personalizada</td> 
   <td>Devuelve el referente de búsqueda basado en una dirección URL personalizada.</td> 
   <td> 
  <code>
        var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>Nombre de host de URL de coincidencia con Regex personalizado</b></td> 
   <td> Pase un regex personalizado para que coincida con el nombre de host de la URL de referencia. </td> 
   <td> 
  <code>
      var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/
    search.aspx?q=adobe+rules",{ 
       hostPattern:/ehow\./, 
         queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Coincidencia de patrones de búsqueda con un regex personalizado</b> </td> 
   <td> Pase un regex personalizado para realizar una búsqueda personalizada. </td> 
   <td> 
    <code>
      var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
    {
       hostPattern:/ehow\./, 
           search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## Decomposeuri

Disassembles a Uniform Resource Identifier ( [!DNL URI]) into its constituent components: `hash`, `host`, `href`, `pathname`, `protocol`, `search`, and `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Function signature: `DIL.tools.decomposeURI`

### Parámetros de función

`decomposeURI` acepta:

* *`uri {string}`*: *(Opcional)* Una cadena que contiene el URI. Defaults to `document.location.href` if not specified.

Y devuelve:

* *`{object}`*: Objeto que contiene nombres y palabras clave válidos.

### Código de muestra


```javascript
var uriData = DIL.tools.decomposeURI('https://www.adobe.com/?arg1=123&arg2=456#am'); 
{ 
  hash : "#am", 
  host : "www.adobe.com", 
  hostname : "www.adobe.com", 
  href : "https://www.adobe.com/?arg1=123&arg2=456#am", 
  pathname : "", 
  protocol : "https:", 
  search : "?arg1=123&arg2=456", 
  uriParams : { 
    arg1 : "123", 
    arg2 : "456" 
  } 
}
```

## Getmetatags

Busca contenido específico definido en las etiquetas meta en una página Web y devuelve esos datos en un objeto.

<!-- 

r_dil_get_metatags.xml

 -->

### Firma de función

Function signature: `DIL.tools.getMetaTags( 1 or more parameters)`

### Parámetros de función

`getMetaTags` acepta uno o varios parámetros de nombre (tipo de cadena) para buscar. Devuelve un objeto compuesto por pares clave-valor.

### Código de muestra

<pre class="&ldquo;javascript&rdquo;"><code>var datalib = DIL. create ({ 
 socio: '<i>Partnername '</i>, 
 Containernsid: <i>Containernsid</i> }); 
Datalib. api. señales (DIL. tools. getmetatags ('<i>application</i>','<i>keywords</i>','<i>description</i>'),' c_'). submit ();</code>
</pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 
dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
