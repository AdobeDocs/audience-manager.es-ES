---
description: Los componentes de recopilación de datos incluyen los servidores de recopilación de datos, la API de DIL, las transferencias de datos de servidor a servidor entrantes y los archivos de registro.
seo-description: Los componentes de recopilación de datos incluyen los servidores de recopilación de datos, la API de DIL, las transferencias de datos de servidor a servidor entrantes y los archivos de registro.
seo-title: Componentes de recopilación de datos
solution: Audience Manager
title: Componentes de recopilación de datos
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: 'Componentes del sistema '
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 7%

---

# Componentes de recopilación de datos{#data-collection-components}

Los componentes de recopilación de datos incluyen los servidores de recopilación de datos, la API de DIL, las transferencias de datos de servidor a servidor entrantes y los archivos de registro.

<!-- 

c_compcollect.xml

 -->

El Audience Manager contiene los siguientes componentes de recopilación de datos:

* [Servidores de recopilación de datos (DCS) y servidores de caché de perfiles (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Biblioteca de integración de datos (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Servidor a servidor entrante](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Archivos de registro](../../reference/system-components/components-data-collection.md#log-files)

## Servidores de recopilación de datos (DCS) y servidores de caché de perfil (PCS) {#dcs-pcs}

El DCS y el PCS colaboran y proporcionan por separado servicios relacionados con la realización de características, la segmentación de audiencias y el almacenamiento de datos.

**[!UICONTROL Data Collection Servers (DCS)]Función**

En [!DNL Audience Manager], el DCS:

* Recibe y evalúa los datos de rasgos de una llamada de evento. Esto incluye información utilizada para la segmentación en tiempo real y datos pasados a intervalos programados mediante transferencias de servidor a servidor.
* Segmenta a los usuarios en función de sus características realizadas y las reglas de calificación que cree con el [Generador de segmentos](../../features/segments/segment-builder.md).
* Crea y administra ID de dispositivo e ID de perfil autenticados. Esto incluye identificadores como ID de proveedores de datos, ID de usuario, ID declarados, códigos de integración, etc.
* Comprueba que el PCS tenga características adicionales que un usuario ya ha realizado antes de una llamada de evento en tiempo real. Esto permite que el DCS clasifique a los usuarios según los datos en tiempo real y los datos históricos.
* Escribe archivos de registro y los envía a sistemas de análisis para su almacenamiento y procesamiento.

**[!DNL DCS]Gestiona La Demanda Mediante[!UICONTROL Global Server Load Balancing (GSLB)]**

El [!DNL DCS] es un sistema distribuido geográficamente y con equilibrio de carga. Esto significa que [!DNL Audience Manager] puede dirigir las solicitudes hacia y desde un centro de datos regional en función de la ubicación geográfica de un visitante del sitio. Esta estrategia ayuda a mejorar los tiempos de respuesta porque una respuesta [!DNL DCS] va directamente a un centro de datos que contiene información sobre ese visitante. [!UICONTROL GSLB] hace que nuestro sistema sea eficiente porque los datos relevantes se almacenan en caché en los servidores más cercanos al usuario.

>[!IMPORTANT]
>
>El [!DNL DCS] solo detecta el tráfico web originado por dispositivos que utilizan IPv4.

En una llamada de evento, la ubicación geográfica se captura en un par clave-valor devuelto en un cuerpo mayor de datos JSON. Este par clave-valor es el parámetro `"dcs_region": region ID`.

![](assets/dcs-map.png)

Como cliente, interactúa con [!DNL DCS] indirectamente a través de nuestro código de recopilación de datos. También puede trabajar directamente con [!DNL DCS] a través de un conjunto de API. Consulte [Métodos y código de la API del servidor de recopilación de datos (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

El [!UICONTROL PCS] es una base de datos grande (básicamente, una enorme cookie del lado del servidor). Almacena los datos recibidos para los usuarios activos desde las transferencias de servidor a servidor y desde [!DNL DCS]. Los datos [!UICONTROL PCS] constan de los ID de dispositivo, ID de perfil autenticados y sus rasgos asociados. Cuando el [!DNL DCS] recibe una llamada en tiempo real, comprueba el [!UICONTROL PCS] de otros rasgos a los que un usuario puede pertenecer o para los que califique. Además, si se agrega un rasgo a un segmento más adelante, esos ID de rasgo se añaden al [!UICONTROL PCS] y los usuarios pueden calificarse para ese segmento automáticamente, sin necesidad de visitar un sitio o aplicación concretos. El [!UICONTROL PCS] ayuda a comprender mejor a los usuarios porque puede hacer coincidir y segmentar a los usuarios en tiempo real o entre bastidores con datos de características nuevos e históricos. [!DNL Audience Manager] Este comportamiento le ofrece una imagen más completa y precisa de los usuarios que de las cualificaciones en tiempo real.

No hay controles de interfaz de usuario que permitan a nuestros clientes trabajar directamente con [!UICONTROL PCS]. El acceso de los clientes al [!UICONTROL PCS] es indirecto, ya que se trata de un almacén de datos y de transferencias de datos. El [!UICONTROL PCS] se ejecuta en Apache Cassandra.

**Depuración de ID inactivos desde el[!UICONTROL PCS]**

Como se indicó anteriormente, el [!UICONTROL PCS] almacena los ID de rasgos para los usuarios activos. Un usuario activo es cualquier usuario que haya sido visto por los [servidores de datos Edge](../../reference/system-components/components-edge.md) desde cualquier dominio durante los últimos 14 días. Estas llamadas a [!UICONTROL PCS] mantienen a un usuario en estado activo:

* [!DNL /event] llamadas
* [!DNL /ibs] llamadas (sincronizaciones de ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

El [!UICONTROL PCS] borra los rasgos si están inactivos durante 17 días. Sin embargo, estos rasgos no se pierden. Están almacenados en el Hadoop. Si se vuelve a ver al usuario en otro momento, el Hadoop reenvía todos sus rasgos a [!UICONTROL PCS], normalmente dentro de un período de 24 horas.

**Otros  [!UICONTROL DCS/PCS] procesos: Exclusión de privacidad**

Estos sistemas de servidor administran las solicitudes de privacidad y exclusión de los usuarios. La información de las cookies de usuario no se recopila en el archivo de registro si un usuario ha excluido la recopilación de datos. Para obtener más información sobre nuestras políticas de privacidad, consulte el [Centro de privacidad del Adobe](https://www.adobe.com/es/privacy/advertising-services.html).

## Biblioteca de integración de datos (DIL)  {#dil}

[!UICONTROL DIL] es el código que se coloca en la página para la recopilación de datos. Consulte la [API del DIL](../../dil/dil-overview.md) para obtener más información sobre los servicios y métodos disponibles.

## Servidor a servidor entrante {#inbound-outbound-server}

Son sistemas que reciben datos enviados por varias integraciones servidor a servidor con nuestros clientes. Consulte la documentación sobre [envío de datos de audiencia](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) para obtener más información.

## Archivos de registro {#log-files}

El [!UICONTROL PCS] crea y escribe datos en los archivos de registro. Se envían a otros sistemas de bases de datos para procesamiento, reporting y almacenamiento.

>[!MORELIKETHIS]
>
>* [Centro de privacidad de Adobe](https://www.adobe.com/es/privacy.html)

