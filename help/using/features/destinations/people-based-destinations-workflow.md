---
description: Los destinos basados en personas oferta varias estrategias de implementación, según la estructura de los datos del cliente. En este artículo se proporciona una descripción general de los pasos de implementación que debe seguir para los destinos basados en personas, según el escenario.
seo-description: 'Los destinos basados en personas oferta varias estrategias de implementación, según la estructura de los datos del cliente. En este artículo se proporciona una descripción general de los pasos de implementación que debe seguir para los destinos basados en personas, según el escenario.  '
seo-title: Guía de implementación de destinos basados en personas
solution: Audience Manager
title: Directrices de implementación
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1379'
ht-degree: 2%

---


# Guía de implementación {#implementation-guidance}

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

[!DNL People-Based Destinations] oferta varias estrategias de implementación, según la estructura de los datos del cliente. Este artículo proporciona una visión general de los pasos de implementación que debe seguir [!DNL People-Based Destinations], según el escenario.

## Información general {#overview}

La configuración de [!DNL People-Based Destinations] lo lleva a través de varias secciones de Audience Manager y requiere diferentes configuraciones y métodos de incorporación de datos, según el tipo de datos de cliente que ya tenga en Audience Manager y el tipo de objetivo de audiencia que desee realizar.

>[!IMPORTANT]
> Antes de configurar [!DNL People-Based Destinations], asegúrese de leer este artículo de forma cuidadosa y completa. Después de leer esta guía, debe tener una clara comprensión del escenario que habilitará a través de [!DNL People-Based Destinations].

Hay seis aspectos de implementación que debe aclarar antes de utilizar [!DNL People-Based Destinations]. Este artículo le ayudará a comprender cuál es su configuración actual, de modo que pueda seguir correctamente los pasos de implementación de su escenario.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Definición del Caso de Uso {#defining-your-use-case}

Antes de comenzar a implementar [!DNL People-Based Destinations], debe definir claramente el caso de uso para el que utilizará esta función. Puede utilizar [!DNL People-Based Destinations] para destinatario de audiencias de dos maneras, según la actividad de audiencias:

**R) Objetivo de Audiencia basado en la actividad** combinada de usuarios en línea y sin conexión. En este escenario, desea combinar los datos de audiencia existentes del Audience Manager con los datos del sistema interno [!DNL CRM] y enviar los segmentos de audiencia resultantes a [!DNL People-Based Destinations]. Este es un ejemplo que ilustra este escenario:

Su compañía, una aerolínea, tiene diferentes niveles de clientes (Bronce, Plata y Oro), y usted quiere proporcionar a cada uno de los niveles ofertas personalizadas a través de las plataformas sociales. Utilice Audience Manager para analizar la actividad de los clientes en su sitio web. Sin embargo, no todos los clientes utilizan la aplicación móvil de la aerolínea y algunos de ellos no han iniciado sesión en el sitio web de la compañía. Los datos del cliente se limitan principalmente a los ID de pertenencia y las direcciones de correo electrónico.

Para destinatario en medios sociales y canales similares basados en personas, puede traer sus [direcciones de correo electrónico con hash](people-based-destinations-prerequisites.md) a Audience Manager y combinarlas con sus características de actividad en línea existentes, para crear nuevos segmentos de audiencia. A continuación, puede utilizar esos segmentos para destinatario de la audiencia a través de [!DNL People-Based Destinations].

**B) Segmentación de Audiencias basada exclusivamente en la actividad** del usuario sin conexión. En este escenario, su [!DNL CRM] sistema contiene las direcciones de correo electrónico del cliente y otros atributos del cliente, pero los clientes no han interactuado con su sitio web, por lo que no tiene ninguna actividad del cliente en Audience Manager. Este es un ejemplo que ilustra este escenario:

Su compañía, un proveedor de servicios de telecomunicaciones, mantiene los datos de los clientes como direcciones de correo electrónico y los planes de telecomunicaciones adquiridos en un [!DNL CRM] interno. Desea destinatario a los clientes existentes en las plataformas sociales para que les apliquen ofertas a fin de actualizar los paquetes en función de sus suscripciones existentes. Para ello, puede ingerir las direcciones de correo electrónico de los clientes con hash en Audience Manager y crear segmentos basados en las suscripciones de los clientes existentes. A continuación, puede enviar estos segmentos a [!DNL People-Based Destinations] para destinatario a sus clientes con ofertas personalizadas.

## 2. Defina el tipo de direcciones de correo electrónico de objetivo {#define-target-email}

El segundo paso en la definición de la estrategia de implementación consiste en decidir qué tipo de direcciones de correo electrónico de cliente desea destinatario.

**R) Objetivo de Audiencia basado en las direcciones** de correo electrónico autenticadas. En este caso, los usuarios tienen varias cuentas asociadas con varias direcciones de correo electrónico y desea destinatarios con ofertas personalizadas, basadas únicamente en la dirección de correo electrónico que autentican en el sitio web, en tiempo real.

**B) Objetivo de Audiencia basado en todas las direcciones** de correo electrónico asociadas. En este escenario, los usuarios tienen varias cuentas asociadas con varias direcciones de correo electrónico y desea darles un destinatario en todas sus direcciones de correo electrónico asociadas, independientemente de la actividad autenticada.

## 3. Identifique el tipo de ID de cliente (ID de CRM) que tiene {#identify-customer-id}

La segmentación de audiencias en [!DNL People-Based Destinations] requiere que envíe [versiones con hash de SHA256](people-based-destinations-prerequisites.md) de las direcciones de correo electrónico de los clientes. Según la configuración de Audience Manager existente, puede encontrarse en uno de los dos casos siguientes:

**R) Los ID de cliente de su Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ya están en minúsculas y tienen direcciones** de correo electrónico con hash. En este escenario, puede utilizar estos ID existentes para destinatario de sus audiencias en [!DNL People-Based Destinations].

**B) Los ID de cliente de su Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) no son direcciones** de correo electrónico con hash en minúsculas. En este escenario, los ID de cliente existentes no se pueden enviar a [!DNL People-Based Destinations]. Para utilizar [!DNL People-Based Destinations], debe realizar una sincronización de ID entre los ID de cliente existentes y las versiones en minúsculas y con hash de las direcciones de correo electrónico de los clientes. Esto se realiza mediante [sincronización de ID basada en archivos](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) o mediante [ID declarados](../declared-ids.md).

## 4. Calificación de rasgo {#trait-qualification}

Para realizar un destinatario preciso de su audiencia en [!DNL People-Based Destinations], los usuarios deben cumplir los requisitos para las características basadas en reglas o integradas, según el tipo de objetivo de audiencia que desee realizar.

**R) Califique los ID de cliente y de dispositivo en tiempo real para las características** basadas en reglas. Esta opción se aplica al caso de uso A de [1. Definición del Caso de Uso](people-based-destinations-workflow.md#defining-your-use-case). Si su plan es destinatario de audiencias basadas en actividades en línea y sin conexión, es muy probable que ya esté calificando su audiencia para [características basadas en reglas](../traits/trait-and-segment-qualification-reference.md).

**B) Características integradas con sus ID de cliente mediante archivos** de datos de entrada. Esta opción se aplica al caso de uso B de [1. Definición del Caso de Uso](people-based-destinations-workflow.md#defining-your-use-case). Al dirigir su audiencia en función de una actividad sin conexión, debe calificar los ID de cliente para características integradas mediante [archivos de datos de entrada](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Crear o etiquetar fuentes de datos y direcciones de correo electrónico con hash integradas {#create-label-data-sources}

Según el tipo de ID de cliente que tenga en Audience Manager (consulte [3. Identifique el tipo de ID de cliente (ID de CRM) que tiene](people-based-destinations-workflow.md#identify-customer-id), se encontrará en uno de los siguientes escenarios:

**A) Etiquetar una fuente** de datos existente. Esta opción se aplica al escenario en el que los ID de cliente de su Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) ya están en minúsculas y las direcciones de correo electrónico con hash. En este caso, lo que debe hacer es etiquetar la fuente de datos en la que almacena los ID como una fuente de datos [!DNL PII]. Consulte [Configuración de fuente de datos](../datasources-list-and-settings.md) para obtener más información sobre la configuración de la fuente de datos. Lo que debe hacer es asegurarse de que la opción No puede estar vinculada a información personal no está marcada.

**B) Crear una nueva fuente** de datos. Esta opción se aplica al escenario en el que los ID de cliente de su Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) no son direcciones de correo electrónico con hash. En este caso, debe crear una nueva fuente de datos entre dispositivos e incluir sus direcciones de correo electrónico con hash en su contra. Puede hacerlo de dos maneras:

* Utilice la sincronización de ID basada en archivos. Consulte [Requisitos de nombre y contenido para archivos de sincronización de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) para obtener más información sobre la apariencia que deben tener los archivos de sincronización de ID. Al utilizar este método, puede destinatario todas las direcciones de correo electrónico con hash desde la base de datos [!DNL CRM].
* Utilice [ID declarados](../declared-ids.md) para declarar sus direcciones de correo electrónico con hash al pasar ID de cliente autenticados. Al utilizar este método, el Audience Manager solo destinatario las direcciones de correo electrónico con hash de los usuarios que se hayan autenticado en línea. Las direcciones de correo electrónico objetivo en los canales basados en personas son solo las que aparecen en las llamadas declaradas al evento de ID. Otras direcciones de correo electrónico asociadas con el ID de cliente no se activan en tiempo real.

## 6. Usar una regla de combinación de Perfiles para la segmentación {#use-profile-merge-rules}

Según el caso de uso (consulte [1. Definición del caso de uso](people-based-destinations-workflow.md#defining-your-use-case)), existen dos maneras de utilizar [!DNL Profile Merge Rules] para la segmentación.

**A) Usar existente[!DNL Profile Merge Rules]**. Esta opción se aplica al primer caso de uso (objetivo de audiencia basado en la actividad combinada de usuarios en línea y sin conexión). En este escenario, ya tiene actividad de cliente existente en Audience Manager y ha definido al menos una regla de combinación de Perfiles que ha utilizado en la segmentación. En este caso, no es necesario crear ningún [!DNL Profile Merge Rules] nuevo.

**B) Crear una nueva regla [!DNL All Cross-Device Profiles]  de** combinación. Esta opción se aplica al segundo caso de uso (segmentación de audiencias basada exclusivamente en la actividad de usuarios sin conexión). En este escenario, está llevando los datos del cliente sin conexión de su [!DNL CRM] al Audience Manager y desea crear segmentos a partir de esos datos. Para ello, [!DNL People-Based Destinations] introduce una nueva regla de combinación de Perfiles, denominada **[!DNL All Cross-Device Profiles]**. Esta es la regla que debe usar al segmentar datos puramente sin conexión.
