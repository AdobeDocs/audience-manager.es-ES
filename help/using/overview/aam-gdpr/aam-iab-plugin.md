---
description: Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la funcionalidad de inclusión y a través de la compatibilidad con Transparency y Consent Fremework de IAB (Transparency). En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.
seo-description: Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la funcionalidad de inclusión y a través de la compatibilidad con Transparency y Consent Fremework de IAB (Transparency). En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.
seo-title: Complemento de Audience Manager para IAB TCF
solution: Audience Manager
title: Complemento de Audience Manager para IAB TCF
translation-type: tm+mt
source-git-commit: c238a37e1a72edb0679f657d0178e04b8d848ec2

---


# Complemento de Audience Manager para IAB TCF {#aam-iab-plugin}

## Información general

Un aspecto importante de las obligaciones de privacidad que tiene con respecto a los usuarios es la adquisición y la transmisión de las elecciones del usuario sobre cómo se pueden utilizar sus datos personales (por ejemplo: “motivos”) y quién (por ejemplo: “empresas”).

Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de [la funcionalidad de inclusión](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) y a través [de la compatibilidad con Transparency y Consent Fremework de IAB (Transparency)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager. Audience Manager is registered in the IAB TCF with the vendor ID 565.

The Audience Manager Plug-in for IAB TCF utilizes the Opt-in functionality, which is, in turn, part of the Adobe Experience Cloud ID Service (ECID) library.[](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)[](https://marketing.adobe.com/resources/help/en_US/mcvid/)

## Scope and Limitations {#scope-and-limitations}

As a Publisher or Advertiser working with Audience Manager, you are able to convey user choices to Audience Manager as per IAB TCF. Esto le proporciona una manera fácil y coherente de comunicar las opciones de usuario a todos los socios con los que trabaja y Audience Manager puede ayudarle a respetar las opciones de privacidad de sus usuarios.

El soporte TCF de la IAB descrito en este artículo representa la primera fase del soporte planificado por Audience Manager para el marco de la IAB. Actualmente, Audience Manager no admite:

* Flujos de trabajo de dispositivos móviles;
* Gestión del consentimiento entre dispositivos;
* Adición de consentimiento a direcciones URL enviadas a destinos [](/help/using/features/destinations/create-url-destination.md)URL;
* Adición del consentimiento a los segmentos.

## Requisitos previos {#prerequisites}

Debe cumplir los siguientes requisitos previos para utilizar el TCF IAB con Audience Manager:

1. Debe utilizar la versión 4.1 o posterior del servicio Experience Cloud ID (ECID). [Descargue](https://github.com/Adobe-Marketing-Cloud/id-service/releases) nuestra última versión de ECID.
2. 
   1. Debe utilizar la biblioteca de integración de datos de Audience Manager (DIL) versión 9.0 o posterior, descargable desde [aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases). Obtenga información sobre [DIL en la documentación](/help/using/dil/dil-overview.md)de Audience Manager.
   2. Como alternativa, si utiliza el reenvío del lado del servidor (SSF) para importar datos en Audience Manager, debe actualizar a la versión más reciente de AppMeasurement. Descargue AppMeasurement con el Administrador [de códigos de](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)Analytics.
3. Debe utilizar una Plataforma de Gestión de Consentimiento (CMP), ya sea comercial o propia, que admita la IAB y esté registrada en la IAB TCF. Véase la lista de [las CP/RP registradas en el marco](https://advertisingconsent.eu/cmp-list/)de la IAB.

## Recomendaciones y cómo implementar {#recommendations}

Para habilitar la compatibilidad con TCF de IAB en Audience Manager, lea nuestra documentación sobre [cómo configurar IAB con inclusión](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

Para ello, es más fácil utilizar [Adobe Launch](https://docs.adobelaunch.com/) para instrumentar la inclusión de ECID en sus propiedades. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Flujo de trabajo de opciones de usuario al utilizar el marco de trabajo IAB {#user-choice-workflow}

Al visitar una propiedad web, los usuarios pueden proporcionar sus opciones con respecto a cómo el editor y los proveedores externos con los que trabaja el editor utilizarán sus datos. Los usuarios proporcionan sus opciones en forma de propósitos ** estándar y permisos a proveedores *de* terceros registrados en la lista global de proveedores. La siguiente imagen representa un ejemplo de un cuadro de diálogo CMP, mostrado a un visitante nuevo de un sitio web. Tenga en cuenta que este cuadro de diálogo puede tener un aspecto muy diferente, según la implementación del cliente.

![Cuadro de diálogo CMP](/help/using/overview/aam-gdpr/assets/cmp.png)

Los objetivos estándar del marco de la IAB son:

* Almacenamiento de información y acceso
* Personalización
* Selección, envío e informes de publicidad
* Content selection, delivery, and reporting
* vídeo 

Consulte la página [de especificaciones del marco](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) IAB para obtener una descripción de los cinco objetivos estándar.

Users may grant their consent for a combination of standard purposes and vendors. Por ejemplo, los usuarios podrían conceder su consentimiento para almacenamiento, personalización y medición y conceder su consentimiento a todos los proveedores externos que muestre el CMP. Or, in another example, they could grant their consent for all five standard purposes but only grant consent to a few of the vendors displayed by the CMP.

Once the user selects their privacy choices, the user choice(s) are recorded in the IAB TCF consent string. The IAB TCF consent string stores the combination of approved purposes and vendors, along with other metadata information (see the IAB page for more information). [](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) Every vendor registered in the IAB TCF evaluates the IAB TCF consent string and makes decisions based on the users' privacy choices. Keep in mind that the users' privacy choices are valid across all approved vendors.

## Standard purposes needed by Audience Manager {#aam-standard-purposes}

Audience Manager evaluates the users' choices stored in the IAB TFC consent string for:

* Information storage and access (purpose ID 1 in the global vendor list)[](https://vendorlist.consensu.org/vendorlist.json)
* Personalization (purpose ID 2)
* Measurement (purpose ID 5)
* Audience Manager vendor consent to store, process, or activate on data for a publisher.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Manager behavior depends on whether the user grants consent {#aam-behavior-consent}

Audience Manager funciona de forma diferente dependiendo de si Audience Manager detecta en la cadena de consentimiento TCF de IAB que el usuario ha proporcionado su consentimiento para los tres fines (almacenamiento, personalización, medición) o no.

| When your user provides consent, Audience Manager:** | Cuando el usuario *rechaza* el consentimiento, Audience Manager: |
|---|---|
| <ul><li>Realiza todos los casos de uso de Audience Manager que ha solicitado.</li><li>Transmite el consentimiento a terceros en sincronizaciones de ID (pasando gdpr = 1 y la cadena de consentimiento como gdpr_permission en llamadas de sincronización de ID).</li><li>Evalúa y respeta el consentimiento pasado desde los píxeles del servidor de publicidad.</li><li>Honra las sincronizaciones de ID iniciadas por el socio.</li></ul> | <ul><li>No almacena ningún dato de usuario nuevo en su instancia. Esto incluye ID de socio, señales, características o datos de píxeles.</li><li>No inicia sincronizaciones de ID de terceros.</li><li>No respeta las sincronizaciones de ID iniciadas por el socio.</li></ul> |



## Caso de uso del editor {#publisher-use-case}

Al implementar el TCF de IAB, no es necesario mantener el código personalizado para la administración de consentimiento en las propiedades web a través de un mecanismo diferente con Adobe u otros proveedores externos. El caso de uso se describe en la imagen y en los pasos a continuación. Empiece desde la izquierda de la imagen:

1. Un usuario visita una de sus propiedades web. Siempre que utilice las versiones más recientes de las bibliotecas ECID y DIL (consulte [Requisitos previos](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)), se activa el flujo de inclusión.
2. Audience Manager comprueba si se aplica el flujo IAB (`isIabContext=true`). Consulte [Recomendaciones y cómo implementarlas](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations).
3. Audience Manager comprueba si el RGPD se aplica (`gdpr = 1`) y si hay un CMP, registrado con IAB, en la propiedad web. Por ejemplo, esto se aplicaría a los usuarios que visiten el área de la Unión Europea. Tenga en cuenta que es su responsabilidad como editor establecer el indicador del RGPD.
4. Si se aplica GDPR, Audience Manager comprueba la cadena de consentimiento TCF de IAB, pasada en el parámetro `gdpr_consent`, para obtener los permisos necesarios. Audience Manager necesita permisos de almacenamiento, personalización, medición y consentimiento del proveedor de Audience Manager para almacenar, procesar o activar datos.
5. Si la cadena de consentimiento TCF de IAB está presente y contiene los permisos necesarios, Audience Manager pasa la cadena de consentimiento TCF de IAB a nuestros servidores [de recopilación de](/help/using/reference/system-components/components-data-collection.md) datos (DCS).
6. Audience Manager responde configurando una [cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) demdex en el explorador. Audience Manager también inicia y respeta las sincronizaciones de ID de terceros.
7. Como alternativa, si la cadena de consentimiento TCF de IAB pasada en el paso 5 no contiene todos los permisos necesarios, Audience Manager no recopila, procesa ni activa datos y no respeta ni inicia sincronizaciones de ID.

![Caso de uso del editor](assets/publisher-use-case.png)

## Caso de uso del anunciante {#advertiser-use-case}

Audience Manager evalúa y honra el consentimiento pasado en llamadas [en](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)píxeles, de acuerdo con el TCF de IAB.

Pixels are generally placed by Audience Manager customers on their partner pages or they are placed in ad servers to include in the ad response. In the first case, your partner must programmatically retrieve the consent parameter and add it to the pixel before firing. In the second case, which is more common and is described in detail below, ad servers append the consent parameters they receive from the Supply-Side Platform (SSP) or publisher ad servers to all pixels.

Audience Manager uses two parameters to pass user consent in pixel calls:

* `gdpr` can be 0 (GDPR does not apply) or 1 (GDPR applies);
* `gdpr_consent` is the URL-safe base64-encoded GDPR consent string (see specification). [](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications) A sample call for an impression pixel, with the two parameters could look like below:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

The use case is described in the image and in the steps below. Empiece desde la izquierda de la imagen:

1. Your user is served an impression via an ad server. Esto se traduce en una llamada en píxeles a nuestros servidores de recopilación de datos (DCS).
1. Audience Manager comprueba si se aplica el indicador GDPR. Si no lo hace, Audience Manager almacena los datos pasados en variables de macro en llamadas en píxeles.
1. Si la cadena de consentimiento está presente y contiene los permisos necesarios, Audience Manager almacena los datos pasados en variables de macro en llamadas en píxeles.
1. Si falta la cadena de consentimiento o no tiene los permisos necesarios, Audience Manager descargará los datos pasados en variables de macro en llamadas en píxeles.

![Caso de uso del anunciante](assets/advertiser-use-case.png)

## Socios de activación que admiten IAB TCF {#aam-activation-partners}

El complemento Audience Manager para IAB TCF le permite reenviar la cadena de consentimiento TCF de IAB a los socios de activación, respetando al mismo tiempo las opciones de privacidad de los usuarios. Para obtener información sobre los socios de activación que admiten IAB TCF (exacta desde el 7 de julio de 2019), consulte nuestra hoja de Excel de **[socio](/help/using/overview/aam-gdpr/assets/AAM-Partners-October2019.xlsx)**.

## Probar la implementación de IAB {#test-iab-implementation}

Para probar que ha implementado correctamente el complemento Audience Manager para IAB TCF, lea el [Caso de uso 4 en Métodos de validación para la implementación](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html)de inclusión e IAB.

## IAB y exclusión en Audience Manager. Orden de prioridad. {#iab-and-optout}

Otra opción de privacidad a disposición de los usuarios es la posibilidad de desactivar la recopilación de datos. Adobe proporciona a los usuarios los medios para hacerlo en la página [Sus opciones](https://www.adobe.com/privacy/opt-out.html#customeruse) de privacidad.

Audience Manager se ocupa de la gestión de exclusión en un artículo [independiente de nuestra documentación](/help/using/overview/data-security-and-privacy/opt-out-management.md).

>[!NOTE]
>
>**Orden de prioridad** : si el usuario no desea recopilar datos mediante una herramienta de exclusión global, como se describe en el vínculo anterior, esto tiene prioridad sobre las verificaciones de inclusión e IAB.

## Recursos adicionales {#additional-resources}

* [Inclusión en el servicio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [Marco de Transparencia y Consentimiento de la IAB Europa GDPR](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Especificaciones técnicas del marco de transparencia y consentimiento de IAB Europe GDPR](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Complemento TCF IAB: demostración de vídeo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)