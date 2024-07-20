---
description: Recopile datos enviados desde archivos FLA a Analytics y trabaje con esa información en Audience Manager.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: DIL Flash
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 2%

---

# DIL Flash{#flash-dil}

>[!WARNING]
>
>A partir de julio de 2023, el Adobe ha interrumpido el desarrollo de la extensión [!DNL Data Integration Library (DIL)] y [!DNL DIL].
>
>Los clientes existentes pueden seguir usando su implementación de [!DNL DIL]. Sin embargo, el Adobe no se desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes que evalúen [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para su estrategia de recopilación de datos a largo plazo.
>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos a partir de julio de 2023 deben utilizar [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) en su lugar.

Recopile datos enviados desde archivos FLA a Analytics y trabaje con esa información en Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] es una biblioteca de códigos [!DNL ActionScript] que le permite trabajar con datos de reproducción de vídeo en Audience Manager. [!DNL Flash DIL] funciona capturando contenido de SWF que la biblioteca de Adobe [!UICONTROL AppMeasurement] pasa a Analytics. [!DNL Flash DIL] envía esos datos al módulo de recopilación de datos de JavaScript [!UICONTROL DIL] independiente, que pasa esa información al Audience Manager. Datos de Analytics ( [!UICONTROL Props], [!UICONTROL eVars], eventos, etc.) capturado del archivo [!DNL FLA] está disponible en el Audience Manager como rasgos o señales no utilizadas.

## Requisitos para la recopilación de datos del DIL de Flash {#requirements}

Requisitos generales de implementación y relacionados con el código.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisitos de implementación**

La recopilación de datos de [!UICONTROL Flash] requiere:

* La biblioteca de clases [!UICONTROL DIL] (`dil.swc`). Obtenga la biblioteca de clases [!UICONTROL DIL] de su contacto de Soluciones para socios.

* Código de recopilación de datos [!UICONTROL DIL] de JavaScript en la página.
* [Biblioteca de ActionScripts de DIL](../dil/dil-flash.md#flash-dil-actionscript) cargada en el objeto de Flash del que desea recopilar datos.
* La biblioteca [!DNL AS] del Adobe [!DNL AppMeasurement] (versión 3.5.2 o posterior) cargó el objeto [!DNL Flash] del que desea recopilar datos.

**Establecer AllowScriptAccess en `Always` o`sameDomain`**

El `AllowScriptAccess` del código de HTML que carga un archivo de SWF controla la capacidad de realizar el acceso de URL saliente desde el archivo de SWF. Cuando configure una integración de datos de [!UICONTROL Flash DIL], asegúrese de que el parámetro de Flash `AllowScriptAccess` esté establecido en `always` o `sameDomain`. La recopilación de datos de [!UICONTROL Flash DIL] no funcionará si `AllowScriptAccess` está establecido en `never`. Consulte [Controlar el acceso a los scripts o a la página web del host](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**Colocación de código [!UICONTROL DIL] JS**

Intente colocar el módulo de recopilación de datos JS [!UICONTROL DIL] en la página para que se cargue antes del archivo [!DNL FLA]. Cuando el archivo [!DNL FLA] se carga primero, antes de que la recopilación de datos de [!UICONTROL DIL] esté lista, puede perder las señales de datos iniciales que [!UICONTROL Flash DIL] envía a ese módulo. Sin embargo, una vez creada la instancia, el módulo de recopilación de datos [!UICONTROL DIL] capturará todos los datos de archivos de SWF subsiguientes pasados por [!UICONTROL Flash DIL].

## Datos recopilados por el DIL de Flash {#data-collected}

[!UICONTROL Flash DIL] captura la vista de página, el seguimiento de vínculos, el seguimiento de medios y otros eventos de vista de medios de la biblioteca [!UICONTROL AppMeasurement] de Adobe.

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

* `pe` (tipo de vínculo de seguimiento llamado)
* `pev1` (URL de vínculo)
* `pev2`(texto de vínculo)

**Eventos de seguimiento de medios**

A menos que `s.Media.trackVars` especifique lo contrario, [!UICONTROL Flash DIL] recopila todos los datos enumerados en la sección Eventos de vista de página.

**Otros puntos de datos**

Los datos de estos parámetros se recopilan de forma predeterminada:

* `mediaName` (nombre del elemento de medios/vídeo)
* `mediaAdName` (nombre del anuncio)
* `mediaAdParentName` (nombre del contenido multimedia principal bajo el que está anidado el anuncio)
* `mediaAdParentPod` (pod o pausa publicitaria dentro del contenido primario donde se reproduce el anuncio)
* `mediaAdParentPodPos` (La posición numérica dentro del pod donde se reproduce el anuncio. Se puede reproducir más de un anuncio dentro de un pod.

## Datos del DIL de Flash en Audience Manager {#flash-dil-data}

El módulo [!UICONTROL Flash DIL] convierte los datos de Adobe AppMeasurement en rasgos de Audience Manager y señales no utilizadas.

<!-- 

c_flash_dil_in_aam.xml

 -->

Los eventos [!UICONTROL Props], [!UICONTROL eVars] y de Analytics funcionan como rasgos de un Audience Manager. Los rasgos son pares clave-valor y se utilizan para generar segmentos. Por ejemplo, en una propiedad de Analytics como `c30=foo`, `c30` es la clave (una constante) y `foo` es el valor (una variable).

**Igualar características de Audience Manager con variables de Analytics**

Para usar los datos de Analytics pasados por [!UICONTROL Flash DIL], debe crear características de Audience Manager que tengan el valor clave con el prefijo `c_`.

Consulte la tabla para ver ejemplos:

| Elemento de datos de Analytics | Ejemplo de Analytics | Como rasgo Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Datos de DIL/Analytics como señales sin usar**

El Audience Manager acepta eventos [!UICONTROL Props], [!UICONTROL eVars] y de Analytics incluso sin el rasgo correspondiente. En este caso, los datos no están disponibles para la creación de características y aparecen en el informe [Señales no utilizadas](../reporting/dynamic-reports/unused-signals.md). Para aprovechar al máximo esta información, cree características de Audience Manager que coincidan con los datos de Analytics pasados por la biblioteca [!UICONTROL Flash DIL].

## Biblioteca de ActionScripts del DIL de Flash {#flash-dil-actionscript}

Código del objeto [!DNL Flash] para enviar datos de Analytics al Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Para cada objeto [!DNL Flash], el código solo admite una instancia de socio ( `d.partner`).
>
>* Requiere el Adobe [!UICONTROL AppMeasurement] [!DNL AS] versión de biblioteca 3.5.2 o superior.

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
>* [Características](../features/traits/trait-details-page.md)
>* [Señales, rasgos y segmentos](../reference/signal-trait-segment.md)
>* [Pares de clave-valor explicados](../reference/key-value-pairs-explained.md)
>* [Requisitos de prefijo para variables clave](../features/traits/trait-variable-prefixes.md)
