---
description: Este material contiene algunas de las preguntas más comunes planteadas por nuestros clientes y socios en relación con el Reglamento General Europeo de Protección de Datos (RGPD), y cómo Adobe Audience Manager, como procesador de datos, aborda los distintos requisitos del RGPD.
seo-description: Este material contiene algunas de las preguntas más comunes planteadas por nuestros clientes y socios en relación con el Reglamento General Europeo de Protección de Datos (RGPD), y cómo Adobe Audience Manager, como procesador de datos, aborda los distintos requisitos del RGPD.
seo-title: Preguntas más frecuentes sobre el RGPD
solution: Audience Manager
title: Preguntas más frecuentes sobre el RGPD
uuid: e52cad27-6a44-45ee-8524-6080adb86cc8
translation-type: tm+mt
source-git-commit: 98914987331ce31bc8d3e67647d5b8273b287d4c

---


# Preguntas más frecuentes sobre el RGPD{#gdpr-faq}

Este material contiene algunas de las preguntas más comunes planteadas por nuestros clientes y socios en relación con el Reglamento General Europeo de Protección de Datos (RGPD), y cómo Adobe Audience Manager, como procesador de datos, aborda los distintos requisitos del RGPD.

En este artículo, tratamos las preguntas sobre la preparación para RGPD en Audience Manager. Asegúrese de leer también las preguntas más frecuentes sobre el RGPD de [Experience Cloud.](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-faq.md)

El RGPD entró en vigor el 25 de mayo de 2018 con el objetivo primordial de dar a las personas en la UE (sujetos de datos) un mayor control de sus datos personales y, al mismo tiempo, simplificar el marco regulador de las empresas internacionales unificando mejor la normativa dentro de la UE. Como parte de la preparación para el RGPD de Adobe, el equipo de Adobe Audience Manager ha mejorado los servicios y procesos según sea necesario para admitir el acceso y la eliminación de solicitudes de los sujetos de datos, sus consumidores.

## Glosario GDPR {#gdpr-glossay}

Familiarícese con los términos clave utilizados en relación con el RGPD. Hemos resaltado algunos de los términos más utilizados a continuación.

<br> 

**** Controlador de datos: El RGPD define "Contralor" como "la ... persona jurídica que, por sí sola o conjuntamente con otros, determina los fines y medios del tratamiento de datos personales". Los clientes de Audience Manager son controladores de datos. Los clientes controlan cómo se administran los datos en Audience Manager.

<br> 

**** Procesador de datos: El "procesador" es "la ... persona jurídica ... que procesa datos personales en nombre del controlador". En el contexto de Audience Manager (la plataforma de administración de datos de Adobe o DMP), Adobe actúa como "procesador de datos" para cualquier dato personal que procese y almacene y preste servicios mediante DMP. Adobe solo procesa los datos personales de acuerdo con el permiso y las instrucciones del controlador de datos (por ejemplo, según lo establecido en nuestro acuerdo con el cliente).

<br> 

**** Asunto de los datos: Persona a la que se refieren los datos personales. En el contexto de Audience Manager, los sujetos de datos son consumidores o usuarios finales de Audience Manager. Si Audience Manager recibe solicitudes directamente de los sujetos de datos, estas solicitudes se reenviarán a los clientes de Adobe correspondientes.

<br> 

**** Consentimiento: Consentimiento significa que "toda indicación libre, específica, informada e inequívoca de los deseos del interesado, mediante la cual, mediante una declaración o una acción afirmativa clara, se manifiesta de acuerdo con el tratamiento de los datos personales que le conciernan". El consentimiento es responsabilidad del controlador de datos, no de Adobe a través de Audience Manager.

<br> 

**** Acceso: Los sujetos de datos tienen derecho a solicitar al controlador de datos que confirme si el controlador procesa sus datos personales. Cuando el controlador de datos procesa los datos personales del interesado, debe proporcionar acceso a los datos personales y una copia de ellos. Los controladores de datos pueden solicitar a Adobe ayuda con las solicitudes de acceso de los sujetos de datos.

<br> 

**** Eliminar: El RGPD describe el "Derecho al olvido" o el "Derecho a la Eliminación". Los sujetos de datos tienen el derecho de exigir a los encargados de controlar los datos que borren sus datos personales. Los controladores de datos trabajan con sus procesadores, incluido Adobe, para admitir solicitudes de eliminación de sujetos de datos.

<br> 

**** Corrección: Los sujetos de datos tienen el derecho de exigir a los encargados de controlar los datos que corrijan datos personales inexactos. Los controladores de datos trabajan con procesadores, incluido Adobe, para admitir solicitudes de corrección de sujetos de datos.

<br> 

**** Identificadores (ID) de Audience Manager: Adobe Audience Manager almacena varios tipos de ID. La página [RGPD en Audience Manager](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids) proporciona un resumen de estos ID, sus fuentes de datos correspondientes y breves descripciones. Al proporcionar solicitudes a Adobe, haga referencia a estos ID para realizar solicitudes de eliminación o acceso a los temas de datos.

<br> 

**** Datos personales: El RGPD amplía la definición de datos personales. En RGPD, cualquier dato de Audience Manager puede clasificarse como datos personales según el caso de uso del cliente.

<br> 

**** Datos prohibidos: Audience Manager prohíbe a los clientes ingerir información de identificación directa, como el nombre y apellidos, el ID de correo electrónico o el ID de CRM, que se puede utilizar para identificar directamente a un individuo. Las soluciones de Adobe Experience Cloud también prohíben la información confidencial. Consulte su contrato con Adobe para obtener más información sobre estos requisitos. Si estos tipos de puntos de datos deben ingerirse en Audience Manager, consulte con su equipo de consultoría de Adobe para obtener recomendaciones sobre cómo hash estos ID antes de la ingestión.

<br> 

## Administración de derechos GDPR individuales {#manage-ind-gdpr-rights}

**Administración de la participación / Obtención de consentimiento**

El RGPD no cambia cuando los controladores de datos necesitan el consentimiento, sino que cambia la forma de obtener el consentimiento. En los casos en que se necesita el consentimiento para determinadas actividades de comercialización, el consentimiento del consumidor debe estar activo (por ejemplo, no hay casillas de verificación previas o silencio cuando se da el consentimiento), desagregado y las ofertas de servicios no pueden supeditarse al consentimiento del sujeto de datos. Puede incluso haber casos en los que es necesario actualizar ciertos consentimientos para poder seguir utilizando datos a partir de ahora.

Como su procesador de datos, Adobe no puede proporcionar asesoramiento legal para obtener el consentimiento. Consulte a su equipo legal para obtener ayuda. Le recomendamos que trabaje con proveedores de soluciones de administración de consentimiento como [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) o [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/) para ofrecer mejores recomendaciones sobre este tema. Adobe se ha asociado con varios de estos proveedores para ayudar con esta integración mediante Adobe Launch.

Los clientes de Audience Manager pueden almacenar el consentimiento del usuario para varios casos de uso, como la publicidad o la personalización, como características en Audience Manager. La creación de segmentos con estas características incluirá entonces sólo a los usuarios que proporcionen el consentimiento correspondiente para cada uno de estos casos de uso. Tenga en cuenta que el uso de este método no detiene la recopilación de datos, sino que solo afecta al uso de los datos al enviar segmentos para su activación. Cuando los usuarios retiran su consentimiento, puede eliminar estas características del perfil de usuario mediante el proceso [por lotes de](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) entrada de Audience Manager o el proceso de exclusión de Audience Manager como se detalla a continuación.

<br> 

**Administración de la exclusión/retirada del consentimiento**

La exclusión se puede administrar para Adobe Experience Cloud a través de la página [Sus opciones](https://www.adobe.com/privacy/opt-out.html#customeruse) de privacidad. Las funciones de 1 clic permiten a los usuarios finales controlar y excluir la recopilación de datos mediante las soluciones de publicidad de Adobe Experience Cloud (incluido Audience Manager). Concretamente, consulte la sección [del cliente](https://www.adobe.com/privacy/opt-out.html#customeruse) comercial de la página Opciones de privacidad. Para los exploradores que no admiten cookies de terceros, consulte [Establecimiento de objetivos](../../features/declared-ids.md#declared-id-targeting)de ID declarados. En el caso de los dispositivos móviles, recupere los identificadores de Audience Manager relevantes y llame a las API de exclusión de Audience Manager como se indica en los ejemplos [de exclusión de ID](../../features/declared-ids.md#opt-out-examples)declarados. A continuación, puede dejar de recopilar todos los datos de esos usuarios con las API de exclusión del SDK de Mobile (consulte Dispositivos [](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) Android y dispositivos [](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html)iOS). Puede encontrar más detalles sobre la exclusión en la documentación [de exclusión de](../../overview/data-security-and-privacy/opt-out-management.md)Audience Manager.

<br> 

**Envío de solicitudes de acceso y eliminación de GDPR de Audience Manager a Adobe**

Puede enviar solicitudes individuales de RGPD para acceder y eliminar a través de la interfaz de usuario [de los servicios al cliente de](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) RGPD o llamando a la API [de](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-id-onboarding.md)RGPD. Todos los identificadores [de](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)Audience Manager se pueden enviar en las solicitudes junto con sus respectivos ID de espacio de nombres (ID de fuentes de datos). Si envía identificadores entre dispositivos, como los de CRM, Audience Manager tomará medidas en el perfil autenticado, así como en los ID de dispositivo vinculados a él. Se recomienda que los clientes utilicen el ID de usuario único de Audience Manager (AAM UUID) siempre que sea posible.

<br> 

**Administración de solicitudes de acceso**

Antes del 25 de mayo de 2018, Audience Manager admitía el acceso manual a características, ID de cliente y segmentos asociados con un ID único en Audience Manager. A partir del 25 de mayo de 2018, apoyamos estas solicitudes de la manera descrita anteriormente con diversas mejoras en los productos y servicios. Además de características, ID de cliente, segmentos, una solicitud de respuesta a Access incluye un resumen del número total de características y segmentos, tipo de característica, descripciones de características y segmentos, junto con los respectivos nombres de fuentes de datos. La respuesta de Access también incluye datos de terceros y de terceros a los que el controlador de datos puede acceder junto con los datos de origen. Consulte más información en Solicitudes [de acceso a datos](../../overview/aam-gdpr/aam-gdpr-details.md#access-data).

<br> 

**Administración de solicitudes de eliminación**

Antes del 25 de mayo de 2018, Audience Manager admitía la eliminación manual de características, ID de cliente y segmentos asociados con un ID único en Audience Manager. Una vez que el RGPD entre en vigor, apoyamos estas solicitudes de la manera descrita anteriormente con diversas mejoras de productos y servicios. Además de la operación de eliminación, los identificadores respectivos de Audience Manager para el sujeto de datos se excluirán de la recopilación de datos y se eliminarán las asignaciones de ID correspondientes. Consulte más información en Solicitudes [de eliminación de datos](../../overview/aam-gdpr/aam-gdpr-details.md#delete-data).

<br> 

**Proveedores de datos de terceros y administración del consentimiento**

Por lo general, los proveedores de datos de segunda parte son también controladores de datos y son propietarios del proceso para obtener el consentimiento necesario del sujeto de datos para compartir datos con sus socios de datos de segunda parte. Es responsabilidad del cliente de Audience Manager determinar si el segundo proveedor de datos ha obtenido el consentimiento necesario para su caso de uso. Más detalles sobre la obtención del consentimiento se tratan más arriba.

<br> 

**Proveedores de datos de terceros y administración del consentimiento**

Los proveedores de datos también son controladores de datos y son propietarios de su proceso para obtener el consentimiento y administrar las solicitudes de acceso, eliminación o corrección. Adobe solicita de forma proactiva que los proveedores de datos actualicen la información de perfil de su empresa en [Adobe Audience Finder](https://www.adobe-audience-finder.com/) con información adicional sobre la recopilación de datos de los usuarios. La información se obtendrá de los proveedores de datos y el objetivo es actualizar la herramienta para el segundo trimestre de 2018. Sin embargo, corresponde a cada cliente de Audience Manager determinar que el proveedor de datos de terceros ha obtenido el consentimiento necesario para el caso de uso de ese cliente. Adobe no realiza ninguna representación sobre el alcance o la validez del consentimiento obtenido o notificado por un proveedor de datos de terceros para un caso de uso determinado.

<br> 

**Impacto de las solicitudes de eliminación para la activación de audiencias**

Audience Manager notifica a los socios de activación acerca de las solicitudes de eliminación enviándoles información de segmentos para los sujetos de datos que solicitan la eliminación de ciertos datos. Sin embargo, algunos socios de activación: 1) no puede admitir solicitudes de dessegmentación (o eliminación de segmentos) de Adobe y/o 2) no pueden recibir actualizaciones de nosotros con una frecuencia inferior a 30 días. En estos casos, los clientes de Audience Manager no pueden enviar solicitudes de eliminación a socios de activación de forma automática a través de Audience Manager. La documentación [de](../../overview/aam-gdpr/aam-gdpr-partners.md) Sindicatos del RGPD proporciona información sobre las capacidades sin segmentar y la frecuencia del intercambio de datos para todos los socios de activación.

<br> 

**Retención de datos en Audience Manager**

La aplicación de políticas de retención de datos apropiadas, seguras y oportunas a sus datos es una parte importante del cumplimiento del RGPD. Los clientes de Audience Manager pueden establecer períodos de retención personalizados en características y segmentos mediante la definición del TTL requerido (tiempo de vida). Hemos reducido el período de retención para [!UICONTROL Customer Data Feeds] ( [!UICONTROL CDF]) y los [!UICONTROL Batch Outbound] pedidos a 8 días. También se aplicará un período de retención para perfiles CRM inactivos y asignaciones de ID. Encontrará más detalles sobre los períodos de retención en nuestras Preguntas más frecuentes [sobre la retención](../../faq/faq-privacy.md)de datos.

<br> 

**Administración de solicitudes de corrección de datos**

Dado que Audience Manager no es la fuente de los datos, existe una función limitada para la corrección de datos en Audience Manager. La corrección podría significar que el sujeto de datos ha solicitado que se le descalifique de un rasgo o segmento incorrecto o que se le califique para el rasgo o segmento deseado. Audience Manager Los clientes pueden capturar las señales, características o segmentos relevantes con perfiles de usuario y enviar esta información a Audience Manager a través de la ingestión de datos sin conexión. Tenga en cuenta que el usuario seguirá calificándose para la característica original y los segmentos si repiten su comportamiento.

<br> 

**Transferencias de datos transfronterizas**

El RGPD no prohíbe la transferencia de datos fuera de Europa. Exige que la protección de la privacidad de los datos europeos persista dondequiera que se transfieran. Visite el [Adobe Privacy Center](https://www.adobe.com/privacy/eudatatransfers.html) para obtener más información.

<br> 

## Guía de preparación de GDPR para clientes de Audience Manager (controladores de datos) {#gdpr-readiness-guidance}

Recomendamos ser proactivos en las esferas de la gobernanza de los datos y la preparación de la organización. Esto garantiza que los datos del consumidor se organizarán para los procesos relacionados con las solicitudes de acceso o eliminación, que los equipos se habilitarán y habilitarán para administrar estas solicitudes y que los consumidores (sujetos de datos) tendrán una experiencia positiva y diferenciada con su marca.

Tenga en cuenta que, como su procesador de datos, Adobe no puede proporcionar asesoramiento legal sobre los requisitos del RGPD ni sobre el proceso para obtener el consentimiento de los sujetos de datos. Consulte con su asesor legal para obtener instrucciones sobre el cumplimiento del RGPD para su organización.

<br> 

**Administración de datos: Empiece a pensar en cómo se administran los datos de consumo en la instancia de Audience Manager**

* Revise los distintos ID de cliente que sus equipos de mercadotecnia utilizan para identificar usuarios en Audience Manager, junto con las fuentes de datos en las que se almacenan. Esto optimizará el proceso de solicitudes (como eliminar o acceder), ya que determinados tipos de datos serán hash por los equipos antes de su inserción en Audience Manager.
* Los ID de dispositivos móviles IDFA/GAID se utilizan en varios casos de uso en Audience Manager. Si utiliza el SDK de Adobe Mobile, asegúrese de enviar el ID de Experience Cloud (MID) junto con IDFA/GAID para asegurarse de que las respuestas del RGPD están completas.
* Con la definición de datos personales cada vez más amplia, las direcciones IP pueden considerarse datos personales en su región. Póngase en contacto de forma proactiva con el consultor de Adobe para ocultar el último octeto.
* Determinar una política y un proceso de validación/autenticación para confirmar la identidad de un sujeto de datos cuando realiza una solicitud de RGPD.
* Considere la posibilidad de utilizar controles [](../../features/data-export-controls.md) de exportación de datos para bloquear la activación de la audiencia en tecnologías que albergan datos personales. Por ejemplo, los segmentos con datos de terceros no deben estar sindicados a proveedores de servicios de correo electrónico. Configure un [!UICONTROL Data Export Control] para asegurarse de que nadie de su organización pueda activar accidentalmente estos datos.
* Empiece a utilizar los controles [de acceso basados en](../../features/administration/administration-overview.md) roles para garantizar que los equipos adecuados tengan acceso a los datos deseados.
* Considere períodos [de](../../faq/faq-privacy.md#data-retention-faq) retención adecuados para los datos.
* Revisar las políticas de vinculación de identidad y privacidad y los requisitos legales para ver cuándo y dónde es apropiado unir los conjuntos de identidades; se utiliza correctamente mediante las reglas [de combinación de](../../features/profile-merge-rules/merge-rules-overview.md)perfiles de Audience Manager.

<br> 

**Preparación de la organización: Establecimiento de un proceso comercial**

* Identifique un proceso para recibir/responder a las solicitudes del sujeto de datos. Considere la posibilidad de crear una herramienta automatizada para enviar solicitudes a Audience Manager.
* Designe un punto de contacto de privacidad dentro de su centro de excelencia de DMP. Conecte el punto de contacto de privacidad de su organización con el equipo de uso del producto de Audience Manager para comprender cómo puede administrar los requisitos de ID de entrada.
* Realice una revisión de los datos antes de compartirlos con el sujeto de datos. Documenta los pasos que ha puesto en marcha para ayudarle a establecer la responsabilidad.

