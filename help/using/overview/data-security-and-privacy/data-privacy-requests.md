---
description: Este documento trata los aspectos técnicos relacionados con el cumplimiento de las regulaciones de privacidad de datos para Audience Manager.
seo-description: This document covers the technicalities related to data privacy regulations compliance for Audience Manager.
seo-title: Data Privacy Requests
solution: Audience Manager
keywords: IU DEL RGPD, API DEL RGPD, CCPA, privacidad
title: Solicitudes de privacidad de datos
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: a1fc9c21-3417-4899-a585-92ad2cb25362
source-git-commit: 6b43885deddb0cdaeb3698051ea110f0a4eed44e
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 42%

---

# Solicitudes de privacidad de datos {#data-privacy-requests}

## Información general {#overview}

Este documento proporciona información general sobre la administración de la privacidad de datos individuales y las solicitudes de exclusión que puede enviar a [!DNL Audience Manager] a través de la [IU de Privacy Service](https://privacyui.cloud.adobe.io/) y **[!DNL Privacy Service API]**.

Estas herramientas le permiten enviar solicitudes de privacidad de datos de consumo realizadas en [!DNL GDPR] y [!DNL CCPA].

Antes de leer este artículo, le recomendamos consultar el [Glosario del RGPD](../data-security-and-privacy/aam-gdpr-glossary.md) y el [Glosario de la CCPA](aam-ccpa-glossary.md) para entender mejor la terminología empleada.

Puede enviar solicitudes individuales para acceder a los datos de consumidores y eliminarlos de [!DNL Audience Manager] de dos maneras:

* A través de la [interfaz de usuario del Privacy Service](https://privacyui.cloud.adobe.io/). Consulte la documentación [aquí](https://docs.adobe.com/content/help/es-ES/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* A través de la **[!DNL Privacy Service API]**. Vea la documentación [aquí](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=es) y la referencia [!DNL API] [aquí](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

Al enviar solicitudes de privacidad de datos individuales, puede enviar cualquier identificador (ID) [!DNL Audience Manager], tal como se describe en la sección **[Identificadores de Audience Manager](data-privacy-ids.md)**, junto con sus respectivos ID de área de nombres (ID de fuentes de datos).

El [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es) admite dos tipos de solicitudes: solicitudes de acceso a datos y eliminación de datos.

## Solicitudes de acceso a datos {#access-data}

Puede enviar solicitudes de acceso a datos individuales a través de la [interfaz de usuario del Privacy Service](https://privacyui.cloud.adobe.io) (documentación [aquí](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=es) o llamando a la API del Privacy Service (documentación [aquí](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=es) y [!DNL API] hacen referencia a [aquí](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

La [interfaz de usuario del Privacy Service](https://privacyui.cloud.adobe.io/) permite crear nuevas solicitudes de trabajo mediante el uso del [!UICONTROL Request Builder] o cargando un archivo [!DNL JSON].

Para ver la apariencia de un archivo [!DNL JSON]válido, puede [ descargar una muestra de JSON](../data-security-and-privacy/assets/access_request.json).

Entendemos su compromiso de cumplir con sus solicitudes de privacidad de datos dentro del período de tiempo establecido por la legislación.

## Solicitudes de eliminación de datos {#delete-data}

Puede enviar solicitudes de eliminación de datos a través de la [interfaz de usuario del Privacy Service](https://privacyui.cloud.adobe.io) (documentación [aquí](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=es) o llamando a la API del Privacy Service (documentación [aquí](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=es) y [!DNL API] hacen referencia a [aquí](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

La [interfaz de usuario del Privacy Service](https://privacyui.cloud.adobe.io/) permite crear nuevas solicitudes de trabajo mediante el uso del [!UICONTROL Request Builder] o cargando un archivo [!DNL JSON].

Para ver la apariencia de un archivo [!DNL JSON]válido, puede [ descargar una muestra de JSON](../data-security-and-privacy/assets/access_request.json).

Adobe entiende su compromiso de cumplir sus solicitudes de privacidad de datos en un plazo de 30 días. Por ese motivo, [!DNL Adobe] se compromete a procesar su solicitud de eliminación de datos lo antes posible.

En respuesta a sus solicitudes de eliminación de datos de consumo, [!DNL Audience Manager] elimina los rasgos y segmentos asociados con el identificador [!DNL Audience Manager] incluido en la solicitud. Además, se eliminarán los identificadores respectivos de [!DNL Audience Manager] para el individuo exclusión de una recopilación de datos adicional por [!DNL Audience Manager] y las asignaciones de ID correspondientes.

Cuando envía ID declarados, como ID de [!DNL CRM] en varios dispositivos o ID de [!DNL cookie], en las solicitudes de privacidad de datos, [!DNL Audience Manager] realizará la eliminación necesaria en todos los dispositivos vinculados (hasta 100 dispositivos por ID declarado).

[!DNL Audience Manager] intentará notificar a los socios de activación sobre las solicitudes de eliminación enviándoles información sin segmentar para los sujetos de datos que soliciten la eliminación de ciertos datos. Sin embargo, algunos socios de activación:

1. No se pueden admitir las solicitudes de eliminación de la segmentación de [!DNL Audience Manager] y/o
2. No pueden recibir actualizaciones de [!DNL Audience Manager] con una frecuencia inferior a 30 días. En estos casos, los clientes de [!DNL Audience Manager] no pueden enviar solicitudes de eliminación a socios de activación de forma automatizada a través de [!DNL Audience Manager].

En estos casos, no puede enviar solicitudes de eliminación a socios de activación de forma automatizada a través de [!DNL Audience Manager].

Consulte nuestra [documentación de la lista de destinos basados en dispositivos](assets/AAM-Partners-October2019.xlsx) para ver qué socios de activación de [!DNL Audience Manager] admiten la eliminación de la segmentación.

## Solicitudes de exclusión {#opt-out-requests}

[!DNL Audience Manager] admite los estándares de toda la industria con respecto a la administración de la exclusión. Continúe leyendo para obtener información completa sobre los tipos de exclusión admitidos por [!DNL Audience Manager].

Mientras que las solicitudes de acceso y eliminación de datos se administran a través del [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es), las solicitudes de exclusión se admiten actualmente a través de [!DNL DCS API]. Siga leyendo para saber la apariencia que deben tener las llamadas de exclusión [!DNL API].

### Solicitudes globales de exclusión

La exclusión global representa una exclusión entre [!DNL Audience Manager] y otras [!DNL Adobe Experience Cloud] soluciones para todas las marcas. La siguiente tabla incluye los métodos utilizados para la exclusión global:

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
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://experienceleague.adobe.com/docs/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Dispositivos Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://experienceleague.adobe.com/docs/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> Dispositivos iOS </a> </li> 
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

La exclusión a nivel de socio le permite excluir a los usuarios de la recopilación de datos por socios específicos de [!DNL Audience Manager]. Puede enviar solicitudes de exclusión a nivel de socio para ID entre dispositivos, incluidos [!DNL CRM] ID y direcciones de correo electrónico con hash.

Después de una exclusión a nivel de socio con una llamada de ID declarada:

* El [ID de CRM](../../reference/ids-in-aam.md) se excluye de la recopilación de datos;
* El último ID de dispositivo ([ID de usuario único de Audience Manager](../../reference/ids-in-aam.md)) vinculado al [ID de CRM](../../reference/ids-in-aam.md) se excluye de la recopilación de datos.
* [!DNL Audience Manager] dejará de recopilar, segmentar o realizar activaciones de datos para el identificador de [!DNL CRM] y el último identificador de dispositivo vinculado al identificador de [!DNL CRM];
* [!DNL Audience Manager] elimina de la segmentación el ID de [!DNL CRM] excluido y el último ID de dispositivo de todos los segmentos;
* [!UICONTROL Destination] socios reciben la solicitud de eliminación de la segmentación para el ID de [!DNL CRM] y el último ID de dispositivo. La eliminación de la segmentación sirve tanto para destinos de lote como [en tiempo real](data-privacy-requests.md#aam-partners-with-unsegmentation).
* No se eliminan datos históricos.

Cuando [!DNL Audience Manager] recibe una solicitud de exclusión a nivel de socio, el [!DNL JSON] devuelto por el [!DNL DCS] contiene el [código de error 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), con el mensaje [!UICONTROL "Encountered opt out tag"], en lugar del ID de usuario [!DNL Audience Manager].

Puede realizar una solicitud de exclusión de ID declarada con los pares de clave-valor `d_cid` y `d_cid_ic`. Los parámetros heredados como `d_dpid` y `d_dpuuid` siguen funcionando, pero se consideran obsoletos. Consulte [CID reemplaza DPID y DPUUID](../../reference/cid.md). En los ejemplos, la *cursiva* indica un marcador de posición para una variable.

#### Exclusión con [!DNL CID] y [!DNL CID_IC]

Para obtener una descripción y sintaxis, consulte [variables de URL y Sintaxis para ID declarados](../../features/declared-ids.md#variables-and-syntax).

| Opción de exclusión mediante | Ejemplo de código |
|--- |--- |
| ID de proveedor de datos e ID de usuario. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Código de integración e ID de usuario. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Varios pares de clave-valor `d_cid` y `d_cid_ic`. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Opción de exclusión de nivel de socio con llamadas de ID de dispositivo

La exclusión a nivel de socio le permite excluir a los usuarios de la recopilación de datos por socios específicos de [!DNL Audience Manager]. Puede desactivar la recopilación de datos en un ID de dispositivo determinado para una marca haciendo las siguientes llamadas a la [API de DCS](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Opción de exclusión mediante | Ejemplo de código |
|--- |--- |
| Un [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un identificador de [!DNL Experience Cloud] (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Obtenga más información sobre `uuid`, `mid` y `imsOrgId` en el [Índice de ID de Audience Manager](/help/using/reference/ids-in-aam.md).

Después de una exclusión a nivel de socio con una llamada de ID de dispositivo:

* El ID del dispositivo se excluye de la recopilación de datos.
* [!DNL Audience Manager] cancelará toda la recopilación, segmentación o activación de datos para el socio para el ID del dispositivo.
* [!DNL Audience Manager] elimina de la segmentación el ID de dispositivo de todos los segmentos;
* Los socios de destino reciben la solicitud de eliminación de la segmentación para el ID del dispositivo. La eliminación de la segmentación sirve tanto para destinos de lote como [en tiempo real](data-privacy-requests.md#aam-partners-with-unsegmentation).
* No se eliminan datos históricos.

## [!DNL Audience Manager] Se Asocia Con Capacidades De Eliminación De La Segmentación {#aam-partners-with-unsegmentation}

Para ayudarle a automatizar sus solicitudes de privacidad de datos de consumo, [!DNL Audience Manager] intentará notificar a los socios de activación sobre las solicitudes de eliminación de los sujetos de datos enviándoles información de eliminación de la segmentación.

Sin embargo, algunos de los socios de activación:

1. No se pueden admitir solicitudes sin segmentar de [!DNL Audience Manager] y/o
2. No pueden recibir actualizaciones de [!DNL Audience Manager] con una frecuencia superior a una vez cada 30 días.

En estos casos, no puede enviar solicitudes de eliminación a socios de activación de forma automatizada a través de [!DNL Audience Manager].

Consulte la [lista de destinos basados en dispositivos](/help/using/features/destinations/device-based-destinations-list.md) para ver qué socios de activación de [!DNL Audience Manager] admiten la eliminación de la segmentación.

## Solicitudes de corrección de datos {#correction}

Dado que [!DNL Audience Manager] no es el origen de los datos, existe un rol limitado para la corrección de datos en [!DNL Audience Manager]. La corrección puede significar que el consumidor ha solicitado que se le descalifique de un(a) [!UICONTROL trait]/[!UICONTROL segment] incorrecto(a) o que se le califique para el(la) [!UICONTROL trait]/[!UICONTROL segment] deseado(a).

[!DNL Audience Manager] clientes pueden elegir capturar las señales, rasgos o segmentos relevantes con perfiles de usuarios y enviar esta información a través de [ingesta de datos sin conexión](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) a [!DNL Audience Manager]. Tenga en cuenta que el usuario seguirá cumpliendo los requisitos para el(la) [!UICONTROL trait] y [!UICONTROL segments] originales si repite su comportamiento.
