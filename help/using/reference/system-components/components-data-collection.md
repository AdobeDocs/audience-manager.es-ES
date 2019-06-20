---
description: Los componentes de recopilación de datos incluyen los servidores de recopilación de datos, la API DIL, las transferencias de datos de servidor a servidor y los archivos de registro.
seo-description: Los componentes de recopilación de datos incluyen los servidores de recopilación de datos, la API DIL, las transferencias de datos de servidor a servidor y los archivos de registro.
seo-title: Componentes de recopilación de datos
solution: Audience Manager
title: Componentes de recopilación de datos
uuid: 51 bb 1719-5 ff 2-4 bc 7-8 eb 1-98795 e 05 d 08 f
translation-type: tm+mt
source-git-commit: 0b9da38fd8b999637bdf6c3fe6af8aa2426eb6ae

---


# Data Collection Components{#data-collection-components}

Los componentes de recopilación de datos incluyen los servidores de recopilación de datos, la API DIL, las transferencias de datos de servidor a servidor y los archivos de registro.

<!-- 

c_compcollect.xml

 -->

Audience Manager contiene los siguientes componentes de recopilación de datos:

* [Servidores de recopilación de datos (DCS) y servidores caché de perfil (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Biblioteca de integración de datos (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Servidor de entrada a servidor](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Archivos de registro](../../reference/system-components/components-data-collection.md#log-files)

## Data Collection Servers (DCS) and Profile Cache Servers (PCS) {#dcs-pcs}

El DCS y el PCS trabajan juntos y proporcionan servicios relacionados de forma independiente con la realización de características, la segmentación de audiencias y el almacenamiento de datos.

**[!UICONTROL Data Collection Servers (DCS)]Función**

In [!DNL Audience Manager], the DCS:

* Recibe y evalúa los datos de características de una llamada de evento. Esto incluye información utilizada para la segmentación en tiempo real y los datos pasados a intervalos programados por transferencias servidor a servidor.
* Segments users based on their realized traits and the qualification rules you create with [Segment Builder](../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74).
* Crea y gestiona los ID de dispositivo y los ID de perfil autenticados. Esto incluye identificadores como ID de proveedor de datos, ID de usuario, ID declarados, códigos de integración, etc.
* Comprueba el PCS de características adicionales que un usuario ya ha realizado antes de una llamada de evento en tiempo real. Esto permite al DCS calificar a los usuarios en función de datos en tiempo real y datos históricos.
* Escribe archivos de registro y los envía a sistemas de Analytics para almacenamiento y procesamiento.

**[!UICONTROL DCS]Gestiona la demanda[!UICONTROL Global Server Load Balancing (GSLB)]**

The [!UICONTROL DCS] is a geographically distributed and load-balanced system. This means [!DNL Audience Manager] can direct requests to and from a regional data center based on the geographic location of a site visitor. This strategy helps improve response times because a [!UICONTROL DCS] response goes directly to a data center that contains information about that visitor. [!UICONTROL GSLB] hace que nuestro sistema sea eficiente porque los datos relevantes se almacenan en caché en servidores más próximos al usuario.

>[!IMPORTANT]
>
>The [!UICONTROL DCS] only detects web traffic originating from devices that use IPv4.

En una llamada de evento, la ubicación geográfica se captura en un par de valores clave devueltos en un cuerpo mayor de datos JSON. This key-value pair is the `"dcs_region": region ID` parameter.

![](assets/dcs-map.png)

As a customer, you engage with the [!UICONTROL DCS] indirectly through our data collection code. You can also work directly with the [!UICONTROL DCS] through a set of APIs. See [Data Collection Server (DCS) API Methods and Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

The [!UICONTROL PCS] is a large database (basically, a huge server-side cookie). It stores data received for active users from server-to-server transfers and the [!UICONTROL DCS]. [!UICONTROL PCS] consiste en ID de dispositivo, ID de perfiles autenticados y sus características asociadas. When the [!UICONTROL DCS] receives a real time call, it checks the [!UICONTROL PCS] for other traits a user may belong to or qualify for. And, if a trait is added to a segment at a later time, those trait IDs are added to the [!UICONTROL PCS] and users can qualify for that segment automatically, without a visit to a particular site or app. [!UICONTROL PCS] Esto ayuda a profundizar [!DNL Audience Manager]la comprensión de los usuarios, ya que puede relacionar y segmentar a los usuarios en tiempo real o entre bastidores con datos de características nuevos e históricos. Este comportamiento proporciona una imagen más completa y completa de los usuarios que de las calificaciones en tiempo real.

There are no UI controls that lets our customers work directly with the [!UICONTROL PCS]. Customer access to the [!UICONTROL PCS] is indirect, through its role as a data store and data transfers. [!UICONTROL PCS] Las ejecuciones en Apache Cassandra.

**Purgando ID inactivos de la variable[!UICONTROL PCS]**

As indicated previously, the [!UICONTROL PCS] stores trait IDs for active users. An active user is any user who has been seen by the [edge data servers](../../reference/system-components/components-edge.md) from any domain during the last 14-days. These calls to the [!UICONTROL PCS] keep a user in an active state:

* [!DNL /event] llamadas
* [!DNL /ibs] llamadas (sincronización de ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

The [!UICONTROL PCS] flushes traits if they&#39;re inactive for 17-days. Sin embargo, estas características no se pierden. Se almacenan en Hadoop. If the user is seen again at another time, then Hadoop pushes all of their traits back to the [!UICONTROL PCS], typically within a 24-hour period.

**Otros[!UICONTROL DCS/PCS]procesos: Exclusión de privacidad**

Estos sistemas de servidor administran la privacidad y las solicitudes de exclusión del usuario. La información de la cookie de usuario no se recopila en el archivo de registro si un usuario ha excluido la recopilación de datos. For more information about our privacy policies see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

## Biblioteca de integración de datos (DIL) {#dil}

[!UICONTROL DIL] es el código que coloca en la página para la recopilación de datos. See the [DIL API](../../dil/dil-overview.md) for more information about available services and methods.

## Inbound Server-to-Server {#inbound-outbound-server}

Sistemas que reciben datos enviados por diversas integraciones servidor a servidor con nuestros clientes. See the documentation on [sending audience data](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) for more information.

## Log Files {#log-files}

The [!UICONTROL PCS] creates and writes data to the log files. Se envían a otros sistemas de base de datos para procesamiento, informes y almacenamiento.

>[!MORE_ LIKE_ THIS]
>
>* [Centro de privacidad de Adobe](https://www.adobe.com/privacy.html)

