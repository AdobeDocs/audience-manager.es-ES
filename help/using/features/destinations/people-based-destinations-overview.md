---
description: 'Utilice destinos basados en personas para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos se cierran en los ecosistemas pertenecientes a una entidad que controla el contenido que se muestra dentro de él. Incluyen plataformas sociales como Facebook y otras plataformas que dependen de cuentas de cliente para personalizar el contenido mostrado. '
seo-description: 'Utilice destinos basados en personas para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos se cierran en los ecosistemas pertenecientes a una entidad que controla el contenido que se muestra dentro de él. Incluyen plataformas sociales como Facebook y otras plataformas que dependen de cuentas de cliente para personalizar el contenido mostrado.  '
seo-title: Información general sobre los destinos basados en personas y casos de uso
solution: Audience Manager
title: Información general y casos de uso
translation-type: tm+mt
source-git-commit: 5624eac36a7f2b8892136688f89fc22af241fc3a

---


# Información general y casos de uso {#overview-use-cases}

Se utiliza [!DNL People-Based Destinations] para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos se cierran en los ecosistemas pertenecientes a una entidad que controla el contenido que se muestra dentro de él. Incluyen plataformas sociales como, y [!DNL Facebook]otras plataformas que dependen de cuentas de cliente para personalizar el contenido mostrado.

## Información general {#overview}

[!DNL People-Based Destinations] le permite aplicar segmentación en datos en línea y sin conexión para crear segmentos de audiencia basados en identificadores hash, como direcciones de correo electrónico o números de teléfono. A continuación, puede enviar estos segmentos a "jardines en pantalla" como, por [!DNL Facebook]ejemplo, dónde puede dirigirse a la audiencia independientemente de su estado de autenticación o interacciones en línea. [!DNL People-Based Destinations] puede ayudarle a:

* Segmentar audiencias sin conexión y audiencias en línea en plataformas como, por [!DNL Facebook]ejemplo, direcciones de correo electrónico hash;
* Permite controlar las capacidades de segmentación de dispositivo y de dispositivo existentes de Audience Manager;
* Elimine los costes asociados con soluciones de integración de datos de terceros;
* Elimine los costes asociados al desarrollo de flujos de trabajo de integración de datos personalizados;
* Segmentar audiencias en entornos sin cookies;
* Dirija las audiencias al desduplicar las direcciones de correo electrónico que coincidan con los ID de cliente.

Puede utilizar [!DNL People-Based Destinations] para segmentar y segmentar clientes de valor elevado que nunca hayan visitado el sitio web o dejar de segmentar aquellos que ya hayan convertido sin conexión. Además, puede aprovechar [!DNL Profile Merge Rules] para combinar datos de origen sin conexión con datos de origen en línea, incluidos los datos de clientes de otras soluciones de Adobe Experience Cloud, para optimizar los esfuerzos publicitarios de los medios sociales.

![pbd-overview](assets/pbd-overview.png)

## Availability {#availability}

[!DNL People-Based Destinations] es una integración Premium de Audience Manager. Comuníquese con el consultor de Audience Manager para obtener más detalles sobre los precios y la implementación.

## ¿Por qué debe utilizar destinos basados en personas? {#why-use}

**Proporcione a sus clientes una experiencia uniforme entre canales administrando su segmentación de audiencia completa desde Audience Manager.**

La no activación de los segmentos de audiencia en los canales basados en personas a través de Audience Manager produce experiencias disjoinadas entre lo que ven los clientes al visitar el sitio web y lo que ven, por ejemplo, en sus [!DNL Facebook] fuentes. El tener una segmentación coherente en los canales puede aumentar los ingresos publicitarios al optimizar la inversión en publicidad.

**Llegue a audiencias en canales basados en personas sin necesidad de una solución de integración de datos dedicada o flujos de trabajo personalizados para enviar audiencias.**

La forma más "tradicional" de segmentar audiencias entre canales basados en personas implica que usted debe exportar los datos de sus clientes en un formato aceptado por la plataforma que desee publicitar y luego utilizar el método de integración de datos dedicado a la plataforma para traer los datos del cliente a la cuenta del anunciante. Es todo el trabajo manual que debe hacer por cada plataforma que desee anunciar. Además, las distintas plataformas pueden tener diferentes requisitos de formato de datos, lo que hace que el proceso sea aún más tedioso.

![pbd-overview](assets/pbd-diagram.png)

A través [!DNL People-Based Destinations]de, Audience Manager le ayuda a centralizar todos los datos de sus clientes, a crear segmentos de audiencia y a activarlos en varios canales basados en personas. Puede hacerlo todo desde la interfaz de usuario de Audience Manager, evitando el trabajo adicional de cargar manualmente los datos en cada plataforma, lo que ahorra tiempo valioso en el proceso.

**Cree y active segmentos de audiencia desde perfiles puramente sin conexión.**

[!DNL People-Based Destinations] resolver el problema que anteriormente, solo podía activar segmentos de audiencia en función de la actividad del dispositivo. Con [!DNL People-Based Destinations], puede crear segmentos a partir de datos simples sin conexión y [!DNL CRM]activarlos en plataformas basadas en personas. Además, puede correlacionar datos sin conexión con datos de dispositivos que ya tiene en Audience Manager.

**Aproveche los controles de privacidad y administración de datos de Audience Manager para administrar datos de clientes de forma segura.**

[!DNL People-Based Destinations] utilice únicamente identificadores hash, de modo que los datos del cliente siempre están protegidos, desde el momento en que se realice en Audience Manager, hasta el momento en el que llega al destino de destino. Esto elimina los riesgos de privacidad asociados a la carga manual de datos de clientes confidenciales en cada plataforma de activación.

## Casos de uso {#use-cases}

Para ayudarle a comprender mejor cómo y cuándo debe utilizarse [!DNL People-Based Destinations], aquí se muestran dos casos de uso de muestra que los clientes de Audience Manager pueden resolver mediante esta función.

### Use Case #1 {#use-case-1}

Un minorista en línea desea llegar a los clientes existentes a través de plataformas sociales y mostrarles ofertas personalizadas según sus pedidos anteriores. Con [!DNL People-Based Destinations], pueden ingestar direcciones de correo electrónico hash de su propio [!DNL CRM] a Audience Manager, crear segmentos desde los datos sin conexión y enviar estos segmentos a las plataformas sociales en las que desean anunciarse, optimizando su inversión en publicidad.

### Use Case #2 {#use-case-2}

Una aerolínea tiene diferentes niveles de cliente (Bronce, Plata y Oro) y quiere proporcionar cada uno de los niveles con ofertas personalizadas a través de plataformas sociales. La empresa utiliza Audience Manager para analizar la actividad del cliente en el sitio Web. Sin embargo, no todos los clientes utilizan la aplicación móvil de la aerolínea y algunos nunca han iniciado sesión en el sitio web de la compañía. Los únicos identificadores que la empresa tiene sobre estos clientes son ID de abono y direcciones de correo electrónico.

Para segmentar a través de medios sociales y canales similares basados en personas, pueden confiar en los datos del cliente desde Audience [!DNL CRM] Manager, utilizando las direcciones de correo electrónico hash como identificadores.

A continuación, pueden combinar los datos sin conexión con características de actividades en línea existentes, para crear nuevos segmentos de audiencia a los [!DNL People-Based Destinations]que pueden dirigirse.
