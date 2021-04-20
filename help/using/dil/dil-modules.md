---
description: Describe los métodos del espacio de nombres DIL.module. Estos módulos permiten recopilar datos mediante programación y trabajar con objetos de Audience Manager.
seo-description: Describe los métodos del espacio de nombres DIL.module. Estos módulos permiten recopilar datos mediante programación y trabajar con objetos de Audience Manager.
seo-title: Módulos DIL
solution: Audience Manager
title: Módulos DIL
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e40233ace5cb74743db7d0f9f90707fa596a7e79
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 4%

---


# Módulos DIL{#dil-modules}

Describe los métodos del espacio de nombres `DIL.modules`. Estos módulos permiten recopilar datos mediante programación y trabajar con objetos de Audience Manager.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Funciona con [!UICONTROL DIL] para enviar elementos de etiqueta [!DNL Analytics] (variables, props, eVars, etc.) al Audience Manager. Devuelve datos de una lista separada por comas. Disponible en la versión 2.6.

**Firma de función:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>Debe colocar este código en la página *antes* de la función `s.t();`.

<!-- 

r_dil_sc_init.xml

 -->

**Parámetros**

<table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> variable </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> names </code> </td> 
   <td colname="col2"> Cadena </td> 
   <td colname="col3"> <p>Matriz de cadenas que contiene variables <span class="keyword"> Analytics </span> no enumeradas como <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code>, etc. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> Objeto </td> 
   <td colname="col3"> <p>Matriz de objetos que contiene variables <span class="keyword"> </span> enumeradas de Analytics, como props y evars (p. ej. <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> Número entero </td> 
   <td colname="col3"> <p>Indica cuántos nombres repetidos desea devolver. Por ejemplo, para devolver dos props o evars, establezca <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> Objeto </td> 
   <td colname="col3"> <p>Un objeto que representa el objeto <span class="keyword"> Analytics </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> Objeto </td> 
   <td colname="col3"> <p>Un objeto que representa el DIL <span class="wintitle"> </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Objeto </td> 
   <td colname="col3"> <p>Opciones adicionales: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>Si no especifica otra cosa, los puntos se sustituyen por el guión bajo predeterminado ( _ ). </p> <p>Por ejemplo, <code> s.contextData = {abc.def = '123'} </code>resultaría en <code> c_contextData_abc_def=123 </code> en la cadena de consulta de llamada de evento. </p> <p>Esta opción solo está disponible en el DIL <span class="wintitle"> </span> versión 5.0 o posterior. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>Por ejemplo, <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> resultaría en que la matriz de cadenas se filtrara desde la recopilación de datos de contexto. Esta opción excluye Información de identificación personal (PII). </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Datos capturados por siteCatalyst.init**

Esta función devuelve detalles sobre las siguientes [!DNL Analytics] propiedades:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `eVar` (1 - 250)
* `prop` (1 - 75)
* `pe`
* `pev1`
* `pev2`
* `pev3`

**Código de ejemplo**

Este código crea una lista separada por comas de eventos [!DNL Analytics] (props, eVars, etc.) si existen valores para ellos.

```
// Get the Site Catalyst object instance: 
var s = s_gi(s_account); 
  
// Instantiate DIL code: 
var scDil = DIL.create({ 
        partner: 'adobe', 
        containerNSID: 5 
}); 
 
// Use the module: 
DIL.modules.siteCatalyst.init(s, scDil, { 
        //Specify the Site Catalyst variables you want to capture: 
        names: ['pageName', 'channel', 'campaign'], 
        //Use this to create iterated variable names: 
        iteratedNames: [{ 
               name: 'eVar', 
               maxIndex: 75 
        }, { 
               name: 'prop', 
               maxIndex: 75 
        }] 
});
```

Para rastrear todos los puntos de datos [!DNL Analytics] monitorizados sin la función adicional mostrada arriba, invoque `siteCatalyst.init` de esta manera:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

La función `GA.submitUniversalAnalytics();` envía datos del [!DNL Universal Analytics] de Google al Audience Manager. Esta función [!UICONTROL DIL] está diseñada para funcionar con `analytics.js`, que es la última biblioteca de códigos para Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] no tiene ninguna perspectiva ni control sobre la biblioteca de  `analytics.js` código de Google. Debe verificar que la recopilación de datos [!UICONTROL DIL] sigue funcionando si Google publica nuevas versiones de `analytics.js` o cuándo lo hace.
   >
   >
* No puede utilizar `GA.submitUniversalAnalytics();` si sigue trabajando con el código de seguimiento de análisis heredado de Google (por ejemplo, `ga.js` o `dc.js`). Consulte [GA.init](../dil/dil-modules.md#ga-init) en su lugar.

>



**Firma de función:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Propiedades**

La función `GA.submitUniversalAnalytics();` acepta las siguientes propiedades.

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Propiedad </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> gaObject </code> </p> </td> 
   <td colname="col2"> <p>La variable global para su instancia de <span class="keyword"> Google Analytics </span>. Normalmente es <code> ga </code> de forma predeterminada, a menos que haya personalizado el código <span class="keyword"> de los Google Analytics </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>La variable que representa la instancia del DIL <span class="wintitle"> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(Opcional)</i> En la  <code> analytics.js </code> biblioteca, la propiedad interna es la variable minificada  <code> 'b' </code>. Esta variable contiene <span class="keyword"> datos </span> de los Google Analytics. </p> <p>Esta propiedad es opcional porque no es necesario establecerla a menos que Google cambie el nombre de su variable interna. Por ejemplo, si esta variable minificada cambiara a <code> 'a' </code>, llamaría a <code> GA.submitUniversalAnalytics(); </code> de esta manera: </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ejemplo**

Recuerde definir primero el objeto [!DNL Google Analytics] `ga` antes de llamar a [!UICONTROL DIL] y `GA.submitUniversalAnalytics();`. Su código podría tener un aspecto similar a este:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

La función `GA.init()` envía datos de la versión heredada/obsoleta de [!DNL Google Analytics] al Audience Manager.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` solo funciona con el código de seguimiento de análisis heredado de Google,  `ga.js` o  `dc.js`. No puede invocar esta función [!UICONTROL DIL] si utiliza `analytics.js`, que es la última biblioteca de códigos para Google [!DNL Universal Analytics]. [!DNL Audience Manager] los clientes que utilizan  [!UICONTROL DIL] y  [!DNL Universal Analytics] deben ver  [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics).

**Firma de función:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `_gaq` | Matriz | Matriz que contiene comandos GA. |
| `dilInstance` | Objeto | Un objeto que contiene la instancia de DIL. |
| `trackVars` | Objeto | *(Opcional)* Un objeto que consta de la  `names` propiedad. Esta propiedad es una matriz de nombres de comando GA que desea rastrear. |

**Llamadas a funciones GA admitidas**

De forma predeterminada, `GA.init` captura datos de las siguientes funciones:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL crea claves para datos GA**

Audience Manager acepta datos en forma de pares clave-valor mientras GA trabaja con elementos en una matriz. Para trabajar con datos GA, [!UICONTROL DIL] crea automáticamente un par clave-valor y forma una clave como esta: `c_ <key name>`. Además, los elementos de las matrices GA aparecen en un orden específico. Como resultado, debe proporcionar todos los parámetros en ese orden, incluso cuando no contengan datos. [!UICONTROL DIL] asigna claves para los siguientes métodos GA:

```js
// Tracking Social Interactions 
_gaq.push(['_trackSocial', 
    'facebook',                        // c_socialNetwork 
    'like',                            // c_socialAction 
    'https://www.adobe.com/cool.php',   // c_socialTarget 
    '/cool.php'                        // c_socialPagePath 
]);  
 
// Tracking a Transaction 
_gaq.push(['_addTrans', 
   '1234',           // c_transOrderId 
   'Womens Apparel', // c_transAfflication 
   '28.28',          // c_transTotal 
   '1.29',           // c_tranTax 
   '15.00',          // c_transShipping 
   'San Jose',       // c_transCity 
   'California',     // c_transState 
   'USA'             // c_transCountry 
]); 
 
// Tracking an item 
_gaq.push(['_addItem', 
   '1234',           // c_itemOrderId=1234 
   'DD44',           // c_itemSku 
   'T-Shirt',        // c_itemName 
   'Olive Medium',   // c_itemCategory 
   '11.99',          // c_itemPrice 
   '1'               // c_itenQuantity 
]);
```

**Código de ejemplo**

```js
// DIL JavaScript library needs to be loaded and executed here 
var dilInstance = DIL.create({ 
    partner : "adobe" 
}); 
 
// Assume ga.js has not loaded 
var _gaq = _gaq || []; 
_gaq.push( 
  ['_setAccount', 'UA-XXXXX-X'], 
  ['_setDomainName', 'example.com'], 
  ['_setCustomVar', 1, 'Section', 'Life & Style', 3], 
  ['_trackPageview'] 
); 
_gaq.push([ 
  '_addItem', 
  '1234',         // order ID - necessary to associate item with transaction 
  'DD44',         // SKU/code - required 
  'T-Shirt',      // product name - necessary to associate revenue with product 
  'Olive Medium', // category or variation 
  '11.99',        // unit price - required 
  '1'             // quantity - required 
]); 
```

Para rastrear todas las métricas de GA monitoreadas sin la función adicional que se muestra arriba, invoque `GA.init` de esta manera:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Ejemplo de llamada de evento**

La llamada de evento de URL al Audience Manager puede tener un aspecto similar a este:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Código de seguimiento de Google Analytics](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Actualización web completa: ga.js/dc.js a analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [Adición de analytics.js a su sitio](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [Referencia de métodos de objetos ga](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

