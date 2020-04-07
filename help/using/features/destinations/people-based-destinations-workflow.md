---
description: Los destinos basados en personas oferta varias estrategias de implementación, según la estructura de los datos del cliente. En este artículo se proporciona una descripción general de los pasos de implementación que debe seguir para los destinos basados en personas, según el escenario.
seo-description: 'Los destinos basados en personas oferta varias estrategias de implementación, según la estructura de los datos del cliente. En este artículo se proporciona una descripción general de los pasos de implementación que debe seguir para los destinos basados en personas, según el escenario.  '
seo-title: Guía de implementación de destinos basados en personas
solution: Audience Manager
title: Directrices de implementación
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# Directrices de implementación {#implementation-guidance}

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

[!DNL People-Based Destinations] oferta varias estrategias de implementación, según la estructura de los datos del cliente. En este artículo se proporciona una descripción general de los pasos de implementación que debe seguir [!DNL People-Based Destinations]según el escenario.

## Información general {#overview}

La configuración de [!DNL People-Based Destinations] le lleva a través de varias secciones del Administrador de Audiencias y requiere diferentes configuraciones y métodos de incorporación de datos, según el tipo de datos de cliente que ya tenga en el Administrador de Audiencias y el tipo de objetivos de audiencia que desee realizar.

>[!IMPORTANT]
> Antes de configurar [!DNL People-Based Destinations], asegúrese de leer este artículo de forma cuidadosa y completa. Después de leer esta guía, debe tener una clara comprensión del escenario que habilitará mediante [!DNL People-Based Destinations].

Hay seis aspectos de implementación que debe aclarar antes de usar [!DNL People-Based Destinations]. Este artículo le ayudará a comprender cuál es su configuración actual, de modo que pueda seguir correctamente los pasos de implementación de su escenario.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Definición de Casos de Uso {#defining-your-use-case}

Antes de comenzar a implementar [!DNL People-Based Destinations], debe definir claramente el caso de uso para el que va a utilizar esta función. Puede usar [!DNL People-Based Destinations] para destinatario de audiencias de dos maneras, según la actividad de audiencias:

**R) Objetivo de Audiencia basado en la actividad** combinada de usuarios en línea y sin conexión. En este escenario, desea combinar los datos de audiencia existentes del Administrador de Audiencias con los datos del [!DNL CRM] sistema interno y enviar los segmentos de audiencia resultantes a [!DNL People-Based Destinations]. Este es un ejemplo que ilustra este escenario:

Su compañía, una aerolínea, tiene diferentes niveles de clientes (Bronce, Plata y Oro), y usted quiere proporcionar a cada uno de los niveles ofertas personalizadas a través de las plataformas sociales. Utilice el Administrador de Audiencias para analizar la actividad de los clientes en su sitio web. Sin embargo, no todos los clientes utilizan la aplicación móvil de la aerolínea y algunos de ellos no han iniciado sesión en el sitio web de la compañía. Los datos del cliente se limitan principalmente a los ID de pertenencia y las direcciones de correo electrónico.

Para destinatario en los medios sociales y canales similares basados en personas, puede incluir sus direcciones [de correo electrónico](people-based-destinations-prerequisites.md) con hash en el Administrador de Audiencias y combinarlas con sus características de actividad en línea existentes para crear nuevos segmentos de audiencia. A continuación, puede utilizar esos segmentos para realizar destinatarios en la audiencia [!DNL People-Based Destinations].

**B) Segmentación de Audiencias basada exclusivamente en la actividad** del usuario sin conexión. En este caso, el [!DNL CRM] sistema contiene las direcciones de correo electrónico del cliente y otros atributos del cliente, pero los clientes no han interactuado con el sitio web, por lo que no tiene ninguna actividad del cliente en el Administrador de Audiencias. Este es un ejemplo que ilustra este escenario:

Su compañía, un proveedor de servicios de telecomunicaciones, mantiene los datos de los clientes como direcciones de correo electrónico y los planes de telecomunicaciones adquiridos en un [!DNL CRM]servidor interno. Desea destinatario a los clientes existentes en las plataformas sociales para que les apliquen ofertas a fin de actualizar los paquetes en función de sus suscripciones existentes. Para ello, puede ingerir las direcciones de correo electrónico de los clientes con hash en el Administrador de Audiencias y crear segmentos basados en las suscripciones de los clientes existentes. A continuación, puede enviar estos segmentos para [!DNL People-Based Destinations] que destinatario a sus clientes con ofertas personalizadas.

## 2. Definir el tipo de direcciones de correo electrónico de objetivo {#define-target-email}

El segundo paso en la definición de la estrategia de implementación consiste en decidir qué tipo de direcciones de correo electrónico de cliente desea destinatario.

**R) Segmentación de Audiencias en función de las direcciones** de correo electrónico autenticadas. En este caso, los usuarios tienen varias cuentas asociadas con varias direcciones de correo electrónico y desea destinatarios con ofertas personalizadas, basadas únicamente en la dirección de correo electrónico que autentican en el sitio web, en tiempo real.

**B) Objetivo de Audiencia basado en todas las direcciones** de correo electrónico asociadas. En este escenario, los usuarios tienen varias cuentas asociadas con varias direcciones de correo electrónico y desea darles un destinatario en todas sus direcciones de correo electrónico asociadas, independientemente de la actividad autenticada.

## 3. Identifique el tipo de ID de cliente (ID de CRM) que tiene {#identify-customer-id}

La segmentación de audiencias en [!DNL People-Based Destinations] requiere que envíe versiones con hash [de](people-based-destinations-prerequisites.md) SHA256 de sus direcciones de correo electrónico de clientes. Según la configuración del Administrador de Audiencias existente, puede encontrarse en uno de los dos casos siguientes:

**R) Los ID de cliente de Audiencia Manager ([DPUUID](../../reference/ids-in-aam.md)) ya están en minúsculas y tienen direcciones** de correo electrónico con hash. En este escenario, puede utilizar estos ID existentes para destinatario de sus audiencias en [!DNL People-Based Destinations].

**B) Los ID de cliente ([DPUUID](../../reference/ids-in-aam.md)) del administrador de Audiencias no se escriben en minúsculas y tienen hash las direcciones** de correo electrónico. En este escenario, no se pueden enviar los ID de cliente existentes a [!DNL People-Based Destinations]. Para usar [!DNL People-Based Destinations], debe realizar una sincronización de ID entre los ID de cliente existentes y las versiones en minúsculas y con hash de las direcciones de correo electrónico de los clientes. Esto se realiza mediante sincronización [de ID basada en](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) archivos o mediante ID [declarados](../declared-ids.md).

## 4. Cualificación de características {#trait-qualification}

Para realizar un destinatario preciso de la audiencia en [!DNL People-Based Destinations], los usuarios deben cumplir los requisitos para las características basadas en reglas o integradas, según el tipo de objetivo de audiencia que desee realizar.

**R) Califique los ID de cliente y de dispositivo en tiempo real para las características** basadas en reglas. Esta opción se aplica al caso de uso A de [1. Definición del Caso](people-based-destinations-workflow.md#defining-your-use-case)de Uso. Si su plan es destinatario de audiencias en base a la actividad en línea y sin conexión, lo más probable es que ya esté calificando su audiencia para características basadas en [reglas](../traits/trait-and-segment-qualification-reference.md).

**B) Características integradas con sus ID de cliente mediante archivos** de datos de entrada. Esta opción se aplica al caso de uso B de [1. Definición del Caso](people-based-destinations-workflow.md#defining-your-use-case)de Uso. Al dirigir la audiencia en función de la actividad sin conexión, debe cualificar los ID de cliente para características integradas mediante archivos [de datos de](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)entrada.

## 5. Crear o etiquetar fuentes de datos y direcciones de correo electrónico con hash integradas {#create-label-data-sources}

Según el tipo de ID de cliente que tenga en el Administrador de Audiencias (consulte [3. Identifique el tipo de ID de cliente (ID de CRM) que tiene](people-based-destinations-workflow.md#identify-customer-id), y se encontrará en uno de los siguientes escenarios:

**A) Etiquetar una fuente** de datos existente. Esta opción se aplica al escenario en el que los ID de cliente ([DPUUID](../../reference/ids-in-aam.md)) del Administrador de Audiencias ya están en minúsculas y las direcciones de correo electrónico con hash. En este caso, lo que debe hacer es etiquetar la fuente de datos en la que almacena los ID como una fuente [!DNL PII] de datos. Consulte Configuración [](../datasources-list-and-settings.md) de fuente de datos para obtener más información sobre la configuración de la fuente de datos. Lo que debe hacer es asegurarse de que la opción No puede estar vinculada a información personal no está marcada.

**B) Crear una nueva fuente** de datos. Esta opción se aplica al escenario en el que los ID de cliente ([DPUUID](../../reference/ids-in-aam.md)) del Administrador de Audiencias no son direcciones de correo electrónico con hash. En este caso, debe crear una nueva fuente de datos entre dispositivos e incluir sus direcciones de correo electrónico con hash en su contra. Puede hacerlo de dos maneras:

* Utilice la sincronización de ID basada en archivos. Consulte Requisitos de [nombre y contenido para archivos](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de sincronización de ID para obtener más información sobre el aspecto que deben tener los archivos de sincronización de ID. Al utilizar este método, puede realizar el destinatario de todas las direcciones de correo electrónico con hash desde la [!DNL CRM] base de datos.
* Use ID [](../declared-ids.md) declarados para declarar sus direcciones de correo electrónico con hash al pasar ID de cliente autenticados. Al utilizar este método, el Administrador de Audiencias solo destinatario las direcciones de correo electrónico con hash de los usuarios que se hayan autenticado en línea. Las direcciones de correo electrónico objetivo en los canales basados en personas son solo las que aparecen en las llamadas declaradas al evento de ID. Otras direcciones de correo electrónico asociadas con el ID de cliente no se activan en tiempo real.

## 6. Usar una regla de combinación de Perfiles para la segmentación {#use-profile-merge-rules}

Según el caso de uso (consulte [1. Definición del caso](people-based-destinations-workflow.md#defining-your-use-case)de uso), existen dos maneras de utilizarlo [!DNL Profile Merge Rules] para la segmentación.

**A) Usar existente[!DNL Profile Merge Rules]**. Esta opción se aplica al primer caso de uso (objetivo de audiencia basado en la actividad combinada de usuarios en línea y sin conexión). En este escenario, ya tiene una actividad de cliente existente en el Administrador de Audiencias y ha definido al menos una regla de combinación de Perfiles que ha utilizado en la segmentación. En este caso, no es necesario crear ningún nuevo[!DNL Profile Merge Rules].

**B) Crear una nueva regla[!DNL All Cross-Device Profiles]de combinación**. Esta opción se aplica al segundo caso de uso (segmentación de audiencias basada exclusivamente en la actividad de usuarios sin conexión). En este escenario, los datos de clientes sin conexión de su empresa se [!DNL CRM] incorporan al Administrador de Audiencias y desea crear segmentos a partir de esos datos. Para ello, [!DNL People-Based Destinations] introduce una nueva regla de combinación de Perfiles, denominada **[!DNL All Cross-Device Profiles]**. Esta es la regla que debe usar al segmentar datos puramente sin conexión.
