---
description: Preguntas y problemas comunes relacionados con la segmentación
seo-description: Common targeting-related questions and issues.
seo-title: Targeting FAQ
solution: Audience Manager
title: Preguntas frecuentes sobre segmentación
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
feature: Match Rates
exl-id: e5f761fd-dfc8-4859-a81e-89abbd7f2914
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 100%

---

# Preguntas frecuentes sobre segmentación{#targeting-faq}

Preguntas y problemas comunes relacionados con la segmentación

<br> 

<!-- 

faq_targeting.xml

 -->

**¿Dónde puedo encontrar una lista completa de proveedores de datos de terceros admitidos por Audience Manager?**

Consulte [Adobe Exchange Marketplace](https://exchange.adobe.com/experiencecloud.html) para obtener una lista completa de los proveedores de datos de terceros que admite [!DNL Audience Manager].

<br> 

**Para aproximarme a usuarios que nunca he visto en mi sitio con datos de terceros, ¿debo usar datos de terceros en Audience Manager o en un DSP?**

La respuesta depende de los objetivos perseguidos. Por ejemplo, si la campaña está diseñada para encontrar nuevos clientes con datos de terceros, trabaje directamente con un DSP. Se debe tener en cuenta que Audience Manager sincroniza los datos con un proveedor de datos de terceros solo cuando vemos a ese usuario. El sistema no tendrá información sobre ese visitante del sitio si nunca lo había visto. Para campañas en las que solo desee utilizar datos de terceros para aproximarse a usuarios que nunca habían visitado sus propiedades, cree dichos segmentos a través del DSP.

<br> 

**¿Puedo comercializar con particulares?**

Audience Manager le permite juntar usuarios y hacerles llegar ofertas en función de rasgos o atributos compartidos. Sin embargo, en cumplimiento de las normas del sector, los clientes de [!DNL Audience Manager] no pueden enviar información personal identificable (PII) a nuestros sistemas. Como resultado, no se pueden utilizar direcciones de correo electrónico, nombres individuales, direcciones postales, etc. para la segmentación.

<br> 

**¿Cómo puedo continuar resegmentando los datos de manera segura?**

Recomendamos que use una conexión servidor a servidor para intercambiar datos con su plataforma de resegmentación preferida. Audience Manager intercambia datos con la mayoría de los DSP principales a través de conexiones de servidor a servidor. Las transferencias de datos de servidor a servidor ayudan a evitar que otros intercepten sus datos y vuelvan a vender esa información sobre la audiencia.

<br> 

**¿El ID de usuario único (UUID) de Audience Manager está vinculado al ID de usuario único de un servidor de publicidad a través de la sincronización de ID directamente en la página?**

No. Las sincronizaciones de ID no se realizan en la página para editores o servidores in situ. El UUID de Audience Manager se inserta en el campo `u=` de los archivos de registro del servidor de publicidad. Esto sucede cuando el segmento se incorpora a la segmentación. El módulo de código DIL realiza esta función. Se trata del mismo mecanismo que permite asignar el ID de usuario del servidor a un usuario de Audience Manager para la creación de informes sobre rendimiento de segmentos. Sin embargo, si hay un servidor de publicidad en el sitio, sincronizamos los ID directamente en la página.

<br> 

**¿Audience Manager cuenta un usuario que inicia sesión desde distintos dispositivos como un usuario único o como diferentes usuarios únicos?**

[La segmentación de ID declarada](../features/declared-ids.md#declared-id-targeting) ayuda a Audience Manager a identificar a un visitante en varios dispositivos con un único identificador. Sin embargo, desde una perspectiva de segmentación o de destino, se trata de dos o más usuarios, ya que los DSP no pueden hacer cuadrar estos ID múltiples.

<br> 

**¿Audience Manager puede identificar a un usuario desde una pantalla y dispositivos móviles?**

Sí. Consulte [Segmentación de ID declarado](../features/declared-ids.md#declared-id-targeting).

<br> 

**¿Puedo puntuar a los usuarios con los datos recopilados en línea y resegmentarlos en función de esa puntuación?**

Sí. Audience Manager puede aportar archivos de datos para ayudarle a puntuar a los usuarios, pero debe trabajar con otros proveedores o software para analizar y clasificar esta información. Envíe estos datos a Audience Manager en forma de pares clave-valor. Podemos añadir esta información a los perfiles de usuario existentes. Póngase en contacto con su representante de Soluciones para socios para revisar este proceso.

<br> 

**¿Cuál es la tasa de eliminación de cookies durante un periodo determinado de entre uno y dos meses?**

La eliminación de cookies es difícil de medir. La mayoría de las eliminaciones de cookies provienen de unos pocos visitantes que las borran con frecuencia. Sin embargo, la mayoría de las cookies del navegador son estables durante al menos 30 días, aunque algunas pueden tener una duración limitada. Algunos estudios sugieren que una segmentación en la parte inicial del canal de más de 30 días supondría una supresión del 7% de la audiencia de destino en el explorador durante un periodo de 30 días. Es sabido que la duración estándar de una campaña para un determinado mensaje creativo es de 30 días. Por lo que hemos visto, ese dato de la caída del 7% es preciso.

La eliminación de cookies tiene un efecto adverso en los cálculos de alcance y frecuencia. Por ello, es destacable el valor de los datos de comportamiento para comprender el auténtico carácter de las tendencias de consumo a la hora de planificar las campañas. Nuestros clientes pueden aprovechar los informes de Audience Manager sobre superposición de segmentos, de frecuencia de impresión óptima y las tendencias de usuario único en intervalos específicos de fechas, a fin de incorporar una perspectiva más científica en la planificación de campañas y en los intervalos óptimos de fechas para ejecutarlas.

<br> 

**¿Qué periodo de caducidad tienen las cookies de Audience Manager?**

La interfaz de usuario permite determinar el intervalo de caducidad de las cookies. Las cookies se pueden configurar para que caduquen después de *n* días o nunca.

<br> 

**¿Tiene un mayor coste implementar un elemento creativo de campaña en una llamada de evento?**

Depende. El coste se basa en los usuarios únicos. Si una campaña logra nuevos usuarios netos, entonces el coste será mayor. Si su campaña llega a lugares donde ya estamos recopilando datos, entonces no hay coste adicional. Si la campaña se ejecuta en sitios relacionados donde hay una superposición significativa, habrá un coste adicional por los nuevos usuarios únicos.

<br> 

**Audience Manager muestra métricas de [!UICONTROL Addressable Audiences] y tasas de coincidencia solo para los destinos [!UICONTROL Server-to-Server]. ¿Por qué no vemos estas cifras para los destinos de cookies y URL?**

Esto se debe básicamente a sincronizaciones de ID. Para destinos [!UICONTROL Server-to-Server], transferimos datos sin conexión (ya sea en tiempo real o por lotes) y tenemos que enviar un ID que el socio de destino entienda, de modo que pueda volver a asignarlo al explorador. El número accesible del segmento es un subconjunto de la población total del segmento.

En el caso de las cookies y los destinos URL, el usuario ya está en el explorador y lo que [!DNL Audience Manager] envía son solo los segmentos para los que el usuario cumple los requisitos. El socio de destino solo puede recoger las asignaciones de segmentos y trabajar con esa información. Por lo tanto, tenga en cuenta que la tasa de coincidencia para los destinos de cookies y URL siempre son del 100%.
