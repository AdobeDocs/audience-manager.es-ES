---
description: Utilice destinos basados en personas para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se muestra dentro de ella. Incluyen plataformas sociales como Facebook y otras plataformas que dependen de las cuentas de los clientes para personalizar el contenido mostrado.
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

Uso [!DNL People-Based Destinations] para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se muestra dentro de ella. Incluyen plataformas sociales como [!DNL Facebook]y otras plataformas que dependen de cuentas de cliente para personalizar el contenido mostrado.

>[!IMPORTANT]
>Este artículo contiene documentación del producto que le guiará a través de la configuración y el uso de esta función. Nada de lo que contiene aquí es asesoramiento legal. Por favor, consulte a su propio asesor legal para obtener orientación legal.

## Información general {#overview}

[!DNL People-Based Destinations] permite aplicar la segmentación en datos en línea y sin conexión para crear segmentos de audiencia basados en [identificadores hash](people-based-destinations-prerequisites.md#hashing-requirements), como direcciones de correo electrónico. A continuación, puede enviar estos segmentos a &quot;jardines amurallados&quot;, como [!DNL Facebook], donde puede segmentar su audiencia en las plataformas sociales. [!DNL People-Based Destinations] puede ayudarle a:

* Segmente audiencias sin conexión y en línea en plataformas como [!DNL Facebook], en función de las direcciones de correo electrónico con hash;
* Complementar las capacidades existentes de segmentación de dispositivos y cookies de Audience Manager.
* Eliminar los costes asociados con las soluciones de incorporación de datos de terceros.
* Eliminar los costes asociados con el desarrollo de flujos de trabajo de incorporación de datos personalizados.
* Audiencias de Target en entornos sin cookies;
* Segmente las audiencias deduplicando las direcciones de correo electrónico con hash coincidentes con los ID de cliente.

Puede utilizar [!DNL People-Based Destinations] segmentar y segmentar a clientes de alto valor que no hayan visitado su sitio web o dejar de segmentar a aquellos que ya se han convertido sin conexión. Además, puede aprovechar [!DNL Profile Merge Rules] para combinar los datos de origen sin conexión con los datos de origen en línea, incluidos los datos de clientes de otras soluciones de Adobe Experience Cloud, para optimizar los esfuerzos publicitarios de medios sociales.

![pbd-overview](assets/pbd-overview.png)

## Disponibilidad {#availability}

[!DNL People-Based Destinations] es una integración de Audience Manager premium. Póngase en contacto con el representante del Adobe para aprovechar esta función Premium.

## Por qué debe utilizar [!UICONTROL People-Based Destinations] {#why-use}

**Ofrezca a sus clientes experiencias multicanal coherentes mediante la administración de toda la segmentación de audiencia desde Audience Manager.**

Si no activa los segmentos de audiencia en canales basados en personas a través de Audience Manager, se generan experiencias inconexas entre lo que ven los clientes al visitar el sitio web y lo que ven, por ejemplo, en su [!DNL Facebook] fuentes. Tener una segmentación coherente en todos los canales puede aumentar los ingresos por publicidad y optimizar al mismo tiempo el gasto en publicidad.

**Llegue a las audiencias en canales basados en personas sin necesidad de una solución de incorporación de datos dedicada o flujos de trabajo personalizados para enviar audiencias.**

La forma más &quot;tradicional&quot; de segmentar audiencias en canales basados en personas implica exportar los datos de los clientes en un formato aceptado por la plataforma en la que desea anunciarse y, a continuación, utilizar el método de incorporación de datos dedicado de la plataforma para llevar los datos de los clientes a la cuenta del anunciante. Todo esto es trabajo manual que debe hacer para cada plataforma en la que desee anunciarse. Además, las distintas plataformas pueden tener diferentes requisitos de formato de datos, lo que hace que el proceso sea aún más tedioso.

![pbd-overview](assets/pbd-diagram.png)

Pasante [!DNL People-Based Destinations], Audience Manager le ayuda a centralizar los datos de sus clientes, crear segmentos de audiencia y activarlos en varios canales basados en personas. Puede hacerlo desde la interfaz de usuario del Audience Manager, lo que evita el trabajo adicional de cargar datos manualmente en cada plataforma, lo que le ahorra un tiempo valioso en el proceso.

**Cree y active segmentos de audiencia a partir de perfiles puramente sin conexión.**

[!DNL People-Based Destinations] solucione el problema que anteriormente solo podía activar segmentos de audiencia basados en la actividad del dispositivo. Con [!DNL People-Based Destinations], puede crear segmentos a partir de datos puramente sin conexión de los suyos propios [!DNL CRM]y activarlos en plataformas basadas en personas. Además, puede correlacionar los datos sin conexión con datos de dispositivos que ya tiene en Audience Manager.

**Aproveche los controles de privacidad y control de datos de Audience Manager para gestionar de forma segura los datos de los clientes.**

[!DNL People-Based Destinations] requiere que solo utilice identificadores con hash irreversible. Esto reduce el riesgo asociado con la carga manual de datos de clientes en cada plataforma de destino.

Vea el siguiente vídeo para obtener información general sobre el flujo de datos al utilizar [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Casos de uso {#use-cases}

Para ayudarle a comprender mejor cómo y cuándo debe utilizar [!DNL People-Based Destinations]Sin embargo, estos son dos casos de uso de ejemplo que los clientes de Audience Manager pueden solucionar mediante esta función.

### #1 de casos de uso {#use-case-1}

Un minorista en línea quiere llegar a los clientes existentes a través de plataformas sociales y mostrarles ofertas personalizadas basadas en sus pedidos anteriores. Con [!DNL People-Based Destinations], el minorista en línea puede ingerir direcciones de correo electrónico con hash desde su propia cuenta [!DNL CRM] para Audience Manager, genere segmentos a partir de sus propios datos sin conexión y envíelos a las plataformas sociales en las que desee anunciarse, optimizando así el gasto en publicidad.

### #2 de casos de uso {#use-case-2}

Una aerolínea tiene diferentes niveles de clientes (Bronce, Plata y Oro) y desea proporcionar a cada uno de los niveles ofertas personalizadas a través de plataformas sociales. La empresa utiliza Audience Manager para analizar la actividad de los clientes en el sitio web. Sin embargo, no todos los clientes utilizan la aplicación móvil de la aerolínea y algunos de ellos no han iniciado sesión en el sitio web de la compañía. Los únicos identificadores que la compañía tiene sobre estos clientes son ID de miembros y direcciones de correo electrónico.

Para segmentarlos en medios sociales y canales similares basados en personas, pueden incorporar los datos de clientes de su [!DNL CRM] en el Audience Manager, utilizando las direcciones de correo electrónico con hash como identificadores.

A continuación, puede combinar sus datos sin conexión con sus rasgos de actividad en línea existentes para crear nuevos segmentos de audiencia a través de los cuales dirigirse [!DNL People-Based Destinations].
