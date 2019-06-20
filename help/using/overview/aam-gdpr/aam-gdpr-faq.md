---
description: Este material contiene algunas de las preguntas más comunes planteadas por nuestros clientes y socios relacionadas con el Reglamento general de protección de datos (RGPD) europea y cómo Adobe Audience Manager, como procesador de datos, trata los distintos requisitos del RGPD.
seo-description: Este material contiene algunas de las preguntas más comunes planteadas por nuestros clientes y socios relacionadas con el Reglamento general de protección de datos (RGPD) europea y cómo Adobe Audience Manager, como procesador de datos, trata los distintos requisitos del RGPD.
seo-title: Preguntas más frecuentes sobre el RGPD
solution: Audience Manager
title: Preguntas más frecuentes sobre el RGPD
uuid: e 52 cad 27-6 a 44-45 ee -8524-6080 adb 86 cc 8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Preguntas más frecuentes sobre el RGPD{#gdpr-faq}

Este material contiene algunas de las preguntas más comunes planteadas por nuestros clientes y socios relacionadas con el Reglamento general de protección de datos (RGPD) europea y cómo Adobe Audience Manager, como procesador de datos, trata los distintos requisitos del RGPD.

En este artículo analizamos las preguntas sobre la preparación del RGPD en Audience Manager. Make sure you also read the [Experience Cloud GDPR FAQ.](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-faq.md)

El RGPD entró en vigor el 25 de mayo de 2018 con objetivos primarios de proporcionar a las personas de la UE (temas de datos) un mayor control de sus datos personales a la vez que se simplifica el entorno regulatorio para las empresas internacionales mediante la mejor unificación de la regulación dentro de la UE. Como parte de la disposición del RGPD de Adobe, el equipo de Adobe Audience Manager cuenta con servicios y procesos mejorados según sea necesario para permitir el acceso y eliminar solicitudes de temas de datos, sus consumidores.

## GDPR Glossary {#gdpr-glossay}

Familiarícese con los términos clave utilizados con el RGPD. Hemos resaltado algunos de los términos más utilizados a continuación.

<br> 

**Controlador de datos:** El RGPD define &quot;Controller&quot; como &quot;the… legal person… which alone or together with others determina los propósitos y medios del procesamiento de datos personales. »» Los clientes de Audience Manager son controladores de datos. Los clientes controlan cómo se administran los datos en Audience Manager.

<br> 

**Procesador de datos:** El «Procesador» es «la persona legal… que procesa datos personales en nombre del controlador». En el contexto de Audience Manager (plataforma de administración de datos de Adobe o DMP), Adobe actúa como «procesador de datos» para cualquier dato personal que procese y almacena y services a través de DMP. Adobe solo procesa los datos personales de acuerdo con los permisos y las instrucciones del Controlador de datos (por ejemplo, tal como se establece en nuestro acuerdo con el cliente).

<br> 

**Asunto de los datos:** Persona a la que se relacionan los datos personales. En el contexto de Audience Manager, los temas de datos son clientes de Audience Manager o usuarios finales. Si Audience Manager recibe solicitudes directamente desde Temas de datos, estas solicitudes se reenvían a los respectivos clientes de Adobe.

<br> 

**Consentimiento:** El consentimiento significa &quot;cualquier indicación libre, específica, informada y sin ambigüedades de los deseos del sujeto de datos por los cuales, por medio de una declaración o de una acción afirmativa clara, significa que usted acepta el procesamiento de datos personales relacionados con usted o su&quot;. El consentimiento es responsabilidad del controlador de datos, no de Adobe a través de Audience Manager.

<br> 

**Acceso:** Los sujetos de datos tienen derecho a requerir al controlador de datos que confirme si el controlador procesa sus datos personales. Cuando el controlador de datos procesa los datos personales del sujeto de datos, debe proporcionar acceso a los datos personales y una copia de ellos. Los controladores de datos pueden solicitar a Adobe que ayuda en las solicitudes de acceso a los temas de datos.

<br> 

**Eliminar:** El RGPD describe la «derecha para ser olvidada» o «Derecha para retruncar». »» Los sujetos de datos tienen derecho a solicitar a los controladores de datos que borren sus datos personales. Los controladores de datos trabajan con sus procesadores, incluido Adobe, para admitir solicitudes de eliminación de temas de datos.

<br> 

**Corrección:** Los sujetos de datos tienen derecho a solicitar controladores de datos para corregir datos personales inexactos. Los controladores de datos trabajan con procesadores, incluida Adobe, para admitir solicitudes de corrección de temas de datos.

<br> 

**Identificadores de Audience Manager (ID):** Adobe Audience Manager almacena varios tipos de ID. [El RGPD de la página Audience Manager](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids) proporciona un resumen de estos ID, sus fuentes de datos correspondientes y descripciones breves. Cuando proporcione solicitudes a Adobe, haga referencia a estos ID para hacer las solicitudes de eliminación o acceso de los temas de datos.

<br> 

**Datos personales:** El RGPD expande la definición de los datos personales. En el RGPD, cualquier dato de Audience Manager puede clasificarse como datos personales según el caso de uso del cliente.

<br> 

**Datos prohibidos:** Audience Manager prohíbe que los clientes introduzcan información identificable directamente, como nombre y apellidos, ID de correo electrónico, ID de CRM, que se pueden utilizar para identificar directamente a un individuo. Las soluciones de Adobe Experience Cloud también prohíben información delicada. Consulte su contrato con Adobe para obtener más detalles sobre estos requisitos. Si es necesario ingestar estos tipos de puntos de datos en Audience Manager, póngase en contacto con su equipo de asesores de Adobe para obtener recomendaciones sobre cómo asignar hash estos ID antes de la ingesta.

<br> 

## Managing Individual GDPR Rights {#manage-ind-gdpr-rights}

**Administración de la inclusión/Obtención de consentimiento**

El RGPD no cambia cuando los controladores de datos necesitan consentimiento, cambia cómo obtener el consentimiento. En aquellas instancias en las que se necesita consentimiento para determinadas actividades de mercadotecnia, es necesario que el consentimiento del consumidor esté activo (por ejemplo, sin casillas premarcadas o silencio como assend), descompilado y las ofertas de servicios no deban condicionarse cuando el asunto de datos dé consentimiento. Es posible que haya instancias en las que ciertos consentimientos deban actualizarse para poder continuar usando datos en adelante.

Como procesador de datos, Adobe no puede proporcionar asesoría legal para obtener el consentimiento. Consulte con su equipo legal para obtener ayuda. We recommend that you work with a consent management solution providers such as [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) or [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/) to provide better recommendations on this. Adobe se ha asociado con varios proveedores para ayudarlo en esta integración a través de Adobe Launch.

Los clientes de Audience Manager podían almacenar el consentimiento del usuario para distintos casos de uso como la publicidad o personalización como características en Audience Manager. La creación de segmentos con estas características incluirá a los usuarios únicamente el consentimiento correspondiente para cada uno de estos casos de uso. Tenga en cuenta que, al utilizar este método, no se detiene la recopilación de datos, pero solo se afecta el uso de los datos al enviar segmentos para la activación. When users withdraw their consent, you can remove these traits from user profile using the Audience Manager [inbound batch process](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) or Audience Manager opt-out process as detailed below.

<br> 

**Administración de la exclusión/retirada del consentimiento**

Opt out can be managed for the Adobe Experience Cloud via the [Your Privacy Choices](https://www.adobe.com/privacy/opt-out.html#customeruse) page. Las funciones de 1 clic permiten a los usuarios finales controlar y excluir la recopilación de datos por las soluciones de publicidad de Adobe Experience Cloud (incluido Audience Manager). Specifically, see the [business customer section](https://www.adobe.com/privacy/opt-out.html#customeruse) of the Privacy Choices page. For Browsers that do not support third-party cookies, see [Declared ID targeting](../../features/declared-ids.md#declared-id-targeting). For mobile devices, please retrieve the relevant Audience Manager identifiers and call the Audience Manager opt-out APIs as mentioned in the [Declared ID Opt-Out examples](../../features/declared-ids.md#opt-out-examples). Following that, you can cease all data collection for those users with the opt out APIs from Mobile SDK - see [Android devices](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) and [iOS devices](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html). You can find additional details for opt-out in the [Audience Manager Opt-Out Documentation](../../overview/data-security-and-privacy/opt-out-management.md).

<br> 

**Envío de las solicitudes a Adobe Audience Manager Access y Eliminar solicitudes a Adobe**

You can submit Individual GDPR requests for Access and Delete either through the [GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md) or by calling the [GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-id-onboarding.md). Any [Audience Manager identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids), can be submitted in the requests along with their respective namespace IDs (data source IDs). Si envía identificadores de dispositivo cruzado como ID de CRM, Audience Manager realizará una acción en el perfil autenticado así como los ID de dispositivo vinculados a él. Se recomienda que los clientes utilicen el ID de usuario único de Audience Manager (AAM UUID) siempre que sea posible.

<br> 

**Administración de solicitudes de acceso**

Antes del 25 de mayo de 2018, Audience Manager permitía acceder a características, ID de cliente y segmentos asociados con un ID único en Audience Manager, manualmente. Desde el 25 de mayo de 2018, admitimos estas solicitudes de la manera descrita anteriormente con varias mejoras de productos y servicios. Además de características, ID de cliente, segmentos, una respuesta a la solicitud de acceso incluye un resumen del número total de características y segmentos, tipo de características, descripciones de características y segmentos junto con los nombres de fuentes de datos respectivos. La respuesta Acceso también incluye datos de terceros y de terceros accesibles al controlador de datos junto con los datos de origen. See more in [Data Access Requests](../../overview/aam-gdpr/aam-gdpr-details.md#access-data).

<br> 

**Administración de solicitudes de eliminación**

Antes del 25 de mayo de 2018, Audience Manager permitía eliminar manualmente características, ID de cliente y segmentos asociados con un ID único en Audience Manager. Cuando el RGPD entró en vigor, se admiten estas solicitudes de la manera descrita anteriormente con varias mejoras de productos y servicios. Además de la operación de eliminación, los identificadores correspondientes de Audience Manager para el asunto de los datos no se excluirán de la recopilación de datos y se eliminarán las asignaciones de ID correspondientes. See more in [Data Deletion Requests](../../overview/aam-gdpr/aam-gdpr-details.md#delete-data).

<br> 

**Proveedores de datos de terceros y administración de consentimiento**

Por lo general, los proveedores de datos de terceros también son controladores de datos y son propietarios del proceso para obtener cualquier consentimiento necesario de los datos de asunto para compartir datos con sus socios de datos de terceros. El cliente de Audience Manager tiene la responsabilidad de determinar si el proveedor de datos de terceros ha obtenido el consentimiento necesario para su caso de uso. Más información sobre cómo obtener el consentimiento se trata arriba.

<br> 

**Proveedores de datos de terceros y administración de consentimiento**

Los proveedores de datos también son controladores de datos y son propietarios de su proceso para obtener el consentimiento y administrar las solicitudes de acceso/eliminación/corrección. Adobe is proactively requesting that Data Providers update their company profile information within [Adobe Audience Finder](https://www.adobe-audience-finder.com/) with additional information on user data collection. La información se originará desde los proveedores de datos y el objetivo es que la herramienta se actualice antes del 2 de septiembre de 2018. Sin embargo, es responsabilidad de cada cliente de Audience Manager determinar que el proveedor de datos de terceros obtuvo el consentimiento necesario para el caso de uso de ese cliente. Adobe no realiza ninguna representación sobre el ámbito o validez del consentimiento obtenido o informado por un proveedor de datos de terceros para un caso de uso determinado.

<br> 

**Impacto de la eliminación de solicitudes para la activación de audiencias**

Audience Manager notifica a los socios de activación de las solicitudes de eliminación enviando información de dessegmentación para los temas de datos solicitando eliminar ciertos datos. Sin embargo, algunos socios de activación: 1) no admite solicitudes de segmentos (o eliminación de segmentos) de Adobe o 2) no pueden recibir actualizaciones de nosotros con una frecuencia de menos de 30 días. En estos casos, los clientes de Audience Manager no pueden enviar solicitudes de eliminación a socios de activación de forma automática a través de Audience Manager. The [GDPR Partner Unsegment documentation](../../overview/aam-gdpr/aam-gdpr-partners.md) provides information about unsegment capabilities and frequency of data exchange for all activation partners.

<br> 

**Retención de datos en Audience Manager**

La aplicación de normativas adecuadas, seguras y oportunas de retención de datos a sus datos es una parte importante para cumplir con el RGPD. Los clientes de Audience Manager tienen la capacidad de establecer períodos de retención personalizados en características y segmentos definiendo el TTL necesario (tiempo para activarse). We have reduced the retention period for [!UICONTROL Customer Data Feeds] ( [!UICONTROL CDF]) and [!UICONTROL Batch Outbound] orders to 8 days. También aplicaremos un período de retención para perfiles inactivos CRM y asignaciones de ID. Please find the more details about retention periods in our [Data Retention FAQ](../../faq/faq-privacy.md).

<br> 

**Administración de solicitudes de corrección de datos**

Dado que Audience Manager no es la fuente de datos, existe una función limitada para la corrección de datos en Audience Manager. La corrección podría significar que el sujeto de datos ha solicitado que se descalifique de un rasgo/segmento incorrecto o que esté cualificado para el atributo/segmento deseado. Audience Manager Los clientes pueden elegir capturar las señales, características o segmentos relevantes con perfiles de usuario y enviar esta información mediante la ingesta de datos sin conexión a Audience Manager. Tenga en cuenta que el usuario seguirá adquiriendo cualificación para el rasgo original y los segmentos si repite su comportamiento.

<br> 

**Transferencias de datos entre bordes**

El RGPD no prohíbe la transferencia de datos fuera de Europa. Requiere que las protecciones de privacidad de los datos europeos persisten siempre que se transfieren los datos. Visit the [Adobe Privacy Center](https://www.adobe.com/privacy/eudatatransfers.html) to learn more.

<br> 

## GDPR Readiness Guidance for Audience Manager Customers (Data Controllers) {#gdpr-readiness-guidance}

Recomendamos ser proactivo en las áreas de administración de datos y preparación para la organización. Esto garantiza que los datos de los clientes se organicen para procesos relacionados con el acceso o eliminación de solicitudes, que los equipos estén habilitados y capacitados para administrar estas solicitudes, y que sus consumidores (temas de datos) tengan una experiencia positiva y diferenciada con su marca.

Tenga en cuenta que, como procesador de datos, Adobe no puede proporcionar asesoría legal sobre los requisitos del RGPD ni el proceso para obtener el consentimiento de sus temas de datos. Consulte con su asesor legal para obtener instrucciones sobre el cumplimiento del RGPD de su organización.

<br> 

**Administración de datos: Comience a pensar cómo se administran los datos de su consumidor en la instancia de Audience Manager**

* Revise los distintos ID de cliente que utilizan los equipos de mercadotecnia para identificar usuarios en Audience Manager, junto con las fuentes de datos en las que se almacenan. Esto racionalizará el proceso de las solicitudes (como eliminar o acceder), ya que algunos tipos de datos serán hash por sus equipos antes de realizar la inserción en Audience Manager.
* Los ID de dispositivos móviles IDFA/GAID se utilizan para varios casos de uso en Audience Manager. Si utiliza el SDK de Adobe Mobile, asegúrese de enviar el ID de Experience Cloud (MID) junto con IDFA/GAID para asegurarse de que las respuestas del RGPD están completas.
* Una vez que la definición de los datos personales se torna más amplia, las direcciones IP pueden considerarse datos personales en su región. Interactivamente interactivamente con Adobe Consulting para proteger el último octeto.
* Determine un proceso y una normativa de autenticación y autenticación para confirmar la identidad de un asunto de datos cuando se realice una solicitud RGPD.
* Consider using [Data Export Controls](../../features/data-export-controls.md) to block audience activation to technologies that house personal data. Por ejemplo, los segmentos con datos de terceros no deberían sindicarse con proveedores de servicios de correo electrónico. Set a [!UICONTROL Data Export Control] to ensure that no one in your organization can accidentally activate this data.
* Begin utilizing [Role Based Access Controls](../../features/administration/administration-overview.md) to ensure the right teams have access to intended data.
* Consider appropriate [retention periods](../../faq/faq-privacy.md#data-retention-faq) for the data.
* Review identity linkage and privacy policies and legal requirements to see when and where it is appropriate to tie identity sets together; use appropriately via Audience Manager’s [Profile Merge Rules](../../features/profile-merge-rules/merge-rules-overview.md).

<br> 

**Preparación de la organización: Establecer un proceso empresarial**

* Identifique un proceso para recibir/responder solicitudes de asunto de datos. Considere crear una herramienta automatizada para enviar solicitudes a Audience Manager.
* Designe un punto de contacto de privacidad dentro del centro de excelencia DMP. Conecte el punto de contacto de privacidad de su organización con el equipo de uso de productos de Audience Manager para comprender cómo administrar los requisitos de ID de entrada.
* Realice una revisión de datos antes de compartirla con el asunto de datos. Documente los pasos que implemente para ayudarle a establecer la responsabilidad.

