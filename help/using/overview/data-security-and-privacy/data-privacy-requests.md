---
description: Este documento cubre los aspectos técnicos relacionados con la conformidad de las regulaciones de privacidad de datos para el Audience Manager.
seo-description: Este documento cubre los aspectos técnicos relacionados con la conformidad de las regulaciones de privacidad de datos para el Audience Manager.
seo-title: Solicitudes de privacidad de datos
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Solicitudes de privacidad de datos
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1487'
ht-degree: 1%

---


# Solicitudes de privacidad de datos {#data-privacy-requests}

## Información general {#overview}

Este documento proporciona información general sobre la administración de la privacidad de datos individuales y las solicitudes de exclusión a las que puede enviar [!DNL Audience Manager] a través de la interfaz de usuario [del](https://privacyui.cloud.adobe.io/) Privacy Service y el **[!DNL Privacy Service API]**.

Estas herramientas le permiten enviar solicitudes de privacidad de datos del consumidor realizadas en [!DNL GDPR] y [!DNL CCPA].

Antes de leer este artículo, recomendamos ir a través del Glosario [del](../data-security-and-privacy/aam-gdpr-glossary.md) GDPR y del Glosario [CCPA](aam-ccpa-glossary.md), para comprender mejor la terminología utilizada aquí.

Puede enviar solicitudes individuales para acceder a los datos de consumo y eliminarlos de [!DNL Audience Manager]dos maneras:

* A través de la interfaz de usuario del [Privacy Service](https://privacyui.cloud.adobe.io/). Consulte la documentación [aquí](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* A través del **[!DNL Privacy Service API]**. Consulte la documentación [aquí](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) y la [!DNL API] referencia [aquí](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Al enviar solicitudes de privacidad de datos individuales, puede enviar cualquier identificador de Audience Manager (ID), tal como se describe en la sección Identificadores **[de](data-privacy-ids.md)**Audience Manager, junto con sus respectivos ID de Área de nombres (ID de fuentes de datos).

El [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) admite dos tipos de solicitudes: solicitudes de acceso a datos y eliminación de datos.

## Solicitudes de acceso a datos {#access-data}

Puede enviar solicitudes de acceso a datos individuales a través de la interfaz de usuario [del](https://privacyui.cloud.adobe.io/) Privacy Service ( [aquí](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)encontrará la documentación) o llamando a la [!DNL Privacy Service API] (la documentación [aquí](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) y la [!DNL API] referencia [aquí](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

La interfaz de usuario [del](https://privacyui.cloud.adobe.io/) Privacy Service le permite crear nuevas solicitudes de trabajo mediante el uso [!UICONTROL Request Builder] o cargando un [!DNL JSON] archivo.

Para ver el aspecto de un [!DNL JSON] archivo válido, puede [descargar un JSON](../data-security-and-privacy/assets/access_request.json)de muestra.

Comprendemos su compromiso de cumplir con sus solicitudes de privacidad de datos dentro del período de tiempo establecido por la legislación.

## Solicitudes de eliminación de datos{#delete-data}

Puede enviar solicitudes de eliminación de datos a través de la interfaz de usuario [del](https://privacyui.cloud.adobe.io/) Privacy Service (documentación [aquí](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) o llamando a la [!DNL Privacy Service API] (documentación [aquí](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) y referencia de API [aquí](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

La interfaz de usuario [del](https://privacyui.cloud.adobe.io/) Privacy Service le permite crear nuevas solicitudes de trabajo mediante el uso [!UICONTROL Request Builder] o cargando un [!DNL JSON] archivo.

Para ver el aspecto de un [!DNL JSON] archivo válido, puede [descargar un JSON](../data-security-and-privacy/assets/access_request.json)de muestra.

Adobe comprende su compromiso de cumplir sus solicitudes de privacidad de datos en un plazo de 30 días. Por este motivo, [!DNL Adobe] se compromete a procesar su solicitud de eliminación de datos lo antes posible.

En respuesta a las solicitudes de eliminación de datos de consumo, [!DNL Audience Manager] elimina las características y los segmentos asociados con el [!DNL Audience Manager] identificador incluido en la solicitud. Además, se eliminarán los [!DNL Audience Manager] identificadores respectivos para el individuo exclusión de una recopilación de datos posterior por [!DNL Audience Manager] y las asignaciones de ID correspondientes.

Al enviar ID declarados, como [!DNL CRM] ID de dispositivos cruzados o ID de cookies, en las solicitudes de privacidad de datos, [!DNL Audience Manager] se realizará la eliminación necesaria en todos los dispositivos vinculados (hasta 100 dispositivos por ID declarado).

[!DNL Audience Manager] intentará notificar a los socios de activación acerca de las solicitudes de eliminación enviándoles información sin segmentar para los sujetos de datos que soliciten la eliminación de ciertos datos. Sin embargo, algunos socios de activación:

1. No se pueden admitir solicitudes de dessegmentación (o eliminación de segmentos) de [!DNL Audience Manager] y/o
2. No pueden recibir actualizaciones de [!DNL Audience Manager] con una frecuencia inferior a 30 días. En esos casos, [!DNL Audience Manager] los clientes no pueden enviar solicitudes de eliminación a los socios de activación de forma automatizada a través de [!DNL Audience Manager].

En estos casos, no puede enviar solicitudes de eliminación a socios de activación de forma automatizada [!DNL Audience Manager].

Descargue nuestra hoja [de Excel de](assets/AAM-Partners-October2019.xlsx) socio para ver qué socios de [!DNL Audience Manager] activación admiten el dessegmento.

## Solicitudes de exclusión {#opt-out-requests}

[!DNL Audience Manager] apoya las normas de toda la industria en relación con la gestión de la exclusión. Continúe leyendo para obtener información completa sobre los tipos de exclusión admitidos por [!DNL Audience Manager].

Mientras que las solicitudes de acceso y eliminación de datos se gestionan a través del [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), las solicitudes de exclusión se admiten actualmente a través del [!DNL DCS API]. Siga leyendo para conocer el aspecto que deben tener las llamadas de exclusión [!DNL API] .

### Solicitudes globales de exclusión

La exclusión global representa una exclusión entre [!DNL Audience Manager] y otras [!DNL Adobe Experience Cloud] soluciones para todas las marcas. La siguiente tabla lista los métodos utilizados para la exclusión global:

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
   <td colname="col2"> <p>La página <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Sus opciones de privacidad </a> proporciona funciones de 1 clic que permiten a los usuarios finales controlar y excluir la recopilación de datos mediante las soluciones de publicidad de Adobe Experience Cloud (incluido el Audience Manager). Concretamente, consulte la sección <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> cliente comercial </a> de la página Opciones de privacidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Llamadas de API directas al Audience Manager </p> </td> 
   <td colname="col2"> <p>Los usuarios pueden desactivar la recopilación de datos de todas las marcas Audience Manager haciendo una llamada a la API de DCS a continuación e incluir el ID de usuario <a href="../../reference/ids-in-aam.md"> Audience Manager </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Como resultado, estableceremos <code>demdex=NOTARGET</code> y <code>dextp=NOTARGET</code> cookies para el ID de usuario del Audience Manager enviado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dispositivos móviles </p> </td> 
   <td colname="col2"> <p>Consulte la configuración de exclusión y privacidad para: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Dispositivos Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> Dispositivos iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Los usuarios finales también pueden exclusión la recopilación global de datos visitando los sitios web de nuestros socios de estándares del sector.

* [La Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Iniciativa de publicidad en red (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Siguiendo las solicitudes de exclusión descritas anteriormente:

* [!DNL Audience Manager] cesará toda recopilación, segmentación o activación de datos, siempre que el usuario no borre las cookies del explorador.
* Los datos históricos se eliminan del perfil del usuario pasados 120 días.

### Opción de exclusión de nivel de socio con llamadas de ID declaradas

La exclusión a nivel de socio le permite excluir a los usuarios de la recopilación de datos por parte de [!DNL Audience Manager] socios específicos. Puede enviar solicitudes de exclusión a nivel de socio para ID entre dispositivos, incluidos [!DNL CRM] ID y direcciones de correo electrónico con hash.

Después de una exclusión a nivel de socio con una llamada de ID declarada:

* El ID [de](../../reference/ids-in-aam.md) CRM se exclusión de la recopilación de datos;
* El último ID de dispositivo (ID[de usuario único de](../../reference/ids-in-aam.md)Audience Manager) vinculado al ID [de](../../reference/ids-in-aam.md) CRM se exclusión de la recopilación de datos.
* [!DNL Audience Manager] cesará toda recopilación, segmentación o activación de datos a partir de ahora para el [!DNL CRM] ID y el último ID del dispositivo vinculado al [!DNL CRM] ID;
* [!DNL Audience Manager] dessegmenta el ID de exclusión [!DNL CRM] y el último ID de dispositivo de todos los segmentos;
* Los socios de destino reciben la solicitud de dessegmentación para el ID y el último ID del [!DNL CRM] dispositivo. La dessegmentación funciona tanto para destinos de lote como en tiempo [real](data-privacy-requests.md#aam-partners-with-unsegmentation) .
* No se eliminan datos históricos.

Cuando [!DNL Audience Manager] recibe una solicitud de exclusión a nivel de socio, el [!DNL JSON] devuelto por el [!DNL DCS] contiene el código de [error 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), con el mensaje [!UICONTROL "Encountered opt out tag"], en lugar del ID de [!DNL Audience Manager] usuario.

Puede realizar una solicitud de exclusión de ID declarada con los pares `d_cid` y `d_cid_ic` clave-valor. Los parámetros heredados como `d_dpid` y `d_dpuuid` siguen funcionando, pero se consideran obsoletos. Consulte [CID sustituye DPID y DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

#### Opción de exclusión con CID y CID_IC

Para obtener una descripción y sintaxis, consulte Variables [URL y Sintaxis de ID declarados](../../features/declared-ids.md#variables-and-syntax).

| Opción de exclusión mediante | Ejemplo de código |
|--- |--- |
| ID de proveedor de datos e ID de usuario. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Código de integración e ID de usuario. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Varios pares `d_cid` y `d_cid_ic` clave-valor. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Opción de exclusión de nivel de socio con llamadas de ID de dispositivo

La exclusión a nivel de socio le permite excluir a los usuarios de la recopilación de datos por parte de [!DNL Audience Manager] socios específicos. Puede desactivar la recopilación de datos en un ID de dispositivo determinado para una marca haciendo las siguientes llamadas a la API [de](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)DCS:

| Opción de exclusión mediante | Ejemplo de código |
|--- |--- |
| An [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Obtenga más información sobre `uuid`el `mid` índice de ID en Audience Manager `imsOrgId` y [](/help/using/reference/ids-in-aam.md)en él.

Después de una exclusión a nivel de socio con una llamada de ID de dispositivo:

* El ID del dispositivo se exclusión de la recopilación de datos.
* [!DNL Audience Manager] cesará toda la recopilación, segmentación o activación de datos para el socio a partir del ID del dispositivo.
* [!DNL Audience Manager] dessegmenta el ID del dispositivo de todos los segmentos;
* Los socios de destino reciben la solicitud de dessegmentación para el ID del dispositivo. La dessegmentación funciona tanto para destinos de lote como en tiempo [real](data-privacy-requests.md#aam-partners-with-unsegmentation) .
* No se eliminan datos históricos.

## Socios Audience Manager con capacidades de dessegmentación {#aam-partners-with-unsegmentation}

A fin de ayudarle a automatizar sus solicitudes de privacidad de datos de consumo, [!DNL Audience Manager] intentará notificar a los socios de activación acerca de las solicitudes de eliminación de los sujetos de datos enviándoles información sin segmentar (o eliminando segmentos).

Sin embargo, algunos de nuestros socios de activación:

1. No se pueden admitir solicitudes de dessegmentación de [!DNL Audience Manager] y/o
2. No pueden recibir actualizaciones desde [!DNL Audience Manager] más de una vez en 30 días.

En estos casos, no puede enviar solicitudes de eliminación a socios de activación de forma automatizada [!DNL Audience Manager].

Consulte la [lista de destinos](/help/using/features/destinations/device-based-destinations-list.md) basados en dispositivos para ver qué socios de [!DNL Audience Manager] activación admiten el unsegment.

## Solicitudes de corrección de datos {#correction}

Dado que no [!DNL Audience Manager] es la fuente de los datos, existe una función limitada para la corrección de datos en [!DNL Audience Manager]. La corrección podría significar que el consumidor ha solicitado que se le descalifique de un rasgo o segmento incorrecto o que se le califique para el rasgo o segmento deseado.

[!DNL Audience Manager] los clientes pueden elegir capturar las señales, características o segmentos relevantes en relación con los perfiles de los usuarios y enviar esta información a través de la ingesta [de datos](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) sin conexión a [!DNL Audience Manager]. Tenga en cuenta que el usuario seguirá calificándose para la característica original y los segmentos si repiten su comportamiento.
