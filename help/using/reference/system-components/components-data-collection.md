---
description: Los componentes de recopilación de datos incluyen los servidores de recopilación de datos, la API de DIL, las transferencias de datos de entrada de servidor a servidor y los archivos de registro.
seo-description: Los componentes de recopilación de datos incluyen los servidores de recopilación de datos, la API de DIL, las transferencias de datos de entrada de servidor a servidor y los archivos de registro.
seo-title: Componentes de recopilación de datos
solution: Audience Manager
title: Componentes de recopilación de datos
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 6%

---


# Componentes de recopilación de datos{#data-collection-components}

Los componentes de recopilación de datos incluyen los servidores de recopilación de datos, la API de DIL, las transferencias de datos de entrada de servidor a servidor y los archivos de registro.

<!-- 

c_compcollect.xml

 -->

Audience Manager contiene los siguientes componentes de recopilación de datos:

* [Servidores de recopilación de datos (DCS) y servidores de caché de Perfil (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Biblioteca de integración de datos (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Servidor entrante a servidor](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Archivos de registro](../../reference/system-components/components-data-collection.md#log-files)

## Servidores de recopilación de datos (DCS) y servidores de caché de Perfil (PCS) {#dcs-pcs}

El DCS y el PCS colaboran y proporcionan por separado servicios relacionados con la realización de características, la segmentación de audiencias y el almacenamiento de datos.

**[!UICONTROL Data Collection Servers (DCS)]Función**

En [!DNL Audience Manager], el DCS:

* Recibe y evalúa los datos de características de una llamada de evento. Esto incluye la información utilizada para la segmentación en tiempo real y los datos pasados a intervalos programados por transferencias de servidor a servidor.
* Segmenta a los usuarios según sus características realizadas y las reglas de calificación que cree con [Generador de segmentos](../../features/segments/segment-builder.md).
* Crea y gestiona ID de dispositivo e ID de perfil autenticados. Esto incluye identificadores como ID de proveedores de datos, ID de usuario, ID declarados, códigos de integración, etc.
* Comprueba si el PCS tiene características adicionales que ya ha adquirido un usuario antes de realizar una llamada de evento en tiempo real. Esto permite que el DCS califique a los usuarios en función de datos en tiempo real y datos históricos.
* Escribe archivos de registro y los envía a los sistemas de análisis para su almacenamiento y procesamiento.

**[!DNL DCS]Gestiona La Demanda A Través De[!UICONTROL Global Server Load Balancing (GSLB)]**

El [!DNL DCS] es un sistema distribuido geográficamente y con equilibrio de carga. Esto significa que [!DNL Audience Manager] puede dirigir las solicitudes hacia y desde un centro de datos regional según la ubicación geográfica de un visitante del sitio. Esta estrategia ayuda a mejorar los tiempos de respuesta porque una respuesta [!DNL DCS] va directamente a un centro de datos que contiene información sobre ese visitante. [!UICONTROL GSLB] hace que nuestro sistema sea eficiente porque los datos relevantes se almacenan en caché en los servidores más cercanos al usuario.

>[!IMPORTANT]
>
>El [!DNL DCS] sólo detecta el tráfico Web originado en dispositivos que utilizan IPv4.

En una llamada de evento, la ubicación geográfica se captura en un par clave-valor devuelto en un cuerpo mayor de datos JSON. Este par clave-valor es el parámetro `"dcs_region": region ID`.

![](assets/dcs-map.png)

Como cliente, usted interactúa con [!DNL DCS] indirectamente a través de nuestro código de recopilación de datos. También puede trabajar directamente con [!DNL DCS] a través de un conjunto de API. Consulte [Métodos y código de la API del servidor de recopilación de datos (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

El [!UICONTROL PCS] es una base de datos grande (básicamente, una enorme cookie del lado del servidor). Almacena los datos recibidos para los usuarios activos desde las transferencias de servidor a servidor y desde [!DNL DCS]. Los datos [!UICONTROL PCS] constan de los ID de dispositivo, ID de perfil autenticados y sus rasgos asociados. Cuando [!DNL DCS] recibe una llamada en tiempo real, comprueba la [!UICONTROL PCS] para conocer otras características a las que un usuario puede pertenecer o para las que califica. Y, si se agrega una característica a un segmento más adelante, esas ID de características se agregan al [!UICONTROL PCS] y los usuarios pueden calificar para ese segmento automáticamente, sin visitar un sitio o aplicación en particular. El [!UICONTROL PCS] ayuda a profundizar la comprensión de [!DNL Audience Manager] de sus usuarios, ya que puede relacionar y segmentar usuarios en tiempo real o entre bastidores con datos de características nuevas e históricas. Este comportamiento le ofrece una imagen más completa y precisa de los usuarios que de las calificaciones en tiempo real.

No hay controles de interfaz de usuario que permitan a nuestros clientes trabajar directamente con [!UICONTROL PCS]. El acceso del cliente a [!UICONTROL PCS] es indirecto, a través de su función de almacén de datos y transferencias de datos. El [!UICONTROL PCS] se ejecuta en Apache Cassandra.

**Depuración de ID inactivos de la variable[!UICONTROL PCS]**

Como se indicó anteriormente, [!UICONTROL PCS] almacena los ID de características para los usuarios activos. Un usuario activo es cualquier usuario que haya sido visto por los [servidores de datos Edge](../../reference/system-components/components-edge.md) desde cualquier dominio durante los últimos 14 días. Estas llamadas a [!UICONTROL PCS] mantienen a un usuario en estado activo:

* [!DNL /event] llamadas
* [!DNL /ibs] llamadas (sincronizaciones de ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

El [!UICONTROL PCS] borra las características si están inactivos durante 17 días. Sin embargo, estos rasgos no se pierden. Están almacenados en Hadoop. Si se vuelve a ver al usuario en otro momento, Hadoop devuelve todas sus características al [!UICONTROL PCS], generalmente dentro de un período de 24 horas.

**Otros  [!UICONTROL DCS/PCS] procesos: Exclusión de privacidad**

Estos sistemas de servidor gestionan las solicitudes de privacidad y de exclusión de usuarios. La información de las cookies de usuario no se recopila en el archivo de registro si un usuario ha exclusión de la recopilación de datos. Para obtener más información sobre nuestras políticas de privacidad, consulte el [Centro de privacidad de Adobe](https://www.adobe.com/es/privacy/advertising-services.html).

## Biblioteca de integración de datos (DIL)  {#dil}

[!UICONTROL DIL] es el código que se coloca en la página para la recopilación de datos. Consulte la [API de DIL](../../dil/dil-overview.md) para obtener más información sobre los métodos y servicios disponibles.

## Servidor a servidor entrante {#inbound-outbound-server}

Son sistemas que reciben datos enviados por diversas integraciones servidor a servidor con nuestros clientes. Consulte la documentación sobre [envío de datos de audiencia](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) para obtener más información.

## Archivos de registro {#log-files}

El [!UICONTROL PCS] crea y escribe datos en los archivos de registro. Se envían a otros sistemas de bases de datos para procesamiento, sistema de informes y almacenamiento.

>[!MORELIKETHIS]
>
>* [Centro de privacidad de Adobe](https://www.adobe.com/es/privacy.html)

