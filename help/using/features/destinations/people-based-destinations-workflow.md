---
description: Los destinos basados en personas ofrecen varias estrategias de implementación, según la estructura de los datos del cliente. En este artículo se proporciona una descripción general de los pasos de implementación que debe seguir para los destinos basados en personas, según el escenario.
seo-description: 'Los destinos basados en personas ofrecen varias estrategias de implementación, según la estructura de los datos del cliente. En este artículo se proporciona una descripción general de los pasos de implementación que debe seguir para los destinos basados en personas, según el escenario.  '
seo-title: Guía de implementación de destinos basados en personas
solution: Audience Manager
title: Directrices de implementación
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# Directrices de implementación {#implementation-guidance}

[!DNL People-Based Destinations] ofrece varias estrategias de implementación, según la estructura de los datos del cliente. En este artículo se proporciona una descripción general de los pasos de implementación que debe seguir [!DNL People-Based Destinations]según el escenario.

## Información general {#overview}

La configuración de [!DNL People-Based Destinations] le lleva a través de varias secciones de Audience Manager y requiere diferentes opciones de configuración y métodos de incorporación de datos, según el tipo de datos de cliente que ya tenga en Audience Manager y el tipo de segmentación de audiencia que desee realizar.

>[!IMPORTANT]
> Antes de configurar [!DNL People-Based Destinations], asegúrese de leer este artículo de forma cuidadosa y completa. Después de leer esta guía, debe tener una clara comprensión del escenario que habilitará mediante [!DNL People-Based Destinations].

Hay seis aspectos de implementación que debe aclarar antes de usar [!DNL People-Based Destinations]. Este artículo le ayudará a comprender cuál es su configuración actual, de modo que pueda seguir correctamente los pasos de implementación de su escenario.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Definición de Casos de Uso {#defining-your-use-case}

Antes de comenzar a implementar [!DNL People-Based Destinations], debe definir claramente el caso de uso para el que va a utilizar esta función. Puede usar [!DNL People-Based Destinations] para segmentar audiencias de dos formas, según la actividad de la audiencia:

**A) Segmentación de audiencias en función de la actividad** combinada de usuarios en línea y sin conexión. En este escenario, desea combinar los datos de audiencia existentes de Audience Manager con los datos del sistema interno [!DNL CRM] y enviar los segmentos de audiencia resultantes a [!DNL People-Based Destinations]. Este es un ejemplo que ilustra este escenario:

Su compañía, una aerolínea, tiene diferentes niveles de clientes (Bronce, Plata y Oro), y usted quiere proporcionar a cada uno de los niveles ofertas personalizadas a través de plataformas sociales. Audience Manager se utiliza para analizar la actividad de los clientes en el sitio web. Sin embargo, no todos los clientes utilizan la aplicación móvil de la aerolínea y algunos de ellos ni siquiera iniciaron sesión en el sitio web de la empresa. Los datos del cliente se limitan principalmente a los ID de pertenencia y las direcciones de correo electrónico.

Para dirigirlos a través de medios sociales y canales similares basados en personas, puede incluir las direcciones [de correo electrónico con](people-based-destinations-prerequisites.md) hash en Audience Manager y combinarlas con características de actividad en línea existentes para crear nuevos segmentos de audiencia. A continuación, puede utilizar estos segmentos para dirigirse a la audiencia a través de [!DNL People-Based Destinations].

**B) Segmentación de público basada exclusivamente en la actividad** del usuario sin conexión. En este caso, el [!DNL CRM] sistema contiene direcciones de correo electrónico de clientes y otros atributos de cliente, pero los clientes no han interactuado con el sitio web, por lo que no tiene actividad de cliente en Audience Manager. Este es un ejemplo que ilustra este escenario:

Su empresa, un proveedor de servicios de telecomunicaciones, mantiene los datos de los clientes, como direcciones de correo electrónico, y los planes de telecomunicaciones adquiridos en un sistema interno [!DNL CRM]. Desea dirigirse a los clientes existentes en las plataformas sociales para ofrecerles paquetes de actualización basados en sus suscripciones existentes. Para ello, puede ingerir direcciones de correo electrónico de clientes con hash en Audience Manager y crear segmentos basados en las suscripciones de clientes existentes. A continuación, puede enviar estos segmentos a [!DNL People-Based Destinations] para que se dirijan a sus clientes con ofertas personalizadas.

## 2. Definir el tipo de direcciones de correo electrónico de objetivo {#define-target-email}

El segundo paso en la definición de la estrategia de implementación consiste en decidir qué tipo de direcciones de correo electrónico de cliente desea dirigir.

**A) Segmentación de audiencias basada en direcciones** de correo electrónico autenticadas. En este escenario, los usuarios tienen varias cuentas asociadas con varias direcciones de correo electrónico y desea segmentar con ofertas personalizadas, basadas únicamente en la dirección de correo electrónico que autentican en el sitio web, en tiempo real.

**B) Segmentación de audiencias en función de todas las direcciones** de correo electrónico asociadas. En este escenario, los usuarios tienen varias cuentas asociadas con varias direcciones de correo electrónico y desea segmentarlas en todas sus direcciones de correo electrónico asociadas, independientemente de la actividad autenticada.

## 3. Identifique el tipo de ID de cliente (ID de CRM) que tiene {#identify-customer-id}

La segmentación de audiencias en [!DNL People-Based Destinations] requiere que envíe versiones con hash [de](people-based-destinations-prerequisites.md) SHA256 de las direcciones de correo electrónico de los clientes. Según la configuración de Audience Manager existente, puede encontrarse en uno de los dos escenarios siguientes:

**R) Los ID de cliente de Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ya están en minúsculas y tienen direcciones** de correo electrónico con hash. En este escenario, puede utilizar estos ID existentes para dirigirse a sus audiencias en [!DNL People-Based Destinations].

**B) Los ID de cliente de Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) no se escriben en minúsculas ni tienen hash**. En este escenario, no se pueden enviar los ID de cliente existentes a [!DNL People-Based Destinations]. Para usar [!DNL People-Based Destinations], debe realizar una sincronización de ID entre los ID de cliente existentes y las versiones en minúsculas y con hash de las direcciones de correo electrónico de los clientes. Esto se realiza mediante sincronización [de ID basada en](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) archivos o mediante ID [declarados](../declared-ids.md).

## 4. Cualificación de características {#trait-qualification}

Para dirigirse a la audiencia con precisión en [!DNL People-Based Destinations], los usuarios deben cumplir los requisitos para las características basadas en reglas o integradas, según el tipo de segmentación de audiencia que desee realizar.

**R) Califique los ID de cliente y de dispositivo en tiempo real para las características** basadas en reglas. Esta opción se aplica al caso de uso A de [1. Definición del Caso](people-based-destinations-workflow.md#defining-your-use-case)de Uso. Si su plan es dirigirse a audiencias en función de la actividad en línea y sin conexión, lo más probable es que ya esté calificando a la audiencia para las características basadas en [reglas](../traits/trait-qualification-reference.md).

**B) Características integradas con ID de cliente mediante archivos** de datos de entrada. Esta opción se aplica al caso de uso B de [1. Definición del Caso](people-based-destinations-workflow.md#defining-your-use-case)de Uso. Al segmentar la audiencia según la actividad que se realice sin conexión, debe cualificar los ID de cliente para características integradas mediante archivos [de datos de](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)entrada.

## 5. Crear o etiquetar fuentes de datos y direcciones de correo electrónico con hash integradas {#create-label-data-sources}

Según el tipo de ID de cliente que tenga en Audience Manager (consulte [3. Identifique el tipo de ID de cliente (ID de CRM) que tiene](people-based-destinations-workflow.md#identify-customer-id), y se encontrará en uno de los siguientes escenarios:

**A) Etiquetar una fuente** de datos existente. Esta opción se aplica al escenario en el que los ID de cliente de Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ya están en minúsculas y tienen hash las direcciones de correo electrónico. En este caso, lo que debe hacer es etiquetar la fuente de datos en la que almacena los ID como una fuente [!DNL PII] de datos. Consulte Configuración [](../datasources-list-and-settings.md) de fuente de datos para obtener más información sobre la configuración de la fuente de datos. Lo que debe hacer es asegurarse de que la opción No puede estar vinculada a información personal no está marcada.

**B) Crear una nueva fuente** de datos. Esta opción se aplica al escenario en el que los ID de cliente de Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) no son direcciones de correo electrónico con hash. En este caso, debe crear una nueva fuente de datos entre dispositivos e incluir las direcciones de correo electrónico con hash en su contra. Puede hacerlo de dos maneras:

* Utilice la sincronización de ID basada en archivos. Consulte Requisitos de [nombre y contenido para archivos](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de sincronización de ID para obtener más información sobre el aspecto que deben tener los archivos de sincronización de ID. Al utilizar este método, puede segmentar todas las direcciones de correo electrónico con hash de la [!DNL CRM] base de datos.
* Utilice ID [](../declared-ids.md) declarados para declarar direcciones de correo electrónico con hash al pasar ID de cliente autenticados. Al utilizar este método, Audience Manager solo segmenta las direcciones de correo electrónico con hash de los usuarios que se hayan autenticado en línea. Las direcciones de correo electrónico que se dirigen a través de Facebook son solo las que aparecen en las llamadas de evento de ID declaradas. Otras direcciones de correo electrónico asociadas con el ID de cliente no se activan en tiempo real.

## 6. Usar una regla de combinación de perfiles para la segmentación {#use-profile-merge-rules}

Según el caso de uso (consulte [1. Definición del caso](people-based-destinations-workflow.md#defining-your-use-case)de uso), existen dos maneras de utilizarlo [!DNL Profile Merge Rules] para la segmentación.

**A) Usar existente[!DNL Profile Merge Rules]**. Esta opción se aplica al primer caso de uso (segmentación de audiencia en función de la actividad combinada de usuarios en línea y sin conexión). En este escenario, tiene actividad de cliente existente en Audience Manager y ya ha definido al menos una regla de combinación de perfiles que ha utilizado en la segmentación. En este caso, no es necesario crear ningún nuevo [!DNL Profile Merge Rules].

**B) Crear una nueva regla[!DNL All Cross-Device Profiles]de combinación**. Esta opción se aplica al segundo caso de uso (segmentación de audiencia basada exclusivamente en la actividad de usuario sin conexión). En este escenario, los datos de clientes sin conexión de su empresa [!DNL CRM] se van a incluir en Audience Manager y desea crear segmentos a partir de esos datos. Para ello, [!DNL People-Based Destinations] introduce una nueva regla de combinación de perfiles, denominada **[!DNL All Cross-Device Profiles]**. Esta es la regla que debe usar al segmentar datos puramente sin conexión.
