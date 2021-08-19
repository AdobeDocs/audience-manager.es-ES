---
description: Ejemplos de código y descripciones para casos de uso de DIL específicos.
seo-description: Ejemplos de código y descripciones para casos de uso de DIL específicos.
seo-title: Casos de uso DIL y ejemplos de código
solution: Audience Manager
title: Casos de uso DIL y ejemplos de código
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: Implementación del DIL
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 3%

---

# Casos de uso DIL y ejemplos de código{#dil-use-cases-and-code-samples}

Ejemplos de código y descripciones para casos de uso de DIL específicos.

<!-- 

c_dil_use_case.xml

 -->

## Envío de elementos de datos al Audience Manager con el DIL {#send-data-elements-dil}

Cree una variable de objeto que envíe información sobre los elementos de página al Audience Manager. Esto resulta útil para la recopilación general de datos o como alternativa a la recopilación de datos con variables de Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descripción**

El siguiente código muestra cómo recopilar datos de página y enviarlos al Audience Manager con [!UICONTROL DIL]. Estos ejemplos utilizan una variable para contener elementos de datos en una lista plana o una matriz. Recuerde, pase las variables como [pares clave-valor](../reference/key-value-pairs-explained.md). Además, observe el prefijo `c_` antes de la clave en el par clave-valor. Este [prefijo obligatorio](../features/traits/trait-variable-prefixes.md) identifica la información como datos definidos por el usuario. En el primer ejemplo, debe anexar `c_` manualmente a la clave. En el segundo ejemplo, [!UICONTROL DIL] lo hace automáticamente.

**Mantener la coherencia de las propiedades del valor**

Recuerde mantener las propiedades del valor igual al pasar los datos. Por ejemplo, si tiene dos claves idénticas con valores diferentes, el valor del último par clave-valor tiene prioridad sobre los objetos de valor anteriores. Por ejemplo, al pasar `color:blue` y `color:red` se establece el valor devuelto en rojo (sobrescribe el azul).

**Ejemplo 1: Enviar datos como pares de clave-valor**

Este ejemplo básico envía datos de color y precio al Audience Manager en forma de pares clave-valor. Su código podría tener un aspecto similar al siguiente:

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**Ejemplo 2: Enviar datos en un objeto**

En este ejemplo avanzado se muestra cómo enviar datos en un objeto al Audience Manager. Al trabajar con este método, [!UICONTROL DIL] permite pasar un objeto como parámetro de función al método [!DNL signals()]. [!UICONTROL DIL] Su código podría tener un aspecto similar al siguiente:

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Ejemplo 3: Enviar datos de página en una matriz**

En este caso, la variable `my_object` utiliza una matriz para contener datos. Este ejemplo se basa en la información pasada por el método recomendado anteriormente, pero agrega una capa adicional para acomodar un tipo de producto y un modelo. Su código podría tener un aspecto similar al siguiente:

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

Capture y envíe una dirección URL de referencia al Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Este método solo funciona cuando los usuarios se mueven entre páginas con protocolos similares (HTTP o HTTPS). Por ejemplo, el explorador conserva una dirección URL de referencia cuando navega de un sitio seguro a otro sitio seguro. Los navegadores no conservan la dirección URL de referencia cuando se mueven entre sitios seguros y no seguros. Este comportamiento es una funcionalidad normal del explorador y [!UICONTROL DIL] no puede eludirlo.

**Ejemplo de código**

Su código podría tener un aspecto similar al siguiente:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Capturar tipos de motores de búsqueda y términos de búsqueda de palabras clave {#capture-search-engine-types}

Envíe información sobre el tipo de motor de búsqueda y las búsquedas de palabras clave al Audience Manager.

>[!IMPORTANT]
>
>En esta sección se describe la funcionalidad heredada, que no es compatible con las últimas versiones de DIL.

**Motores de búsqueda admitidos**

De forma predeterminada, `DIL.getSearchReferrer` reconoce las búsquedas desde estos motores de búsqueda (incluidas las variaciones internacionales):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descripción**

El siguiente código muestra cómo obtener el referente de búsqueda para cualquiera de los motores de búsqueda admitidos. En este caso, supongamos que un usuario ha buscado el término &quot;hogares&quot; desde [!DNL Google] Canadá ( `www.google.ca`). Este código le ayudará a capturar esos términos de búsqueda y enviarlos al Audience Manager.

**Código básico**

El código básico para obtener el referente de búsqueda (de `google.com`, por ejemplo) tiene este aspecto:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Ejemplo de código del motor de búsqueda enumerado**

En este caso, supongamos que un usuario buscó el término &quot;hogares&quot; desde [!DNL Google] Canadá ( `www.google.ca`). Observe cómo el código prefiere el parámetro `c_` requerido al motor de búsqueda ( `c_se`) y al término de búsqueda ( `c_st`). `c_` es un  [prefijo ](../features/traits/trait-variable-prefixes.md) obligatorio que identifica estas variables como variables definidas por el cliente para el Audience Manager.

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

En este caso, supongamos que un usuario buscó el término &quot;hogares&quot; de `dogpile.com`. Como [!DNL Dogpile] no es compatible de forma predeterminada, puede configurar el DIL para que reconozca este motor de búsqueda y devuelva los términos de búsqueda al Audience Manager. Su código podría tener un aspecto similar al siguiente:

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

En un par clave-valor, el prefijo `c_` anexado a la clave identifica la señal como datos definidos por el cliente. Los datos definidos por el cliente se utilizan para segmentar en el sitio específico que pasó datos en una llamada de evento. Sin embargo, a veces desea que esta información esté disponible en todas las propiedades de la cuenta de Audience Manager. Para ello, asigne el valor de un par clave-valor `c_` a una clave a nivel de plataforma. A una clave de nivel de plataforma se le agregará el prefijo `d_` y la señal estará disponible para todos los objetivos de las propiedades de la cuenta.

Por ejemplo, recopila datos de código postal de un sitio en particular, pero desea dirigirlos a todas sus propiedades de Audience Manager. Para que el código postal esté disponible a nivel de plataforma, puede asignar la clave de código postal definida por el cliente (p. ej. `c_zip`) a una clave definida por la plataforma como se muestra a continuación.

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

## DIL de tráfico en Google Tag Manager (GTM) {#traffic-dil-gtm}

Configure y sirva un DIL con una etiqueta GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Este procedimiento supone que tiene una cuenta [!DNL Google Tag Manager], algún conocimiento práctico de ese producto y su archivo `dil.js` de Audience Manager.

Para enviar el archivo `dil.js` a GTM:

1. Cree un contenedor nuevo o abra un contenedor existente.
1. Agregue una etiqueta nueva al contenedor.
1. Abra la etiqueta para editarla y:

   * Asigne un nombre a la etiqueta .
   * Seleccione **[!UICONTROL Custom HTML Tag]** en la lista desplegable **[!UICONTROL Tag Type]**.
   * En el campo HTML, coloque el código [!UICONTROL DIL] (biblioteca + el código personalizado) dentro de las etiquetas de script `<script>DIL code</script>`.
   * Haga clic **[!UICONTROL Save]**.

1. Publique el contenedor.
1. Genere el código de etiqueta contenedora y colóquelo en su inventario.

>[!MORELIKETHIS]
>
>* [Centro de ayuda de Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)
>* [Señales](../dil/dil-instance-methods.md#signals)
* [Requisitos de prefijo para variables clave](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)

