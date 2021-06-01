---
description: Recopile datos enviados desde archivos FLA a Analytics y trabaje con esa información en Audience Manager.
seo-description: Recopile datos enviados desde archivos FLA a Analytics y trabaje con esa información en Audience Manager.
seo-title: DIL Flash
solution: Audience Manager
title: DIL Flash
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: Implementación del DIL
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 4%

---

# DIL Flash{#flash-dil}

Recopile datos enviados desde archivos FLA a Analytics y trabaje con esa información en Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] es una biblioteca de  [!DNL ActionScript] código que le permite trabajar con datos de reproducción de vídeo en Audience Manager. [!DNL Flash DIL] funciona capturando contenido SWF que la  [!UICONTROL AppMeasurement] biblioteca de Adobe pasa a Analytics. [!DNL Flash DIL] envía esos datos al módulo de recopilación de datos de  [!UICONTROL DIL] JavaScript independiente, que pasa esa información al Audience Manager. Datos de Analytics ( [!UICONTROL Props], [!UICONTROL eVars], eventos, etc.) capturado del archivo [!DNL FLA] está disponible en Audience Manager como rasgos o señales no utilizadas.

## Requisitos para la recopilación de datos del DIL de Flash {#requirements}

Implementación general y requisitos relacionados con el código.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisitos de implementación**

[!UICONTROL Flash] la recopilación de datos requiere:

* La biblioteca de clases [!UICONTROL DIL] ( `dil.swc`). Obtenga la biblioteca de clases [!UICONTROL DIL] de su contacto Soluciones para socios.

* Código de recopilación de datos JavaScript [!UICONTROL DIL] en la página.
* [biblioteca de ActionScript de DIL ](../dil/dil-flash.md#flash-dil-actionscript) cargada en el objeto de Flash del que desea recopilar datos.
* La biblioteca [!DNL AppMeasurement] [!DNL AS] de Adobe (versión 3.5.2 o posterior) cargó el objeto [!DNL Flash] del que desea recopilar los datos.

**Establezca AllowScriptAccess como  `Always` o`sameDomain`**

El `AllowScriptAccess` en código HTML que carga un archivo SWF controla la capacidad de realizar el acceso de URL saliente desde el archivo SWF. Cuando configure una integración de datos [!UICONTROL Flash DIL], asegúrese de que el parámetro de Flash `AllowScriptAccess` esté establecido en `always` o `sameDomain`. [!UICONTROL Flash DIL] la recopilación de datos no funcionará si  `AllowScriptAccess` está configurada en  `never`. Consulte [Control de acceso a scripts o Host Web Page](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**Colocación del  [!UICONTROL DIL] código JS**

Intente colocar el módulo de recopilación de datos JS [!UICONTROL DIL] en la página para que se cargue antes que el archivo [!DNL FLA]. Cuando el archivo [!DNL FLA] se carga primero, antes de que [!UICONTROL DIL] la recopilación de datos esté lista, puede perder las señales de datos iniciales que [!UICONTROL Flash DIL] envía a ese módulo. Sin embargo, una vez creada la instancia, el módulo de recopilación de datos [!UICONTROL DIL] capturará todos los datos de archivos SWF subsiguientes pasados por [!UICONTROL Flash DIL].

## Datos recopilados por el DIL de Flash {#data-collected}

[!UICONTROL Flash DIL] captura la vista de página, el seguimiento de vínculos, el seguimiento de medios y otros eventos de vistas de medios de la  [!UICONTROL AppMeasurement] biblioteca de Adobe.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventos de vista de página**

A menos que `s.trackVars` especifique lo contrario, [!UICONTROL Flash DIL] recopila los siguientes datos de Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Eventos de seguimiento de vínculos**

A menos que `s.linkTrackVars` especifique lo contrario, [!UICONTROL Flash DIL] recopila los siguientes datos del Adobe [!UICONTROL AppMeasurement]:

* `pe` (Tipo de vínculo de seguimiento llamado)
* `pev1` (Dirección URL del vínculo)
* `pev2`(Texto de vínculo)

**Eventos de seguimiento de contenidos**

A menos que `s.Media.trackVars` especifique lo contrario, [!UICONTROL Flash DIL] recopila todos los datos enumerados en la sección Eventos de vista de página .

**Otros puntos de datos**

Los datos de estos parámetros se recopilan de forma predeterminada:

* `mediaName` (Nombre del elemento de medio/vídeo)
* `mediaAdName` (Nombre del anuncio)
* `mediaAdParentName` (Nombre del contenido multimedia principal en el que está anidado el anuncio)
* `mediaAdParentPod` (La secuencia o pausa publicitaria dentro del contenido principal en la que se reproduce el anuncio)
* `mediaAdParentPodPos` (Posición numérica dentro del pod donde se reproduce el anuncio. Se puede reproducir más de un anuncio en un pod.

## Datos del DIL de Flash en el Audience Manager {#flash-dil-data}

El módulo [!UICONTROL Flash DIL] convierte los datos de Adobe AppMeasurement en características de Audience Manager y señales no utilizadas.

<!-- 

c_flash_dil_in_aam.xml

 -->

Los eventos [!UICONTROL Props], [!UICONTROL eVars] y de Analytics funcionan como características en el Audience Manager. Los rasgos son pares clave-valor y se utilizan para generar segmentos. Por ejemplo, en una prop de Analytics como `c30=foo`, `c30` es la clave (una constante) y `foo` es el valor (una variable).

**Hacer coincidir características de Audience Manager con variables de Analytics**

Para utilizar los datos de Analytics pasados por [!UICONTROL Flash DIL], debe crear características de Audience Manager que tengan el valor clave con el prefijo `c_`.

Consulte la tabla para ver ejemplos:

| Elemento de datos de Analytics | Ejemplo de Analytics | Como rasgo de Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Datos de DIL/Analytics como señales no utilizadas**

El Audience Manager acepta eventos [!UICONTROL Props], [!UICONTROL eVars] y de Analytics incluso sin la característica correspondiente. En este caso, los datos no están disponibles para la creación de características y aparecen en el [Informe de señales no utilizadas](../reporting/dynamic-reports/unused-signals.md) en su lugar. Para sacar el máximo partido a esta información, cree características de Audience Manager que coincidan con los datos de Analytics pasados por la biblioteca [!UICONTROL Flash DIL].

## Biblioteca de ActionScripts del DIL de Flash {#flash-dil-actionscript}

Código del objeto [!DNL Flash] para enviar datos de Analytics al Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Para cada objeto [!DNL Flash], el código solo admite una instancia de socio ( `d.partner`).
   >
   >
* Requiere la versión 3.5.2 o superior de la biblioteca [!UICONTROL AppMeasurement] [!DNL AS] de Adobe.


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
* [Señales, rasgos y segmentos](../reference/signal-trait-segment.md)
* [Pares de clave-valor explicados](../reference/key-value-pairs-explained.md)
* [Requisitos de prefijo para variables clave](../features/traits/trait-variable-prefixes.md)

