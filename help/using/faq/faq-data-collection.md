---
description: Cuestiones y problemas comunes de recopilación e integración de datos.
seo-description: Cuestiones y problemas comunes de recopilación e integración de datos.
seo-title: Preguntas frecuentes sobre la recopilación de datos y la integración de productos
solution: Audience Manager
title: Preguntas frecuentes sobre la recopilación de datos y la integración de productos
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
feature: Administration
translation-type: tm+mt
source-git-commit: 1f3b3d7d7ea8eaa0c1b64f147dc60b85f4e2f487
workflow-type: tm+mt
source-wordcount: '1151'
ht-degree: 86%

---


# Preguntas frecuentes sobre la recopilación de datos y la integración de productos {#data-collection-and-product-integration-faq}

Cuestiones y problemas comunes de recopilación e integración de datos.

<br> 

**¿Cómo puedo diferenciar el tráfico entrante del tráfico de [!DNL DCS] en las exportaciones de archivos de registros de [!DNL DCS]?**

Los rasgos incorporados mediante [!UICONTROL Inbound] se rellenan con [!UICONTROL Inbound] de la misma manera en que se rellenan con [!DNL DCS]. Hay varias formas diferentes de saber que el tráfico viene de [!UICONTROL Inbound]:

* La IP remota se establecerá en 68.67.173.18
* DomainID se establecerá en 5325
* La región se establecerá en 0

<br> 

**¿Puede proporcionarme una lista de las direcciones IP que puedo agregar a una lista de permitidos para dpm.demdex.net?**

Desafortunadamente, no podemos. Estas direcciones IP se asignan dinámicamente, por región geográfica, a través de [!DNL Amazon Web Services]. Como resultado, [!DNL Audience Manager] no controla el rango de direcciones IP que se pueden asignar a esta dirección.

 

**¿Puede proporcionarme una dirección IP que pueda agregar a una lista de permitidos para su servidor SFTP entrante y saliente?**

Sí, consulte la información siguiente.

| Servidor | Direcciones IP |
| ---------|----------|
| ftp-in-gtw.demdex.com | 52.3.74.119; 3 233 68 222 |
| ftp-out-gtw.demdex.com | 23.22.232.252; 18.211.109.184 |

 

Los servidores SFTP siguientes están en desuso. No se aprovisionará ninguna cuenta nueva con estos servidores.

| Servidor | Dirección IP |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

 

**¿Cómo configuro la instancia de Audience Manager para utilizar los nuevos servidores SFTP?**

Póngase en contacto con su [!DNL Audience Manager] consultor o con el Servicio de atención al cliente y configurará sus nuevas cuentas de SFTP.

 

**¿Cuáles son los métodos de autenticación admitidos para los nuevos servidores SFTP?**

Los nuevos servidores SFTP (`ftp-in-gtw` y `ftp-out-gtw`) admiten [!DNL OpenSSH Key-Based Authentication]. Podemos generar las [!DNL SSH] claves para usted o puede proporcionarnos su propia clave pública.

 

**¿Cuáles son los requisitos de colocación de código y carga de página para una integración de datos de [!UICONTROL DIL] y [!DNL Analytics]?**

Para incorporar datos de [!DNL Analytics] en [!DNL Audience Manager], cargue [!UICONTROL DIL] después del módulo `s_code` pero *antes* de la función `s.t()`. Por ejemplo, coloque el código o asegúrese de que se carga en este orden:

1. [!DNL Analytics] `s_code`

2. Módulo [!UICONTROL DIL] de [!DNL Audience Manager]

3. Función `s.t()` de [!DNL Analytics]

Como práctica recomendada, configure la integración entre [!DNL Audience Manager] y [!DNL Analytics] con cualquiera de estos dos métodos:

* Ponga [!UICONTROL DIL] directamente en el `s_code`.

* Entregue [!UICONTROL DIL] y el `s_code` mediante [!DNL Adobe Experience Platform Launch] o [!DNL Adobe DTM].

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

**[!DNL Google Ad Manager]Quiero recopilar datos en un sitio y segmentar los usuarios a través de en un sitio diferente. ¿Debo implementar código en la otra propiedad si no quiero recopilar datos de esa ubicación?**

No. Si la recopilación de datos en el segundo sitio no es un requisito, no es necesario implementar DIL allí. Siempre y cuando tenga acceso al inventario en el segundo sitio a través de [!DNL Google Ad Manager], puede utilizar la recopilación de datos del sitio inicial y el destinatario a través de [!DNL Google Ad Manager].

<br> 

**¿Cuál es el mejor proveedor de datos de terceros?**

Cada proveedor aporta algo único a la tabla, por lo que la respuesta depende de lo que esté buscando. Podemos habilitar el sistema de informes de superposición (sin coste alguno) para ayudarle a comprender qué proveedor puede funcionar mejor para usted.

<br> 

**¿Cómo se  [!DNL Audience Manager] configuran las cookies y se pasan las variables a  [!DNL Google Ad Manager]?**

[!DNL Audience Manager][!DNL Google Ad Manager] establece 2 cookies: Una envía variables de segmento a la etiqueta de publicidad de y la otra establece su ID de usuario único (UUID), que también lo puede leer [!DNL Google Ad Manager]. Añadir el UUID a la etiqueta de publicidad significa que podemos realizar la detección de sistemas de informes y audiencias a nivel de usuario.

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

En una primera llamada al [!DNL DCS], los ID declarados *no están* vinculados a ningún UUID (es decir, no hay ninguna cookie [demdex](hhttps://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) en el lado del cliente). El [!DNL DCS] generará aleatoriamente un UUID y establecerá una cookie [!DNL demdex] y la transmitirá en la llamada de respuesta, pero no transmitirá el UUID al servidor.

>[!NOTE]
>
>El UUID generado solo se materializará en nuestro almacenamiento de datos back-end una vez que el dispositivo en el que se configura la cookie inicie una actividad adicional.

Por este motivo, los informes no reflejarán los eventos activados por los ID declarados en la llamada. Le recomendamos que utilice UUID, ECID (anteriormente MID) o ID de dispositivos móviles en las llamadas de prueba de evento a [!DNL DCS]. A continuación, puede verificar las realizaciones de rasgos y segmentos en los [!UICONTROL General Reports] y en los [!UICONTROL Trend Reports].

Consulte también el [Índice de ID de Audience Manager](../reference/ids-in-aam.md).

<br> 

**¿Cuánto tiempo tardan los perfiles de usuario en sincronizarse entre [regiones](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

Normalmente, un perfil de usuario tarda hasta 24 horas en sincronizarse entre regiones. Sin embargo, en casos excepcionales, el proceso puede tardar hasta 48 horas.
