---
description: Preguntas y problemas comunes relacionados con los objetivos.
seo-description: Preguntas y problemas comunes relacionados con los objetivos.
seo-title: Preguntas más frecuentes sobre objetivo
solution: Audience Manager
title: Preguntas más frecuentes sobre objetivo
uuid: ee 96 ef 71-b 903-4953-afc 4-8 ec 8 e 48 bd 49 e
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Targeting FAQ{#targeting-faq}

Preguntas y problemas comunes relacionados con los objetivos.

<br> 

<!-- 

faq_targeting.xml

 -->

**¿Dónde puedo encontrar una lista completa de proveedores de datos de terceros compatibles con Audience Manager?**

See the [Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) (https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) for a complete list of third-party data providers that [!DNL Audience Manager] supports.

<br> 

**Para dirigir a los usuarios que nunca he visto en el sitio con datos de terceros,¿debo utilizar datos de terceros en Audience Manager o en un DSP?**

La respuesta depende de sus objetivos. Por ejemplo, si la campaña está diseñada para buscar nuevos clientes con datos de terceros, trabaje directamente con un DSP. Recuerde, Audience Manager sincroniza los datos con un proveedor de datos de terceros solo cuando vemos que el usuario. Si nunca antes vimos un usuario, nuestro sistema no tendrá información para el visitante del sitio. En el caso de campañas que solo deseen utilizar datos de terceros para dirigirse a usuarios que nunca hayan visitado ninguna de sus propiedades, a continuación, cree esos segmentos a través de DSP.

<br> 

**¿Puedo hacer un mercado para individuos?**

Audience Manager le permite agregar usuarios y comercializarlos en función de atributos o características compartidos. However, to comply with industry regulations, [!DNL Audience Manager] customers may not send personally identifiable information (PII) to our systems. Como resultado, no puede utilizar direcciones de correo electrónico, nombres individuales, direcciones físicas, etc. para la segmentación.

<br> 

**¿Cómo sigo regenerando datos de forma segura?**

Le recomendamos que utilice una conexión servidor a servidor para intercambiar datos con su plataforma de redestino preferida. Audience Manager intercambia datos con la mayoría de los principales DP a través de conexiones servidor a servidor. Las transferencias de datos de servidor a servidor ayudan a impedir que otros actores intercepten sus datos y vuelvan a vender dicha información de audiencia.

<br> 

**¿El ID de usuario único de Audience Manager (UUID) se asocia al ID de usuario único de un servidor de publicidad mediante la sincronización de ID directamente en la página?**

No. Los sincronizadores de ID no se realizan en la página para editores o servidores internos. The Audience Manager UUID is inserted into the `u=` field of the ad server log files. Esto sucede cuando se pasa el segmento por objetivo. El módulo de código DIL realiza esta función. Este es el mismo mecanismo que permite asignar el ID de usuario del servidor a un usuario de Audience Manager para los informes de rendimiento de segmentos. Sin embargo, si hay un servidor de publicidad en el sitio, entonces sincronizamos los ID directamente en la página.

<br> 

**¿Cuenta Audience Manager un usuario que inicia sesión desde distintos dispositivos como un único usuario o como usuarios únicos diferentes?**

[El targeting de ID declarado](../features/declared-ids.md#declared-id-targeting) ayuda a Audience Manager a identificar a un visitante en varios dispositivos con un único identificador único. Sin embargo, desde una perspectiva de destino o destino, ésta sigue siendo 2 (o más) usuarios porque los DSP no pueden reconciliar esos múltiples ID.

<br> 

**Puede identificar a un usuario desde la visualización y los dispositivos móviles.**

Sí. See [Declared ID Targeting](../features/declared-ids.md#declared-id-targeting).

<br> 

**¿Puedo puntuar a usuarios con datos recopilados en línea y retardarlos en base a esta puntuación de modelo?**

Sí. Audience Manager puede proporcionar archivos de datos para ayudarle a puntuar a los usuarios, pero debe trabajar con otros proveedores o software para analizar y clasificar esta información. Envíe estos datos a Audience Manager en forma de pares de clave-valor. Podemos tomar esta información y anexarla a perfiles de usuario existentes. Comuníquese con el representante de Soluciones de socio para consultar este proceso.

<br> 

**¿Cuáles son las tasas de eliminación de cookies en un período de 1 a 2 meses determinado?**

La eliminación de cookies es difícil de medir. La mayor parte de la eliminación de cookies procede de algunos visitantes que eliminan cookies con frecuencia. Sin embargo, la mayoría de las cookies del navegador son estables durante al menos 30 días, aunque algunos tengan una duración limitada. Algunos estudios sugieren que la segmentación por canal superior que es superior a 30 días eliminaría de forma eficaz el 7% de la audiencia objetivo del navegador durante un período de 30 días. Como usted sabe, las campañas de 30 días para un mensaje creativo determinado son estándar en el sector. A partir de lo que hemos visto, la devolución del 7% es precisa.

La eliminación de cookies tiene un efecto adverso en los cálculos de alcance y frecuencia. Como resultado, se subraya el valor de los datos de comportamiento al intentar comprender la naturaleza verdadera de las tendencias del consumidor para la planificación de campañas de visualización. Nuestros clientes pueden aprovechar los informes de superposición de segmentos de Audience Manager, los informes de frecuencia de impresión óptima y las tendencias de usuarios únicos en intervalos de fechas específicos para que sean más científicos sobre la planificación de campañas y los intervalos de fechas óptimos para ejecutar campañas.

<br> 

**¿Cuál es la ventana de caducidad para las cookies de Audience Manager?**

La interfaz de usuario permite determinar el intervalo de caducidad de la cookie. You can set cookies to expire after *n* number of days or never.

<br> 

**¿La implementación de un elemento creativo de campaña en una llamada de evento nos cuesta más?**

Depende. El costo se basa en usuarios únicos. Si una campaña da como resultado nuevos usuarios netos, entonces sí, esto costará más. Si la campaña llega a lugares en los que ya recopilamos datos, no habrá costo adicional. Si la campaña se ejecuta en sitios relacionados donde existe una superposición significativa, habrá costos adicionales para los nuevos usuarios únicos que vemos.

<br> 

**Audience Manager muestra[!UICONTROL Addressable Audiences]las métricas y tasas de coincidencia solo para[!UICONTROL Server-to-Server]destinos. Can you explain why we don&#39;t see these figures for Cookie and URL destinations?**

Se reduce a las sincronizaciones de ID. For [!UICONTROL Server-to-Server] destinations, we transfer data offline (either real-time or batch) and we need to send the ID that the destination partner understands, so they can map it back to the browser. El número objetivo de segmentos es un subconjunto de la población total de segmentos.

In the case of Cookie and URL destinations, the user is already on the browser, and what [!DNL Audience Manager] sends is just the segments that the user qualified for. El socio de destino sólo puede recoger las asignaciones de segmentos y trabajar con esa información. Por lo tanto, considere las tasas de coincidencia para destinos de Cookie y URL siempre 100%.
