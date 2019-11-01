---
description: Muestras de código y descripciones para casos de uso DIL específicos.
seo-description: Muestras de código y descripciones para casos de uso DIL específicos.
seo-title: Casos de uso DIL y ejemplos de código
solution: Audience Manager
title: Casos de uso DIL y ejemplos de código
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Casos de uso DIL y ejemplos de código{#dil-use-cases-and-code-samples}

Muestras de código y descripciones para casos de uso DIL específicos.

<!-- 

c_dil_use_case.xml

 -->

## Envío de elementos de datos a Audience Manager con DIL {#send-data-elements-dil}

Cree una variable de objeto que envíe información sobre los elementos de página a Audience Manager. Esto resulta útil para la recopilación general de datos o como alternativa para recopilar datos con variables de Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descripción**

El siguiente código muestra cómo recopilar datos de página y enviarlos a Audience Manager con [!UICONTROL DIL]. Estos ejemplos utilizan una variable para contener elementos de datos en una lista plana o una matriz. Recuerde, pase variables como pares [](../reference/key-value-pairs-explained.md)clave-valor. Además, observe el `c_` prefijo antes de la clave en el par clave-valor. Este prefijo [](../features/traits/trait-variable-prefixes.md) requerido identifica la información como datos definidos por el usuario. En el primer ejemplo, debe anexar manualmente `c_` la clave. En el segundo ejemplo, [!UICONTROL DIL] lo hace automáticamente.

**Mantener consistentes las propiedades del valor**

Recuerde mantener las propiedades de valor igual al pasar datos. Por ejemplo, si tiene dos claves idénticas con valores diferentes, el valor del último par clave-valor tiene prioridad sobre los objetos de valor anteriores. Por ejemplo, al pasar `color:blue` y `color:red` establecer el valor devuelto en rojo (sobrescribe el azul).

**Ejemplo 1: Enviar datos como pares de clave-valor**

Este ejemplo básico envía datos de color y precio a Audience Manager en forma de pares clave-valor. El código podría tener un aspecto similar al siguiente:

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**Ejemplo 2: Envío de datos a un objeto**

Este ejemplo avanzado muestra cómo enviar datos en un objeto a Audience Manager. Al trabajar con este método, [!UICONTROL DIL] le permite pasar un objeto como parámetro de función al [!DNL signals()] método. [!UICONTROL DIL] El código podría tener un aspecto similar al siguiente:

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Ejemplo 3: Envío de datos de página en una matriz**

En este caso, la variable `my_object` utiliza una matriz para almacenar datos. Este ejemplo se basa en la información pasada por el método recomendado anteriormente, pero agrega una capa adicional para dar cabida a un modelo y tipo de producto. El código podría tener un aspecto similar al siguiente:

<pre class="java"><code>
var my_objects = [{ 
   color : "blue", 
   price : "900" 
}, { 
   type : "acura", 
   model : "tl" 
}]; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

## Capturar URL de referencia {#capture-referring-url}

Capture y envíe una dirección URL de referencia a Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Este método solo funciona cuando los usuarios se mueven entre páginas con protocolos similares (HTTP vs HTTPS). Por ejemplo, el explorador retiene una dirección URL de referencia cuando navega de un sitio seguro a otro. Los navegadores no retienen la dirección URL de referencia cuando se mueven entre sitios seguros y no seguros. Este comportamiento es una funcionalidad normal del explorador y no se puede evitar [!UICONTROL DIL].

**Ejemplo de código**

El código podría tener un aspecto similar al siguiente:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Capturar tipos de motores de búsqueda y términos de búsqueda de palabras clave {#capture-search-engine-types}

Envíe información sobre el tipo de motor de búsqueda y las búsquedas de palabras clave a Audience Manager.

>[!IMPORTANT]
>
>En esta sección se describe la funcionalidad heredada, que no se admite en las últimas versiones de DIL.

**Motores de búsqueda admitidos**

De manera predeterminada, `DIL.getSearchReferrer` reconoce las búsquedas desde estos motores de búsqueda (incluidas las variaciones internacionales):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descripción**

El siguiente código muestra cómo obtener el referente de búsqueda para cualquiera de los motores de búsqueda admitidos. En este caso, supongamos que un usuario buscó el término "hogares" desde [!DNL Google] Canadá ( `www.google.ca`). Este código le ayudará a capturar esos términos de búsqueda y enviarlos a Audience Manager.

**Código básico**

El código básico para obtener el referente de búsqueda (por `google.com`ejemplo) tiene este aspecto:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Ejemplo de código de motor de búsqueda enumerado**

En este caso, supongamos que un usuario buscó el término "hogares" desde [!DNL Google] Canadá ( `www.google.ca`). Observe cómo el código prefiere el parámetro requerido `c_` al motor de búsqueda ( `c_se`) y al término de búsqueda ( `c_st`). `c_` es un prefijo [](../features/traits/trait-variable-prefixes.md) requerido que identifica estas variables como variables definidas por el cliente en Audience Manager.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

**Ejemplo de código de motor de búsqueda no enumerado**

En este caso, supongamos que un usuario buscó el término "hogares" desde `dogpile.com`. Debido a que no [!DNL Dogpile] se admite de forma predeterminada, puede configurar DIL para que reconozca este motor de búsqueda y devuelva los términos de búsqueda a Audience Manager. El código podría tener un aspecto similar al siguiente:

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, {  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Asignar valores clave a otras claves {#map-key-values}

Asocie el valor de un par clave-valor a otra clave.

<!-- 

c_dil_map_keys.xml

 -->

**Descripción**

En un par clave-valor, el `c_` prefijo anexado a la clave identifica la señal como datos definidos por el cliente. Los datos definidos por el cliente se utilizan para segmentar en el sitio específico que pasó los datos en una llamada de evento. Sin embargo, a veces desea que esta información esté disponible en todas las propiedades de su cuenta de Audience Manager. Para ello, asigne el valor de un par `c_` clave-valor a una clave de nivel de plataforma. Se añade un prefijo a una clave de nivel de plataforma `d_` y la señal está disponible para la segmentación en todas las propiedades de la cuenta.

Por ejemplo, recopila datos de código postal de un sitio en particular, pero desea segmentarlos en todas sus propiedades de Audience Manager. Para que el código postal esté disponible a nivel de plataforma, puede asignar la clave de código postal definida por el cliente (p. ej. `c_zip`) a una clave definida por la plataforma como se muestra a continuación.

**Ejemplo de código**

El código podría tener un aspecto similar al siguiente:

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

## DIL de tráfico en Google Tag Manager (GTM) {#traffic-dil-gtm}

Configure y proporcione DIL con una etiqueta GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Este procedimiento supone que tiene una [!DNL Google Tag Manager] cuenta, algún conocimiento práctico de ese producto y el archivo de Audience Manager `dil.js` .

Para el tráfico del `dil.js` archivo en GTM:

1. Cree un nuevo contenedor o abra un contenedor existente.
1. Agregue una nueva etiqueta al contenedor.
1. Abra la etiqueta para editarla y:

   * Asigne un nombre a la etiqueta.
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * En el campo HTML, coloque el [!UICONTROL DIL] código (biblioteca + el código personalizado) dentro de las etiquetas de script `<script>DIL code</script>`.
   * Haga clic en **[!UICONTROL Save]**.

1. Publique el contenedor.
1. Genere el código de etiqueta de contenedor y colóquelo en el inventario.

>[!MORELIKETHIS]
>
>* [Centro de ayuda del Administrador de etiquetas de Google](https://support.google.com/tagmanager#topic=3441530)
>* [Señales](../dil/dil-instance-methods.md#signals)
>* [Requisitos de prefijo para variables clave](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)

