---
description: Los destinos basados en personas ofrecen varias estrategias de implementación, según la estructura de los datos del cliente. Este artículo proporciona información general sobre los pasos de implementación que debe seguir para los destinos basados en personas, según el escenario.
seo-description: 'Los destinos basados en personas ofrecen varias estrategias de implementación, según la estructura de los datos del cliente. Este artículo proporciona información general sobre los pasos de implementación que debe seguir para los destinos basados en personas, según el escenario.  '
seo-title: Guía de implementación de destinos basada en personas
solution: Audience Manager
title: Guía de implementación
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# Guía de implementación {#implementation-guidance}

[!DNL People-Based Destinations] ofrece varias estrategias de implementación, dependiendo de cómo estén estructurados los datos del cliente. Este artículo proporciona información general sobre los pasos de implementación que [!DNL People-Based Destinations]debe seguir, según su escenario.

## Información general {#overview}

La configuración de [!DNL People-Based Destinations] lo lleva a través de varias secciones de Audience Manager y requiere diferentes ajustes y métodos de integración de datos, según el tipo de datos de cliente que ya tenga en Audience Manager y el tipo de objetivo de audiencia que desee realizar.

>[!IMPORTANT]
> Antes de configurar [!DNL People-Based Destinations], asegúrese de leer este artículo detenidamente y por completo. Después de leer esta guía, debe comprender claramente el escenario en [!DNL People-Based Destinations]el que habilitará.

Existen seis aspectos de implementación que debe aclarar antes de utilizar [!DNL People-Based Destinations]. Este artículo le ayudará a comprender cuál es su configuración actual, para que pueda seguir correctamente los pasos de implementación para su escenario.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Definición de su caso de uso {#defining-your-use-case}

Antes de comenzar a implementar [!DNL People-Based Destinations], debe definir claramente el caso de uso para el que utilizará esta función. Puede usar [!DNL People-Based Destinations] para dirigirse a audiencias de dos maneras, según la actividad de la audiencia:

**A) Segmentación de audiencias basada en la actividad combinada de usuarios en línea y sin conexión**. En este escenario, desea combinar los datos de audiencia existentes de Audience Manager con datos de su sistema interno [!DNL CRM] y enviar los segmentos de audiencia resultantes a [!DNL People-Based Destinations]. Este es un ejemplo que ilustra este escenario:

Su empresa, una aerolínea, tiene diferentes niveles de cliente (Bronce, Plata y Oro) y desea proporcionar cada uno de los niveles con ofertas personalizadas a través de plataformas sociales. Utilice Audience Manager para analizar la actividad del cliente en su sitio Web. Sin embargo, no todos los clientes utilizan la aplicación móvil de la aerolínea y algunos nunca han iniciado sesión en el sitio web de la compañía. Los datos del cliente están principalmente limitados a ID de pertenencia y direcciones de correo electrónico.

Para segmentar por medio de medios sociales y de canales similares basados en personas, puede incorporar las direcciones de correo electrónico [hash](people-based-destinations-prerequisites.md) a Audience Manager y combinarlas con características de actividad en línea existentes, para crear nuevos segmentos de audiencia. A continuación, puede utilizar esos segmentos para dirigirse a la audiencia.[!DNL People-Based Destinations]

**B) Segmentación de audiencias basada exclusivamente en actividades de usuario sin conexión**. En este escenario, [!DNL CRM] el sistema contiene direcciones de correo electrónico del cliente y otros atributos del cliente, pero los clientes no han interactuado con el sitio Web, por lo que no tiene ninguna actividad de cliente en Audience Manager. Este es un ejemplo que ilustra este escenario:

Su empresa, un proveedor de servicios de telecomunicaciones, mantiene datos de clientes como direcciones de correo electrónico y planes de telecomunicaciones adquiridos en un interno [!DNL CRM]. Desea segmentar clientes existentes en plataformas sociales para ofrecerles paquetes de actualización según sus suscripciones existentes. Para ello, puede ingestar las direcciones de correo electrónico de cliente con hash en Audience Manager y crear segmentos basados en las suscripciones existentes al cliente. A continuación, puede enviar estos segmentos a [!DNL People-Based Destinations] fin de dirigirse a sus clientes con ofertas personalizadas.

## 2. Definición del tipo de direcciones de correo electrónico objetivo {#define-target-email}

El segundo paso en la definición de la estrategia de implementación es decidir qué tipo de direcciones de correo electrónico de cliente desea dirigir.

**A) Segmentación de audiencias basada en direcciones de correo electrónico autenticadas**. En este escenario, los usuarios tienen varias cuentas asociadas con varias direcciones de correo electrónico y desea dirigirlas con ofertas personalizadas, basándose solamente en la dirección de correo electrónico que autentican en el sitio web en tiempo real.

**B) Segmentación de audiencias basada en todas las direcciones de correo electrónico asociadas**. En este escenario, los usuarios tienen varias cuentas asociadas con varias direcciones de correo electrónico y desea dirigirlas a todas las direcciones de correo electrónico asociadas, independientemente de la actividad autenticada.

## 3. Identificar el tipo de ID de cliente (ID de CRM) que tiene {#identify-customer-id}

La segmentación de audiencias en [!DNL People-Based Destinations] requiere enviar [versiones hash](people-based-destinations-prerequisites.md) SHA 256 de las direcciones de correo electrónico de sus clientes. Según la configuración existente de Audience Manager, puede encontrarse en uno de los dos casos siguientes:

**R) Los ID de cliente de Audience Manager ([dpuuids](../../reference/ids-in-aam.md)) ya están en minúsculas y tienen hash direcciones** de correo electrónico. En este escenario, puede utilizar estos ID existentes para dirigirse a sus audiencias en [!DNL People-Based Destinations].

**B) Los ID de cliente de Audience Manager ([dpuuids](../../reference/ids-in-aam.md)) no tienen direcciones** de correo electrónico con hash. En este escenario, no se pueden enviar los ID de cliente existentes [!DNL People-Based Destinations]. Para usar [!DNL People-Based Destinations], debe realizar una sincronización de ID entre sus ID de cliente existentes y versiones con hash en minúsculas de las direcciones de correo electrónico del cliente. Esto se realiza mediante [la sincronización de ID basada en archivos](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) o mediante [ID declarados](../declared-ids.md).

## 4. Cualificación de características {#trait-qualification}

Para dirigirse con precisión a la audiencia en [!DNL People-Based Destinations], los usuarios deben cumplir con las características basadas en reglas o en las características integradas, según el tipo de segmentación de audiencias que desee realizar.

**R) Cualifique los ID de cliente y los ID de dispositivos en tiempo real para las características basadas en reglas**. Esta opción se aplica al caso de uso A desde [1. Definición de su caso de uso](people-based-destinations-workflow.md#defining-your-use-case). Si su plan es dirigirse a las audiencias en función de la actividad en línea y sin conexión, es probable que ya esté calificando a su audiencia para características [basadas en reglas](../traits/trait-qualification-reference.md).

**B) Características de la Onboard con ID de cliente a través de archivos de datos de entrada**. Esta opción se aplica al caso de uso B desde [1. Definición de su caso de uso](people-based-destinations-workflow.md#defining-your-use-case). Al segmentar la audiencia en función de la actividad fuera de línea, es necesario calificar los ID de cliente para características integradas a través [de archivos de datos entrantes](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Crear o etiquetar fuentes de datos y direcciones de correo electrónico con hash {#create-label-data-sources}

Según el tipo de ID de cliente que tenga en Audience Manager (consulte [3. Identificar el tipo de ID de cliente (ID de CRM) que tiene](people-based-destinations-workflow.md#identify-customer-id), se encontrará en uno de los escenarios siguientes:

**A) Etiqueta de fuente de datos existente**. Esta opción se aplica al escenario en el que los ID de cliente de Audience Manager ([dpuuids](../../reference/ids-in-aam.md)) ya están en minúsculas y tienen hash direcciones de correo electrónico. En este caso, lo que debe hacer es etiquetar el origen de datos que almacena los ID como fuente [!DNL PII] de datos. Consulte [Configuración de fuentes de datos](../datasources-list-and-settings.md) para obtener más información sobre la configuración de la fuente de datos. Lo que debe hacer es asegurarse de que no se puede vincular la opción de información personal con información de identificación personal.

**B) Cree una nueva fuente de datos**. Esta opción se aplica al escenario donde los ID de cliente de Audience Manager ([dpuuids](../../reference/ids-in-aam.md)) no son direcciones de correo electrónico hash. En este caso, debe crear una nueva fuente de datos entre dispositivos y onboard las direcciones de correo electrónico con hash. Puede hacerlo de dos maneras:

* Utilice la sincronización de ID basada en archivos. Consulte [Requisitos de nombre y contenido para archivos de sincronización de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) para obtener más información sobre los archivos de sincronización de ID que deben aparecer. Al utilizar este método, puede dirigir todas las direcciones de correo electrónico con hash de la [!DNL CRM] base de datos.
* Utilice [los ID declarados](../declared-ids.md) para declarar direcciones de correo electrónico hash al pasar ID de cliente autenticados. Al utilizar este método, Audience Manager solo se dirige a las direcciones de correo electrónico con hash de los usuarios que se han autenticado en línea. Las direcciones de correo electrónico dirigidas a través de Facebook son sólo las de las llamadas de eventos de ID declarados. Otras direcciones de correo electrónico asociadas con el ID de cliente no se activan en tiempo real.

## 6. Utilizar una regla de combinación de perfiles para segmentación {#use-profile-merge-rules}

Según el caso de uso (véase [1. Definición de su caso de uso](people-based-destinations-workflow.md#defining-your-use-case)), existen dos maneras de utilizar [!DNL Profile Merge Rules] la segmentación.

**R) Uso existente[!DNL Profile Merge Rules]**. Esta opción se aplica al primer caso de uso (segmentación de audiencia basada en la actividad combinada de usuarios en línea y sin conexión). En este escenario, tiene actividad de cliente existente en Audience Manager y ya ha definido al menos una regla de combinación de perfiles que ha utilizado en la segmentación. En este caso, no es necesario crear [!DNL Profile Merge Rules]ningún nuevo.

**B) Crear una nueva regla[!DNL All Cross-Device Profiles]de combinación**. Esta opción se aplica al segundo caso de uso (segmentación de audiencia basada exclusivamente en actividad de usuario sin conexión). En este escenario, obtiene datos de cliente sin conexión de su [!DNL CRM] en Audience Manager y desea crear segmentos a partir de esos datos. Para ello [!DNL People-Based Destinations] , introduce una nueva cuarta regla de combinación de perfiles llamada **[!DNL All Cross-Device Profiles]**. Esta es la regla que debe utilizar al segmentar datos simples sin conexión.
