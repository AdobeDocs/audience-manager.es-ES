---
description: Los componentes de recopilación de datos incluyen los servidores de recopilación de datos, la API DIL, las transferencias de datos de entrada de servidor a servidor y los archivos de registro.
seo-description: Los componentes de recopilación de datos incluyen los servidores de recopilación de datos, la API DIL, las transferencias de datos de entrada de servidor a servidor y los archivos de registro.
seo-title: Componentes de recopilación de datos
solution: Audience Manager
title: Componentes de recopilación de datos
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 1%

---


# Componentes de recopilación de datos{#data-collection-components}

Los componentes de recopilación de datos incluyen los servidores de recopilación de datos, la API DIL, las transferencias de datos de entrada de servidor a servidor y los archivos de registro.

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

**[!UICONTROL Data Collection Servers (DCS)]Función **

En [!DNL Audience Manager], el DCS:

* Recibe y evalúa los datos de características de una llamada de evento. Esto incluye la información utilizada para la segmentación en tiempo real y los datos pasados a intervalos programados por transferencias de servidor a servidor.
* Segmenta a los usuarios según sus características realizadas y las reglas de calificación que cree con el Generador [de segmentos](../../features/segments/segment-builder.md).
* Crea y gestiona ID de dispositivo e ID de perfil autenticados. Esto incluye identificadores como ID de proveedores de datos, ID de usuario, ID declarados, códigos de integración, etc.
* Comprueba si el PCS tiene características adicionales que ya ha adquirido un usuario antes de realizar una llamada de evento en tiempo real. Esto permite que el DCS califique a los usuarios en función de datos en tiempo real y datos históricos.
* Escribe archivos de registro y los envía a los sistemas de análisis para su almacenamiento y procesamiento.

**[!DNL DCS]Gestiona La Demanda A Través De[!UICONTROL Global Server Load Balancing (GSLB)]**

The [!DNL DCS] is a geographically distributed and load-balanced system. Esto significa [!DNL Audience Manager] que puede dirigir las solicitudes desde y hacia un centro de datos regional en función de la ubicación geográfica del visitante del sitio. Esta estrategia ayuda a mejorar los tiempos de respuesta porque una [!DNL DCS] respuesta va directamente a un centro de datos que contiene información sobre ese visitante. [!UICONTROL GSLB] hace que nuestro sistema sea eficiente porque los datos relevantes se almacenan en caché en los servidores más cercanos al usuario.

>[!IMPORTANT]
>
>El [!DNL DCS] solo detecta el tráfico web que se origina en dispositivos que utilizan IPv4.

En una llamada de evento, la ubicación geográfica se captura en un par clave-valor devuelto en un cuerpo mayor de datos JSON. Este par clave-valor es el `"dcs_region": region ID` parámetro.

![](assets/dcs-map.png)

Como cliente, usted interactúa con el [!DNL DCS] indirectamente a través de nuestro código de recopilación de datos. También puede trabajar directamente con el [!DNL DCS] a través de un conjunto de API. Consulte Métodos y código [de la API del servidor](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)de recopilación de datos (DCS).

**[!UICONTROL Profile Cache Servers (PCS)]**

La [!UICONTROL PCS] es una base de datos grande (básicamente, una enorme cookie del lado del servidor). Almacena los datos recibidos para los usuarios activos desde las transferencias de servidor a servidor y desde el [!DNL DCS]. [!UICONTROL PCS] los datos constan de ID de dispositivo, ID de perfil autenticados y sus características asociadas. Cuando el usuario [!DNL DCS] recibe una llamada en tiempo real, comprueba la existencia [!UICONTROL PCS] de otros rasgos a los que puede pertenecer o a los que calificar. Y, si se agrega una característica a un segmento más adelante, esos ID de características se agregan al segmento [!UICONTROL PCS] y los usuarios pueden calificar para ese segmento automáticamente, sin visitar un sitio o aplicación en particular. Esto [!UICONTROL PCS] ayuda a profundizar [!DNL Audience Manager]la comprensión de los usuarios, ya que puede relacionar y segmentar a los usuarios en tiempo real o entre bastidores con datos de características nuevos e históricos. Este comportamiento le ofrece una imagen más completa y precisa de los usuarios que de las calificaciones en tiempo real.

No hay controles de interfaz de usuario que permitan a nuestros clientes trabajar directamente con el [!UICONTROL PCS]. El acceso de los clientes al [!UICONTROL PCS] sitio es indirecto, a través de su función como almacén de datos y transferencias de datos. El [!UICONTROL PCS] se ejecuta en Apache Cassandra.

**Depuración de ID inactivos de la variable[!UICONTROL PCS]**

Como se indicó anteriormente, los ID de características [!UICONTROL PCS] se almacenan para los usuarios activos. Un usuario activo es cualquier usuario que haya sido visto por los servidores [de datos](../../reference/system-components/components-edge.md) Edge desde cualquier dominio durante los últimos 14 días. Estas llamadas para mantener [!UICONTROL PCS] a un usuario en estado activo:

* [!DNL /event] llamadas
* [!DNL /ibs] llamadas (sincronizaciones de ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Los [!UICONTROL PCS] vaciados se caracterizan si están inactivos durante 17 días. Sin embargo, estos rasgos no se pierden. Están almacenados en Hadoop. Si se vuelve a ver al usuario en otro momento, Hadoop devuelve todas sus características al [!UICONTROL PCS], generalmente en un período de 24 horas.

**Otros[!UICONTROL DCS/PCS]procesos: Exclusión de privacidad**

Estos sistemas de servidor gestionan las solicitudes de privacidad y de exclusión de usuarios. La información de las cookies de usuario no se recopila en el archivo de registro si un usuario ha exclusión de la recopilación de datos. Para obtener más información sobre nuestras políticas de privacidad, consulte [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

## Biblioteca de integración de datos (DIL) {#dil}

[!UICONTROL DIL] es el código que se coloca en la página para la recopilación de datos. Consulte la API [](../../dil/dil-overview.md) DIL para obtener más información sobre los servicios y métodos disponibles.

## Servidor entrante a servidor {#inbound-outbound-server}

Son sistemas que reciben datos enviados por diversas integraciones servidor a servidor con nuestros clientes. Consulte la documentación sobre el [envío de datos](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) de audiencia para obtener más información.

## Archivos de registro {#log-files}

El [!UICONTROL PCS] crea y escribe datos en los archivos de registro. Se envían a otros sistemas de bases de datos para procesamiento, sistema de informes y almacenamiento.

>[!MORELIKETHIS]
>
>* [Centro de privacidad de Adobe](https://www.adobe.com/privacy.html)

