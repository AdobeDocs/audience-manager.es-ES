---
description: Este documento cubre los aspectos técnicos relacionados con la conformidad de las regulaciones de privacidad de datos para el Administrador de Audiencias.
seo-description: Este documento cubre los aspectos técnicos relacionados con la conformidad de las regulaciones de privacidad de datos para el Administrador de Audiencias.
seo-title: Solicitudes de privacidad de datos
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Solicitudes de privacidad de datos
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Solicitudes de privacidad de datos {#data-privacy-requests}

## Información general {#overview}

Este documento proporciona información general sobre la administración de la privacidad de datos individuales y las solicitudes de exclusión que puede enviar al Administrador de Audiencias a través de la interfaz de usuario [de](https://privacyui.cloud.adobe.io/) Privacy Service y de **[!DNL Privacy Service API]**.

Estas herramientas le permiten enviar solicitudes de privacidad de datos de consumo realizadas en GDPR y CCPA.

Antes de leer este artículo, recomendamos ir a través del Glosario [del](../data-security-and-privacy/aam-gdpr-glossary.md) GDPR y del Glosario [CCPA](aam-ccpa-glossary.md), para comprender mejor la terminología utilizada aquí.

Puede enviar solicitudes individuales para acceder a los datos de consumo y eliminarlos del Administrador de Audiencias de dos formas:

* A través de la interfaz de usuario [de](https://privacyui.cloud.adobe.io/)Privacy Service. Consulte la documentación [aquí](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* A través del **[!DNL Privacy Service API]**. Consulte la documentación [aquí](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) y la referencia de API [aquí](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Al enviar solicitudes de privacidad de datos individuales, puede enviar cualquier identificador (ID) del Administrador de Audiencias, tal como se describe en la sección Identificadores **[del Administrador de](data-privacy-ids.md)**Audiencias, junto con sus respectivos ID de Áreas de nombres (ID de fuentes de datos).

El servicio [de privacidad](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) admite dos tipos de solicitudes: solicitudes de acceso a datos y eliminación de datos.

## Solicitudes de acceso a datos {#access-data}

Puede enviar solicitudes de acceso a datos individuales a través de la interfaz de usuario [de](https://privacyui.cloud.adobe.io/) Privacy Service (documentación [aquí](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) o llamando a la [!DNL Privacy Service API] (documentación [aquí](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) y [!DNL API] referencia [aquí](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

La interfaz de usuario [de](https://privacyui.cloud.adobe.io/) Privacy Service permite crear nuevas solicitudes de trabajo mediante el uso del [!UICONTROL Request Builder] archivo o cargando un [!DNL JSON] archivo.

Para ver el aspecto de un [!DNL JSON] archivo válido, puede [descargar un JSON](../data-security-and-privacy/assets/access_request.json)de muestra.

Comprendemos su compromiso de cumplir con sus solicitudes de privacidad de datos dentro del período de tiempo establecido por la legislación.

## Solicitudes de eliminación de datos{#delete-data}

Puede enviar solicitudes de eliminación de datos a través de la interfaz de usuario [de](https://privacyui.cloud.adobe.io/) Privacy Service (documentación [aquí](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) o llamando a la [!DNL Privacy Service API] (documentación [aquí](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) y referencia de API [aquí](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

La interfaz de usuario [de](https://privacyui.cloud.adobe.io/) Privacy Service permite crear nuevas solicitudes de trabajo mediante el uso del [!UICONTROL Request Builder] archivo o cargando un [!DNL JSON] archivo.

Para ver el aspecto de un [!DNL JSON] archivo válido, puede [descargar un JSON](../data-security-and-privacy/assets/access_request.json)de muestra.

Adobe comprende su compromiso de cumplir sus solicitudes de privacidad de datos en un plazo de 30 días. Por este motivo, Adobe se compromete a procesar su solicitud de eliminación de datos lo antes posible.

En respuesta a las solicitudes de eliminación de datos de consumo, el Administrador de Audiencias elimina las características y los segmentos asociados con el identificador del Administrador de Audiencias incluido en la solicitud. Además, se eliminarán los identificadores respectivos del Administrador de Audiencias para el individuo exclusión de una recopilación de datos adicional por el Administrador de Audiencias y las asignaciones de ID correspondientes.

Cuando envía ID declarados, como [!DNL CRM] ID de varios dispositivos o ID de cookies, en las solicitudes de privacidad de datos, el Administrador de Audiencias realizará la eliminación necesaria en todos los dispositivos vinculados (hasta 100 dispositivos por ID declarado).

El Administrador de Audiencias intentará notificar a los socios de activación acerca de las solicitudes de eliminación enviándoles información sin segmentar para los sujetos de datos que soliciten la eliminación de ciertos datos. Sin embargo, algunos socios de activación:

1. No se pueden admitir las solicitudes de dessegmentación (o eliminación de segmentos) del Administrador de Audiencias y/o
2. No pueden recibir actualizaciones del Administrador de Audiencias con una frecuencia inferior a 30 días. En estos casos, los clientes del Administrador de Audiencias no pueden enviar solicitudes de eliminación a socios de activación de forma automatizada a través del Administrador de Audiencias.

En estos casos, no puede enviar solicitudes de eliminación a socios de activación de forma automatizada a través del Administrador de Audiencias.

Descargue nuestra hoja [de Excel de](assets/AAM-Partners-October2019.xlsx) socio para ver qué socios de activación del Administrador de Audiencias admiten el dessegmento.

## Solicitudes de exclusión {#opt-out-requests}

El Administrador de Audiencias admite los estándares de toda la industria con respecto a la administración de la exclusión. Continúe leyendo para obtener información completa sobre los tipos de exclusión admitidos por el Administrador de Audiencias.

Aunque las solicitudes de acceso y eliminación de datos se gestionan a través de [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), las solicitudes de exclusión se admiten actualmente a través de la API de DCS. Continúe leyendo para conocer el aspecto que deben tener las llamadas de API de exclusión.

### Solicitudes globales de exclusión

La exclusión global representa una exclusión entre el Administrador de Audiencias y otras soluciones de Adobe Experience Cloud para todas las marcas. La siguiente tabla lista los métodos utilizados para la exclusión global:

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
   <td colname="col2"> <p>La página <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Opciones de privacidad </a> proporciona funciones de 1 clic que permiten a los usuarios finales controlar y excluir la recopilación de datos mediante las soluciones de publicidad de Adobe Experience Cloud (incluido el Administrador de Audiencias). Concretamente, consulte la sección <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> cliente comercial </a> de la página Opciones de privacidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Llamadas de API directas al Administrador de Audiencias </p> </td> 
   <td colname="col2"> <p>Los usuarios pueden desactivar la recopilación de datos en todas las marcas del Administrador de Audiencias haciendo una llamada a la API de DCS a continuación e incluyendo el ID de usuario del Administrador de <a href="../../reference/ids-in-aam.md"> Audiencias </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Como resultado, estableceremos <code>demdex=NOTARGET</code> y <code>dextp=NOTARGET</code> cookies para el ID de usuario del administrador de Audiencias enviado. </p> </td> 
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

* El Administrador de Audiencias detendrá toda la recopilación, segmentación o activación de datos, siempre que el usuario no borre las cookies del explorador.
* Los datos históricos se eliminan del perfil del usuario pasados 120 días.

### Opción de exclusión de nivel de socio con llamadas de ID declaradas

La exclusión a nivel de socio le permite excluir a los usuarios de la recopilación de datos por parte de socios específicos del Administrador de Audiencias. Puede enviar solicitudes de exclusión a nivel de socio para ID entre dispositivos, incluidos los ID de CRM y las direcciones de correo electrónico con hash.

Después de una exclusión a nivel de socio con una llamada de ID declarada:

* El ID [de](../../reference/ids-in-aam.md) CRM se exclusión de la recopilación de datos;
* El último ID de dispositivo (ID[de usuario único del administrador de](../../reference/ids-in-aam.md)Audiencias) vinculado al ID [de](../../reference/ids-in-aam.md) CRM se exclusión de la recopilación de datos.
* El Administrador de Audiencias dejará de recopilar, segmentar o realizar activaciones de datos para el ID de CRM y el último ID de dispositivo vinculado al ID de CRM;
* El Administrador de Audiencias dessegmenta el ID de CRM optado y el último ID de dispositivo de todos los segmentos;
* Los socios de destino reciben la solicitud de dessegmentación para el ID de CRM y el último ID de dispositivo. La dessegmentación funciona tanto para destinos de lote como en tiempo [real](data-privacy-requests.md#aam-partners-with-unsegmentation) .
* No se eliminan datos históricos.

Cuando el Administrador de Audiencias recibe una solicitud de exclusión a nivel de socio, el JSON devuelto por el DCS contiene el código de [error 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), con el mensaje [!UICONTROL "Encountered opt out tag"], en lugar del ID de usuario del Administrador de Audiencias.

Puede realizar una solicitud de exclusión de ID declarada con los pares `d_cid` y `d_cid_ic` clave-valor. Los parámetros heredados como `d_dpid` y `d_dpuuid` siguen funcionando, pero se consideran obsoletos. Consulte [CID sustituye DPID y DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

#### Opción de exclusión con CID y CID_IC

Para obtener una descripción y sintaxis, consulte Variables [URL y Sintaxis de los ID](../../features/declared-ids.md#variables-and-syntax)declarados.

| Opción de exclusión mediante | Ejemplo de código |
|--- |--- |
| ID de proveedor de datos e ID de usuario. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Código de integración e ID de usuario. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Varios pares de clave-valor d_cid y d_cid_ic. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Opción de exclusión de nivel de socio con llamadas de ID de dispositivo

La exclusión a nivel de socio le permite excluir a los usuarios de la recopilación de datos por parte de socios específicos del Administrador de Audiencias. Puede desactivar la recopilación de datos en un ID de dispositivo determinado para una marca haciendo las siguientes llamadas a la API [de](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)DCS:

| Opción de exclusión mediante | Ejemplo de código |
|--- |--- |
| Un ID de usuario único (`uuid`) del Administrador de Audiencias. | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un ID de Experience Cloud (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Obtenga más información sobre `uuid`los ID `mid` y `imsOrgId` en el [Índice de ID del Administrador](/help/using/reference/ids-in-aam.md)de Audiencias.

Después de una exclusión a nivel de socio con una llamada de ID de dispositivo:

* El ID del dispositivo se exclusión de la recopilación de datos.
* El Administrador de Audiencias dejará de recopilar, segmentar o activación de datos para el socio a partir del ID del dispositivo.
* El Administrador de Audiencias dessegmenta el ID del dispositivo de todos los segmentos;
* Los socios de destino reciben la solicitud de dessegmentación para el ID del dispositivo. La dessegmentación funciona tanto para destinos de lote como en tiempo [real](data-privacy-requests.md#aam-partners-with-unsegmentation) .
* No se eliminan datos históricos.

## Audiencia Manager Se Asocia Con Las Capacidades De Dessegmentación {#aam-partners-with-unsegmentation}

A fin de ayudarle a automatizar sus solicitudes de privacidad de datos de consumo, el Administrador de Audiencias intentará notificar a los socios de activación acerca de las solicitudes de eliminación de los sujetos de datos enviándoles información de dessegmentación (o eliminación de segmentos).

Sin embargo, algunos de nuestros socios de activación:

1. No se pueden admitir solicitudes sin segmentar del Administrador de Audiencias y/o
2. No pueden recibir actualizaciones del Administrador de Audiencias con más frecuencia de una vez en 30 días.

En estos casos, no puede enviar solicitudes de eliminación a socios de activación de forma automatizada a través del Administrador de Audiencias.

Consulte la [lista de destinos](/help/using/features/destinations/device-based-destinations-list.md) basados en dispositivos para ver qué socios de activación del Administrador de Audiencias admiten el unsegment.

## Solicitudes de corrección de datos {#correction}

Dado que el Administrador de Audiencias no es la fuente de los datos, existe una función limitada para la corrección de datos en el Administrador de Audiencias. La corrección podría significar que el consumidor ha solicitado que se le descalifique de un rasgo o segmento incorrecto o que se le califique para el rasgo o segmento deseado.

Administrador de Audiencias Los clientes pueden elegir capturar las señales, características o segmentos relevantes con perfiles de usuarios y enviar esta información a través de la ingesta [de datos](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) sin conexión al Administrador de Audiencias. Tenga en cuenta que el usuario seguirá calificándose para la característica original y los segmentos si repiten su comportamiento.
