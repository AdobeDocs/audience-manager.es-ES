---
description: Preguntas y problemas comunes relacionados con los objetivos.
seo-description: Preguntas y problemas comunes relacionados con los objetivos.
seo-title: Preguntas más frecuentes sobre objetivos
solution: Audience Manager
title: Preguntas más frecuentes sobre objetivos
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Preguntas más frecuentes sobre objetivos{#targeting-faq}

Preguntas y problemas comunes relacionados con los objetivos.

<br> 

<!-- 

faq_targeting.xml

 -->

**¿Dónde puedo encontrar una lista completa de proveedores de datos de terceros admitidos por Audience Manager?**

Consulte [Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) (https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) para obtener una lista completa de proveedores de datos de terceros que [!DNL Audience Manager] admiten.

<br> 

**Para dirigirse a usuarios que nunca he visto en mi sitio con datos de terceros, ¿debo usar datos de terceros en Audience Manager o en un DSP?**

La respuesta depende de tus objetivos. Por ejemplo, si la campaña está diseñada para encontrar nuevos clientes con datos de terceros, trabaje directamente con un DSP. Recuerde que Audience Manager sincroniza los datos con un proveedor de datos de terceros solo cuando se ve ese usuario. Si nunca antes hemos visto a un usuario, nuestro sistema no tendrá información para ese visitante del sitio. En el caso de campañas que solo deseen utilizar datos de terceros para dirigirse a usuarios que nunca hayan visitado ninguna de sus propiedades, cree dichos segmentos a través del DSP.

<br> 

**¿Puedo comercializar con individuos?**

Audience Manager le permite agregar usuarios y comercializarlos en función de atributos o características compartidos. Sin embargo, para cumplir con las regulaciones de la industria, los clientes no pueden enviar información personal (PII) a nuestros sistemas. [!DNL Audience Manager] Como resultado, no puede utilizar direcciones de correo electrónico, nombres individuales, direcciones físicas, etc. para objetivos.

<br> 

**¿Cómo sigo dirigiendo los datos de forma segura?**

Le recomendamos que utilice una conexión servidor a servidor para intercambiar datos con su plataforma de resegmentación preferida. Audience Manager intercambia datos con la mayoría de los principales DSP mediante conexiones de servidor a servidor. Las transferencias de datos de servidor a servidor ayudan a evitar que otros actores intercepten sus datos y vuelvan a vender la información de la audiencia.

<br> 

**¿El ID de usuario único (UUID) de Audience Manager está vinculado al ID de usuario único de un servidor de publicidad mediante la sincronización directa de ID en la página?**

No. Las sincronizaciones de ID no se realizan en la página para editores o servidores en el sitio. El UUID de Audience Manager se inserta en el `u=` campo de los archivos de registro del servidor de publicidad. Esto sucede cuando se pasa el segmento por objetivos. El módulo de código DIL realiza esta función. Este es el mismo mecanismo que nos permite asignar el ID de usuario del servidor a un usuario de Audience Manager para los informes de rendimiento de segmentos. Sin embargo, si hay un servidor de publicidad en el sitio, entonces sincronizamos los ID directamente en la página.

<br> 

**¿Cuenta Audience Manager un usuario que inicia sesión desde distintos dispositivos como un usuario único o como otro usuario único?**

[La segmentación](../features/declared-ids.md#declared-id-targeting) de ID declarada ayuda a Audience Manager a identificar a un visitante en varios dispositivos con un único identificador único. Sin embargo, desde una perspectiva de objetivo o de destino, sigue habiendo 2 (o más) usuarios, ya que los DSP no pueden reconciliar estos ID múltiples.

<br> 

**Puede Audience Manager identificar a un usuario desde la pantalla y los dispositivos móviles.**

Sí. Consulte Objetivo [de ID declarado](../features/declared-ids.md#declared-id-targeting).

<br> 

**¿Puedo puntuar a los usuarios con los datos recopilados en línea y volver a segmentar según esta puntuación de modelo?**

Sí. Audience Manager puede proporcionar archivos de datos para ayudarle a puntear a los usuarios, pero debe trabajar con otros proveedores o software para analizar y clasificar esta información. Envíe estos datos a Audience Manager en forma de pares clave-valor. Podemos tomar esta información y anexarla a los perfiles de usuario existentes. Póngase en contacto con su representante de soluciones de socio para revisar este proceso.

<br> 

**¿Cuáles son las tasas de eliminación de cookies durante un período de 1 a 2 meses determinado?**

La eliminación de cookies es difícil de medir. La mayoría de las eliminaciones de cookies provienen de algunos visitantes que las eliminan con frecuencia. Sin embargo, la mayoría de las cookies del navegador son estables durante al menos 30 días, aunque algunas pueden tener una vida limitada. Algunos estudios sugieren que la segmentación por canales superiores que sea superior a 30 días eliminaría efectivamente el 7 % de la audiencia objetivo del explorador durante un período de 30 días. Como sabe, las campañas de 30 días para un mensaje creativo determinado son estándar en el sector. Por lo que hemos visto, esa caída del 7% es precisa.

La eliminación de cookies tiene un efecto adverso en los cálculos de alcance y frecuencia. Como resultado, resaltamos el valor de los datos de comportamiento al intentar comprender la verdadera naturaleza de las tendencias de los consumidores para la planificación de campañas de visualización. Nuestros clientes pueden aprovechar los informes de superposición de segmentos de Audience Manager, los informes de frecuencia de impresión óptima y las tendencias únicas de los usuarios en intervalos de fechas específicos para ser más científicos sobre la planificación de campañas y los intervalos de fechas óptimos para ejecutar campañas.

<br> 

**¿Cuál es la ventana de caducidad de las cookies de Audience Manager?**

La interfaz de usuario permite determinar el intervalo de caducidad de la cookie. Puede configurar las cookies para que caduquen después de *n* días o nunca.

<br> 

**¿Nos cuesta más implementar un elemento creativo de campaña en una llamada de evento?**

Depende. El costo se basa en usuarios únicos. Si una campaña resulta en nuevos usuarios netos, entonces sí, esto costará más. Si la campaña llega a lugares donde ya estamos recopilando datos, entonces no hay costo adicional. Si la campaña se ejecuta en sitios relacionados donde hay una superposición significativa, habrá costo adicional para los nuevos usuarios únicos que vemos.

<br> 

**Audience Manager muestra[!UICONTROL Addressable Audiences]métricas y tasas de coincidencia solo para[!UICONTROL Server-to-Server]destinos. ¿Puede explicar por qué no vemos estas cifras para los destinos de cookies y URL?**

Se reduce a sincronizaciones de ID. Para [!UICONTROL Server-to-Server] destinos, transferimos datos sin conexión (ya sea en tiempo real o por lotes) y necesitamos enviar el ID que el socio de destino entienda, para que pueda asignarlo de nuevo al explorador. El número direccionable del segmento es un subconjunto de la población total del segmento.

En el caso de las cookies y los destinos URL, el usuario ya está en el explorador y lo que [!DNL Audience Manager] envía son solo los segmentos para los que el usuario cumple los requisitos. El socio de destino solo puede recoger las asignaciones de segmentos y trabajar con esa información. Por lo tanto, tenga en cuenta que las tasas de coincidencia para los destinos de cookies y URL siempre son del 100 %.
