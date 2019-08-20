---
description: Ejemplos de código y descripciones para casos de uso DIL específicos.
seo-description: Ejemplos de código y descripciones para casos de uso DIL específicos.
seo-title: Casos de uso DIL y Muestras de código
solution: Audience Manager
title: Casos de uso DIL y Muestras de código
uuid: 27995 c 2 d -6572-438 e-af 99-b 5477 f 090 ae 9
translation-type: tm+mt
source-git-commit: 8763bff3960e2033951cf68e65f5ad44377b2917

---


# Casos de uso DIL y Muestras de código{#dil-use-cases-and-code-samples}

Ejemplos de código y descripciones para casos de uso DIL específicos.

<!-- 

c_dil_use_case.xml

 -->

## Envío de elementos de datos a Audience Manager con DIL {#send-data-elements-dil}

Cree una variable de objeto que envíe información sobre los elementos de página a Audience Manager. Esto resulta útil para la recopilación de datos generales o como alternativa a la recopilación de datos con variables de Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descripción**

El siguiente código muestra cómo recopilar datos de página y enviarlos a Audience Manager con [!UICONTROL DIL]. En estos ejemplos se utiliza una variable para contener elementos de datos en una lista plana o matriz. Recuerde, pase variables como [pares clave-valor](../reference/key-value-pairs-explained.md). Asimismo, tenga en cuenta el `c_` prefijo antes de la clave en el par clave-valor. Este [prefijo obligatorio](../features/traits/trait-variable-prefixes.md) identifica la información como datos definidos por el usuario. En el primer ejemplo, debe anexar manualmente `c_` a la clave. En el segundo ejemplo, [!UICONTROL DIL] realiza esto automáticamente.

**Mantener propiedades de valor coherentes**

Recuerde mantener las propiedades del valor igual al pasar datos. Por ejemplo, si tiene dos claves idénticas con valores diferentes, el valor del último par clave-valor tiene prioridad sobre los objetos de valor anteriores. Por ejemplo, pasar `color:blue` y `color:red` configura el valor devuelto a rojo (sobrescribe azul).

**Ejemplo 1: Enviar datos como pares clave-valor**

Este ejemplo básico envía datos de color y cotización a Audience Manager en forma de pares clave-valor. Su código podría tener un aspecto similar al siguiente:

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
sample_ dil. api. señales ({ 
 c_ color: " blue ", 
 c_ price: " 900 "}); 
sample_ dil. api. submit ();</code>
</pre>

**Ejemplo 2: Enviar datos en un objeto**

Este ejemplo avanzado muestra cómo enviar datos de un objeto a Audience Manager. Al trabajar con este método [!UICONTROL DIL] , le permite pasar un objeto como parámetro de función al [!DNL signals()] método. [!UICONTROL DIL] Su código podría tener un aspecto similar al siguiente:

<pre class="java"><code>var my_ object = { 
 color: " blue ", 
 price: " 900 "}; 
 
var sample_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
//Load el objeto y anexe "c_" a todas las claves de los pares clave-valor y envíe datos a audiencemanager. 
sample_ dil. api. señales (my_ object, "c_"). submit ();</code>
</pre>

**Ejemplo 3: Enviar datos de página en una matriz**

En este caso, la variable `my_object` utiliza una matriz para retener datos. Este ejemplo se basa en la información pasada por el método recomendado anteriormente, pero agrega una capa adicional para dar cabida a un modelo y modelo de producto. Su código podría tener un aspecto similar al siguiente:

<pre class="java"><code>var my_ objects = [{ 
 color: " blue ", 
 price: " 900 "}, 
{ 
 type: " acura ", 
 modelo: " tl "}]; 
 
var sample_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
 
for (var i = 0; i &lt; my_ objects. length; i + +) 
//Load el objeto y anexe "c_" a todas las claves de los pares de clave-valor. 
{{{{{{{{{{ 
 sample_ dil. api. señales (my_ objects [i], "c_"); 
} 
sample_ dil. api. submit ();</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [señales](../dil/dil-instance-methods.md#signals)


## Capturar URL de referencia {#capture-referring-url}

Capture y envíe una URL de referencia a Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Este método solo funciona cuando los usuarios se mueven entre páginas con protocolos similares (HTTP frente a HTTPS). Por ejemplo, el explorador conserva una dirección URL de referencia cuando navega desde un sitio seguro a otro sitio seguro. Los navegadores no conservan la dirección URL de referencia cuando se desplaza entre sitios seguros y no seguros. Este comportamiento es una funcionalidad de navegador normal y no se puede sortear por [!UICONTROL DIL].

**Ejemplo de código**

Su código podría tener un aspecto similar al siguiente:

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
adobe_ dil. api. señales ({d_ referer: document. referrer}). submit ();</code>
</pre>

## Capturar tipos de motores de búsqueda y términos de búsqueda de palabras clave {#capture-search-engine-types}

Envíe información sobre el tipo de motor de búsqueda y las búsquedas de palabras clave a Audience Manager.

>[!IMPORTANT]
>
>Esta sección describe las funciones heredadas, que no se admiten en las versiones más recientes de DIL.

**Motores de búsqueda admitidos**

De forma predeterminada `DIL.getSearchReferrer` , reconoce las búsquedas desde estos motores de búsqueda (incluso variaciones internacionales):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descripción**

El siguiente código muestra cómo obtener el referente de búsqueda para cualquiera de los motores de búsqueda admitidos. En este caso, supongamos que un usuario buscó el término "domicilios" de [!DNL Google] Canadá ( `www.google.ca`). Este código le ayudará a capturar esos términos de búsqueda y enviarlos a Audience Manager.

**Código básico**

El código básico para obtener el referente de búsqueda (por `google.com`ejemplo, de) tiene este aspecto:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Muestra de código de motor de búsqueda enumerada**

En este caso, supongamos que un usuario buscó el término "domicilios" de [!DNL Google] Canadá ( `www.google.ca`). Observe cómo el código prefiera el parámetro requerido `c_` en el motor de búsqueda ( `c_se`) y el término de búsqueda ( `c_st`). `c_` es [un prefijo](../features/traits/trait-variable-prefixes.md) requerido que identifica estas variables definidas por el cliente a Audience Manager.

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

En este caso, supongamos que un usuario buscó el término «domicilios». `dogpile.com` Debido a que [!DNL Dogpile] no se admite de forma predeterminada, puede configurar DIL para que reconozca este motor de búsqueda y devolver los términos de búsqueda a Audience Manager. Su código podría tener un aspecto similar al siguiente:

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
var search_ referrer = DIL. tools. getsearchreferrer (document. referrer, { 
 Hostpattern: /dogpile\./, 
 Queryparam: " q "}); 
 
if (search_ referrer &amp; &amp; search_ referrer. valid) { 
 adobe_ dil. api. señales ({ 
 c_ se: se. name, 
 c_ st: se. keywords 
 }). submit (); 
}</code>
</pre>

## Asignar valores clave a otras claves {#map-key-values}

Asocie el valor de un par de valores clave a otra clave.

<!-- 

c_dil_map_keys.xml

 -->

**Descripción**

En un par de valor clave, el `c_` prefijo anexado a la clave identifica la señal como datos definidos por el cliente. Los datos definidos por el cliente se utilizan para segmentar en el sitio específico que pasó los datos en una llamada de evento. Sin embargo, a veces desea que esta información esté disponible en todas las propiedades de su cuenta de Audience Manager. Para ello, asigne el valor en un par `c_` de valores clave a una clave de nivel de plataforma. Una clave de nivel de plataforma tiene un prefijo `d_` y pone la señal a disposición para segmentar en todas las propiedades de su cuenta.

Como ejemplo, recopila datos de código postal de un sitio en particular pero quiere dirigirlo a todas las propiedades de Audience Manager. Para que el código postal esté disponible a nivel de plataforma, puede asignar la clave de código postal definida por el cliente (p. ej. `c_zip`) a una clave definida de plataforma como se muestra a continuación.

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


## DIL de tráfico en Google Tag Manager (GTM) {#traffic-dil-gtm}

Configure y proporcione DIL con una etiqueta GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Este procedimiento supone que tiene una [!DNL Google Tag Manager] cuenta, algunos conocimientos prácticos de ese producto y `dil.js` el archivo de Audience Manager.

Para procesar el `dil.js` archivo en GTM:

1. Cree un contenedor nuevo o abra un contenedor existente.
1. Agregue una etiqueta nueva al contenedor.
1. Abra la etiqueta para editarla y:

   * Asigne un nombre a la etiqueta.
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * En el campo HTML, coloque [!UICONTROL DIL] el código (biblioteca + el código personalizado) dentro de etiquetas `<script>DIL code</script>`de script.
   * Haga clic en **[!UICONTROL Save]**.

1. Publique el contenedor.
1. Genere código de etiqueta de contenedor y colóquelo en el inventario.

>[!MORE_ LIKE_ THIS]
>
>* [Centro de ayuda de Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)

