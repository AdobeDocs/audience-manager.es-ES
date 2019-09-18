---
description: 'Use destinos basados en personas para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se muestra dentro de ellos. Incluyen plataformas sociales como Facebook y otras que dependen de cuentas de clientes para personalizar el contenido mostrado. '
seo-description: 'Use destinos basados en personas para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se muestra dentro de ellos. Incluyen plataformas sociales como Facebook y otras que dependen de cuentas de clientes para personalizar el contenido mostrado.  '
seo-title: Información general de destinos basados en personas y casos de uso
solution: Audience Manager
title: Información general y casos de uso
translation-type: tm+mt
source-git-commit: 62c27a3990c2c39d069c7a6e4ef32e8e8b3f1998

---


# Información general y casos de uso {#overview-use-cases}

Se utiliza [!DNL People-Based Destinations] para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se muestra dentro de ellos. Incluyen plataformas sociales como [!DNL Facebook]y otras que dependen de cuentas de clientes para personalizar el contenido mostrado.

## Información general {#overview}

[!DNL People-Based Destinations] le permite aplicar segmentación en datos en línea y sin conexión para crear segmentos de audiencia basados en identificadores con hash, como direcciones de correo electrónico o números de teléfono. A continuación, puede enviar estos segmentos a "jardines amurallados" como, por ejemplo, [!DNL Facebook]donde puede dirigirse a su audiencia independientemente de sus interacciones en línea o del estado de autenticación. [!DNL People-Based Destinations] puede ayudarle a:

* Dirigirse a audiencias en línea y sin conexión en plataformas como [!DNL Facebook], por ejemplo, basadas en direcciones de correo electrónico con hash;
* Complementar las capacidades de segmentación de cookies y dispositivos existentes de Audience Manager;
* Eliminar los costos asociados con las soluciones de incorporación de datos de terceros;
* Eliminar los costos asociados con el desarrollo de flujos de trabajo personalizados de incorporación de datos;
* Dirigirse a audiencias en entornos sin cookies;
* Dirija la audiencia deduplicando las direcciones de correo electrónico coincidentes con los ID de cliente.

Puede usar [!DNL People-Based Destinations] para segmentar y segmentar clientes de alto valor que nunca hayan visitado el sitio web, o para dejar de dirigirse a aquellos que ya se han convertido sin conexión. Además, puede aprovechar [!DNL Profile Merge Rules] para combinar datos de origen sin conexión con datos de origen en línea, incluidos datos de clientes de otras soluciones de Adobe Experience Cloud, para optimizar sus esfuerzos de publicidad en medios sociales.

![pbd-overview](assets/pbd-overview.png)

## Availability {#availability}

[!DNL People-Based Destinations] es una integración Premium de Audience Manager. Póngase en contacto con su representante de Adobe para aprovechar esta función Premium.

## Por qué debe usar destinos basados en personas {#why-use}

**Proporcione a sus clientes experiencias coherentes entre canales administrando toda la segmentación de audiencias desde Audience Manager.**

Si no activa los segmentos de audiencia en canales basados en personas a través de Audience Manager, se producen experiencias desconectadas entre lo que ven los clientes al visitar el sitio web y lo que ven, por ejemplo, en sus [!DNL Facebook] fuentes. Tener un objetivo uniforme en todos los canales puede aumentar los ingresos de la publicidad y, al mismo tiempo, optimizar la inversión en publicidad.

**Llegar a audiencias en canales basados en personas sin necesidad de una solución de integración de datos dedicada o flujos de trabajo personalizados para enviar audiencias.**

La forma más "tradicional" de segmentar audiencias en los canales basados en personas implica tener que exportar los datos de cliente en un formato aceptado por la plataforma en la que desee publicitar y, a continuación, utilizar el método de incorporación de datos dedicado de la plataforma para llevar los datos de cliente a la cuenta del anunciante. Todo esto es trabajo manual que debe realizar para cada plataforma en la que desee publicitar. Además, diferentes plataformas pueden tener diferentes requisitos de formato de datos, lo que hace que el proceso sea aún más tedioso.

![pbd-overview](assets/pbd-diagram.png)

A través de [!DNL People-Based Destinations]Audience Manager le ayuda a centralizar todos los datos de clientes, a crear segmentos de audiencia y a activarlos en varios canales basados en personas. Puede hacerlo todo desde la interfaz de usuario de Audience Manager, evitando así el trabajo adicional de cargar manualmente datos en cada plataforma, lo que le ahorra un tiempo valioso en el proceso.

**Cree y active segmentos de audiencia a partir de perfiles puramente sin conexión.**

[!DNL People-Based Destinations] solucione el problema que anteriormente solo podía activar segmentos de audiencia en función de la actividad del dispositivo. Con [!DNL People-Based Destinations], puede crear segmentos a partir de datos puramente sin conexión propios [!DNL CRM]y activarlos en plataformas basadas en personas. Además, puede correlacionar datos sin conexión con datos de dispositivos que ya tenga en Audience Manager.

**Aproveche los controles de privacidad y administración de datos de Audience Manager para administrar con seguridad los datos de los clientes.**

[!DNL People-Based Destinations] solo utilice identificadores con hash, de modo que los datos de cliente siempre estarán protegidos, desde el momento en que los incorpore a Audience Manager, hasta el momento en que alcancen su destino de destino. Esto elimina los riesgos de privacidad asociados con la carga manual de datos confidenciales de clientes en cada plataforma de activación.

## Casos de uso {#use-cases}

Para ayudarle a comprender mejor cómo y cuándo debe usar [!DNL People-Based Destinations], aquí hay dos casos de uso de muestra que los clientes de Audience Manager pueden resolver con esta función.

### Use Case #1 {#use-case-1}

Un minorista en línea quiere llegar a los clientes existentes a través de plataformas sociales y mostrarles ofertas personalizadas basadas en sus pedidos anteriores. Con [!DNL People-Based Destinations], pueden ingerir direcciones de correo electrónico con hash propias [!DNL CRM] a Audience Manager, generar segmentos a partir de los datos sin conexión y enviar estos segmentos a las plataformas sociales en las que deseen publicitar, optimizando así el gasto en publicidad.

### Use Case #2 {#use-case-2}

Una aerolínea tiene diferentes niveles de clientes (bronce, plata y oro), y desea ofrecer a cada uno de los niveles ofertas personalizadas a través de plataformas sociales. La empresa utiliza Audience Manager para analizar la actividad de los clientes en el sitio web. Sin embargo, no todos los clientes utilizan la aplicación móvil de la aerolínea y algunos de ellos ni siquiera iniciaron sesión en el sitio web de la empresa. Los únicos identificadores que tiene la empresa sobre estos clientes son los ID de pertenencia y las direcciones de correo electrónico.

Para dirigirlos a través de los medios sociales y canales similares basados en personas, pueden incorporar los datos de clientes del [!DNL CRM] en Audience Manager, utilizando como identificadores las direcciones de correo electrónico con hash.

A continuación, pueden combinar los datos sin conexión con las características de actividad en línea existentes para crear nuevos segmentos de audiencia a través de los cuales pueden dirigirse [!DNL People-Based Destinations].
