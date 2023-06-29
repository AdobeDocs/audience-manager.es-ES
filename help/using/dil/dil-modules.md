---
description: Describe los métodos del espacio de nombres DIL.modules. Estos módulos le permiten recopilar datos mediante programación y trabajar con objetos de Audience Manager.
seo-description: Describes methods in the DIL.modules namespace. These modules let you programmatically collect data and work with Audience Manager objects.
seo-title: DIL Modules
solution: Audience Manager
title: Módulos DIL
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL Implementation
exl-id: 4685bcbb-a63b-4613-bc94-54de9881966e
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 4%

---

# Módulos DIL{#dil-modules}

>[!WARNING]
>
>A partir de julio de 2023, el Adobe ha interrumpido el desarrollo del [!DNL Data Integration Library (DIL)] y el [!DNL DIL] extensión.
><br>
>Los clientes existentes pueden seguir utilizando su [!DNL DIL] implementación. Sin embargo, el Adobe no se desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes que evalúen [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para su estrategia de recopilación de datos a largo plazo.
><br>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos a partir de julio de 2023 deben utilizar [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) en su lugar.

Describe los métodos en la `DIL.modules` namespace. Estos módulos le permiten recopilar datos mediante programación y trabajar con objetos de Audience Manager.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Funciona con [!UICONTROL DIL] para enviar [!DNL Analytics] elementos de etiqueta (variables, props, eVars, etc.) al Audience Manager. Devuelve datos en una lista separada por comas. Disponible en la versión 2.6.

**Firma de función:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>Debe colocar este código en la página *antes* el `s.t();` función.

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
   <td colname="col3"> <p>Matriz de cadenas que contiene cadenas no enumeradas <span class="keyword"> Analytics </span> variables como <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code>, etc. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> Objeto </td> 
   <td colname="col3"> <p>Matriz de objetos que contiene elementos enumerados <span class="keyword"> Analytics </span> variables como props y evars (por ejemplo, <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> Número entero </td> 
   <td colname="col3"> <p>Indica cuántos nombres iterados desea devolver. Por ejemplo, para devolver dos props o evars, establezca <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> Objeto </td> 
   <td colname="col3"> <p>Un objeto que representa el <span class="keyword"> Analytics </span> objeto. </p> </td> 
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
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>Si no especifica nada más, los puntos se sustituyen por el guion bajo predeterminado ( _ ). </p> <p>Por ejemplo <code> s.contextData = {abc.def = '123'} </code>resultaría en <code> c_contextData_abc_def=123 </code> en la cadena de consulta de llamada de evento. </p> <p>Esta opción solo está disponible en <span class="wintitle"> DIL </span> versión 5.0 o posterior. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>Por ejemplo, <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> Esto haría que la matriz de cadenas se filtrara de la recopilación de datos de datos de contexto. Esta opción excluye la información de identificación personal (PII). </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Datos capturados por siteCatalyst.init**

Esta función devuelve detalles sobre lo siguiente [!DNL Analytics] propiedades:

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

Este código crea una lista separada por comas de [!DNL Analytics] eventos (props, eVars, etc.) si existen valores para ellos.

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

Para realizar un seguimiento de todos los [!DNL Analytics] puntos de datos sin la función adicional mostrada anteriormente, invoque `siteCatalyst.init` por sí solo así:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

El `GA.submitUniversalAnalytics();` Google envía datos desde la función de [!DNL Universal Analytics] al Audience Manager. Esta [!UICONTROL DIL] está diseñada para trabajar con `analytics.js`, que es la biblioteca de códigos más reciente para Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] no tiene ninguna perspectiva ni control sobre Google `analytics.js` biblioteca de códigos. Debe comprobar que [!UICONTROL DIL] la recopilación de datos sigue funcionando si Google publica nuevas versiones de `analytics.js`.
>
>* No puede utilizar `GA.submitUniversalAnalytics();` si sigue trabajando con el código de seguimiento de analytics heredado de Google (por ejemplo, `ga.js` o `dc.js`). Consulte [GA.init](../dil/dil-modules.md#ga-init) en su lugar.
>

**Firma de función:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Propiedades**

El `GA.submitUniversalAnalytics();` La función acepta las siguientes propiedades.

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
   <td colname="col2"> <p>La variable global para la instancia de <span class="keyword"> Google Analytics </span>. Esto suele ser <code> ga </code> de forma predeterminada, a menos que haya personalizado su <span class="keyword"> Google Analytics </span> código. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>La variable que representa su instancia de <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(Opcional)</i> En el <code> analytics.js </code> , la propiedad interna es la variable minificada <code> 'b' </code>. Esta variable contiene <span class="keyword"> Google Analytics </span> datos. </p> <p>Esta propiedad es opcional porque no es necesario configurarla a menos que Google cambie el nombre de su variable interna. Por ejemplo, si esta variable minificada cambió a <code> 'a' </code>, llamaría a <code> GA.submitUniversalAnalytics(); </code> así: </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ejemplo**

Recuerde definir la variable [!DNL Google Analytics] `ga` primero, antes de llamar a [!UICONTROL DIL] y `GA.submitUniversalAnalytics();`. Su código podría ser similar al siguiente:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

El `GA.init()` envía datos desde la versión heredada o obsoleta de [!DNL Google Analytics] al Audience Manager.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` solo funciona con el código de seguimiento de analytics heredado de Google, `ga.js` o `dc.js`. No puede invocar esto [!UICONTROL DIL] función si utiliza `analytics.js`, que es la biblioteca de códigos más reciente para Google [!DNL Universal Analytics]. [!DNL Audience Manager] clientes que utilizan [!UICONTROL DIL] y [!DNL Universal Analytics] debería ver [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics).

**Firma de función:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `_gaq` | Matriz | Matriz que contiene comandos de GA. |
| `dilInstance` | Objeto | Un objeto que contiene la instancia de DIL. |
| `trackVars` | Objeto | *(Opcional)* Un objeto que consta de la variable `names` propiedad. Esta propiedad es una matriz de nombres de comandos de GA que desea rastrear. |

**Llamadas a funciones GA compatibles**

De forma predeterminada, `GA.init` captura datos de las siguientes funciones:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL crea claves para los datos de GA**

El Audience Manager acepta datos en forma de pares clave-valor mientras que GA trabaja con elementos en una matriz. Para trabajar con datos de GA, [!UICONTROL DIL] crea automáticamente un par clave-valor y forma una clave como esta: `c_ <key name>`. Además, los elementos de las matrices de GA aparecen en un orden específico. Como resultado, debe proporcionar todos los parámetros en ese orden, incluso cuando no contengan datos. [!UICONTROL DIL] asigna claves para los siguientes métodos de GA:

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

Para realizar un seguimiento de todas las métricas de GA monitorizadas sin la función adicional mostrada anteriormente, invoque `GA.init` por sí solo así:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Ejemplo de llamada de evento**

La llamada de evento de URL al Audience Manager puede tener un aspecto similar al siguiente:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Código de seguimiento de Google Analytics](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Actualización web completa: ga.js/dc.js a analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [Añadir analytics.js a su sitio](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [Referencia de métodos de objeto ga](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)
