---
description: People-Based Destinations offers multiple implementation strategies, depending on how your customer data is structured. This article provides an overview of the implementation steps that you need to follow for People-Based Destinations, depending on your scenario.
seo-description: 'People-Based Destinations offers multiple implementation strategies, depending on how your customer data is structured. This article provides an overview of the implementation steps that you need to follow for People-Based Destinations, depending on your scenario.  '
seo-title: Guía de implementación de destinos basados en personas
solution: Audience Manager
title: Implementation Guidance
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

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

**R) Segmentación de audiencias en función de la actividad** combinada de usuarios en línea y sin conexión. En este escenario, desea combinar los datos de audiencia existentes de Audience Manager con los datos del sistema interno [!DNL CRM] y enviar los segmentos de audiencia resultantes a [!DNL People-Based Destinations]. Este es un ejemplo que ilustra este escenario:

Su compañía, una aerolínea, tiene diferentes niveles de clientes (Bronce, Plata y Oro), y usted quiere proporcionar a cada uno de los niveles ofertas personalizadas a través de plataformas sociales. Audience Manager se utiliza para analizar la actividad de los clientes en el sitio web. Sin embargo, no todos los clientes utilizan la aplicación móvil de la aerolínea y algunos de ellos no han iniciado sesión en el sitio web de la empresa. Los datos del cliente se limitan principalmente a los ID de pertenencia y las direcciones de correo electrónico.

Para dirigirlos a través de medios sociales y canales similares basados en personas, puede traer sus direcciones [de correo electrónico](people-based-destinations-prerequisites.md) con hash a Audience Manager y combinarlas con sus características de actividad en línea existentes para crear nuevos segmentos de audiencia. A continuación, puede utilizar estos segmentos para dirigirse a la audiencia a través de [!DNL People-Based Destinations].

**B) Segmentación de audiencias basada exclusivamente en la actividad** de los usuarios sin conexión. En este escenario, el [!DNL CRM] sistema contiene las direcciones de correo electrónico del cliente y otros atributos del cliente, pero los clientes no han interactuado con el sitio web, por lo que no tiene actividad de cliente en Audience Manager. Este es un ejemplo que ilustra este escenario:

Su empresa, un proveedor de servicios de telecomunicaciones, mantiene los datos de los clientes, como direcciones de correo electrónico, y los planes de telecomunicaciones adquiridos en un sistema interno [!DNL CRM]. Desea dirigirse a los clientes existentes en las plataformas sociales para ofrecerles paquetes de actualización basados en sus suscripciones existentes. Para ello, puede ingerir las direcciones de correo electrónico de los clientes con hash en Audience Manager y crear segmentos basados en las suscripciones de los clientes existentes. Then, you can send these segments to  to target your customers with personalized offers.[!DNL People-Based Destinations]

## 2. Definir el tipo de direcciones de correo electrónico de objetivo {#define-target-email}

El segundo paso en la definición de la estrategia de implementación consiste en decidir qué tipo de direcciones de correo electrónico de cliente desea dirigir.

**A) Audience targeting based on your authenticated email addresses.** In this scenario, your users have multiple accounts associated with multiple email addresses, and you want to target them with personalized offers, based only on the email address that they authenticate on your website, in real time.

**B) Audience targeting based on all of your associated email addresses.** In this scenario, your users have multiple accounts associated with multiple email addresses, and you want to target them across all of their associated email addresses, regardless of authenticated activity.

## 3. Identify the Type of Customer IDs (CRM IDs) That You Have {#identify-customer-id}

Targeting audiences in  requires you to send SHA256 hashed versions of your customer email addresses. [!DNL People-Based Destinations][](people-based-destinations-prerequisites.md) Depending on your existing Audience Manager configuration, you may find yourself in one of the following two scenarios:

**A) Your Audience Manager customer IDs (DPUUIDs) are already lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)** In this scenario, you can use these existing IDs to target your audiences in .[!DNL People-Based Destinations]

**B) Your Audience Manager customer IDs (DPUUIDs) are not lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)** In this scenario, your existing customer IDs cannot be sent to . [!DNL People-Based Destinations] To use , you need to perform an ID synchronization between your existing customer IDs and lowercase, hashed versions of your customer email addresses. [!DNL People-Based Destinations] You do this either through file-based ID synchronization or by using declared IDs.[](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)[](../declared-ids.md)

## 4. Cualificación de características {#trait-qualification}

Para dirigirse a la audiencia con precisión en [!DNL People-Based Destinations], los usuarios deben cumplir los requisitos para las características basadas en reglas o integradas, según el tipo de segmentación de audiencia que desee realizar.

**R) Califique los ID de cliente y de dispositivo en tiempo real para las características** basadas en reglas. This option applies to use case A from 1. [ Definición del Caso](people-based-destinations-workflow.md#defining-your-use-case)de Uso. Si su plan es dirigirse a audiencias en función de la actividad en línea y sin conexión, lo más probable es que ya esté calificando a la audiencia para las características basadas en [reglas](../traits/trait-qualification-reference.md).

**B) Características integradas con sus ID de cliente mediante archivos** de datos de entrada. Esta opción se aplica al caso de uso B de [1. Definición del Caso](people-based-destinations-workflow.md#defining-your-use-case)de Uso. Al segmentar la audiencia según la actividad que se realice sin conexión, debe cualificar los ID de cliente para características integradas mediante archivos [de datos de](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)entrada.

## 5. Crear o etiquetar fuentes de datos y direcciones de correo electrónico con hash integradas {#create-label-data-sources}

Según el tipo de ID de cliente que tenga en Audience Manager (consulte [3. Identifique el tipo de ID de cliente (ID de CRM) que tiene](people-based-destinations-workflow.md#identify-customer-id), y se encontrará en uno de los siguientes escenarios:

**A) Etiquetar una fuente** de datos existente. Esta opción se aplica al escenario en el que los ID de cliente de Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) ya están en minúsculas y tienen hash las direcciones de correo electrónico. En este caso, lo que debe hacer es etiquetar la fuente de datos en la que almacena los ID como una fuente [!DNL PII] de datos. Consulte Configuración [](../datasources-list-and-settings.md) de fuente de datos para obtener más información sobre la configuración de la fuente de datos. Lo que debe hacer es asegurarse de que la opción No puede estar vinculada a información personal no está marcada.

**B) Crear una nueva fuente** de datos. Esta opción se aplica al escenario en el que los ID de cliente de Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) no son direcciones de correo electrónico con hash. En este caso, debe crear una nueva fuente de datos entre dispositivos e incluir sus direcciones de correo electrónico con hash en su contra. You can do this in two ways:

* Utilice la sincronización de ID basada en archivos. Consulte Requisitos de [nombre y contenido para archivos](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de sincronización de ID para obtener más información sobre el aspecto que deben tener los archivos de sincronización de ID. Al utilizar este método, puede segmentar todas las direcciones de correo electrónico con hash de la [!DNL CRM] base de datos.
* Use ID [](../declared-ids.md) declarados para declarar sus direcciones de correo electrónico con hash al pasar ID de cliente autenticados. Al utilizar este método, Audience Manager, en su nombre, solo segmenta las direcciones de correo electrónico con hash de los usuarios que se hayan autenticado en línea. Las direcciones de correo electrónico que se dirigen a los canales basados en personas son solo las que aparecen en las llamadas de evento de ID declaradas. Otras direcciones de correo electrónico asociadas con el ID de cliente no se activan en tiempo real.

## 6. Use a Profile Merge Rule for Segmentation {#use-profile-merge-rules}

Según el caso de uso (consulte [1. Definición del caso](people-based-destinations-workflow.md#defining-your-use-case)de uso), existen dos maneras de utilizarlo [!DNL Profile Merge Rules] para la segmentación.

**A) Use existing .[!DNL Profile Merge Rules]** Esta opción se aplica al primer caso de uso (segmentación de audiencia en función de la actividad combinada de usuarios en línea y sin conexión). In this scenario, you have existing customer activity in Audience Manager and you have already defined at least one Profile Merge Rule that you have used in segmentation. In this case, you don't need to create any new .[!DNL Profile Merge Rules]

**B) Create a new,  Merge Rule.[!DNL All Cross-Device Profiles]** This option applies to the second use case (audience targeting based exclusively on offline user activity). In this scenario you are bringing your offline customer data from your  into Audience Manager, and want to create segments from that data. [!DNL CRM] To do this,  introduces a new, fourth Profile Merge Rule, called . [!DNL People-Based Destinations]**[!DNL All Cross-Device Profiles]** This is the rule that you need to use when segmenting purely offline data.
