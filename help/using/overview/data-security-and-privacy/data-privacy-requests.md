---
description: Este documento trata los aspectos técnicos relacionados con el cumplimiento de las regulaciones de privacidad de datos para Audience Manager.
seo-description: Este documento trata los aspectos técnicos relacionados con el cumplimiento de las regulaciones de privacidad de datos para Audience Manager.
seo-title: Solicitudes de privacidad de datos
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Solicitudes de privacidad de datos
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 62%

---


# Solicitudes de privacidad de datos {#data-privacy-requests}

## Información general {#overview}

This document provides an overview of managing individual data privacy and opt-out requests that you can send to [!DNL Audience Manager] through the [Privacy Service UI](https://privacyui.cloud.adobe.io/) and the **[!DNL Privacy Service API]**.

These tools allow you to send consumer data privacy requests made under [!DNL GDPR] and [!DNL CCPA].

Antes de leer este artículo, le recomendamos consultar el [Glosario del RGPD](../data-security-and-privacy/aam-gdpr-glossary.md) y el [Glosario de la CCPA](aam-ccpa-glossary.md) para entender mejor la terminología empleada.

You can submit individual requests to access and delete consumer data from [!DNL Audience Manager], in two ways:

* A través de la [interfaz de usuario del Privacy Service](https://privacyui.cloud.adobe.io/). Consulte la documentación [aquí](https://docs.adobe.com/content/help/es-ES/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* A través de la **[!DNL Privacy Service API]**. Consulte la documentación [aquí](https://docs.adobe.com/content/help/es-ES/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)[!DNL API] y la referencia de la [aquí](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

When sending individual data privacy requests, you can submit any [!DNL Audience Manager] identifiers (IDs), as described in the **[Audience Manager Identifiers](data-privacy-ids.md)** section, along with their respective namespace IDs (data source IDs).

El [Privacy Service](https://docs.adobe.com/content/help/es-ES/experience-platform/privacy/home.html) admite dos tipos de solicitudes: solicitudes de acceso a datos y eliminación de datos.

## Solicitudes de acceso a datos {#access-data}

You can send individual data access requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io) (documentation [here](https://docs.adobe.com/content/help/es-ES/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the Privacy Service API (documentation [here](https://docs.adobe.com/content/help/es-ES/experience-platform/privacy/home.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

La [interfaz de usuario del Privacy Service](https://privacyui.cloud.adobe.io/) permite crear nuevas solicitudes de trabajo mediante el uso del [!UICONTROL Request Builder] o cargando un archivo [!DNL JSON].

Para ver la apariencia de un archivo [!DNL JSON]válido, puede [ descargar una muestra de JSON](../data-security-and-privacy/assets/access_request.json).

Entendemos su compromiso de cumplir con sus solicitudes de privacidad de datos dentro del período de tiempo establecido por la legislación.

## Solicitudes de eliminación de datos {#delete-data}

You can send data deletion requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io) (documentation [here](https://docs.adobe.com/content/help/es-ES/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the Privacy Service API (documentation [here](https://docs.adobe.com/content/help/es-ES/experience-platform/privacy/home.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

La [interfaz de usuario del Privacy Service](https://privacyui.cloud.adobe.io/) permite crear nuevas solicitudes de trabajo mediante el uso del [!UICONTROL Request Builder] o cargando un archivo [!DNL JSON].

Para ver la apariencia de un archivo [!DNL JSON]válido, puede [ descargar una muestra de JSON](../data-security-and-privacy/assets/access_request.json).

Adobe entiende su compromiso de cumplir sus solicitudes de privacidad de datos en un plazo de 30 días. For that reason, [!DNL Adobe] is committed to processing your data deletion request as soon as possible.

In response to your consumer data deletion requests, [!DNL Audience Manager] deletes traits and segments associated with the [!DNL Audience Manager] identifier included in the request. Additionally, the respective [!DNL Audience Manager] identifiers for the individual opted out of further data collection by [!DNL Audience Manager] and the respective ID mappings will be removed.

When you send declared IDs, such as cross device [!DNL CRM] IDs or [!DNL cookie] IDs, in data privacy requests, [!DNL Audience Manager] will perform the necessary deletion on all the linked devices (up to 100 devices per declared ID).

[!DNL Audience Manager] intentará notificar a los socios de activación sobre las solicitudes de eliminación enviándoles información sin segmentar para los sujetos de datos que soliciten la eliminación de ciertos datos. Sin embargo, algunos socios de activación:

1. Cannot support unsegment (or remove segment) requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] with a frequency of less than 30 days. In those cases, [!DNL Audience Manager] customers are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

En estos casos, no puede enviar solicitudes de eliminación a socios de activación de forma automatizada a través de [!DNL Audience Manager].

Descargue nuestra [hoja Excel de socio](assets/AAM-Partners-October2019.xlsx) para ver qué socios de activación de admiten el desegmento.[!DNL Audience Manager]

## Solicitudes de exclusión {#opt-out-requests}

[!DNL Audience Manager] apoya las normas de toda la industria en relación con la gestión de la exclusión. Siga leyendo para disponer de toda la información sobre los tipos de exclusión admitidos por [!DNL Audience Manager].

While data access and deletion requests are handled through the [Privacy Service](https://docs.adobe.com/content/help/es-ES/experience-platform/privacy/home.html), opt-out requests are currently supported through the [!DNL DCS API]. Read on to learn what the opt-out [!DNL API] calls should look like.

### Solicitudes globales de exclusión

The global opt-out represents an opt-out across [!DNL Audience Manager] and other [!DNL Adobe Experience Cloud] solutions for all brands. La siguiente tabla incluye los métodos utilizados para la exclusión global:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exclusión para </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>La <a href="https://www.adobe.com/es/privacy/opt-out.html#customeruse" format="http" scope="external"> página de opciones de privacidad </a> incluye funciones de 1 clic que permiten a los usuarios finales controlar y excluir la recopilación de datos mediante las soluciones de publicidad de Adobe Experience Cloud (incluido Audience Manager). Concretamente, consulte la <a href="https://www.adobe.com/es/privacy/opt-out.html#customeruse" format="http" scope="external"> sección cliente comercial </a> de la página Opciones de privacidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Llamadas de API directas a Audience Manager </p> </td> 
   <td colname="col2"> <p>Los usuarios pueden desactivar la recopilación de datos en todas las marcas de Audience Manager haciendo una llamada a la siguiente API de DCS e incluir el <a href="../../reference/ids-in-aam.md">ID de usuario de Audience Manager</a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Como resultado, estableceremos las cookies <code>demdex=NOTARGET</code> y <code>dextp=NOTARGET</code> para el ID de usuario de Audience Manager enviado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dispositivos móviles </p> </td> 
   <td colname="col2"> <p>Consulte la configuración de exclusión y privacidad para: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/es-ES/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Dispositivos Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/es-ES/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> Dispositivos iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Los usuarios finales también pueden excluir la recopilación global de datos visitando los sitios web de nuestros socios de estándares del sector.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Según las solicitudes de exclusión descritas anteriormente:

* [!DNL Audience Manager] cancelará toda la recopilación, segmentación o activación de datos, siempre que el usuario no borre las cookies del explorador.
* Los datos históricos se eliminan del perfil del usuario transcurridos 120 días.

### Opción de exclusión de nivel de socio con llamadas de ID declaradas

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. You can send partner-level opt-out requests for cross-device IDs, including [!DNL CRM] IDs and hashed email addresses.

Después de una exclusión a nivel de socio con una llamada de ID declarada:

* El [ID de CRM](../../reference/ids-in-aam.md) se excluye de la recopilación de datos;
* El último ID de dispositivo ([ID de usuario único de Audience Manager](../../reference/ids-in-aam.md)) vinculado al [ID de CRM](../../reference/ids-in-aam.md) se excluye de la recopilación de datos.
* [!DNL Audience Manager] dejará de recopilar, segmentar o realizar activaciones de datos para el ID de y el último ID de dispositivo vinculado al ID de ;[!DNL CRM][!DNL CRM]
* [!DNL Audience Manager] dessegmenta el ID de exclusión [!DNL CRM] y el último ID de dispositivo de todos los segmentos;
* [!UICONTROL Destination] los socios reciben la solicitud de dessegmentación para el ID del [!DNL CRM] dispositivo y el ID del último dispositivo. La eliminación de la segmentación sirve tanto para destinos de lote como [en tiempo real](data-privacy-requests.md#aam-partners-with-unsegmentation).
* No se eliminan datos históricos.

When [!DNL Audience Manager] receives a partner-level opt-out request, the [!DNL JSON] returned by the [!DNL DCS] contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the [!DNL Audience Manager] user ID.

Puede realizar una solicitud de exclusión de ID declarada con los pares de clave-valor `d_cid` y `d_cid_ic`. Los parámetros heredados como `d_dpid` y `d_dpuuid` siguen funcionando, pero se consideran obsoletos. Consulte [CID reemplaza DPID y DPUUID](../../reference/cid.md). En los ejemplos, la *cursiva* indica un marcador de posición para una variable.

#### Opción de exclusión con [!DNL CID] y [!DNL CID_IC]

Para obtener una descripción y sintaxis, consulte [variables de URL y Sintaxis para ID declarados](../../features/declared-ids.md#variables-and-syntax).

| Opción de exclusión mediante | Ejemplo de código |
|--- |--- |
| ID de proveedor de datos e ID de usuario. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Código de integración e ID de usuario. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Varios pares `d_cid` y `d_cid_ic` clave-valor. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Opción de exclusión de nivel de socio con llamadas de ID de dispositivo

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. Puede desactivar la recopilación de datos en un ID de dispositivo determinado para una marca haciendo las siguientes llamadas a la [API de DCS](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Opción de exclusión mediante | Ejemplo de código |
|--- |--- |
| An [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Obtenga más información sobre `uuid`, `mid` y `imsOrgId` en el [Índice de ID de Audience Manager](/help/using/reference/ids-in-aam.md).

Después de una exclusión a nivel de socio con una llamada de ID de dispositivo:

* El ID del dispositivo se excluye de la recopilación de datos.
* [!DNL Audience Manager] cancelará cualquier recopilación, segmentación o activación de datos para el socio para el ID del dispositivo.
* [!DNL Audience Manager] dessegmenta el ID del dispositivo de todos los segmentos;
* Los socios de destino reciben la solicitud de eliminación de la segmentación para el ID del dispositivo. La eliminación de la segmentación sirve tanto para destinos de lote como [en tiempo real](data-privacy-requests.md#aam-partners-with-unsegmentation).
* No se eliminan datos históricos.

## [!DNL Audience Manager] Socios con capacidades de dessegmentación {#aam-partners-with-unsegmentation}

In order to help you automate your consumer data privacy requests, [!DNL Audience Manager] will attempt to notify activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

Sin embargo, algunos de los socios de activación:

1. Cannot support unsegment requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] more frequently than once in 30 days.

En estos casos, no puede enviar solicitudes de eliminación a socios de activación de forma automatizada a través de [!DNL Audience Manager].

Consulte la [lista de destinos basados en dispositivos](/help/using/features/destinations/device-based-destinations-list.md) para ver qué socios de activación de admiten la eliminación de la segmentación.[!DNL Audience Manager]

## Solicitudes de corrección de datos {#correction}

Given that [!DNL Audience Manager] is not the source of the data, there is a limited role for data correction in [!DNL Audience Manager]. The correction could mean that the consumer has requested to either be disqualified from an incorrect [!UICONTROL trait]/[!UICONTROL segment] or qualified to the desired [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] los clientes pueden elegir capturar las señales, características o segmentos relevantes en relación con los perfiles de los usuarios y enviar esta información a través de la ingesta [de datos](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) sin conexión a [!DNL Audience Manager]. Please note that the user will continue to get qualified to the original [!UICONTROL trait] and [!UICONTROL segments] if they repeat their behavior.
