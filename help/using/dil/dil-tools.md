---
description: Describe los métodos del espacio de nombres DIL.tools. Estas funciones de utilidad le ayudan a realizar tareas específicas.
seo-description: Describe los métodos del espacio de nombres DIL.tools. Estas funciones de utilidad le ayudan a realizar tareas específicas.
seo-title: Herramientas DIL
solution: Audience Manager
title: Herramientas DIL
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: Implementación del DIL
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 5%

---

# Herramientas DIL

Describe los métodos del espacio de nombres `DIL.tools`. Estas funciones de utilidad le ayudan a realizar tareas específicas.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Devuelve los términos de búsqueda utilizados para llegar a la página actual.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Objetivo de `getSearchReferrer`

En el DIL, `getSearchReferrer` devuelve los resultados de búsqueda (nombres y palabras clave) utilizados para llegar al sitio. Puede pasar términos de búsqueda específicos a esta función o permitir que busque los motores de búsqueda admitidos ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google] y [!DNL Yahoo]) con `document.referrer` de forma predeterminada.

### Firma de función

Firma de función: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Parámetros de función

`getSearchReferrer` acepta:

* *`{string}`*:  *(Opcional)* Una cadena que contiene la dirección URL de búsqueda (se utiliza  `document.referrer` si no está definida).
* *`{object}`*:  *(Opcional)* Un objeto que contiene la configuración de  `hostPattern`,  `queryParam` o  `queryPattern`.

Y devuelve:

* `{object}` Un objeto que contiene nombres y palabras clave válidos.

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
   <td> Devuelve los términos de búsqueda de palabra clave utilizados por los motores de búsqueda AOL, Ask, Bing, Google y Yahoo. </td> 
   <td>
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>Pasar una dirección URL personalizada</td> 
   <td>Devuelve el referente de búsqueda basado en una dirección URL personalizada.</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>Hacer coincidir el nombre de host de la URL con un regex personalizado</b></td> 
   <td> Pase una regex personalizada para que coincida con el nombre de host de la dirección URL de referencia. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",{ 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Hacer coincidir patrones de búsqueda con un regex personalizado</b> </td> 
   <td> Pase una regex personalizada para realizar una búsqueda personalizada. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      {
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decomposeURI

Desmonta un identificador uniforme de recursos ( [!DNL URI]) en sus componentes constitutivos: `hash`, `host`, `href`, `pathname`, `protocol`, `search` y `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Firma de función: `DIL.tools.decomposeURI`

### Parámetros de función

`decomposeURI` acepta:

* *`uri {string}`*:  *(Opcional)* Una cadena que contiene el URI. Si no se especifica lo contrario, el valor predeterminado es `document.location.href`.

Y devuelve:

* *`{object}`*: Un objeto que contiene nombres y palabras clave válidos.

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

## getMetaTags

Busca contenido específico definido en las metaetiquetas de una página web y devuelve esos datos en un objeto.

<!-- 

r_dil_get_metatags.xml

 -->

### Firma de función

Firma de función: `DIL.tools.getMetaTags( 1 or more parameters)`

### Parámetros de función

`getMetaTags` acepta uno o más parámetros de nombre (tipo de cadena) que se van a buscar. Devuelve un objeto compuesto por pares de clave-valor.

### Código de muestra

<pre class="&ldquo;javascript&rdquo;"><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
