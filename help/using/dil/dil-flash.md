---
description: Recopile datos enviados desde archivos FLA a Analytics y trabaje con esa información en Audience Manager.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: DIL Flash
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 3%

---

# DIL Flash{#flash-dil}

>[!WARNING]
>
>A partir de julio de 2023, el Adobe ha interrumpido el desarrollo del [!DNL Data Integration Library (DIL)] y el [!DNL DIL] extensión.
><br><br>
>Los clientes existentes pueden seguir utilizando su [!DNL DIL] implementación. Sin embargo, el Adobe no se desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes que evalúen [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para su estrategia de recopilación de datos a largo plazo.
><br><br>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos a partir de julio de 2023 deben utilizar [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) en su lugar.

Recopile datos enviados desde archivos FLA a Analytics y trabaje con esa información en Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] es un [!DNL ActionScript] biblioteca de códigos que permite trabajar con datos de reproducción de vídeo en Audience Manager. [!DNL Flash DIL] funciona capturando contenido de SWF en el Adobe [!UICONTROL AppMeasurement] La biblioteca de pasa a Analytics. [!DNL Flash DIL] envía esos datos a la instancia de [!UICONTROL DIL] Módulo de recopilación de datos de JavaScript que pasa esa información a Audience Manager. Datos de Analytics ( [!UICONTROL Props], [!UICONTROL eVars], eventos, etc.) capturado desde el [!DNL FLA] el archivo está disponible en Audience Manager como rasgos o señales no utilizadas.

## Requisitos para la recopilación de datos del DIL de Flash {#requirements}

Requisitos generales de implementación y relacionados con el código.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisitos de implementación**

[!UICONTROL Flash] la recopilación de datos requiere:

* El [!UICONTROL DIL] biblioteca de clases ( `dil.swc`). Obtenga la [!UICONTROL DIL] Biblioteca de clases de su contacto de Soluciones para socios.

* JavaScript [!UICONTROL DIL] código de recopilación de datos en la página.
* [biblioteca de ActionScript del DIL](../dil/dil-flash.md#flash-dil-actionscript) cargado en el objeto de Flash del que desea recopilar datos.
* Adobe [!DNL AppMeasurement] [!DNL AS] La biblioteca (versión 3.5.2 o posterior) cargó el [!DNL Flash] objeto del que desea recopilar datos.

**Establezca AllowScriptAccess en `Always` o`sameDomain`**

El `AllowScriptAccess` en el código de HTML que carga un archivo de SWF controla la capacidad de realizar el acceso de URL saliente desde el archivo de SWF. Al configurar un [!UICONTROL Flash DIL] integración de datos, compruebe el Flash `AllowScriptAccess` El parámetro se ha establecido en `always` o `sameDomain`. [!UICONTROL Flash DIL] la recopilación de datos no funcionará si `AllowScriptAccess` se establece en `never`. Consulte [Controlar el acceso a las secuencias de comandos o a la página Web del host](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] Colocación de código**

Intente colocar el JS [!UICONTROL DIL] módulo de recopilación de datos en la página para que se cargue antes de que [!DNL FLA] archivo. Si la variable [!DNL FLA] el archivo se carga primero, antes de [!UICONTROL DIL] la recopilación de datos está lista, puede perder las señales de datos iniciales que [!UICONTROL Flash DIL] envía a ese módulo. Sin embargo, una vez creada la instancia, la variable [!UICONTROL DIL] el módulo de recopilación de datos capturará todos los datos de archivo del SWF subsiguientes que haya pasado [!UICONTROL Flash DIL].

## Datos recopilados por el DIL de Flash {#data-collected}

[!UICONTROL Flash DIL] captura la vista de página, el seguimiento de vínculos, el seguimiento de medios y otros eventos de vista de medios desde el Adobe [!UICONTROL AppMeasurement] biblioteca.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventos de vista de página**

A menos que especifique lo contrario `s.trackVars`, [!UICONTROL Flash DIL] recopila los datos siguientes de Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Eventos de seguimiento de vínculos**

A menos que especifique lo contrario `s.linkTrackVars`, [!UICONTROL Flash DIL] recopila los datos siguientes del Adobe [!UICONTROL AppMeasurement]:

* `pe` (Tipo de vínculo de seguimiento llamado)
* `pev1` (Dirección URL del vínculo)
* `pev2`(Texto del vínculo)

**Eventos de seguimiento de medios**

A menos que especifique lo contrario `s.Media.trackVars`, [!UICONTROL Flash DIL] recopila todos los datos enumerados en la sección Eventos de vista de página.

**Otros puntos de datos**

Los datos de estos parámetros se recopilan de forma predeterminada:

* `mediaName` (Nombre del elemento de medios/vídeo)
* `mediaAdName` (Nombre del anuncio)
* `mediaAdParentName` (Nombre del contenido multimedia principal bajo el que está anidado el anuncio)
* `mediaAdParentPod` (El pod o el salto de anuncio dentro del contenido primario donde se reproduce el anuncio)
* `mediaAdParentPodPos` (Posición numérica dentro de la secuencia en la que se reproduce el anuncio. Se puede reproducir más de un anuncio dentro de un pod.

## Datos del DIL de Flash en Audience Manager {#flash-dil-data}

El [!UICONTROL Flash DIL] : convierte los datos de Adobe AppMeasurement en rasgos de Audience Manager y señales no utilizadas.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars]Los eventos, y funcionan como rasgos en Audience Manager. Los rasgos son pares clave-valor y se utilizan para generar segmentos. Por ejemplo, en una prop de Analytics como `c30=foo`, `c30` es la clave (una constante) y `foo` es el valor (una variable).

**Igualar características de Audience Manager con variables de Analytics**

Para utilizar los datos de Analytics pasados por [!UICONTROL Flash DIL], debe crear rasgos Audience Manager que tengan el valor clave con el prefijo `c_`.

Consulte la tabla para ver ejemplos:

| Elemento de datos de Analytics | Ejemplo de Analytics | Como rasgo Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Datos de DIL/Analytics como señales no utilizadas**

El Audience Manager acepta Analytics [!UICONTROL Props], [!UICONTROL eVars]y eventos incluso sin un rasgo correspondiente. En este caso, los datos no están disponibles para la creación de rasgos y aparecen en [Informe Señales no utilizadas](../reporting/dynamic-reports/unused-signals.md) en su lugar. Para aprovechar al máximo esta información, cree rasgos de Audience Manager que coincidan con los datos de Analytics pasados por el [!UICONTROL Flash DIL] biblioteca.

## Biblioteca de ActionScripts del DIL de Flash {#flash-dil-actionscript}

Código para su [!DNL Flash] para enviar datos de Analytics al Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Para cada [!DNL Flash] , el código admite una instancia de socio ( `d.partner`) únicamente.
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
>* [Rasgos ](../features/traits/trait-details-page.md)
>* [Señales, rasgos y segmentos](../reference/signal-trait-segment.md)
>* [Pares de clave-valor explicados](../reference/key-value-pairs-explained.md)
>* [Requisitos de prefijo para variables clave](../features/traits/trait-variable-prefixes.md)
