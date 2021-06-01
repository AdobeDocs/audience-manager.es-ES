---
description: En este documento se explica la gestión del consentimiento en Audience Manager.
seo-description: En este documento se explica la gestión del consentimiento en Audience Manager.
seo-title: Gestión del consentimiento
solution: Audience Manager
keywords: Interfaz de usuario del RGPD, API del RGPD, CCPA, privacidad, consentimiento
title: Gestión del consentimiento
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Administración de datos y privacidad
exl-id: 9e545e8d-dbe4-4df9-8801-af3c2c73e406
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 98%

---

# Gestión del consentimiento

## Información general {#overview}

En las instancias en las que es necesario un consentimiento para determinadas actividades de marketing, los clientes de Audience Manager deben determinar el ámbito y, en su caso, actualizar consentimientos específicos para poder seguir utilizando datos.

Audience Manager le ofrece sus herramientas para facilitar la obtención de los consentimientos necesarios por parte de los usuarios, de modo que pueda ofrecerles experiencias personalizadas en todos los canales.

>[!IMPORTANT]
>
> Este documento no contiene un asesoramiento legal ni está pensado para sustituirlo.
>
> Adobe, como responsable del procesamiento de sus datos, no puede proporcionar asesoramiento legal sobre el proceso de recabar el consentimiento. Considere también la opción de trabajar con un gestor de consentimiento, como [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) o [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), y con el departamento legal de su compañía para asesorarse sobre el consentimiento y las prácticas necesarias al configurar su implementación de inclusión.

## Servicio de inclusión de Experience Cloud

El [servicio de inclusión de Experience Cloud](https://docs.adobe.com/content/help/es-ES/id-service/using/implementation/opt-in-service/optin-overview.html) le permite configurar protocolos para que el visitante de su sitio decida si permite que se establezca una cookie en su dispositivo o navegador.

Esta es una extensión de [!DNL Experience Cloud ID (ECID) Service], diseñada para que usted pueda controlar si las soluciones de Experience Cloud pueden crear cookies en las páginas web de los visitantes antes del consentimiento del usuario, y cuáles pueden hacerlo.

El [servicio de inclusión de Experience Cloud](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) también le permite definir protocolos para integrarlos con su Plataforma de gestión de consentimiento (CMP) y con los demás sistemas, como parte de su diseño general.

## Gestión de la inclusión / Obtención de consentimiento

Los clientes de Audience Manager pueden almacenar el consentimiento del usuario en varios casos de uso, como publicidad o personalización, como rasgos de Audience Manager. Los segmentos que genere con estos rasgos solamente incluirán a los usuarios que den el correspondiente consentimiento a cada uno de esos casos de uso. Tenga en cuenta que este método no impide la recopilación de datos, sino que solo afecta al uso de los datos cuando se envían segmentos para ser activados. Cuando los usuarios retiran su consentimiento, puede eliminar estos rasgos del perfil del usuario mediante el [proceso por lotes de entrada](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) o el proceso de exclusión de Audience Manager, como se detalla a continuación.

## Gestión de la exclusión / Retirada del consentimiento

En Adobe Experience Cloud, la exclusión se puede administrar en la página [Sus opciones de privacidad](https://www.adobe.com/es/privacy/opt-out.html#customeruse). Las funciones de un clic permiten que sus usuarios finales controlen y excluyan la recopilación de datos mediante las soluciones de publicidad de Adobe Experience Cloud (entre ellas, Audience Manager). Para saber más, consulte la [sección de cliente comercial](https://www.adobe.com/privacy/opt-out.html#customeruse) de la página Opciones de privacidad. Para exploradores que no admiten cookies de terceros, consulte [Segmentación de ID declarados](../../features/declared-ids.md#declared-id-targeting). En el caso de los dispositivos móviles, recupere los identificadores relevantes de Audience Manager y llame a las API de exclusión de Audience Manager, tal y como se indica en los [ejemplos de exclusión de ID declarados](../../features/declared-ids.md#opt-out-examples). A continuación, puede interrumpir la recopilación de datos de esos usuarios con las API de exclusión del SDK móvil; consulte [dispositivos Android](https://docs.adobe.com/content/help/es-ES/mobile-services/android/gdpr-privacy-android/privacy.html) y [dispositivos iOS](https://docs.adobe.com/content/help/es-ES/mobile-services/ios/privacy-gdpr-ios/privacy.html). Puede encontrar más detalles sobre exclusión en la [Documentación de solicitudes de privacidad de datos](../../overview/data-security-and-privacy/data-privacy-requests.md).

## Gestión del consentimiento para socios de segundo nivel

Los socios de segundo nivel también suelen ser responsables del tratamiento de datos y propietarios del proceso de obtención del consentimiento solicitado al sujeto de los datos, a fin de compartirlos con sus socios de datos de segundo nivel. Como cliente de Audience Manager, es su responsabilidad determinar si el socio de segundo nivel ha obtenido el consentimiento necesario para el caso de uso que le concierne a usted. Más arriba se encuentran los detalles sobre la obtención del consentimiento.

## Gestión del consentimiento para los socios de tercera entidad de Audience Marketplace

Los socios de tercera entidad de Audience Marketplace también son responsables del tratamiento de datos y propietarios del proceso de obtener el consentimiento y administrar las solicitudes de acceso, eliminación o corrección. Adobe solicita activamente que los socios de tercera entidad de Audience Marketplace actualicen su información de perfil de empresa en [Adobe Audience Finder](https://www.adobe-audience-finder.com/) con información adicional sobre la recopilación de datos de usuarios. La información se obtendrá de los socios de tercera entidad de Audience Marketplace y se actualizará periódicamente. Sin embargo, cada cliente de Audience Manager debe determinar que el socio de tercera entidad de Audience Marketplace haya obtenido el consentimiento necesario para el caso de uso de cada cliente. Adobe no realiza ninguna declaración sobre el alcance o la validez del consentimiento obtenido o notificado por un socio de tercera entidad de Audience Marketplace en un determinado caso de uso.
