---
description: People-Based Destinations ofrece varias estrategias de implementación, según la estructura de los datos de sus clientes. Este artículo proporciona información general sobre los pasos de implementación que debe seguir para los destinos basados en personas, según el escenario.
seo-description: 'People-Based Destinations ofrece varias estrategias de implementación, según la estructura de los datos de sus clientes. Este artículo proporciona información general sobre los pasos de implementación que debe seguir para los destinos basados en personas, según el escenario.  '
seo-title: Guía de implementación de destinos basados en personas
solution: Audience Manager
title: Directrices de implementación
feature: Destinos basados en personas
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 2%

---

# Directrices de implementación {#implementation-guidance}

>[!IMPORTANT]
>Este artículo contiene documentación del producto pensada para guiarle en la configuración y uso de esta función. Nada de lo contenido en este documento es asesoramiento jurídico. Consulte a su propio asesor jurídico para obtener asesoramiento jurídico.

[!DNL People-Based Destinations] ofrece varias estrategias de implementación, según la estructura de los datos de sus clientes. Este artículo proporciona información general sobre los pasos de implementación que debe seguir para [!DNL People-Based Destinations], según el escenario.

## Información general {#overview}

La configuración de [!DNL People-Based Destinations] le lleva a través de varias secciones de Audience Manager y requiere diferentes configuraciones y métodos de incorporación de datos, según el tipo de datos de cliente que ya tenga en Audience Manager y el tipo de segmentación de audiencia que desee realizar.

>[!IMPORTANT]
> Antes de configurar [!DNL People-Based Destinations], asegúrese de leer este artículo de forma cuidadosa y completa. Después de leer esta guía, debe comprender claramente el escenario que habilitará a través de [!DNL People-Based Destinations].

Hay seis aspectos de implementación que debe aclarar antes de utilizar [!DNL People-Based Destinations]. Este artículo le ayudará a comprender cuál es su configuración actual para que pueda seguir correctamente los pasos de implementación de su escenario.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Definición del caso de uso {#defining-your-use-case}

Antes de comenzar a implementar [!DNL People-Based Destinations], debe definir claramente el caso de uso para el que utilizará esta función. Puede utilizar [!DNL People-Based Destinations] para segmentar audiencias de dos formas, según la actividad de la audiencia:

**A) Segmentación de audiencias en función de la actividad** combinada de los usuarios en línea y sin conexión. En esta situación, debe combinar los datos de audiencia existentes de Audience Manager con los datos de su sistema interno [!DNL CRM] y enviar los segmentos de audiencia resultantes a [!DNL People-Based Destinations]. Este es un ejemplo que ilustra este escenario:

Su empresa, una aerolínea, tiene diferentes niveles de clientes (bronce, plata y oro) y desea proporcionar a cada uno de los niveles ofertas personalizadas a través de plataformas sociales. Utilice un Audience Manager para analizar la actividad de los clientes en su sitio web. Sin embargo, no todos los clientes utilizan la aplicación móvil de la aerolínea y algunos de ellos no han iniciado sesión en el sitio web de la empresa. Los datos de clientes se limitan principalmente a los ID de pertenencia y las direcciones de correo electrónico.

Para dirigirse a ellos en medios sociales y canales basados en personas similares, puede llevar sus [direcciones de correo electrónico con hash](people-based-destinations-prerequisites.md) a Audience Manager y combinarlas con sus características de actividad en línea existentes para crear nuevos segmentos de audiencia. A continuación, puede usar esos segmentos para dirigirse a su audiencia a través de [!DNL People-Based Destinations].

**B) Segmentación de audiencias basada exclusivamente en la actividad** del usuario sin conexión. En esta situación, el sistema [!DNL CRM] contiene las direcciones de correo electrónico del cliente y otros atributos del cliente, pero los clientes no han interactuado con el sitio web, por lo que no tiene ninguna actividad del cliente en Audience Manager. Este es un ejemplo que ilustra este escenario:

Su empresa, un proveedor de servicios de telecomunicaciones, mantiene los datos de los clientes como direcciones de correo electrónico y planes de telecomunicaciones adquiridos en un [!DNL CRM] interno. Desea dirigirse a los clientes existentes en plataformas sociales para ofrecerles paquetes de actualización basados en sus suscripciones existentes. Para ello, puede ingerir las direcciones de correo electrónico de los clientes con hash en Audience Manager y crear segmentos basados en las suscripciones de los clientes existentes. A continuación, puede enviar estos segmentos a [!DNL People-Based Destinations] para dirigirse a sus clientes con ofertas personalizadas.

## 2. Defina el tipo de direcciones de correo electrónico de destino {#define-target-email}

El segundo paso para definir la estrategia de implementación consiste en decidir qué tipo de direcciones de correo electrónico de los clientes desea segmentar.

**A) Segmentación de audiencias en función de las direcciones** de correo electrónico autenticadas. En esta situación, los usuarios tienen varias cuentas asociadas con varias direcciones de correo electrónico y desea dirigirlas a ofertas personalizadas, basadas únicamente en la dirección de correo electrónico que autentican en el sitio web en tiempo real.

**B) Segmentación de audiencias en función de todas las direcciones** de correo electrónico asociadas. En esta situación, los usuarios tienen varias cuentas asociadas con varias direcciones de correo electrónico y desea segmentarlas en todas sus direcciones de correo electrónico asociadas, independientemente de la actividad autenticada.

## 3. Identifique el tipo de ID de cliente (ID de CRM) que tiene {#identify-customer-id}

Para dirigir audiencias en [!DNL People-Based Destinations] es necesario que envíe versiones con hash [SHA256](people-based-destinations-prerequisites.md) de las direcciones de correo electrónico de los clientes. Según la configuración de Audience Manager existente, puede encontrarse en uno de los dos escenarios siguientes:

**A) Los ID de cliente de Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ya están en minúsculas y tienen direcciones** de correo electrónico con hash. En esta situación, puede utilizar estos ID existentes para dirigirse a las audiencias en [!DNL People-Based Destinations].

**B) Los ID de cliente de Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) no son direcciones** de correo electrónico con hash ni en minúsculas. En esta situación, los ID de cliente existentes no se pueden enviar a [!DNL People-Based Destinations]. Para utilizar [!DNL People-Based Destinations], debe realizar una sincronización de ID entre los ID de cliente existentes y las versiones en minúsculas y con hash de las direcciones de correo electrónico de los clientes. Para ello, utilice la [sincronización de ID basada en archivos](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) o utilice [ID declarados](../declared-ids.md).

## 4. Calificación de rasgos {#trait-qualification}

Para dirigirse a la audiencia con precisión en [!DNL People-Based Destinations], los usuarios deben cumplir los requisitos para rasgos basados en reglas o integrados, según el tipo de segmentación de audiencia que desee realizar.

**R) Califique sus ID de cliente y de dispositivo en tiempo real para rasgos** basados en reglas. Esta opción se aplica al caso de uso A de [1. Definición del caso de uso](people-based-destinations-workflow.md#defining-your-use-case). Si su plan es segmentar audiencias en función de la actividad en línea y sin conexión, lo más probable es que ya esté calificando a su audiencia para [rasgos basados en reglas](../traits/trait-and-segment-qualification-reference.md).

**B) Incorpore características con sus ID de cliente a través de archivos** de datos entrantes. Esta opción se aplica al caso de uso B de [1. Definición del caso de uso](people-based-destinations-workflow.md#defining-your-use-case). Al segmentar la audiencia en función de la actividad puramente sin conexión, debe clasificar los ID de cliente para rasgos incorporados a través de [archivos de datos entrantes](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Crear o etiquetar fuentes de datos y direcciones de correo electrónico con hash integradas {#create-label-data-sources}

Según el tipo de ID de cliente que tenga en el Audience Manager (consulte [3. Identifique el tipo de ID de cliente (ID de CRM) que tiene](people-based-destinations-workflow.md#identify-customer-id), y se encontrará en uno de los siguientes casos:

**A) Etiquetar una fuente** de datos existente. Esta opción se aplica al caso en el que los ID de cliente de Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) ya estén en minúsculas y tengan direcciones de correo electrónico con hash. En este caso, lo que debe hacer es etiquetar la fuente de datos en la que almacena los ID como fuente de datos [!DNL PII]. Consulte [Configuración de fuente de datos](../datasources-list-and-settings.md) para obtener más información sobre la configuración de la fuente de datos. Lo que debe hacer es asegurarse de que la opción No se puede asociar a información personal esté desmarcada.

**B) Crear una nueva fuente** de datos. Esta opción se aplica al escenario en el que los ID de cliente de Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) no son direcciones de correo electrónico con hash. En este caso, debe crear una nueva fuente de datos entre dispositivos e incluir sus direcciones de correo electrónico con hash en su lugar. Puede hacerlo de dos maneras:

* Utilice la sincronización de ID basada en archivos. Consulte [Requisitos de nombre y contenido para archivos de sincronización de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) para obtener más información sobre la apariencia que deben tener los archivos de sincronización de ID. Al utilizar este método, puede dirigir todas las direcciones de correo electrónico con hash desde la base de datos [!DNL CRM].
* Utilice [ID declarados](../declared-ids.md) para declarar las direcciones de correo electrónico con hash al pasar los ID de cliente autenticados. Al utilizar este método, el Audience Manager, en su nombre, solo segmenta las direcciones de correo electrónico con hash de los usuarios que se hayan autenticado en línea. Las direcciones de correo electrónico segmentadas en los canales basados en personas solo son las que aparecen en las llamadas de evento de ID declaradas. Otras direcciones de correo electrónico asociadas con el ID de cliente no se activan en tiempo real.

## 6. Utilizar una regla de combinación de perfiles para la segmentación {#use-profile-merge-rules}

Según el caso de uso (consulte [1. Definición del caso de uso](people-based-destinations-workflow.md#defining-your-use-case)), existen dos maneras de utilizar [!DNL Profile Merge Rules] para la segmentación.

**A) Usar[!DNL Profile Merge Rules]**. Esta opción se aplica al primer caso de uso (segmentación de audiencia en función de la actividad combinada de usuarios en línea y sin conexión). En esta situación, tiene actividad de cliente existente en Audience Manager y ya ha definido al menos una regla de combinación de perfiles que ha utilizado en la segmentación. En este caso, no es necesario crear ningún [!DNL Profile Merge Rules] nuevo.

**B) Crear una regla de  [!DNL All Cross-Device Profiles] combinación nueva**. Esta opción se aplica al segundo caso de uso (segmentación de audiencia basada exclusivamente en la actividad del usuario sin conexión). En este escenario, está llevando los datos de clientes sin conexión de su [!DNL CRM] al Audience Manager y desea crear segmentos a partir de esos datos. Para ello, [!DNL People-Based Destinations] introduce una nueva regla de combinación de perfiles, denominada **[!DNL All Cross-Device Profiles]**. Esta es la regla que debe utilizar al segmentar datos puramente sin conexión.
