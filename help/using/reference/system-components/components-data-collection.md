---
description: Los componentes de recopilación de datos incluyen los servidores de recopilación de datos, la API de DIL, las transferencias de datos de servidor a servidor entrantes y los archivos de registro.
seo-description: Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.
seo-title: Data Collection Components
solution: Audience Manager
title: Componentes de recopilación de datos
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 6%

---

# Componentes de recopilación de datos{#data-collection-components}

Los componentes de recopilación de datos incluyen los servidores de recopilación de datos, la API de DIL, las transferencias de datos de servidor a servidor entrantes y los archivos de registro.

<!-- 

c_compcollect.xml

 -->

Audience Manager contiene los siguientes componentes de recopilación de datos:

* [Servidores de recopilación de datos (DCS) y servidores de caché de perfiles (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Biblioteca de integración de datos (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Servidor a servidor entrante](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Archivos de registro](../../reference/system-components/components-data-collection.md#log-files)

## Servidores de recopilación de datos (DCS) y servidores de caché de perfiles (PCS) {#dcs-pcs}

El DCS y el PCS trabajan juntos y ofrecen por separado servicios relacionados con la realización de características, la segmentación de audiencia y el almacenamiento de datos.

**[!UICONTROL Data Collection Servers (DCS)]Función**

Entrada [!DNL Audience Manager], el DCS:

* Recibe y evalúa datos de rasgos de una llamada de evento. Esto incluye información utilizada para la segmentación en tiempo real y datos pasados a intervalos programados por transferencias de servidor a servidor.
* Segmenta a los usuarios según sus rasgos comprobados y las reglas de calificación que cree con [Generador de segmentos](../../features/segments/segment-builder.md).
* Crea y administra los ID de dispositivo y los ID de perfil autenticados. Esto incluye identificadores como ID de proveedor de datos, ID de usuario, ID declarados, códigos de integración, etc.
* Comprueba en el PCS los rasgos adicionales que un usuario ya ha observado antes de una llamada de evento en tiempo real. Esto permite que el DCS clasifique a los usuarios en función de los datos en tiempo real y los datos históricos.
* Escribe archivos de registro y los envía a sistemas de análisis para su almacenamiento y procesamiento.

**[!DNL DCS]Gestiona La Demanda Mediante[!UICONTROL Global Server Load Balancing (GSLB)]**

El [!DNL DCS] es un sistema distribuido geográficamente y con equilibrio de carga. Esto significa que [!DNL Audience Manager] puede dirigir solicitudes hacia y desde un centro de datos regional en función de la ubicación geográfica de un visitante del sitio. Esta estrategia ayuda a mejorar los tiempos de respuesta porque una [!DNL DCS] La respuesta va directamente a un centro de datos que contiene información sobre ese visitante. [!UICONTROL GSLB] hace que nuestro sistema sea eficiente porque los datos relevantes se almacenan en caché en los servidores más cercanos al usuario.

>[!IMPORTANT]
>
>El [!DNL DCS] solo detecta el tráfico web procedente de dispositivos que utilizan IPv4.

En una llamada de evento, la ubicación geográfica se captura en un par clave-valor devuelto en un cuerpo más grande de datos JSON. Este par clave-valor es el `"dcs_region": region ID` parámetro.

![](assets/dcs-map.png)

Como cliente, debe interactuar con el [!DNL DCS] indirectamente a través de nuestro código de recopilación de datos. También puede trabajar directamente con el [!DNL DCS] mediante un conjunto de API. Consulte [Métodos y código de la API del servidor de recopilación de datos (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

El [!UICONTROL PCS] es una base de datos grande (básicamente, una enorme cookie del lado del servidor). Almacena los datos recibidos para los usuarios activos desde las transferencias de servidor a servidor y desde [!DNL DCS]. Los datos [!UICONTROL PCS] constan de los ID de dispositivo, ID de perfil autenticados y sus rasgos asociados. Si la variable [!DNL DCS] recibe una llamada en tiempo real y comprueba la [!UICONTROL PCS] para otros rasgos a los que un usuario puede pertenecer o cumplir los requisitos. Y, si se añade una característica a un segmento más adelante, esos ID de característica se añaden a la variable [!UICONTROL PCS] Los usuarios de y pueden pertenecer a ese segmento automáticamente, sin visitar un sitio o una aplicación determinados. El [!UICONTROL PCS] ayuda a profundizar [!DNL Audience Manager]Comprensión de los usuarios de porque puede hacer coincidir y segmentar usuarios en tiempo real o entre bastidores con datos de rasgos nuevos e históricos. Este comportamiento le ofrece una imagen más completa y precisa de sus usuarios que solo de las cualificaciones en tiempo real.

No hay controles de IU que permitan a nuestros clientes trabajar directamente con [!UICONTROL PCS]. Acceso del cliente a [!UICONTROL PCS] es indirecto, a través de su función de almacén de datos y transferencias de datos. El [!UICONTROL PCS] se ejecuta en Apache Cassandra.

**Depuración de ID inactivos de[!UICONTROL PCS]**

Como se indicó anteriormente, la variable [!UICONTROL PCS] almacena los ID de rasgos de los usuarios activos. Un usuario activo es cualquier usuario que haya sido visto por [servidores de datos Edge](../../reference/system-components/components-edge.md) de cualquier dominio durante los últimos 14 días. Estas llamadas a [!UICONTROL PCS] mantener a un usuario en estado activo:

* [!DNL /event] llamadas
* [!DNL /ibs] llamadas (sincronizaciones de ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

El [!UICONTROL PCS] vacía los rasgos si están inactivos durante 17 días. Sin embargo, estos rasgos no se pierden. Están almacenados en el Hadoop. Si se vuelve a ver al usuario en otro momento, el Hadoop vuelve a colocar todos sus rasgos en la etiqueta [!UICONTROL PCS], normalmente en un periodo de 24 horas.

**Otros [!UICONTROL DCS/PCS] Procesos: exclusión de privacidad**

Estos sistemas de servidor gestionan las solicitudes de privacidad y de exclusión de los usuarios. La información de cookies del usuario no se recopila en el archivo de registro si un usuario ha excluido la recopilación de datos. Para obtener más información sobre nuestras políticas de privacidad, consulte la [Centro de privacidad de Adobe](https://www.adobe.com/es/privacy/advertising-services.html).

## Biblioteca de integración de datos (DIL) {#dil}

[!UICONTROL DIL] es el código que se coloca en la página para la recopilación de datos. Consulte la [API de DIL](../../dil/dil-overview.md) para obtener más información sobre los servicios y métodos disponibles.

## Servidor a servidor entrante {#inbound-outbound-server}

Son sistemas que reciben datos enviados por varias integraciones de servidor a servidor con nuestros clientes. Consulte la documentación sobre [envío de datos de audiencia](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) para obtener más información.

## Archivos de registro {#log-files}

El [!UICONTROL PCS] crea y escribe datos en los archivos de registro. Se envían a otros sistemas de base de datos para su procesamiento, creación de informes y almacenamiento.

>[!MORELIKETHIS]
>
>* [Centro de privacidad de Adobe](https://www.adobe.com/es/privacy.html)

