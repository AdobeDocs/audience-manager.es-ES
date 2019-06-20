---
description: Ejemplos de código y descripciones para casos de uso DIL específicos.
seo-description: Ejemplos de código y descripciones para casos de uso DIL específicos.
seo-title: Casos de uso DIL y Muestras de código
solution: Audience Manager
title: Casos de uso DIL y Muestras de código
uuid: 27995 c 2 d -6572-438 e-af 99-b 5477 f 090 ae 9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL Use Cases and Code Samples{#dil-use-cases-and-code-samples}

Ejemplos de código y descripciones para casos de uso DIL específicos.

<!-- 

c_dil_use_case.xml

 -->

## Send Data Elements to Audience Manager with DIL {#send-data-elements-dil}

Cree una variable de objeto que envíe información sobre los elementos de página a Audience Manager. Esto resulta útil para la recopilación de datos generales o como alternativa a la recopilación de datos con variables de Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descripción**

The following code demonstrates how to collect page data and send it to Audience Manager with [!UICONTROL DIL]. En estos ejemplos se utiliza una variable para contener elementos de datos en una lista plana o matriz. Remember, pass in variables as [key-value pairs](../reference/key-value-pairs-explained.md). Also, note the `c_` prefix before the key in the key-value pair. This [required prefix](../features/traits/trait-variable-prefixes.md) identifies information as user-defined data. In the first example, you need to manually append `c_` to the key. In the second example, [!UICONTROL DIL] does this for you automatically.

**Mantener propiedades de valor coherentes**

Recuerde mantener las propiedades del valor igual al pasar datos. Por ejemplo, si tiene dos claves idénticas con valores diferentes, el valor del último par clave-valor tiene prioridad sobre los objetos de valor anteriores. For example, passing in `color:blue` and `color:red` sets the returned value to red (overwrites blue).

**Ejemplo 1: Enviar datos como pares clave-valor**

Este ejemplo básico envía datos de color y cotización a Audience Manager en forma de pares clave-valor. Su código podría tener un aspecto similar al siguiente:

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
sample_ dil. api. señales ({ 
 c_ color: " blue ", 
 c_ price: " 900 "}); 
sample_ dil. api. submit ();</code>
</pre>

**Ejemplo 2: Enviar datos en un objeto**

Este ejemplo avanzado muestra cómo enviar datos de un objeto a Audience Manager. When working with this method, [!UICONTROL DIL] lets you pass an object as a function parameter into the [!DNL signals()] method. [!UICONTROL DIL] Su código podría tener un aspecto similar al siguiente:

<pre class="java"><code>var my_ object = { 
 color: " blue ", 
 price: " 900 "}; 
 
var sample_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
//Load el objeto y anexe "c_" a todas las claves de los pares clave-valor y envíe datos a audiencemanager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Ejemplo 3: Enviar datos de página en una matriz**

In this case, the variable `my_object` uses an array to hold data. Este ejemplo se basa en la información pasada por el método recomendado anteriormente, pero agrega una capa adicional para dar cabida a un modelo y modelo de producto. Su código podría tener un aspecto similar al siguiente:

<pre class="java"><code>var my_ objects = [{ 
 color: " blue ", 
 price: " 900 "}, 
{ 
 type: " acura ", 
 modelo: " tl "}]; 
 
var sample_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
 
for (var i = 0; i &lt; my_ objects. length; i + +) 
//Load el objeto y anexe "c_" a todas las claves de los pares de clave-valor. 
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

>[!MORE_ LIKE_ THIS]
>
>* [señales](../dil/dil-instance-methods.md#signals)


## Capture Referring URL {#capture-referring-url}

Capture y envíe una URL de referencia a Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Este método solo funciona cuando los usuarios se mueven entre páginas con protocolos similares (HTTP frente a HTTPS). Por ejemplo, el explorador conserva una dirección URL de referencia cuando navega desde un sitio seguro a otro sitio seguro. Los navegadores no conservan la dirección URL de referencia cuando se desplaza entre sitios seguros y no seguros. This behavior is normal browser functionality and cannot be circumvented by [!UICONTROL DIL].

**Ejemplo de código**

Su código podría tener un aspecto similar al siguiente:

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
adobe_ dil. api. señales ({d_ referer: document. referrer}). submit ();</code>
</pre>

## Capture Search Engine Types and Keyword Search Terms {#capture-search-engine-types}

Envíe información sobre el tipo de motor de búsqueda y las búsquedas de palabras clave a Audience Manager.

<!-- 

c_dil_search_engine_valid.xml

 -->

**Motores de búsqueda admitidos**

By default, `DIL.getSearchReferrer` recognizes searches from these search engines (including international variations):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descripción**

El siguiente código muestra cómo obtener el referente de búsqueda para cualquiera de los motores de búsqueda admitidos. In this case, let&#39;s assume a user searched on the term &quot;homes&quot; from [!DNL Google] Canada ( `www.google.ca`). Este código le ayudará a capturar esos términos de búsqueda y enviarlos a Audience Manager.

**Código básico**

Basic code for getting the search referrer (from `google.com`, for example) looks like this:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Muestra de código de motor de búsqueda enumerada**

In this case, let&#39;s assume that a user searched for the term &quot;homes&quot; from [!DNL Google] Canada ( `www.google.ca`). Note how the code prefixes the required `c_` parameter to search engine ( `c_se`) and search term ( `c_st`). `c_` es [un prefijo](../features/traits/trait-variable-prefixes.md) requerido que identifica estas variables definidas por el cliente a Audience Manager.

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
var search_ referrer = DIL. tools. getsearchreferrer (); 
 
if (search_ referrer &amp; &amp; search_ referrer. valid) { 
 adobe_ dil. api. señales ({ 
 c_ se: se. name, 
 c_ st: se. keywords 
 }). submit (); 
}</code>
</pre>

**Muestra de código de motor de búsqueda no listada**

In this case, let&#39;s assume that a user searched for the term &quot;homes&quot; from `dogpile.com`. Because [!DNL Dogpile] is not supported by default, you can configure DIL to recognize this search engine and return the search terms to Audience Manager. Su código podría tener un aspecto similar al siguiente:

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
var search_ referrer = DIL. tools. getsearchreferrer (document. referrer, { 
 Hostpattern: /dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer &amp;&amp; search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Map Key Values to Other Keys {#map-key-values}

Asocie el valor de un par de valores clave a otra clave.

<!-- 

c_dil_map_keys.xml

 -->

**Descripción**

In a key-value pair, the `c_` prefix appended to the key identifies the signal as customer-defined data. Los datos definidos por el cliente se utilizan para segmentar en el sitio específico que pasó los datos en una llamada de evento. Sin embargo, a veces desea que esta información esté disponible en todas las propiedades de su cuenta de Audience Manager. To do this, map the value in a `c_` key-value pair to a platform level key. A platform level key is prefixed with `d_` and makes the signal available for targeting across all properties in your account.

Como ejemplo, recopila datos de código postal de un sitio en particular pero quiere dirigirlo a todas las propiedades de Audience Manager. To make the ZIP code available at the platform level, you could map your customer-defined ZIP code key (e.g. `c_zip`) to a platform defined key as shown below.

**Ejemplo de código**

Su código podría tener un aspecto similar al siguiente:

```java
var adobe_dil = DIL.create({ 
    partner : "adobe", 
    mappings : { 
        c_zip : 'd_zip', 
        d_key2 : 'h_dil_key2' 
    } 
}); 
adobe_dil.api.signals({c_zip : '10010'}).submit(); 
// Request will look like /event?c_zip=10010&d_zip=10010
```

>[!MORE_ LIKE_ THIS]
>
>* [Requisitos de prefijo para variables clave](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)


## Traffic DIL in Google Tag Manager (GTM) {#traffic-dil-gtm}

Configure y proporcione DIL con una etiqueta GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

This procedure assumes you have a [!DNL Google Tag Manager] account, some working knowledge of that product, and your Audience Manager `dil.js` file.

To traffic the `dil.js` file in GTM:

1. Cree un contenedor nuevo o abra un contenedor existente.
1. Agregue una etiqueta nueva al contenedor.
1. Abra la etiqueta para editarla y:

   * Asigne un nombre a la etiqueta.
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * In the HTML field, place the [!UICONTROL DIL] code (library + the custom code) within script tags `<script>DIL code</script>`.
   * Haga clic en **[!UICONTROL Save]**.

1. Publique el contenedor.
1. Genere código de etiqueta de contenedor y colóquelo en el inventario.

>[!MORE_ LIKE_ THIS]
>
>* [Centro de ayuda de Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)

