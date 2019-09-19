---
description: Cuestiones y problemas comunes de recopilación e integración de datos.
seo-description: Cuestiones y problemas comunes de recopilación e integración de datos.
seo-title: Preguntas más frecuentes sobre la recopilación de datos y la integración de productos
solution: Audience Manager
title: Preguntas más frecuentes sobre la recopilación de datos y la integración de productos
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Preguntas más frecuentes sobre la recopilación de datos y la integración de productos{#data-collection-and-product-integration-faq}

Cuestiones y problemas comunes de recopilación e integración de datos.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**¿Cómo puedo diferenciar el tráfico entrante del tráfico[!UICONTROL DCS]en las exportaciones de archivos de[!UICONTROL DCS]registro?**

Las características que se [!UICONTROL Inbound] rellenan se rellenan de [!UICONTROL Inbound] la misma manera en que se rellenan con [!UICONTROL DCS]. Existen varias formas diferentes de decir que el tráfico proviene de [!UICONTROL Inbound]:

* La IP remota se establecerá en 68.67.173.18
* DomainID se establecerá en 5325
* La región se establecerá en 0

<br> 

**¿Puede proporcionarme una lista de direcciones IP que puedo incluir en la lista de direcciones permitidas para dpm.demdex.net?**

Desafortunadamente, no podemos. Estas direcciones IP se asignan dinámicamente, por región geográfica, a través de [!DNL Amazon Web Services]. Como resultado, [!DNL Audience Manager] no controla el rango de IP que se pueden asignar a esta dirección.

<br> 

**¿Puede proporcionarme una dirección IP que pueda incluir en la lista de direcciones permitidas para su servidor FTP entrante y saliente?**

Sí, véase a continuación.

| Elemento | Dirección |
---------|----------|
|  ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**¿Cuáles son los requisitos de colocación de código y carga de página para una integración de datos[!UICONTROL DIL]/[!DNL Analytics]?**

Para traer [!DNL Analytics] datos a [!DNL Audience Manager], cargue [!UICONTROL DIL] después del `s_code` módulo pero *antes* de la `s.t()` función. Por ejemplo, coloque el código o asegúrese de que se carga en este orden:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] módulo

3. [!DNL Analytics] `s.t()` función

Como práctica recomendada, configure la [!DNL Audience Manager][!DNL Analytics] integración con cualquiera de estos dos métodos:

* Ponga [!UICONTROL DIL] directamente en el `s_code`.

* Sirve [!UICONTROL DIL] y el `s_code` a través [!DNL Adobe Launch] o [!DNL Adobe DTM].

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**¿Por qué faltan mis[!DNL Analytics]variables en una llamada[!DNL Audience Manager]de evento?**

Esto suele suceder cuando:

* El servicio se realiza [!UICONTROL DIL] a través de un sistema de administración de etiquetas que lo carga asincrónicamente con otros elementos de código de la página.
* La `s.t()` función se carga antes de [!UICONTROL DIL].

<br> 

**¿Con qué versiones de[!DNL Analytics]trabajar[!UICONTROL DIL]?**

Debe utilizar [!DNL Analytics] la versión 20.2 (o superior) y la [!DNL Adobe AppMeasurement AS] biblioteca 3.5.2 (o superior) para trabajar con [!UICONTROL DIL]. Si no conoce su versión [!DNL Analytics] o [!DNL AppMeasurement] , consulte la [!DNL Analytics] llamada que se realiza desde la página. Información de versión que se muestra a continuación:

Este cliente utiliza [!DNL Analytics] la versión 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Este cliente utiliza [!DNL AppMeasurement] la versión 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**¿Puedo recopilar datos de página si no soy[!DNL Analytics]cliente?**

Sí. El [!UICONTROL DIL] módulo le ayuda a recopilar datos de página aunque no los esté utilizando [!DNL Analytics]. Cuando se configura correctamente, [!UICONTROL DIL] puede capturar datos desde y sobre:

* Etiquetas meta
* Direcciones URL y encabezados de URL
* Tipos de motores de búsqueda
* Palabras clave

Además, los clientes pueden implementar un objeto simple en el sitio y rellenarlo con pares de clave-valor en los que desee [!UICONTROL DIL] recopilar datos. Esto permite agregar y eliminar puntos de datos de audiencia específicos en el sitio sin ninguna [!DNL Audience Management] actualización. Póngase en contacto con el representante de soluciones de socio para configurar correctamente esta configuración y asegurarse de que el [!DNL DIL] módulo hace referencia al objeto de página correctamente.

<br> 

**¿Puede[!UICONTROL DIL]recopilar datos de[!DNL Google Analytics]?**

Sí. [!UICONTROL DIL] puede recopilar algunos elementos [!DNL Google Analytics] (GA) y pasar esos datos a [!DNL Audience Manager]. Consulte:

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**¿Puedo obtener datos sin procesar[!DNL Audience Manager]y qué tan granular es?**

Sí, [!DNL Audience Manager] puede proporcionarle datos recopilados para los usuarios que hemos visto en su inventario. Esto incluye:

* El ID de usuario único (UUID) asignado por [!DNL Audience Manager]
* ID de características y segmentos
* Señales no utilizadas
* Marcas de hora
* Direcciones URL de página

<br> 

**Quiero recopilar datos en un sitio y dirigir a los usuarios a través de DFP en otro sitio. ¿Debo implementar código en la otra propiedad si no quiero recopilar datos de esa ubicación?**

No. Si la recopilación de datos en el segundo sitio no es un requisito, no es necesario implementar DIL allí. Siempre que tenga acceso al inventario en el segundo sitio a través de DFP, puede utilizar la recopilación de datos del sitio inicial y el destino a través de DFP.

<br> 

**¿Cuál es el mejor proveedor de datos de terceros?**

Cada proveedor aporta algo único a la tabla, por lo que la respuesta depende de lo que esté buscando. Podemos habilitar los informes de superposición (sin costo) para ayudarle a comprender qué proveedor puede funcionar mejor para usted.

<br> 

**¿Cómo[!DNL Audience Manager]establece las cookies y pasa las variables a DFP?**

[!DNL Audience Manager] establece 2 cookies: Uno envía variables de segmento a la etiqueta de publicidad de DFP y el otro establece su ID de usuario único (UUID), que también es leído por DFP. Agregar el UUID a la etiqueta de publicidad significa que podemos realizar informes a nivel de usuario y descubrimiento de audiencias.

<br> 

**¿Podemos enviar información de DSP sobre los puntos del canal de conversión a los que ha llegado un usuario?**

Sí. Podemos enviar datos de canal, pero el DSP debe tener la capacidad técnica para utilizarlos. Un DSP debe confirmar que puede gestionar varios segmentos. Si no pueden hacerlo, es posible que tengamos que crear segmentos específicos para sacar a un usuario de otros segmentos en función de su progreso de conversión (por ejemplo, los pasos 1 y 2 completados pero no el paso 3). Es posible que desee enviar esta información a un DSP para que pueda redirigirse a los usuarios, dirigirlos a una página de aterrizaje específica o mostrar elementos creativos específicos.

<br> 

**¿Cómo puedo confirmar que los datos enviados por FTP han sido recogidos por[!DNL Audience Manager]?**

Se ha seleccionado un archivo cuando la extensión cambia de `.sync` a `.processed`. Cuando esto sucede, el archivo se encuentra en la cola de ingestión. Además, el administrador de cuentas puede confirmar cuándo se ha cargado un archivo.

<br> 

**Quiero probar la funcionalidad de la API[de](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)DCS. Envío llamadas de evento como la que se muestra a continuación. Las llamadas contienen ID[declarados](../features/declared-ids.md)y señales, lo que debería hacer realidad algunas características y segmentos que ya he configurado. ¿Puedo usar[!UICONTROL General Reports]y[!UICONTROL Trend Reports]para verificar si las poblaciones de rasgos y segmentos están aumentando?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

No, no confíes en el [!UICONTROL General Reports] y en este caso [!UICONTROL Trend Reports] .

Los informes calculan las poblaciones en función de los registros de perfil no autenticados (UUID) que vemos en el servidor en el momento en que se generan los informes.

En una primera llamada al [!UICONTROL DCS], los ID declarados *no están* vinculados a ningún UUID (es decir, no hay ninguna cookie [](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) demdex en el lado del cliente). El [!UICONTROL DCS] generará aleatoriamente un UUID y establecerá una [!DNL demdex] cookie y la transmitirá en la llamada de respuesta, pero no transmitirá el UUID al servidor.

>[!NOTE]
>
>El UUID generado sólo se materializará en nuestro almacenamiento de datos back-end una vez que el dispositivo en el que se configura la cookie active más actividad.

Por este motivo, los informes no reflejarán los eventos activados por las ID declaradas en la llamada. Le recomendamos que utilice UUUID, ECID (anteriormente MID) o ID de dispositivos móviles en las llamadas de prueba de eventos realizadas al [!UICONTROL DCS]. A continuación, puede verificar las realizaciones de rasgos y segmentos en el [!UICONTROL General Reports] y en el [!UICONTROL Trend Reports].

Consulte también [Índice de ID](../reference/ids-in-aam.md)de Audience Manager.

<br> 

**¿Cuánto tiempo tardan los perfiles de usuario en sincronizarse entre[regiones](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

Normalmente, un perfil de usuario tarda hasta 24 horas en sincronizarse entre regiones. Sin embargo, en casos excepcionales, el proceso puede tardar hasta 48 horas.
