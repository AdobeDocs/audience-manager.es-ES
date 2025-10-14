---
description: People-Based Destinations ofrece varias estrategias de implementación, en función de cómo estén estructurados los datos de los clientes. Este artículo proporciona información general sobre los pasos de implementación que debe seguir para los destinos basados en personas, según su escenario.
seo-description: People-Based Destinations offers multiple implementation strategies, depending on how your customer data is structured. This article provides an overview of the implementation steps that you need to follow for People-Based Destinations, depending on your scenario.
seo-title: People-Based Destinations Implementation Guidance
solution: Audience Manager
title: Directrices para la implementación
feature: People-based Destinations
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1350'
ht-degree: 2%

---

# Directrices para la implementación {#implementation-guidance}

>[!IMPORTANT]
>Este artículo contiene documentación del producto que le guiará a través de la configuración y el uso de esta función. Nada de lo que contiene aquí es asesoramiento legal. Por favor, consulte a su propio asesor legal para obtener orientación legal.

[!DNL People-Based Destinations] ofrece varias estrategias de implementación, según la estructura de los datos de los clientes. Este artículo proporciona información general sobre los pasos de implementación que debe seguir para [!DNL People-Based Destinations], según el escenario en que se encuentre.

## Información general {#overview}

La configuración de [!DNL People-Based Destinations] le guía a través de varias secciones de Audience Manager y requiere diferentes configuraciones y métodos de incorporación de datos, según el tipo de datos de clientes que ya tenga en Audience Manager y el tipo de segmentación de audiencia que desee realizar.

>[!IMPORTANT]
> Antes de configurar [!DNL People-Based Destinations], asegúrese de leer este artículo detenidamente y por completo. Después de leer esta guía, debería tener una idea clara del escenario que habilitará a través de [!DNL People-Based Destinations].

Hay seis aspectos de la implementación que debe aclarar antes de usar [!DNL People-Based Destinations]. Este artículo le ayudará a comprender cuál es la configuración actual para que pueda seguir correctamente los pasos de implementación de su escenario.

![pbd-implementation](assets/pbd-implementation.png)

## &#x200B;1. Definición del caso de uso {#defining-your-use-case}

Antes de comenzar a implementar [!DNL People-Based Destinations], debe definir claramente el caso de uso para el que utilizará esta característica. Puede usar [!DNL People-Based Destinations] para segmentar audiencias de dos maneras, según la actividad de la audiencia:

**A) Segmentación de audiencia basada en su actividad combinada de usuario en línea y sin conexión**. En este escenario, desea combinar los datos de audiencia existentes de Audience Manager con los datos de su sistema interno [!DNL CRM] y enviar los segmentos de audiencia resultantes a [!DNL People-Based Destinations]. Este es un ejemplo que ilustra este escenario:

Su compañía, una aerolínea, tiene diferentes niveles de clientes (Bronce, Plata y Oro) y desea proporcionar a cada uno de los niveles ofertas personalizadas a través de plataformas sociales. Audience Manager se utiliza para analizar la actividad de los clientes en el sitio web. Sin embargo, no todos los clientes utilizan la aplicación móvil de la aerolínea y algunos de ellos no han iniciado sesión en el sitio web de la compañía. Los datos de sus clientes se limitan principalmente a ID de miembros y direcciones de correo electrónico.

Para dirigirlas a través de los medios sociales y canales similares basados en personas, puedes incluir tus [direcciones de correo electrónico con hash](people-based-destinations-prerequisites.md) en Audience Manager y combinarlas con tus rasgos de actividad en línea existentes para generar nuevos segmentos de audiencia. A continuación, puede usar esos segmentos para segmentar la audiencia mediante [!DNL People-Based Destinations].

**B) Segmentación de audiencia basada exclusivamente en su actividad de usuario sin conexión**. En esta situación, el sistema [!DNL CRM] contiene las direcciones de correo electrónico de los clientes y otros atributos del cliente, pero los clientes no han interactuado con el sitio web, por lo que no hay ninguna actividad del cliente en Audience Manager. Este es un ejemplo que ilustra este escenario:

Su compañía, un proveedor de servicios de telecomunicaciones, guarda los datos de los clientes, como las direcciones de correo electrónico y los planes de telecomunicaciones comprados, en un [!DNL CRM] interno. Desea segmentar clientes existentes en plataformas sociales para ofrecerles paquetes de actualización basados en sus suscripciones existentes. Para ello, puede introducir sus direcciones de correo electrónico de clientes con hash en Audience Manager y crear segmentos basados en las suscripciones de clientes existentes. A continuación, puede enviar estos segmentos a [!DNL People-Based Destinations] para que se dirijan a sus clientes con ofertas personalizadas.

## &#x200B;2. Defina el tipo de direcciones de correo electrónico objetivo {#define-target-email}

El segundo paso para definir la estrategia de implementación es decidir a qué tipo de direcciones de correo electrónico del cliente desea dirigirse.

**A) Segmentación de audiencia basada en sus direcciones de correo electrónico autenticadas**. En esta situación, los usuarios tienen varias cuentas asociadas con varias direcciones de correo electrónico y desea dirigirlas con ofertas personalizadas, basadas únicamente en la dirección de correo electrónico que autentican en el sitio web y en tiempo real.

**B) Segmentación de audiencia basada en todas las direcciones de correo electrónico asociadas**. En esta situación, los usuarios tienen varias cuentas asociadas con varias direcciones de correo electrónico y desea dirigirlas a todas sus direcciones de correo electrónico asociadas, independientemente de la actividad autenticada.

## &#x200B;3. Identifique el tipo de ID de cliente (ID de CRM) que tiene {#identify-customer-id}

La segmentación de audiencias en [!DNL People-Based Destinations] requiere que envíe [versiones con hash SHA256](people-based-destinations-prerequisites.md) de las direcciones de correo electrónico de sus clientes. Según la configuración de Audience Manager existente, puede encontrarse en una de las dos situaciones siguientes:

**A) Sus ID de cliente de Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ya están en minúsculas y tienen direcciones de correo electrónico con hash**. En este escenario, puede usar estos identificadores existentes para segmentar audiencias en [!DNL People-Based Destinations].

**B) Los identificadores de cliente de Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) no son direcciones de correo electrónico con hash y minúsculas**. En esta situación, los identificadores de cliente existentes no se pueden enviar a [!DNL People-Based Destinations]. Para usar [!DNL People-Based Destinations], debe realizar una sincronización de ID entre los ID de cliente existentes y las versiones en minúsculas y con hash de las direcciones de correo electrónico de los clientes. Esto se hace mediante [sincronización de ID basada en archivos](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) o mediante [ID declarados](../declared-ids.md).

## &#x200B;4. Calificación de rasgos {#trait-qualification}

Para dirigirse a la audiencia con precisión en [!DNL People-Based Destinations], los usuarios deben cumplir los requisitos para rasgos basados en reglas o incorporados, según el tipo de segmentación de audiencia que desee realizar.

**A) Califique sus ID de cliente e ID de dispositivo en tiempo real para los rasgos basados en reglas**. Esta opción se aplica al caso de uso A de [1. Definición del caso de uso &#x200B;](people-based-destinations-workflow.md#defining-your-use-case). Si su plan es segmentar audiencias en función de la actividad en línea y sin conexión, es probable que ya esté calificando a su audiencia para [rasgos basados en reglas](../traits/trait-and-segment-qualification-reference.md).

**B) Incorpore rasgos en sus ID de cliente mediante archivos de datos de entrada**. Esta opción se aplica al caso de uso B de [1. Definición del caso de uso &#x200B;](people-based-destinations-workflow.md#defining-your-use-case). Al segmentar la audiencia según una actividad puramente sin conexión, debe calificar los ID de cliente para rasgos incorporados mediante [archivos de datos de entrada](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## &#x200B;5. Crear o etiquetar fuentes de datos y direcciones de correo electrónico con hash integradas {#create-label-data-sources}

Según el tipo de ID de cliente que tenga en Audience Manager (consulte [3). Identifique el tipo de ID de cliente (CRM ID) que tiene &#x200B;](people-based-destinations-workflow.md#identify-customer-id), en uno de los siguientes casos:

**A) Etiquete un origen de datos existente**. Esta opción se aplica al escenario en el que los ID de cliente de Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ya sean direcciones de correo electrónico con hash y en minúsculas. En este caso, lo que debe hacer es etiquetar el origen de datos en el que almacena los ID como origen de datos de [!DNL PII]. Consulte [Configuración de Data Source](../datasources-list-and-settings.md) para obtener más información sobre la configuración del origen de datos. Lo que debe hacer es asegurarse de que la opción No se puede asociar a información de identificación personal esté desmarcada.

**B) Crear un nuevo origen de datos**. Esta opción se aplica al escenario en el que los ID de cliente de Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) no sean direcciones de correo electrónico con hash. En este caso, debe crear una nueva fuente de datos entre dispositivos e incluir sus direcciones de correo electrónico con hash en ella. Puede hacerlo de dos maneras:

* Utilice la sincronización de ID basada en archivos. Consulte [Requisitos de nombre y contenido para archivos de sincronización de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) para obtener más información sobre la apariencia que deben tener los archivos de sincronización de ID. Al utilizar este método, puede dirigir todas las direcciones de correo electrónico con hash desde la base de datos de [!DNL CRM].
* Use [ID declarados](../declared-ids.md) para declarar sus direcciones de correo electrónico con hash al pasar los ID de cliente autenticados. Al utilizar este método, Audience Manager, en su nombre, solo identifica sus direcciones de correo electrónico con hash de los usuarios que se han autenticado en línea. Las direcciones de correo electrónico segmentadas en canales basados en personas solo son las que aparecen en las llamadas de evento de ID declaradas. Otras direcciones de correo electrónico asociadas con el ID de cliente no se activan en tiempo real.

## &#x200B;6. Uso de una regla de combinación de perfiles para la segmentación {#use-profile-merge-rules}

Según su caso de uso (consulte [1. Definición de su caso de uso (](people-based-destinations-workflow.md#defining-your-use-case)), hay dos maneras de usar [!DNL Profile Merge Rules] para la segmentación.

**A) Use[!DNL Profile Merge Rules]** Existente. Esta opción se aplica al primer caso de uso (segmentación de audiencia basada en la actividad combinada de usuarios en línea y sin conexión). En esta situación, tiene una actividad de cliente existente en Audience Manager y ya ha definido al menos una regla de combinación de perfiles que haya utilizado en la segmentación. En este caso, no es necesario crear ningún(a) [!DNL Profile Merge Rules] nuevo(a).

**B) Cree una nueva regla de combinación [!DNL All Cross-Device Profiles]**. Esta opción se aplica al segundo caso de uso (segmentación de audiencia basada exclusivamente en la actividad de usuarios sin conexión). En esta situación, está trayendo los datos de clientes sin conexión de su [!DNL CRM] a Audience Manager y desea crear segmentos a partir de esos datos. Para ello, [!DNL People-Based Destinations] introduce una nueva y cuarta regla de combinación de perfiles, llamada **[!DNL All Cross-Device Profiles]**. Esta es la regla que debe utilizar al segmentar datos puramente sin conexión.
