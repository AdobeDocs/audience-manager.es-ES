---
description: Recopilar datos enviados desde archivos FLA a Analytics y trabajar con esa información en Audience Manager.
seo-description: Recopilar datos enviados desde archivos FLA a Analytics y trabajar con esa información en Audience Manager.
seo-title: DIL Flash
solution: Audience Manager
title: DIL Flash
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 4%

---


# DIL Flash{#flash-dil}

Recopilar datos enviados desde archivos FLA a Analytics y trabajar con esa información en Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] es una biblioteca [!DNL ActionScript] de código que permite trabajar con datos de reproducción de vídeo en Audience Manager. [!DNL Flash DIL] funciona capturando contenido SWF que la biblioteca de Adobe [!UICONTROL AppMeasurement] pasa a Analytics. [!DNL Flash DIL] envía esos datos al módulo de recopilación de datos [!UICONTROL DIL] JavaScript independiente, que pasa esa información al Audience Manager. Datos de Analytics ( [!UICONTROL Props], [!UICONTROL eVars], eventos, etc.) capturado del [!DNL FLA] archivo está disponible en Audience Manager como características o señales no utilizadas.

## Requisitos para la recopilación de datos DIL de Flash {#requirements}

Requisitos generales de implementación y relacionados con el código.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisitos de implementación**

[!UICONTROL Flash] la recopilación de datos requiere:

* Biblioteca de [!UICONTROL DIL] clases ( `dil.swc`). Obtenga la biblioteca de [!UICONTROL DIL] clases de su contacto de Soluciones de socio.

* Código de recopilación de datos JavaScript [!UICONTROL DIL] en la página.
* [Biblioteca](../dil/dil-flash.md#flash-dil-actionscript) DIL ActionScript cargada en el objeto Flash del que desea recopilar datos.
* La biblioteca de Adobe [!DNL AppMeasurement][!DNL AS] (versión 3.5.2 o posterior) cargó el [!DNL Flash] objeto del que desea recopilar datos.

**Establecer AllowScriptAccess en`Always`o`sameDomain`**

El código `AllowScriptAccess` en HTML que carga un archivo SWF controla la capacidad de realizar el acceso de URL saliente desde el archivo SWF. Cuando configure una integración de [!UICONTROL Flash DIL] datos, asegúrese de que el `AllowScriptAccess` parámetro Flash esté establecido en `always` o `sameDomain`. [!UICONTROL Flash DIL] la recopilación de datos no funcionará si `AllowScriptAccess` está configurada en `never`. Consulte [Control de acceso a secuencias de comandos o página](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)Web de host.

**Ubicación del código de JS[!UICONTROL DIL]**

Intente colocar el módulo de recopilación de datos JS [!UICONTROL DIL] en la página para que se cargue antes del [!DNL FLA] archivo. Cuando el [!DNL FLA] archivo se carga primero, antes de que [!UICONTROL DIL] la recopilación de datos esté lista, puede perder las señales de datos iniciales que [!UICONTROL Flash DIL] envía a ese módulo. Sin embargo, una vez creada la instancia, el módulo de recopilación de datos capturará todos los datos de archivos SWF subsiguientes pasados por [!UICONTROL DIL] [!UICONTROL Flash DIL].

## Datos recopilados por Flash DIL {#data-collected}

[!UICONTROL Flash DIL] captura la vista de página, el seguimiento de vínculos, el seguimiento de medios y otros eventos de vista de medios de la biblioteca de Adobe [!UICONTROL AppMeasurement] .

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventos de Vista de página**

A menos que `s.trackVars`lo especifique lo contrario, [!UICONTROL Flash DIL] recopila los siguientes datos de Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Eventos de seguimiento de vínculos**

A menos que `s.linkTrackVars`lo especifique, [!UICONTROL Flash DIL] recopila los siguientes datos de Adobe [!UICONTROL AppMeasurement]:

* `pe` (Tipo de vínculo de seguimiento llamado)
* `pev1` (Dirección URL del vínculo)
* `pev2`(Texto del vínculo)

**Eventos de seguimiento de medios**

A menos que lo especifique `s.Media.trackVars`, [!UICONTROL Flash DIL] recopila todos los datos enumerados en la sección Eventos de Vista de página.

**Otros puntos de datos**

Los datos de estos parámetros se recopilan de forma predeterminada:

* `mediaName` (Nombre del elemento de medios/vídeo)
* `mediaAdName` (Nombre del anuncio)
* `mediaAdParentName` (Nombre del contenido de medios principal en el que se anida la publicidad)
* `mediaAdParentPod` (El pod o la pausa publicitaria dentro del contenido principal en el que se reproduce el anuncio)
* `mediaAdParentPodPos` (Posición numérica dentro del pod donde se reproduce el anuncio. Se puede reproducir más de un anuncio en un pod.

## Datos DIL de Flash en Audience Manager {#flash-dil-data}

El [!UICONTROL Flash DIL] módulo convierte los datos de Adobe AppMeasurement en características de Audience Manager y señales no utilizadas.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars]y los eventos funcionan como rasgos en el Audience Manager. Las características son pares clave-valor y se utilizan para generar segmentos. Por ejemplo, en una propiedad de Analytics como `c30=foo`, `c30` es la clave (una constante) y `foo` es el valor (una variable).

**Hacer coincidir las características del Audience Manager con las variables de Analytics**

Para utilizar los datos de Analytics pasados por [!UICONTROL Flash DIL], debe crear características de Audience Manager con el prefijo `c_`.

Consulte la tabla para ver ejemplos:

| Elemento Datos de Analytics | Ejemplo de Analytics | Como rasgo Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Datos DIL/Analytics como señales no utilizadas**

Audience Manager acepta Analytics [!UICONTROL Props], [!UICONTROL eVars]y eventos incluso sin la característica correspondiente. En este caso, los datos no están disponibles para la creación de características y aparecen en el informe [Señales](../reporting/dynamic-reports/unused-signals.md) no utilizadas. Para aprovechar al máximo esta información, cree características de Audience Manager que coincidan con los datos de Analytics pasados por la [!UICONTROL Flash DIL] biblioteca.

## Biblioteca de ActionScript DIL de Flash {#flash-dil-actionscript}

Código para que el [!DNL Flash] objeto envíe datos de Analytics al Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Para cada [!DNL Flash] objeto, el código solo admite una instancia de socio ( `d.partner`).
   >
   >
* Requiere la versión 3.5.2 o superior de la biblioteca de Adobe [!UICONTROL AppMeasurement][!DNL AS] .


```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

>[!MORELIKETHIS]
>
>* [Rasgos ](../features/traits/trait-details-page.md)
>* [Señales, rasgos y segmentos](../reference/signal-trait-segment.md)
>* [Pares de clave-valor explicados](../reference/key-value-pairs-explained.md)
>* [Requisitos de prefijo para variables clave](../features/traits/trait-variable-prefixes.md)

