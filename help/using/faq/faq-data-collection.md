---
description: Cuestiones y problemas comunes de recopilación e integración de datos.
seo-description: Common data collection and integration questions and issues.
seo-title: Data Collection and Product Integration FAQ
solution: Audience Manager
title: Preguntas frecuentes sobre la recopilación de datos y la integración de productos
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; dirección SFTP; dirección IP SFTP; dirección FTP
feature: Administration
exl-id: 2951ab0c-6f1c-4126-b83e-ce4a33c0d4ab
TQID: https://experienceleague.adobe.com/C35e-eIULWyFZPASMC-vwOIU1Yk-SH-HZzGRTO89yFg
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a99472c1-6aae-4c7a-8aa0-f60636369620id: b89b323a-1e91-40b1-8d20-96b5b726d55aid: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6cid: b1ecf375-97f8-4f5a-a937-6129552209beid: b52f95d5-ca6b-4fda-a49e-994dc0a63402id: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66id: df401a2a-327d-468c-a5e4-b7b7ccd071a0id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 99abc40141fbc79b15dd87691be58c9e201a705a
workflow-type: tm+mt
source-wordcount: 1276
ht-degree: 74%

---

# Preguntas frecuentes sobre la recopilación de datos y la integración de productos{#data-collection-and-product-integration-faq}

Cuestiones y problemas comunes de recopilación e integración de datos.

<br> 

**¿Cómo puedo diferenciar el tráfico entrante del tráfico de [!DNL DCS] en las exportaciones de archivos de registros de [!DNL DCS]?**

Los rasgos incorporados mediante [!UICONTROL Inbound] se rellenan con [!UICONTROL Inbound] de la misma manera en que se rellenan con [!DNL DCS]. Hay varias formas diferentes de saber que el tráfico viene de [!UICONTROL Inbound]:

* La IP remota se establecerá en 68.67.173.18
* DomainID se establecerá en 5325
* La región se establecerá en 0

<br> 

**¿Puede proporcionarme una lista de direcciones IP que puedo agregar a una lista de permitidos para dpm.demdex.net?**

Desafortunadamente, no podemos. Estas direcciones IP se asignan dinámicamente, por región geográfica, a través de [!DNL Amazon Web Services]. Como resultado, [!DNL Audience Manager] no controla el rango de direcciones IP que se pueden asignar a esta dirección.

 

**¿Puede proporcionarme una dirección IP que pueda agregar a una lista de permitidos para su servidor SFTP entrante y saliente?**

Sí, consulte la información siguiente.

| Servidor | Direcciones IP |
| ---------|----------|
| ftp-in-gtw.demdex.com | 52.3.74.119; 3.233.68.222 |
| ftp-out-gtw.demdex.com | 23.22.232.252; 18.211.109.184 |

 

Los siguientes servidores SFTP están en desuso. No se aprovisionarán nuevas cuentas utilizando estos servidores.

| Servidor | Dirección IP |
|---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

 

**¿Cómo configuro mi instancia de Audience Manager para que use los nuevos servidores SFTP?**

Póngase en contacto con su asesor de [!DNL Audience Manager] o con el Servicio de atención al cliente para que configuren sus nuevas cuentas SFTP.

 

**¿Cuáles son los métodos de autenticación admitidos para los nuevos servidores SFTP?**

Los nuevos servidores SFTP (`ftp-in-gtw` y `ftp-out-gtw`) admiten [!DNL OpenSSH Key-Based Authentication]. Podemos generar las claves [!DNL SSH] para usted o puede proporcionarnos su propia clave pública.

 

**¿Cuáles son los requisitos de colocación de código y carga de página para una integración de datos de [!UICONTROL DIL] y [!DNL Analytics]?**

Para incorporar datos de [!DNL Analytics] en [!DNL Audience Manager], cargue [!UICONTROL DIL] después del módulo `s_code` pero *antes* de la función `s.t()`. Por ejemplo, coloque el código o asegúrese de que se carga en este orden:

1. [!DNL Analytics] `s_code`

2. Módulo [!UICONTROL DIL] de [!DNL Audience Manager]

3. Función `s.t()` de [!DNL Analytics]

Como práctica recomendada, configure la integración entre [!DNL Audience Manager] y [!DNL Analytics] con cualquiera de estos dos métodos:

* Ponga [!UICONTROL DIL] directamente en el `s_code`.

* Proporcionar [!UICONTROL DIL] y `s_code` a través de [!DNL Adobe Experience Platform Tags].

Consulte [API de Data Integration Library (DIL)](../dil/dil-overview.md).

 

**¿Por qué faltan mis variables de [!DNL Analytics] en una llamada de evento de [!DNL Audience Manager]?**

Esto suele suceder cuando:

* Se entrega [!UICONTROL DIL] a través de un sistema de administración de etiquetas que lo carga asincrónicamente con otros elementos de código de la página.
* La función `s.t()` se carga antes de [!UICONTROL DIL].

 

**¿Qué versiones de [!DNL Analytics] trabajan con [!UICONTROL DIL]?**

Debe utilizar [!DNL Analytics] 20.2 (o una versión superior) y la biblioteca de [!DNL Adobe AppMeasurement AS] 3.5.2 (o superior) para trabajar con [!UICONTROL DIL]. Si no conoce su versión de [!DNL Analytics] o [!DNL AppMeasurement], consulte la llamada de [!DNL Analytics] que se realiza desde la página. Información de versión que se muestra a continuación:

Este cliente utiliza [!DNL Analytics] 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Este cliente utiliza [!DNL AppMeasurement] 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**¿Puedo recopilar datos de página si no soy cliente de [!DNL Analytics]?**

Sí. El módulo [!UICONTROL DIL] le ayuda a recopilar datos de página aunque no utilice [!DNL Analytics]. Cuando se configura correctamente, [!UICONTROL DIL] puede capturar datos mediante estos métodos y elementos:

* Metaetiquetas
* Direcciones URL y encabezados de URL
* Tipos de motores de búsqueda
* Palabras clave

Además, los clientes pueden implementar un objeto simple en el sitio y rellenarlo con pares de clave-valor en los que desee que [!UICONTROL DIL] recopile datos. Esto permite agregar y eliminar puntos de datos de audiencia específicos en el sitio sin ninguna actualización de [!DNL Audience Management]. Póngase en contacto con el representante de soluciones de socios para establecer correctamente esta configuración y asegurarse de que el módulo [!DNL DIL] hace referencia al objeto de página correctamente.

<br> 

**¿Puede [!UICONTROL DIL] recopilar datos de [!DNL Google Analytics]?**

Sí. [!UICONTROL DIL] puede recopilar algunos elementos de [!DNL Google Analytics] (GA) y pasar esos datos a [!DNL Audience Manager]. Consulte:

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**¿Puedo obtener datos sin procesar de [!DNL Audience Manager] y con qué granularidad?**

Sí, [!DNL Audience Manager] puede proporcionarle los datos recopilados para los usuarios que hemos visto en su inventario. Esto incluye:

* El ID de usuario único (UUID) asignado por [!DNL Audience Manager]
* ID de rasgos y segmentos
* Señales no utilizadas
* Marcas de hora
* Direcciones URL de página

<br> 

**Deseo recopilar datos en un sitio y segmentar a los usuarios a través de [!DNL Google Ad Manager] en un sitio diferente. ¿Debo implementar código en la otra propiedad si no quiero recopilar datos de esa ubicación?**

No. Si la recopilación de datos en el segundo sitio no es un requisito, no es necesario implementar DIL allí. Siempre que tenga acceso al inventario en el segundo sitio a través de [!DNL Google Ad Manager], puede utilizar la recopilación de datos del sitio inicial y segmentar mediante [!DNL Google Ad Manager].

<br> 

**¿Cuál es el mejor proveedor de datos de terceros?**

Cada proveedor aporta algo único a la tabla, por lo que la respuesta depende de lo que esté buscando. Podemos habilitar el sistema de informes de superposición (sin coste alguno) para ayudarle a comprender qué proveedor puede funcionar mejor para usted.

<br> 

**¿Cómo establece [!DNL Audience Manager] las cookies y pasa las variables a [!DNL Google Ad Manager]?**

[!DNL Audience Manager] establece 2 cookies: una envía variables de segmento a la etiqueta de publicidad [!DNL Google Ad Manager] y la otra establece su identificador de usuario único (UUID), que también lo lee [!DNL Google Ad Manager]. Añadir el UUID a la etiqueta de publicidad significa que podemos realizar la detección de sistemas de informes y audiencias a nivel de usuario.

<br> 

**¿Podemos enviar información de DSP sobre los puntos del canal de conversión a los que ha llegado un usuario?**

Sí. Podemos enviar datos de canal, pero el DSP debe tener la capacidad técnica para utilizarlos. Un DSP debe confirmar que puede gestionar varios segmentos. Si no pueden hacerlo, es posible que tengamos que crear segmentos específicos para sacar a un usuario de otros segmentos en función de su progreso de conversión (por ejemplo, los pasos 1 y 2 completados pero no el paso 3). Es posible que desee enviar esta información a un DSP para que pueda redirigirse a los usuarios, dirigirlos a una página de aterrizaje específica o mostrar algunos elementos creativos.

<br> 

**¿Cómo puedo confirmar que [!DNL Audience Manager] ha recopilado los datos enviados a través de un FTP?**

Se ha seleccionado un archivo cuando la extensión cambia de `.sync` a `.processed`. Cuando esto sucede, el archivo se encuentra en la cola de ingestión. Además, el administrador de cuentas puede confirmar cuándo se ha cargado un archivo.

<br> 

**Quiero probar la funcionalidad de la [API de DCS](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md). Estoy enviando llamadas de evento como la que se muestra a continuación. Las llamadas contienen [ID declarados](../features/declared-ids.md) y señales, lo que debería realizar algunos rasgos y segmentos ya configurados. ¿Puedo usar [!UICONTROL General Reports] y [!UICONTROL Trend Reports] para verificar si las poblaciones de rasgos y segmentos están aumentando?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

No, no confíe en los [!UICONTROL General Reports] ni en [!UICONTROL Trend Reports] en este caso.

Los informes calculan las poblaciones en función de los registros de perfil no autenticados (UUID) que vemos en el servidor en el momento en que se generan los informes.

En una primera llamada al [!DNL DCS], los ID declarados *no están* vinculados a ningún UUID (es decir, no hay ninguna cookie [demdex](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html) en el lado del cliente). El [!DNL DCS] generará aleatoriamente un UUID y establecerá una cookie [!DNL demdex] y la transmitirá en la llamada de respuesta, pero no transmitirá el UUID al servidor.

>[!NOTE]
>
>El UUID generado solo se materializará en nuestro almacenamiento de datos back-end una vez que el dispositivo en el que se configura la cookie inicie una actividad adicional.

Por este motivo, los informes no reflejarán los eventos activados por los ID declarados en la llamada. Le recomendamos que utilice UUID, ECID (anteriormente MID) o ID de dispositivos móviles en las llamadas de prueba de evento a [!DNL DCS]. A continuación, puede verificar las realizaciones de rasgos y segmentos en los [!UICONTROL General Reports] y en los [!UICONTROL Trend Reports].

Consulte también el [Índice de ID de Audience Manager](../reference/ids-in-aam.md).

<br> 

**¿Cuánto tiempo tardan los perfiles de usuario en sincronizarse entre [regiones](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

Normalmente, un perfil de usuario tarda hasta 24 horas en sincronizarse entre regiones. Sin embargo, en casos excepcionales, el proceso puede tardar hasta 48 horas.

 

**¿Qué les sucede a las claves de acceso de usuario inactivas de Amazon S3?**

Adobe proporciona a los clientes de Audience Manager claves de acceso para [!DNL Amazon S3] bloques. Por motivos de seguridad, estas claves de acceso se desactivan automáticamente si permanecen sin utilizar durante 40 días.

Si las claves de acceso están desactivadas, puede ponerse en contacto con Asistencia al cliente para volver a activarlas o solicitar nuevas claves.

Para mejorar la seguridad, las claves de acceso que permanezcan inactivas durante 180 días se eliminarán permanentemente junto con la cuenta de usuario de Amazon S3 IAM. Si es un cliente habitual y necesita acceso después de este período, póngase en contacto con Asistencia al cliente para volver a crear su cuenta y recibir nuevas claves de acceso.
