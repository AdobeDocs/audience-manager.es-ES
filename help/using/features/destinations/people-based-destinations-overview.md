---
description: 'Use destinos basados en personas para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se muestra dentro de ella. Incluyen plataformas sociales como Facebook y otras plataformas que dependen de cuentas de clientes para personalizar el contenido mostrado. '
seo-description: 'Use destinos basados en personas para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se muestra dentro de ella. Incluyen plataformas sociales como Facebook y otras plataformas que dependen de cuentas de clientes para personalizar el contenido mostrado.  '
seo-title: Información general de destinos basados en personas y casos de uso
solution: Audience Manager
title: Información general y casos de uso
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 1%

---


# Información general y casos de uso {#overview-use-cases}

Utilice [!DNL People-Based Destinations] para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se muestra dentro de ella. Incluyen plataformas sociales como [!DNL Facebook] y otras plataformas que dependen de cuentas de clientes para personalizar el contenido mostrado.

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

## Información general {#overview}

[!DNL People-Based Destinations] le permite aplicar segmentación en datos en línea y sin conexión para crear segmentos de audiencia basados en identificadores [ ](people-based-destinations-prerequisites.md#hashing-requirements)hash, como direcciones de correo electrónico o números de teléfono. A continuación, puede enviar estos segmentos a &quot;jardines amurallados&quot; como [!DNL Facebook], donde puede destinatario de su audiencia en las plataformas sociales. [!DNL People-Based Destinations] puede ayudarle a:

* Destinatario audiencias en línea y sin conexión en plataformas como [!DNL Facebook], basadas en direcciones de correo electrónico con hash;
* Complementar las capacidades de segmentación de cookies y dispositivos existentes del Audience Manager;
* Eliminar los costos asociados con las soluciones de incorporación de datos de terceros;
* Eliminar los costos asociados con el desarrollo de flujos de trabajo personalizados de incorporación de datos;
* Audiencias de destinatario en entornos sin cookies;
* Destinatario de audiencias mediante la desduplicación de direcciones de correo electrónico con hash que coinciden con los ID de cliente.

Puede utilizar [!DNL People-Based Destinations] para segmentar y destinatario a los clientes de alto valor que no visiten el sitio web o dejar de segmentar a aquellos que ya se han convertido sin conexión. Además, puede aprovechar [!DNL Profile Merge Rules] para combinar los datos de origen sin conexión con los datos de origen en línea, incluidos los datos de clientes de otras soluciones de Adobe Experience Cloud, para optimizar los esfuerzos de publicidad en medios sociales.

![pbd-overview](assets/pbd-overview.png)

## Disponibilidad {#availability}

[!DNL People-Based Destinations] es una integración de Audience Manager premium. Póngase en contacto con su representante de Adobe para aprovechar esta función de primera calidad.

## Por Qué Debe Utilizar [!UICONTROL People-Based Destinations] {#why-use}

**Proporcione a sus clientes experiencias coherentes entre canales administrando toda la segmentación de audiencias desde Audience Manager.**

Si no se activan los segmentos de audiencia en canales basados en personas mediante Audience Manager, se producen experiencias desvinculadas entre lo que ven los clientes al visitar el sitio web y lo que ven, por ejemplo, en sus [!DNL Facebook] fuentes. Tener un objetivo uniforme en todos los canales puede aumentar los ingresos de la publicidad y optimizar la inversión en publicidad.

**Alcanzar audiencias en canales basados en personas sin necesidad de una solución de integración de datos dedicada o flujos de trabajo personalizados para enviar audiencias.**

La forma más &quot;tradicional&quot; de dirigir audiencias en canales basados en personas implica tener que exportar los datos del cliente en un formato aceptado por la plataforma en la que desee publicitar y, a continuación, utilizar el método de incorporación de datos dedicado de la plataforma para llevar los datos del cliente a la cuenta del anunciante. Todo esto es trabajo manual que debe realizar para cada plataforma en la que desee publicitar. Además, diferentes plataformas pueden tener diferentes requisitos de formato de datos, lo que hace que el proceso sea aún más tedioso.

![pbd-overview](assets/pbd-diagram.png)

A través de [!DNL People-Based Destinations], Audience Manager le ayuda a centralizar los datos de sus clientes, a crear segmentos de audiencia y a activarlos en varios canales basados en personas. Puede hacerlo todo desde la interfaz de usuario del Audience Manager, evitando así el trabajo adicional de cargar manualmente datos en cada plataforma, lo que le ahorra un tiempo valioso en el proceso.

**Cree y active segmentos de audiencia a partir de perfiles puramente sin conexión.**

[!DNL People-Based Destinations] solucione el problema que anteriormente solo podía activar segmentos de audiencia en función de la actividad del dispositivo. Con [!DNL People-Based Destinations], puede crear segmentos a partir de datos puramente sin conexión de su propio [!DNL CRM] y activarlos en plataformas basadas en personas. Además, puede correlacionar los datos sin conexión con los datos del dispositivo que ya tiene en Audience Manager.

**Aproveche la gobernanza de los datos y los controles de privacidad de los Audience Manager para administrar con seguridad los datos de los clientes.**

[!DNL People-Based Destinations] requiere que utilice únicamente identificadores con hash irreversibles. Esto reduce el riesgo asociado con la carga manual de datos de clientes en cada plataforma de destino.

Vea el siguiente vídeo para obtener una visión general del flujo de datos al utilizar [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Casos de uso {#use-cases}

Para ayudarle a comprender mejor cómo y cuándo debe utilizar [!DNL People-Based Destinations], aquí hay dos casos de uso de muestra que los clientes Audience Manager pueden resolver mediante esta función.

### Caso de uso n.º 1 {#use-case-1}

Un minorista en línea quiere llegar a los clientes existentes a través de las plataformas sociales y mostrarles ofertas personalizadas basadas en sus pedidos anteriores. Con [!DNL People-Based Destinations], el minorista en línea puede ingerir direcciones de correo electrónico con hash desde su propio [!DNL CRM] Audience Manager, generar segmentos a partir de sus propios datos sin conexión y enviar estos segmentos a las plataformas sociales en las que desee publicitar, optimizando así la inversión en publicidad.

### Caso de uso #2 {#use-case-2}

Una aerolínea tiene diferentes niveles de clientes (bronce, plata y oro), y quiere ofrecer a cada uno de los niveles ofertas personalizadas a través de las plataformas sociales. La compañía utiliza Audience Manager para analizar la actividad del cliente en el sitio web. Sin embargo, no todos los clientes utilizan la aplicación móvil de la aerolínea y algunos de ellos no han iniciado sesión en el sitio web de la compañía. Los únicos identificadores que tiene la compañía sobre estos clientes son los ID de pertenencia y las direcciones de correo electrónico.

Para destinatario en los medios sociales y canales similares basados en personas, pueden incorporar los datos de clientes de su [!DNL CRM] Audience Manager, usando las direcciones de correo electrónico con hash como identificadores.

A continuación, pueden combinar sus datos sin conexión con sus características de actividad en línea existentes, para crear nuevos segmentos de audiencia a los que pueden realizar destinatarios mediante [!DNL People-Based Destinations].
