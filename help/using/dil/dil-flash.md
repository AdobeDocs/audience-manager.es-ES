---
description: Recopile datos enviados desde archivos FLA a Analytics y trabaje con dicha información en Audience Manager.
seo-description: Recopile datos enviados desde archivos FLA a Analytics y trabaje con dicha información en Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833 cfd -768 e -4 b 16-95 c 5-debd 8411 df 38
translation-type: tm+mt
source-git-commit: 49fff90fa1330c59360e16f2a56e8fba7d4c43dc

---


# Flash DIL{#flash-dil}

Recopile datos enviados desde archivos FLA a Analytics y trabaje con dicha información en Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] es una biblioteca [!DNL ActionScript] de código que permite trabajar con datos de reproducción de vídeo en Audience Manager. [!DNL Flash DIL] funciona capturando contenido SWF que [!UICONTROL AppMeasurement] la biblioteca de Adobe pasa a Analytics. [!DNL Flash DIL] envía esos datos al módulo de [!UICONTROL DIL] recopilación de datos JavaScript independiente, que pasa dicha información a Audience Manager. Analytics data ( [!UICONTROL Props], [!UICONTROL eVars], events, etc.) captured from the [!DNL FLA] file is available in Audience Manager as traits or unused signals.

## Requirements for Flash DIL Data Collection {#requirements}

Implementación general y requisitos relacionados con el código.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisitos de implementación**

[!UICONTROL Flash] la recopilación de datos requiere:

* The [!UICONTROL DIL] class library ( `dil.swc`). Obtain the [!UICONTROL DIL] class library from your Partner Solutions contact.

* JavaScript [!UICONTROL DIL] data collection code on the page.
* [DIL actionscript library](../dil/dil-flash.md#flash-dil-actionscript) loaded in the Flash object you want to collect data from.
* Adobe [!DNL AppMeasurement] [!DNL AS] library (version 3.5.2, or later) loaded the [!DNL Flash] object you want to collect data from.

**Establecer allowscriptaccess como`Always`o`sameDomain`**

The `AllowScriptAccess` in HTML code that loads a SWF file controls the ability to perform outbound URL access from within the SWF file. When you configure a [!UICONTROL Flash DIL] data integration, make sure the Flash `AllowScriptAccess` parameter is set to `always` or `sameDomain`. [!UICONTROL Flash DIL] la recopilación de datos no funcionará si `AllowScriptAccess` se establece `never`en. See [Control Access to Scripts or Host Web Page](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**Ubicación[!UICONTROL DIL]del código JS**

Try to place the JS [!UICONTROL DIL] data collection module on the page so it loads before the [!DNL FLA] file. When the [!DNL FLA] file loads first, before [!UICONTROL DIL] data collection is ready, you can miss the initial data signals that [!UICONTROL Flash DIL] sends to that module. However, once instantiated, the [!UICONTROL DIL] data collection module will capture all subsequent SWF file data passed in by [!UICONTROL Flash DIL].

## Data Collected by Flash DIL {#data-collected}

[!UICONTROL Flash DIL] captura la vista de página, el seguimiento de vínculos, el seguimiento de medios y otros eventos de vista de medios de [!UICONTROL AppMeasurement] la biblioteca de Adobe.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventos de vista de página**

Unless specified otherwise by `s.trackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Eventos de seguimiento de vínculos**

Unless specified otherwise by `s.linkTrackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe [!UICONTROL AppMeasurement]:

* `pe` (Tipo de vínculo de seguimiento llamado)
* `pev1` (Dirección URL del vínculo)
* `pev2`(Texto de vínculo)

**Eventos de seguimiento de medios**

Unless specified otherwise by `s.Media.trackVars`, [!UICONTROL Flash DIL] collects all the data enumerated in the Page View Events section.

**Otros puntos de datos**

Los datos de estos parámetros se recopilan de forma predeterminada:

* `mediaName` (Nombre del elemento de medios/vídeo)
* `mediaAdName` (Nombre del anuncio)
* `mediaAdParentName` (Nombre del contenido de medios principal en el que está anidada la publicidad)
* `mediaAdParentPod` (El pod o pausa publicitaria dentro del contenido principal donde se reproduce la publicidad)
* `mediaAdParentPodPos` (Posición numérica dentro de la secuencia en la que se reproduce la publicidad. Se puede reproducir más de una publicidad dentro de un pod.

>[!MORE_ LIKE_ THIS]
>
>* [Guía de implementación de Flash, Flex y OSMF de appmeasurement](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)


## Flash DIL Data in Audience Manager {#flash-dil-data}

The [!UICONTROL Flash DIL] module turns Adobe AppMeasurement data into Audience Manager traits and unused signals.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars], and events work like traits in Audience Manager. Las características son pares clave-valor y se utilizan para crear segmentos. For example, in an Analytics prop like `c30=foo`, `c30` is the key (a constant) and `foo` is the value (a variable).

**Coincidencia de características de Audience Manager con variables de Analytics**

To use the Analytics data passed by [!UICONTROL Flash DIL], you should create Audience Manager traits that have the key value prefixed with `c_`.

Consulte la tabla para ver ejemplos:

| Elemento de datos de Analytics | Ejemplo de Analytics | Como característica de Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Datos DIL/Analytics como señales no utilizadas**

Audience Manager accepts Analytics [!UICONTROL Props], [!UICONTROL eVars], and events even without a corresponding trait. In this case, the data is unavailable for trait creation and appears in the [Unused Signals report](../reporting/dynamic-reports/unused-signals.md) instead. To make the most of this information, create Audience Manager traits that match the Analytics data passed in by the [!UICONTROL Flash DIL] library.

>[!MORE_ LIKE_ THIS]
>
>* [Características](../features/traits/trait-details-page.md)
>* [Señales, características y segmentos](../reference/signal-trait-segment.md)
>* [Pares de clave-valor explicados](../reference/key-value-pairs-explained.md)
>* [Requisitos de prefijo para variables clave](../features/traits/trait-variable-prefixes.md)


## Flash DIL ActionScript Library {#flash-dil-actionscript}

Code for your [!DNL Flash] object to send Analytics data to Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* For each [!DNL Flash] object, the code supports one partner instance ( `d.partner`) only.
   >
   >
* Requires the Adobe [!UICONTROL AppMeasurement] [!DNL AS] library version 3.5.2 or higher.
>



```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

