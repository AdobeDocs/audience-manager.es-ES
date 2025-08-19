---
description: Describe métodos en el espacio de nombres DIL.modules. Estos módulos permiten recopilar datos mediante programación y trabajar con objetos Audience Manager.
seo-description: Describes methods in the DIL.modules namespace. These modules let you programmatically collect data and work with Audience Manager objects.
seo-title: DIL Modules
solution: Audience Manager
title: Módulos DIL
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL Implementation
exl-id: 4685bcbb-a63b-4613-bc94-54de9881966e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 3%

---

# Módulos DIL{#dil-modules}

>[!WARNING]
>
>A partir de julio de 2023, Adobe Systems ha interrumpido el desarrollo de la [!DNL Data Integration Library (DIL)] y la [!DNL DIL] extensión.
>
>Los clientes existentes pueden seguir usando sus [!DNL DIL] implementación. Sin embargo, Adobe Systems no se desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes que evalúen [Experience Platform SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) web según su estrategia de recopilación de datos a largo plazo.
>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos después de julio de 2023 deberían usar [Experience Platform SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) web.

Describe los métodos del espacio de `DIL.modules` nombres. Estos módulos permiten recopilar datos mediante programación y trabajar con objetos Audience Manager.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Funciona con [!UICONTROL DIL] para enviar [!DNL Analytics] elementos etiqueta (variables, props, eVars, etc.) a Audience Manager. Devuelve datos en un lista separados por comas. Disponible en la versión 2.6.

**Firma de función:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>Debe colocar este código en la Página *antes de* la `s.t();` función.

<!-- 

r_dil_sc_init.xml

 -->

**Parámetros**

<table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombres </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> names </code> </td> 
   <td colname="col2"> Cadena </td> 
   <td colname="col3"> <p>Matriz de cadenas que contiene variables de Analytics <span class="keyword"> sin enumerar </span> gustar <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code>, etc. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> Objeto </td> 
   <td colname="col3"> <p>Matriz de objetos que contiene variables de Analytics enumeradas <span class="keyword"> gustar props y evars (por ejemplo</span>, , <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>).<code> evar4 </code> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> Número entero </td> 
   <td colname="col3"> <p>Indica el número de nombres iterados que desea devolver. Por ejemplo, para devolver dos props o evars, establezca .<code> maxIndex:2 </code> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> Objeto </td> 
   <td colname="col3"> <p>Un objeto que representa el objeto Analytics <span class="keyword"> </span> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> Objeto </td> 
   <td colname="col3"> <p>Un objeto que representa <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Objeto </td> 
   <td colname="col3"> <p>Opciones adicionales: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>Si no especifica otra cosa, los puntos se sustituyen por el guión bajo predeterminado ( _ ). </p> <p>Por ejemplo <code> s.contextData = {abc.def = '123'} </code>, resultaría en <code> c_contextData_abc_def=123 </code> la llamada de evento cadena de consulta. </p> <p>Esta opción solo está disponible en <span class="wintitle"> DIL </span> versión 5.0 o posterior. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>Por ejemplo, <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> provocaría que la matriz de cadenas se filtrara de la recopilación de datos de datos de contexto. Esta opción excluye la información de identificación personal (PII). </p> </li> 
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

Este código crea un lista de [!DNL Analytics] eventos separados por comas (props, eVars, etc.) si existen valores para ellos.

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

Para rastrear todos los puntos de datos monitoreados [!DNL Analytics] sin la función adicional que se muestra arriba, invoque `siteCatalyst.init` por sí mismo gustar esto:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

La `GA.submitUniversalAnalytics();` función envía datos de Google [!DNL Universal Analytics] a Audience Manager. Esta [!UICONTROL DIL] función está diseñada para funcionar con `analytics.js`, que es la última biblioteca de código para Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] no tiene ningún conocimiento ni control sobre el código de Google `analytics.js` biblioteca. Debe verificar que [!UICONTROL DIL] recopilación de datos sigue funcionando cuando Google lance nuevas versiones de `analytics.js`.
>
>* No puede usarlo `GA.submitUniversalAnalytics();` si todavía está trabajando con el código de seguimiento de análisis heredado de Google (por ejemplo, `ga.js` o `dc.js`). Consulte [GA.init](../dil/dil-modules.md#ga-init) en su lugar.
>

**Firma de función:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Propiedades**

La `GA.submitUniversalAnalytics();` función acepta las siguientes propiedades.

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
   <td colname="col2"> <p>El variable global para su instancia de <span class="keyword"> Google Analytics </span>. Normalmente <code> ga </code> , esto sucede de forma predeterminada, a menos que haya personalizado el <span class="keyword"> código Google Analytics </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>El variable que representa su instancia de <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(Opcional)</i> En el <code> analytics.js </code> biblioteca, el Propiedad interno es el variable <code> 'b' </code>minificado. Este variable contiene <span class="keyword"> Google Analytics </span> datos. </p> <p>Este Propiedad es opcional porque no es necesario configurarlo a menos que Google cambie el nombre de su variable interno. Por ejemplo, si este variable minimizado cambiara a <code> 'a' </code>, llamaría <code> GA.submitUniversalAnalytics(); </code> gustar esto: </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ejemplo**

Recuerde definir primero el objeto, antes de [!DNL Google Analytics] llamar y `ga` [!UICONTROL DIL].`GA.submitUniversalAnalytics();` Su código podría tener un aspecto similar al siguiente:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

La `GA.init()` función envía datos de la versión heredada o obsoleta a [!DNL Google Analytics] Audience Manager.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()`solo funciona con el análisis heredado de Google código de seguimiento, o bien`ga.js`. `dc.js` No puede invocar esta [!UICONTROL DIL] función si utiliza `analytics.js`, que es el código más reciente biblioteca para Google [!DNL Universal Analytics]. [!DNL Audience Manager] clientes que usan [!UICONTROL DIL] y [!DNL Universal Analytics] deberían ver [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics).

**Firma de función:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `_gaq` | Matriz | Matriz que contiene comandos GA. |
| `dilInstance` | Objeto | Objeto que contiene el instancia DIL. |
| `trackVars` | Objeto | *(Opcional)* Un objeto que consiste en el `names` Propiedad. Este Propiedad es una matriz de nombres de comandos de GA que desea rastrear. |

**Llamadas a funciones de GA admitidas**

De manera predeterminada, `GA.init` captura datos de las siguientes funciones:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL crea claves para datos de GA**

Audience Manager acepta datos en forma de pares clave-valor, mientras que GA trabaja con elementos de una matriz. Para trabajar con datos GA, [!UICONTROL DIL] crea un par clave-valor automáticamente y forma una clave gustar esto: `c_ <key name>`. Además, los elementos de las matrices GA aparecen en un orden específico. En consecuencia, debe proporcionar todos los parámetros en ese orden, igualado cuando no contengan datos. [!UICONTROL DIL] asigna claves para los siguientes métodos de GA:

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

Para rastrear todas las métricas de GA monitoreadas sin la función adicional que se muestra arriba, invoque `GA.init` por sí sola gustar esto:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Llamada de evento de muestra**

La URL evento llamada a Audience Manager podría tener un aspecto similar al siguiente:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analytics Code de seguimiento](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Actualización web de Todas las aplicaciones: ga.js/dc.js a análisis.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [Agregar análisis.js a su sitio](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [Referencia de métodos de objeto GA](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)
