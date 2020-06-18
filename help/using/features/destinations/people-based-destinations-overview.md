---
description: 'Use destinos basados en personas para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se muestra dentro de ella. Incluyen plataformas sociales como Facebook y otras plataformas que dependen de cuentas de clientes para personalizar el contenido mostrado. '
seo-description: 'Use destinos basados en personas para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se muestra dentro de ella. Incluyen plataformas sociales como Facebook y otras plataformas que dependen de cuentas de clientes para personalizar el contenido mostrado.  '
seo-title: Información general de destinos basados en personas y casos de uso
solution: Audience Manager
title: Información general y casos de uso
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 0%

---


# Información general y casos de uso {#overview-use-cases}

Se utiliza [!DNL People-Based Destinations] para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se muestra dentro de ella. Incluyen plataformas sociales como [!DNL Facebook]y otras que dependen de cuentas de clientes para personalizar el contenido mostrado.

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

## Información general {#overview}

[!DNL People-Based Destinations] le permite aplicar segmentación en datos en línea y sin conexión para crear segmentos de audiencia basados en identificadores [](people-based-destinations-prerequisites.md#hashing-requirements)hash, como direcciones de correo electrónico o números de teléfono. A continuación, puede enviar estos segmentos a &quot;jardines amurallados&quot; como [!DNL Facebook], por ejemplo, donde puede destinatario de su audiencia en las plataformas sociales. [!DNL People-Based Destinations] puede ayudarle a:

* Destinatario de audiencias sin conexión y en línea en plataformas como [!DNL Facebook], por ejemplo, basadas en direcciones de correo electrónico con hash;
* Complementar las capacidades de segmentación de cookies y dispositivos existentes del Audience Manager;
* Eliminar los costos asociados con las soluciones de incorporación de datos de terceros;
* Eliminar los costos asociados con el desarrollo de flujos de trabajo personalizados de incorporación de datos;
* audiencias de Destinatario en entornos sin cookies;
* Destinatario de audiencias mediante la desduplicación de direcciones de correo electrónico con hash que coinciden con los ID de cliente.

Puede usar [!DNL People-Based Destinations] para segmentar y destinatario a clientes de alto valor que no visiten el sitio web o dejar de segmentar a aquellos que ya se han convertido sin conexión. Además, puede aprovechar [!DNL Profile Merge Rules] para combinar los datos de origen sin conexión con los datos de origen en línea, incluidos los datos de clientes de otras soluciones de Adobe Experience Cloud, para optimizar los esfuerzos de publicidad en medios sociales.

![pbd-overview](assets/pbd-overview.png)

## Availability {#availability}

[!DNL People-Based Destinations] es una integración de Audience Manager premium. Póngase en contacto con su representante de Adobe para aprovechar esta función Premium.

## Por qué debe usar destinos basados en personas {#why-use}

**Proporcione a sus clientes experiencias coherentes entre canales administrando toda la segmentación de audiencias desde Audience Manager.**

Si no se activan los segmentos de audiencia en canales basados en personas mediante Audience Manager, se producen experiencias desconectadas entre lo que ven los clientes al visitar el sitio web y lo que ven, por ejemplo, en sus [!DNL Facebook] fuentes. Tener un objetivo uniforme en todos los canales puede aumentar los ingresos de la publicidad y optimizar la inversión en publicidad.

**Alcanzar audiencias en canales basados en personas sin necesidad de una solución de integración de datos dedicada o flujos de trabajo personalizados para enviar audiencias.**

La forma más &quot;tradicional&quot; de dirigir audiencias en canales basados en personas implica tener que exportar los datos del cliente en un formato aceptado por la plataforma en la que desee publicitar y, a continuación, utilizar el método de incorporación de datos dedicado de la plataforma para llevar los datos del cliente a la cuenta del anunciante. Todo esto es trabajo manual que debe realizar para cada plataforma en la que desee publicitar. Además, diferentes plataformas pueden tener diferentes requisitos de formato de datos, lo que hace que el proceso sea aún más tedioso.

![pbd-overview](assets/pbd-diagram.png)

A través [!DNL People-Based Destinations]de Audience Manager, puede centralizar los datos de sus clientes, crear segmentos de audiencia y activarlos en varios canales basados en personas. Puede hacerlo todo desde la interfaz de usuario del Audience Manager, evitando así el trabajo adicional de cargar manualmente datos en cada plataforma, lo que le ahorra un tiempo valioso en el proceso.

**Cree y active segmentos de audiencia a partir de perfiles puramente sin conexión.**

[!DNL People-Based Destinations] solucione el problema que anteriormente solo podía activar segmentos de audiencia en función de la actividad del dispositivo. Con [!DNL People-Based Destinations], puede crear segmentos a partir de datos puramente sin conexión propios [!DNL CRM]y activarlos en plataformas basadas en personas. Además, puede correlacionar los datos sin conexión con los datos del dispositivo que ya tiene en Audience Manager.

**Aproveche la gobernanza de los datos y los controles de privacidad de los Audience Manager para administrar con seguridad los datos de los clientes.**

[!DNL People-Based Destinations] requiere que utilice únicamente identificadores con hash irreversibles. Esto reduce el riesgo asociado con la carga manual de datos de clientes en cada plataforma de destino.

Vea el siguiente vídeo para obtener una descripción general del flujo de datos al utilizarlo [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Casos de uso {#use-cases}

Para ayudarle a comprender mejor cómo y cuándo debe usar [!DNL People-Based Destinations], aquí hay dos casos de uso de muestra que los clientes Audience Manager pueden resolver con esta función.

### Use Case #1 {#use-case-1}

Un minorista en línea quiere llegar a los clientes existentes a través de las plataformas sociales y mostrarles ofertas personalizadas basadas en sus pedidos anteriores. Con [!DNL People-Based Destinations], el minorista en línea puede ingerir direcciones de correo electrónico con hash de su propio [!DNL CRM] a Audience Manager, generar segmentos a partir de sus propios datos sin conexión y enviar estos segmentos a las plataformas sociales en las que desee publicitar, optimizando así la inversión en publicidad.

### Use Case #2 {#use-case-2}

Una aerolínea tiene diferentes niveles de clientes (bronce, plata y oro), y quiere ofrecer a cada uno de los niveles ofertas personalizadas a través de las plataformas sociales. La compañía utiliza Audience Manager para analizar la actividad del cliente en el sitio web. Sin embargo, no todos los clientes utilizan la aplicación móvil de la aerolínea y algunos de ellos no han iniciado sesión en el sitio web de la compañía. Los únicos identificadores que tiene la compañía sobre estos clientes son los ID de pertenencia y las direcciones de correo electrónico.

Para destinatario en los medios sociales y canales similares basados en personas, pueden incorporar los datos de los clientes desde sus [!DNL CRM] Audience Manager, utilizando como identificadores las direcciones de correo electrónico con hash.

A continuación, pueden combinar sus datos sin conexión con sus características de actividad en línea existentes, para crear nuevos segmentos de audiencia a través de los cuales pueden realizar destinatarios [!DNL People-Based Destinations].
