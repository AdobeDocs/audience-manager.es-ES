---
description: Este documento explica cómo funciona la administración de consentimiento en el Administrador de Audiencias.
seo-description: Este documento explica cómo funciona la administración de consentimiento en el Administrador de Audiencias.
seo-title: Administración de consentimiento
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Administración de consentimiento
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Administración de consentimiento

## Información general {#overview}

En los casos en los que se necesita el consentimiento para determinadas actividades de marketing, los clientes del Administrador de Audiencias deben determinar el ámbito y, si es necesario actualizar ciertos consentimientos para poder seguir utilizando datos a partir de ahora.

El Administrador de Audiencias oferta sus herramientas para ayudar a respaldar su capacidad de obtener los consentimientos necesarios de los usuarios, de modo que pueda ofrecerles experiencias personalizadas en todos los canales.

>[!IMPORTANT]
>
> El contenido de este documento no es asesoramiento jurídico y no tiene por objeto sustituir al asesoramiento jurídico.
>
> Como su procesador de datos, Adobe no puede proporcionar asesoramiento legal para obtener el consentimiento. También puede considerar trabajar con un proveedor de soluciones de gestión de consentimiento, como [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) o [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), y consultar al departamento legal de su compañía para obtener asesoramiento sobre el consentimiento y las prácticas al configurar su implementación de inclusión.

## Servicio de inclusión de Experience Cloud

The [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) lets you set up protocols for the visitor to assist you in determining if you can set a cookie on the individual&#39;s device or browser when visiting your site.

This is an extension of the [!DNL Experience Cloud ID (ECID) Service], designed to let you control whether and which Experience Cloud solutions can place cookies on web pages for visitors prior to user consent.

El servicio [de inclusión de](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) Experience Cloud también le permite definir protocolos para integrarlos con la plataforma de gestión de consentimiento (CMP) y los sistemas existentes como parte de su diseño más amplio.

## Administración de la participación / Obtención de consentimiento

Los clientes de Administrador de Audiencias pueden almacenar el consentimiento del usuario para varios casos de uso, como publicidad o personalización, como características en el Administrador de Audiencias. Los segmentos que cree con estas características incluirán entonces sólo los usuarios que proporcionen el consentimiento correspondiente para cada uno de estos casos de uso. Tenga en cuenta que el uso de este método no detiene la recopilación de datos, sino que solo afecta al uso de los datos al enviar segmentos para su activación. Cuando los usuarios retiran su consentimiento, puede eliminar estas características del perfil del usuario mediante el proceso [por lotes de](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) entrada del Administrador de Audiencias o el proceso de exclusión del Administrador de Audiencias, como se detalla a continuación.

## Administración de la exclusión / Retirada del consentimiento

La exclusión se puede administrar para Adobe Experience Cloud a través de la página [Sus opciones](https://www.adobe.com/privacy/opt-out.html#customeruse) de privacidad. Las funciones de 1 clic permiten a los usuarios finales controlar y excluir la recopilación de datos mediante las soluciones de publicidad de Adobe Experience Cloud (incluido el Administrador de Audiencias). Concretamente, consulte la sección [del cliente](https://www.adobe.com/privacy/opt-out.html#customeruse) comercial de la página Opciones de privacidad. Para los exploradores que no admiten cookies de terceros, consulte [Establecimiento de objetivos](../../features/declared-ids.md#declared-id-targeting)de ID declarados. En el caso de los dispositivos móviles, recupere los identificadores relevantes del Administrador de Audiencias y llame a las API de exclusión del Administrador de Audiencias como se indica en los ejemplos [de exclusión de ID](../../features/declared-ids.md#opt-out-examples)declarados. A continuación, puede dejar de recopilar todos los datos de esos usuarios con las API de exclusión del SDK móvil; consulte Dispositivos [](https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html) Android y dispositivos [](https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html)iOS. Puede encontrar más detalles sobre la exclusión en la documentación [de solicitudes de privacidad de](../../overview/data-security-and-privacy/data-privacy-requests.md)datos.

## Administración del consentimiento para socios de segunda parte

Los Socios de Segunda Parte son generalmente también Controladores de Datos y son propietarios del proceso para obtener el consentimiento necesario del Sujeto de Datos para compartir datos con sus socios de datos de segunda Parte. Como cliente administrador de Audiencias, es su responsabilidad determinar si el segundo socio ha obtenido el consentimiento necesario para su caso de uso. Más detalles sobre la obtención del consentimiento se tratan más arriba.

## Administración del consentimiento para los socios de terceros de Audiencia Marketplace

Los socios de terceros de Audiencia Marketplace también son controladores de datos y son propietarios de su proceso para obtener el consentimiento y administrar las solicitudes de acceso, eliminación o corrección. Adobe solicita de forma proactiva que los socios terceros de Audiencia Marketplace actualicen su información de perfil de compañía en [Adobe Audiencia Finder](https://www.adobe-audience-finder.com/) con información adicional sobre la recopilación de datos de usuarios. La información se obtendrá de los socios terceros de Audiencia Marketplace y se actualizará periódicamente. Sin embargo, corresponde a cada cliente del administrador de Audiencias determinar que el socio tercero del mercado de Audiencia ha obtenido el consentimiento necesario para el caso de uso de ese cliente. Adobe no realiza ninguna declaración sobre el alcance o la validez del consentimiento obtenido o notificado por un socio de terceros de Audiencia Marketplace para un caso de uso determinado.
