---
description: 'Utilice destinos basados en personas para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se está mostrando dentro de ella. Incluyen plataformas sociales como Facebook y otras que dependen de cuentas de cliente para personalizar el contenido mostrado. '
seo-description: Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content.
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: Información general y casos de uso
feature: People-based Destinations
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: ab3361a0a54a7200d2f0c03a82ae6ef61a755be9
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 1%

---

# Información general y casos de uso {#overview-use-cases}

Utilice [!DNL People-Based Destinations] para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se está mostrando dentro de ella. Incluyen plataformas sociales como [!DNL Facebook] y otras plataformas que dependen de cuentas de cliente para personalizar el contenido mostrado.

>[!IMPORTANT]
>Este artículo contiene documentación del producto pensada para guiarle en la configuración y uso de esta función. Nada de lo contenido en este documento es asesoramiento jurídico. Consulte a su propio asesor jurídico para obtener asesoramiento jurídico.

## Información general {#overview}

[!DNL People-Based Destinations] permite aplicar segmentación en datos en línea y sin conexión para crear segmentos de audiencia basados en identificadores [ ](people-based-destinations-prerequisites.md#hashing-requirements) hash, como direcciones de correo electrónico. A continuación, puede enviar estos segmentos a &quot;jardines amurallados&quot;, como [!DNL Facebook], donde puede dirigirse a la audiencia en las plataformas sociales. [!DNL People-Based Destinations] puede ayudarle a:

* Segmente audiencias en línea y sin conexión en plataformas como [!DNL Facebook], basadas en direcciones de correo electrónico con hash;
* Complementa las capacidades de segmentación de dispositivos y cookies existentes del Audience Manager;
* Eliminar los costes asociados con las soluciones de incorporación de datos de terceros;
* Eliminar los costes asociados con el desarrollo de flujos de trabajo de incorporación de datos personalizados;
* Segmente audiencias en entornos sin cookies;
* Para segmentar audiencias, deduplique las direcciones de correo electrónico con hash que coincidan con los ID de cliente.

Puede utilizar [!DNL People-Based Destinations] para segmentar y segmentar a los clientes de alto valor que posiblemente no visiten su sitio web, o dejar de segmentar a aquellos que ya se han convertido sin conexión. Además, puede aprovechar [!DNL Profile Merge Rules] para combinar sus datos de origen sin conexión con los datos de origen en línea, incluidos los datos de clientes de otras soluciones de Adobe Experience Cloud, para optimizar sus esfuerzos de publicidad en medios sociales.

![pbd-overview](assets/pbd-overview.png)

## Disponibilidad {#availability}

[!DNL People-Based Destinations] es una integración de Audience Manager premium. Póngase en contacto con su representante de Adobe para aprovechar esta función Premium.

## Por qué debería utilizar [!UICONTROL People-Based Destinations] {#why-use}

**Proporcione a sus clientes experiencias coherentes entre canales al administrar toda la segmentación de audiencias desde el Audience Manager.**

Si no se activan los segmentos de audiencia en canales basados en personas a través del Audience Manager, se generan experiencias no vinculadas entre lo que ven los clientes al visitar el sitio web y lo que ven, por ejemplo, en sus fuentes [!DNL Facebook]. Tener una segmentación uniforme en los distintos canales puede aumentar los ingresos publicitarios al mismo tiempo que optimiza el gasto publicitario.

**Llegue a las audiencias en canales basados en personas sin necesidad de una solución de incorporación de datos dedicada o flujos de trabajo personalizados para enviar audiencias.**

La forma más &quot;tradicional&quot; de segmentar audiencias en canales basados en personas implica que debe exportar los datos de clientes en un formato aceptado por la plataforma en la que desee publicitar y, a continuación, utilizar el método de incorporación de datos específico de la plataforma para llevar los datos de clientes a su cuenta de anunciante. Este es todo el trabajo manual que debe realizar para cada plataforma en la que desee publicitar. Además, diferentes plataformas pueden tener diferentes requisitos de formato de datos, lo que hace que el proceso sea aún más tedioso.

![pbd-overview](assets/pbd-diagram.png)

A través de [!DNL People-Based Destinations], Audience Manager le ayuda a centralizar los datos de sus clientes, crear segmentos de audiencia y activarlos en varios canales basados en personas. Puede hacerlo todo desde la interfaz de usuario del Audience Manager, evitando el trabajo adicional de cargar datos manualmente en cada plataforma, lo que le ahorra tiempo valioso en el proceso.

**Cree y active segmentos de audiencia a partir de perfiles puramente sin conexión.**

[!DNL People-Based Destinations] solucione el problema que anteriormente solo podía activar segmentos de audiencia en función de la actividad del dispositivo. Con [!DNL People-Based Destinations], puede crear segmentos a partir de datos que no estén en línea únicamente de su propio [!DNL CRM] y activarlos en plataformas basadas en personas. Además, puede correlacionar los datos sin conexión con los datos de dispositivos que ya tiene en Audience Manager.

**Aproveche los controles de privacidad y control de administración de datos del Audience Manager para administrar de forma segura los datos de los clientes.**

[!DNL People-Based Destinations] requiere que solo utilice identificadores con hash irreversibles. Esto reduce el riesgo asociado con la carga manual de datos de clientes en cada plataforma de destino.

Vea el siguiente vídeo para obtener una descripción general del flujo de datos al utilizar [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Casos de uso {#use-cases}

Para ayudarle a comprender mejor cómo y cuándo debe utilizar [!DNL People-Based Destinations], estos son dos casos de uso de muestra que los clientes Audience Manager pueden resolver mediante esta función.

### Caso de uso n.º 1 {#use-case-1}

Un comerciante en línea quiere llegar a los clientes existentes a través de plataformas sociales y mostrarles ofertas personalizadas basadas en sus pedidos anteriores. Con [!DNL People-Based Destinations], el comerciante en línea puede ingerir direcciones de correo electrónico con hash desde su propio [!DNL CRM] Audience Manager, crear segmentos a partir de sus propios datos sin conexión y enviar estos segmentos a las plataformas sociales en las que desee publicitar, optimizando así su gasto en publicidad.

### Caso de uso n.º 2 {#use-case-2}

Una aerolínea tiene diferentes niveles de clientes (bronce, plata y oro) y desea proporcionar a cada uno de los niveles ofertas personalizadas a través de plataformas sociales. La empresa utiliza un Audience Manager para analizar la actividad de los clientes en el sitio web. Sin embargo, no todos los clientes utilizan la aplicación móvil de la aerolínea y algunos de ellos no han iniciado sesión en el sitio web de la empresa. Los únicos identificadores que la empresa tiene sobre estos clientes son los ID de pertenencia y las direcciones de correo electrónico.

Para dirigirlos a través de los medios sociales y canales similares basados en personas, pueden incorporar los datos de clientes de su [!DNL CRM] en el Audience Manager, utilizando como identificadores las direcciones de correo electrónico con hash.

A continuación, pueden combinar sus datos sin conexión con sus rasgos de actividad en línea existentes para crear nuevos segmentos de audiencia a los que pueden dirigirse mediante [!DNL People-Based Destinations].
