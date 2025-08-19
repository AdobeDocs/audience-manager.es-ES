---
description: Ejemplos de código y descripciones para casos de uso específicos de DIL.
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: Casos de uso de DIL y ejemplos de código
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 1%

---

# Casos de uso de DIL y ejemplos de código{#dil-use-cases-and-code-samples}

>[!WARNING]
>
>Desde julio de 2023, Adobe ha interrumpido el desarrollo de la extensión [!DNL Data Integration Library (DIL)] y [!DNL DIL].
>
>Los clientes existentes pueden seguir usando su implementación de [!DNL DIL]. Sin embargo, Adobe no desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes evaluar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para su estrategia de recopilación de datos a largo plazo.
>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos a partir de julio de 2023 deben utilizar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) en su lugar.

Ejemplos de código y descripciones para casos de uso específicos de DIL.

<!-- 

c_dil_use_case.xml

 -->

## Envío de elementos de datos a Audience Manager con DIL {#send-data-elements-dil}

Cree una variable de objeto que envíe información sobre elementos de página a Audience Manager. Esto resulta útil para la recopilación de datos generales o como alternativa a la recopilación de datos con variables de Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descripción**

El siguiente código muestra cómo recopilar datos de página y enviarlos a Audience Manager con [!UICONTROL DIL]. En estos ejemplos se utiliza una variable para guardar elementos de datos en una lista plana o una matriz. Recuerde, pase las variables como [pares clave-valor](../reference/key-value-pairs-explained.md). Además, observe el prefijo `c_` antes de la clave en el par clave-valor. Este [prefijo obligatorio](../features/traits/trait-variable-prefixes.md) identifica la información como datos definidos por el usuario. En el primer ejemplo, debe anexar manualmente `c_` a la clave. En el segundo ejemplo, [!UICONTROL DIL] hace esto por usted automáticamente.

**Mantener Coherentes Las Propiedades Del Valor**

Recuerde mantener las mismas propiedades de valor al pasar datos. Por ejemplo, si tiene dos claves idénticas con valores diferentes, el valor del último par clave-valor tiene prioridad sobre los objetos de valor anteriores. Por ejemplo, al pasar `color:blue` y `color:red`, el valor devuelto se establece en rojo (sobrescribe el azul).

**Ejemplo 1: Enviar datos como pares clave-valor**

Este ejemplo básico envía datos de color y precio a Audience Manager en forma de pares clave-valor. Su código puede tener un aspecto similar al siguiente:

<pre class="java"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals(&lbrace; 
   c_color:"blue", 
   c_price:"900" 
&rbrace;); 
sample_dil.api.submit();
</code></pre>

**Ejemplo 2: Enviar datos en un objeto**

En este ejemplo avanzado se muestra cómo enviar datos en un objeto a Audience Manager. Al trabajar con este método, [!UICONTROL DIL] le permite pasar un objeto como parámetro de función al método [!DNL signals()]. [!UICONTROL DIL] Su código podría ser similar al siguiente:

<pre class="java"><code>
var my_object = &lbrace; 
   color : "blue", 
   price : "900" 
&rbrace;; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Ejemplo 3: Enviar datos de página en una matriz**

En este caso, la variable `my_object` utiliza una matriz para contener datos. Este ejemplo se basa en la información pasada por el método recomendado anteriormente, pero agrega una capa adicional para dar cabida a un tipo de producto y a un modelo. Su código puede tener un aspecto similar al siguiente:

<pre class="java"><code>
var my_objects = &lbrack;&lbrace; 
   color : "blue", 
   price : "900" 
&rbrace;, &lbrace; 
   type : "acura", 
   model : "tl" 
&rbrace;&rbrack;; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
&lbrace; 
    sample_dil.api.signals(my_objects[i], "c_"); 
&rbrace; 
sample_dil.api.submit();
</code></pre>

## Capturar URL de referencia {#capture-referring-url}

Capturar y enviar una dirección URL de referencia a Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Este método solo funciona cuando los usuarios se desplazan entre páginas con protocolos similares (HTTP o HTTPS). Por ejemplo, el explorador conserva una dirección URL de referencia cuando se navega de un sitio seguro a otro sitio seguro. Los navegadores no conservan la dirección URL de referencia cuando se desplaza entre sitios seguros y no seguros. Este comportamiento es una funcionalidad normal del explorador y [!UICONTROL DIL] no lo puede eludir.

**Ejemplo de código**

Su código puede tener un aspecto similar al siguiente:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Capturar tipos de motores de búsqueda y términos de búsqueda de palabras clave {#capture-search-engine-types}

Envíe información sobre el tipo de motor de búsqueda y las búsquedas de palabras clave a Audience Manager.

>[!IMPORTANT]
>
>En esta sección se describe la funcionalidad heredada, que no es compatible con las últimas versiones de DIL.

**Motores de búsqueda admitidos**

De manera predeterminada, `DIL.getSearchReferrer` reconoce las búsquedas de estos motores de búsqueda (incluidas las variaciones internacionales):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descripción**

El siguiente código muestra cómo obtener el referente de búsqueda para cualquiera de los motores de búsqueda admitidos. En este caso, supongamos que un usuario ha buscado el término &quot;home&quot; desde [!DNL Google] Canadá ( `www.google.ca`). Este código le ayudará a capturar esos términos de búsqueda y a enviarlos a Audience Manager.

**Código básico**

El código básico para obtener el referente de búsqueda (de `google.com`, por ejemplo) tiene el siguiente aspecto:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Ejemplo de código de motor de búsqueda enumerado**

En este caso, supongamos que un usuario ha buscado el término &quot;home&quot; en [!DNL Google] Canadá ( `www.google.ca`). Observe cómo el código prefija el parámetro `c_` necesario al motor de búsqueda (`c_se`) y al término de búsqueda (`c_st`). `c_` es un [prefijo obligatorio](../features/traits/trait-variable-prefixes.md) que las identifica como variables definidas por el cliente para Audience Manager.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) &lbrace; 
  adobe_dil.api.signals(&lbrace; 
    c_se : se.name, 
    c_st : se.keywords 
  &rbrace;).submit(); 
&rbrace;
</code></pre>

**Ejemplo de código de motor de búsqueda no enumerado**

En este caso, supongamos que un usuario ha buscado el término &quot;home&quot; en `dogpile.com`. Como [!DNL Dogpile] no es compatible de manera predeterminada, puede configurar DIL para que reconozca este motor de búsqueda y devuelva los términos de búsqueda a Audience Manager. Su código puede tener un aspecto similar al siguiente:

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, &lbrace;  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
&rbrace;); 
 
if (search_referrer && search_referrer.valid) &lbrace; 
  adobe_dil.api.signals(&lbrace; 
    c_se : se.name, 
    c_st : se.keywords 
  &rbrace;).submit(); 
&rbrace;
</code></pre>

## Asignar valores de clave a otras claves {#map-key-values}

Asocie el valor de un par clave-valor a otra clave.

<!-- 

c_dil_map_keys.xml

 -->

**Descripción**

En un par clave-valor, el prefijo `c_` anexado a la clave identifica la señal como datos definidos por el cliente. Los datos definidos por el cliente se utilizan para la segmentación en el sitio específico que pasó datos en una llamada de evento. Sin embargo, a veces desea que esta información esté disponible en todas las propiedades de su cuenta de Audience Manager. Para ello, asigne el valor de un par clave-valor de `c_` a una clave de nivel de plataforma. Una clave de nivel de plataforma lleva el prefijo `d_` y hace que la señal esté disponible para la segmentación en todas las propiedades de la cuenta.

Por ejemplo, puede recopilar datos de código postal de un sitio concreto pero querer segmentarlos para que incluyan todas las propiedades de Audience Manager. Para que el código postal esté disponible en toda la plataforma, puede asignar la clave de código postal definida por el cliente (por ejemplo, `c_zip`) a una clave definida en la plataforma como se muestra a continuación.

**Ejemplo de código**

Su código puede tener un aspecto similar al siguiente:

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

Este procedimiento supone que tiene una cuenta de [!DNL Google Tag Manager], algunos conocimientos prácticos de ese producto y el archivo de Audience Manager `dil.js`.

Para enviar tráfico al archivo `dil.js` en GTM:

1. Cree un nuevo contenedor o abra uno existente.
1. Agregue una etiqueta nueva al contenedor.
1. Abra la etiqueta para editarla y:

   * Asigne un nombre a la etiqueta
   * Seleccione **[!UICONTROL Custom HTML Tag]** de la lista desplegable **[!UICONTROL Tag Type]**.
   * En el campo HTML, coloque el código [!UICONTROL DIL] (biblioteca + código personalizado) dentro de las etiquetas de script `<script>DIL code</script>`.
   * Haga clic en **[!UICONTROL Save]**.

1. Publique el contenedor.
1. Genere el código de la etiqueta contenedora y colóquelo en su inventario.

>[!MORELIKETHIS]
>
>* [Centro de ayuda de Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)
>* [Señales](../dil/dil-instance-methods.md#signals)
>* [Requisitos de prefijo para variables clave](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)
