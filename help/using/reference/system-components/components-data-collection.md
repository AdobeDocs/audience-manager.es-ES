---
description: Los componentes de colección datos incluyen los servidores de recopilación de datos, la API DIL, las transferencias de datos entrantes de servidor a servidor y los archivos de registro.
seo-description: Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.
seo-title: Data Collection Components
solution: Audience Manager
title: Componentes de recopilación de datos
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 3%

---

# Componentes de recopilación de datos{#data-collection-components}

Los componentes de colección datos incluyen los servidores de recopilación de datos, la API DIL, las transferencias de datos entrantes de servidor a servidor y los archivos de registro.

<!-- 

c_compcollect.xml

 -->

Audience Manager contiene los siguientes componentes de colección datos:

* [Servidores de recopilación de datos (DCS) y servidores de caché de perfil (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Biblioteca de integración de datos (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Servidor a servidor entrante](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Iniciar sesión Archivos](../../reference/system-components/components-data-collection.md#log-files)

## Servidores de recopilación de datos (DCS) y servidores de caché de perfil (PCS) {#dcs-pcs}

El DCS y el PCS trabajan juntos y proporcionan por separado servicios relacionados con la realización de rasgos, la segmentación de audiencia y la almacenamiento de datos.

**[!UICONTROL Data Collection Servers (DCS)]Función**

En [!DNL Audience Manager], el DCS:

* Recibe y evalúa datos de características de una llamada de evento. Esto incluye la información utilizada para el segmentación en tiempo real y los datos que se transfieren a intervalos programados mediante transferencias de servidor a servidor.
* Segmenta a los usuarios en función de sus características realizadas y de las reglas de cualificación que cree con [el Generador de segmentos](../../features/segments/segment-builder.md).
* Crea y administra ID de dispositivos e ID de perfil autenticados. Esto incluye identificadores como ID de proveedor de datos, ID de usuario, ID declarados, códigos de integración, etc.
* Comprueba el PCS en busca de características adicionales de las que un usuario ya se haya dado cuenta antes de una llamada de evento en tiempo real. Esto permite al DCS calificar a los usuarios basándose en datos y datos históricos en tiempo real.
* Escribe archivos de registro y los envía a análisis sistemas para su almacenamiento y procesamiento.

**[!DNL DCS]Gestiona la demanda a través de[!UICONTROL Global Server Load Balancing (GSLB)]**

Es [!DNL DCS] un sistema geográficamente distribuido y de carga equilibrada. Esto significa que [!DNL Audience Manager] puede dirigir solicitudes hacia y desde un centro de datos regional en función de la ubicación geográfica de una visitante del sitio. Esta estrategia ayuda a mejorar los tiempos de respuesta porque una [!DNL DCS] respuesta va directamente a un centro de datos que contiene información sobre ese visitante. [!UICONTROL GSLB] hace que nuestro sistema sea eficiente porque los datos relevantes se almacenan en caché en los servidores más cercanos al usuario.

>[!IMPORTANT]
>
>El [!DNL DCS] único detecta tráfico web procedentes de dispositivos que utilizan IPv4.

En una llamada de evento, la ubicación geográfica se captura en un par clave-valor devuelto en un cuerpo mayor de datos JSON. Este par clave-valor es el `"dcs_region": region ID` parámetro.

![](assets/dcs-map.png)

Como cliente, usted se involucra indirectamente a [!DNL DCS] través de nuestro código recopilación de datos. También puede trabajar directamente con el [!DNL DCS] a través de un conjunto de API. Consulte [Métodos y Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md) de API del servidor de recopilación de datos (DCS).

**[!UICONTROL Profile Cache Servers (PCS)]**

Es [!UICONTROL PCS] una base de datos grande (básicamente, una gran del lado del servidor cookie). Almacena los datos recibidos para los usuarios activos desde las transferencias de servidor a servidor y desde [!DNL DCS]. [!UICONTROL PCS] los datos se componen de ID de dispositivos, ID de perfil autenticados y sus características asociadas. Cuando recibe [!DNL DCS] una llamada en tiempo real, verifica los otros rasgos a los [!UICONTROL PCS] que un usuario puede pertenecer o para los que puede calificar. Y, si un rasgo se agrega a un segmento en un momento posterior, esos identificadores de rasgos se agregan al [!UICONTROL PCS] y los usuarios pueden calificar para ese segmento automáticamente, sin un visita a un sitio o aplicación en particular. Ayuda [!UICONTROL PCS] a profundizar la [!DNL Audience Manager]comprensión de los usuarios porque puede hacer coincidir y segmento a los usuarios en tiempo real o entre bastidores con datos de rasgos nuevos e históricos. Este comportamiento ofrece una imagen más completa y precisa de los usuarios que el de las cualificaciones en tiempo real.

No existen controles IU que permitan a nuestros clientes trabajar directamente con el [!UICONTROL PCS]. El acceso del cliente al [!UICONTROL PCS] es indirecto, a través de su función como tienda de datos y transferencias de datos. Las [!UICONTROL PCS] ejecuciones en Apache Cassandra.

**Se están purgando los ID inactivos del[!UICONTROL PCS]**

Como se ha indicado anteriormente, almacena [!UICONTROL PCS] los ID de características de los usuarios activos. Un usuario activo es cualquier usuario que haya sido visto por los [servidores](../../reference/system-components/components-edge.md) de datos perimetrales desde cualquier dominio durante los últimos 14 días. Estas llamadas para mantener un [!UICONTROL PCS] usuario en estado activo:

* [!DNL /event] Llamadas
* [!DNL /ibs] llamadas (sincronizaciones de ID)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Los [!UICONTROL PCS] rubores son características si están inactivos durante 17 días. Sin embargo, estos rasgos no se pierden. Se almacenan en Hadoop. Si el usuario se vuelve a ver en otro momento, entonces Hadoop empuja todos sus rasgos de nuevo al [!UICONTROL PCS], normalmente dentro de un período de 24 horas.

**Otros [!UICONTROL DCS/PCS] procesos: Exclusión de privacidad**

Estos sistemas de servidor gestionan las solicitudes de privacidad y usuario exclusión. La información del cookie del usuario no se recopila en el archivo de registro si un usuario ha optado por no participar en recopilación de datos. Para obtener más información sobre nuestras políticas de privacidad, consulte el Centro[ de privacidad de Adobe Systems](https://www.adobe.com/es/privacy/advertising-services.html).

## Biblioteca de integración de datos (DIL) {#dil}

[!UICONTROL DIL] es el código que coloca en el Página para recopilación de datos. Consulte la API[ de DIL para obtener más información sobre los ](../../dil/dil-overview.md)servicios y métodos disponibles.

## Servidor a servidor entrante {#inbound-outbound-server}

Estos son sistemas que reciben datos enviados por varias integraciones de servidor a servidor con nuestros clientes. Consulte la documentación sobre [el envío de datos](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) de audiencia para obtener más información.

## Iniciar sesión Archivos {#log-files}

Crea [!UICONTROL PCS] y escribe datos en los archivos de registro. Se envían a otros sistemas de bases de datos para su procesamiento, sistema de informes y almacenamiento.

>[!MORELIKETHIS]
>
>* [Centro de privacidad de Adobe](https://www.adobe.com/es/privacy.html)
