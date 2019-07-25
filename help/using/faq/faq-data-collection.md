---
description: Preguntas y problemas comunes sobre la integración de datos y la integración.
seo-description: Preguntas y problemas comunes sobre la integración de datos y la integración.
seo-title: Preguntas frecuentes sobre la integración de productos y recopilación de datos
solution: Audience Manager
title: Preguntas frecuentes sobre la integración de productos y recopilación de datos
uuid: fa 8 e 79 f 4-99 cb -41 fd -8 a 85-d 4 f 92 d 03 c 7 a 5
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Data Collection and Product Integration FAQ{#data-collection-and-product-integration-faq}

Preguntas y problemas comunes sobre la integración de datos y la integración.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**¿Cómo puedo diferenciar el tráfico entrante del[!UICONTROL DCS]tráfico en las exportaciones de archivos[!UICONTROL DCS]de registro?**

Traits onboarded via [!UICONTROL Inbound] are populated by [!UICONTROL Inbound] the same way they get populated by [!UICONTROL DCS]. There are a few different ways to tell that traffic came from [!UICONTROL Inbound]:

* La IP remota se establecerá en 68.67.173.18
* Domainid se definirá en 5325
* La región se configurará en 0

<br> 

**Can you with a list of IP address I can whitelist for dpm. demdex. net?**

Desafortunadamente, no podemos. These IPs are assigned dynamically, by geographic region, through [!DNL Amazon Web Services]. As a result, [!DNL Audience Manager] does not control the range of IPs that can be assigned to this address.

<br> 

**¿Puede proporcionarme una dirección IP que pueda incluir en su servidor FTP entrante y saliente?**

Sí, véase a continuación.

| Elemento | Dirección |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**¿Cuáles son los requisitos de carga de código y de carga de página para una[!UICONTROL DIL]integración de datos/[!DNL Analytics]datos?**

To bring [!DNL Analytics] data into [!DNL Audience Manager], load [!UICONTROL DIL] after the `s_code` module but *before* the `s.t()` function. Por ejemplo, coloque el código o asegúrese de que se carga en este orden:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager][!UICONTROL DIL] módulo

3. [!DNL Analytics]`s.t()` function

As a best practice, set up your [!DNL Audience Manager]- [!DNL Analytics] integration with either of these 2 methods:

* Put [!UICONTROL DIL] directly in the `s_code`.

* Serve [!UICONTROL DIL] and the `s_code` through [!DNL Adobe Launch] or [!DNL Adobe DTM].

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**¿Por qué faltan[!DNL Analytics]mis variables en una llamada[!DNL Audience Manager]de evento?**

Esto suele ocurrir cuando:

* You serve [!UICONTROL DIL] through a tag management system that loads it asynchronously with other code elements on the page.
* The `s.t()` function loads before [!UICONTROL DIL].

<br> 

**¿Qué versiones de[!DNL Analytics]trabajo con[!UICONTROL DIL]?**

You must use [!DNL Analytics] version 20.2 (or higher) and the [!DNL Adobe AppMeasurement AS] library version 3.5.2 (or higher) to work with [!UICONTROL DIL]. If you don't know your [!DNL Analytics] or [!DNL AppMeasurement] version, check the [!DNL Analytics] call that gets made from the page. Información de la versión que se muestra a continuación:

This customer uses [!DNL Analytics] version 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

This customer uses [!DNL AppMeasurement] version 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**¿Puedo recopilar datos de página si no soy[!DNL Analytics]cliente?**

Sí. The [!UICONTROL DIL] module helps you collect page data even if you're not using [!DNL Analytics]. When set up properly, [!UICONTROL DIL] can capture data from and about:

* Etiquetas meta
* Direcciones URL y encabezados URL
* Tipos de motores de búsqueda
* Palabras clave

Additionally, clients can deploy a simple onsite object and populate it with key-value pairs that you want [!UICONTROL DIL] to collect data on. This lets you add and remove specific audience data points on your site without any [!DNL Audience Management] updates. Work with your Partner Solutions representative to properly set this up and ensure the [!DNL DIL] module references the page object correctly.

<br> 

**[!UICONTROL DIL]¿Pueden recopilarse datos[!DNL Google Analytics]?**

Sí. [!UICONTROL DIL] puede recopilar algunos [!DNL Google Analytics] elementos (GA) y pasar esos datos a [!DNL Audience Manager]. Consulte:

* [GA. submituniversalanalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA. init](../dil/dil-modules.md#ga-init)

<br> 

**¿Puedo obtener datos sin procesar y[!DNL Audience Manager]cuán granular es?**

Yes, [!DNL Audience Manager] can provide you with data collected for users we've seen on your inventory. Esto incluye:

* The unique user ID (UUID) assigned by [!DNL Audience Manager]
* ID de características y segmentos
* Señales no utilizadas
* Marcas de hora
* Direcciones URL de página

<br> 

**Deseo recopilar datos en un sitio y dirigir a los usuarios a través de DFP en un sitio diferente. Do I need to deploy code on the other property if I don't want to collect data from that location?**

No. Si la recopilación de datos en el segundo sitio no es necesaria, no es necesario implementar DIL allí. Siempre que tenga acceso al inventario en el segundo sitio a través de DFP, puede utilizar la recopilación de datos desde el sitio inicial y segmentar por medio de DFP.

<br> 

**¿Cuál es el mejor proveedor de datos de terceros?**

Cada proveedor aporta algo único a la tabla, por lo que la respuesta depende de lo que está buscando. Podemos habilitar los informes superpuestos (sin coste) para ayudarle a comprender qué proveedor puede funcionar mejor.

<br> 

**¿Cómo[!DNL Audience Manager]establece las cookies y pasa a DFP?**

[!DNL Audience Manager] establece 2 cookies: Uno envía variables de segmentos a la etiqueta de anuncio DFP y la otra define nuestro ID de usuario exclusivo (UUID), que también es leído por DFP. Agregar el UUID a la etiqueta de publicidad significa que podemos realizar informes de nivel de usuario y detección de audiencia.

<br> 

**¿Se puede enviar una información DSP acerca de los puntos del canal de conversión alcanzado por un usuario?**

Sí. Podemos enviar datos de canal, pero el DSP debe tener la capacidad técnica para utilizarla. Un DSP debe confirmar que pueden gestionar varios segmentos. Si no lo son, es posible que necesitemos crear segmentos específicos para sacar a un usuario de otros segmentos según el progreso de la conversión (por ejemplo, los pasos 1 y 2, pero no el paso 3). Es posible que desee enviar esta información a un DSP para que pueda volver a conectarse a los usuarios, dirigirlos a una página de aterrizaje específica o mostrar elementos creativos específicos.

<br> 

**¿Cómo puedo confirmar que los datos enviados por medio de FTP han sido recogidos[!DNL Audience Manager]por?**

A file has been picked up when the extension changes from `.sync` to `.processed`. Cuando esto sucede, el archivo se encuentra en la cola de ingesta. Además, el administrador de cuentas puede confirmar cuándo se ha cargado un archivo.

<br> 

**Deseo probar la funcionalidad de la API[DCS](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md). Estoy enviando llamadas de evento como la que se muestra a continuación. The calls contain[Declared IDs](../features/declared-ids.md)and signals, which should realize some traits and segments I have already set up. Can I use the[!UICONTROL General Reports]and[!UICONTROL Trend Reports]to verify if the trait and segment populations are increasing?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

No, do not rely on the [!UICONTROL General Reports] and [!UICONTROL Trend Reports] in this case.

Los informes calculan poblaciones basadas en registros de perfiles no autenticados (UUID) que vemos en el back-backend en el momento en que se generan los informes.

On a first call to the [!UICONTROL DCS], the declared IDs are *not* linked to any UUID (i.e. no [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) is present on the client side). The [!UICONTROL DCS] will randomly generate a UUID and set a [!DNL demdex] cookie and pass it on in the response call, but it will not transmit the UUID to the backend.

>[!NOTE]
>
>El UUID generado solo se materializará en el almacenamiento de datos de back-backend cuando el dispositivo en el que se establezca la cookie activará una actividad adicional.

Por este motivo, los informes no reflejarán los eventos desencadenados por los ID declarados en la llamada. We recommend you use UUID, ECID (formerly MID) or mobile device IDs in event test calls to the [!UICONTROL DCS]. Then, you can verify the trait and segment realizations in the [!UICONTROL General Reports] and in the [!UICONTROL Trend Reports].

See also, the [Index of Audience Manager IDs](../reference/ids-in-aam.md).

<br> 

**¿Cuánto tarda los perfiles de usuario en sincronizar entre[las regiones](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

Normalmente, un perfil de usuario tarda hasta 24 horas en sincronizarse entre regiones. Sin embargo, en casos excepcionales, el proceso puede tardar hasta 48 horas.
