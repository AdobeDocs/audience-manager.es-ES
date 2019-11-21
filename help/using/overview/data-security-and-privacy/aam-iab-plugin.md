---
description: Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la funcionalidad de inclusión y a través de la compatibilidad con Transparency y Consent Fremework de IAB (Transparency). En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.
seo-description: Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la funcionalidad de inclusión y a través de la compatibilidad con Transparency y Consent Fremework de IAB (Transparency). En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.
seo-title: Complemento de Audience Manager para IAB TCF
solution: Audience Manager
title: Complemento de Audience Manager para IAB TCF
translation-type: tm+mt
source-git-commit: caa5207bc2955ee18b40d6a51613340001cbd92f

---


# Complemento de Audience Manager para IAB TCF {#aam-iab-plugin}

## Información general

Un aspecto importante de las obligaciones de privacidad que tiene con respecto a los usuarios es la adquisición y la transmisión de las elecciones del usuario sobre cómo se pueden utilizar sus datos personales (por ejemplo: “motivos”) y quién (por ejemplo: “empresas”).

Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de [la funcionalidad de inclusión](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) y a través [de la compatibilidad con Transparency y Consent Fremework de IAB (Transparency)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager. Audience Manager está registrado en el TCF de IAB con el ID de proveedor 565.

El complemento Audience Manager para IAB TCF utiliza la funcionalidad [de](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)inclusión, que a su vez forma parte de la biblioteca del servicio de ID de Adobe [Experience Cloud (ECID)](https://marketing.adobe.com/resources/help/en_US/mcvid/) .

## Alcance y limitaciones {#scope-and-limitations}

Como editor o anunciante que trabaja con Audience Manager, puede transmitir las opciones de usuario a Audience Manager según IAB TCF. Esto le proporciona una manera fácil y coherente de comunicar las opciones de usuario a todos los socios con los que trabaje y Audience Manager puede ayudarle a respetar las opciones de privacidad de sus usuarios.

El soporte TCF de la IAB descrito en este artículo representa la primera fase del soporte planificado por Audience Manager para el marco de la IAB. Actualmente, Audience Manager no admite:

* Flujos de trabajo de dispositivos móviles;
* Gestión del consentimiento entre dispositivos;
* Adición de consentimiento a direcciones URL enviadas a destinos [](../../features/destinations/create-url-destination.md)URL;
* Adición del consentimiento a los segmentos.

## Requisitos previos {#prerequisites}

Debe cumplir los siguientes requisitos previos para utilizar el TCF de IAB con Audience Manager:

1. Debe utilizar la versión 4.1 o posterior del servicio Experience Cloud ID (ECID). [Descargue](https://github.com/Adobe-Marketing-Cloud/id-service/releases) nuestra última versión de ECID.
1. Debe utilizar la biblioteca de integración de datos de Audience Manager (DIL) versión 9.0 o posterior, descargable desde [aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases). Obtenga información sobre [DIL en la documentación](../..//dil/dil-overview.md)de Audience Manager.
1. Como alternativa, si utiliza el reenvío del lado del servidor (SSF) para importar datos en Audience Manager, debe actualizar a la versión más reciente de AppMeasurement. Descargue AppMeasurement con el Administrador [de códigos de](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)Analytics.
1. Debe utilizar una Plataforma de Gestión de Consentimiento (CMP), ya sea comercial o propia, que admita la IAB y esté registrada en la IAB TCF. Véase la lista de [las CP/RP registradas en el marco](https://advertisingconsent.eu/cmp-list/)de la IAB.

## Recomendaciones y cómo implementar {#recommendations}

Para habilitar la compatibilidad con TCF de IAB en Audience Manager, lea nuestra documentación sobre [cómo configurar IAB con inclusión](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

Para ello, es más fácil utilizar [Adobe Launch](https://docs.adobelaunch.com/) para instrumentar la inclusión de ECID en sus propiedades. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Flujo de trabajo de opciones de usuario al utilizar el marco de trabajo IAB {#user-choice-workflow}

Al visitar una propiedad web, los usuarios pueden proporcionar sus opciones con respecto a cómo el editor y los proveedores externos con los que trabaja el editor utilizarán sus datos. Los usuarios proporcionan sus opciones en forma de propósitos ** estándar y permisos a proveedores *de* terceros registrados en la lista global de proveedores. La siguiente imagen representa un ejemplo de un cuadro de diálogo de CMP que se muestra a un visitante nuevo de un sitio web. Tenga en cuenta que este cuadro de diálogo puede tener un aspecto muy diferente, según la implementación del cliente.

![Cuadro de diálogo CMP](assets/cmp.png)

Los objetivos estándar del marco de la IAB son:

* Almacenamiento de información y acceso
* Personalización
* Selección, envío e informes de publicidad
* Selección, entrega y creación de informes de contenido
* vídeo 

Consulte la página [de especificaciones del marco](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) IAB para obtener una descripción de los cinco objetivos estándar.

Los usuarios pueden conceder su consentimiento para una combinación de propósitos estándar y proveedores. Por ejemplo, los usuarios podrían conceder su consentimiento para almacenamiento, personalización y medición y conceder su consentimiento a todos los proveedores externos que muestre el CMP. O, en otro ejemplo, podrían conceder su consentimiento para los cinco fines estándar, pero sólo dar su consentimiento a unos pocos de los proveedores mostrados por la CP/RP.

Una vez que el usuario selecciona sus opciones de privacidad, las opciones del usuario se registran en la cadena de consentimiento TCF de IAB. La cadena de consentimiento TCF de la IAB almacena la combinación de propósitos y proveedores aprobados, junto con otra información de metadatos (consulte la página [de la](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) IAB para obtener más información). Cada proveedor registrado en la TCF de la IAB evalúa la cadena de consentimiento TCF de la IAB y toma decisiones en función de las opciones de privacidad de los usuarios. Tenga en cuenta que las opciones de privacidad de los usuarios son válidas en todos los proveedores aprobados.

## Finalidades estándar que Audience Manager necesita {#aam-standard-purposes}

Audience Manager evalúa las opciones de los usuarios almacenadas en la cadena de consentimiento TFC de IAB para:

* Acceso y almacenamiento de información (ID de propósito 1 en la lista [de proveedores](https://vendorlist.consensu.org/vendorlist.json)globales)
* Personalización (ID de propósito 2)
* Medición (ID de propósito 5)
* El consentimiento del proveedor de Audience Manager para almacenar, procesar o activar datos de un editor.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## El comportamiento de Audience Manager depende de si el usuario concede el consentimiento {#aam-behavior-consent}

Audience Manager funciona de forma diferente dependiendo de si Audience Manager detecta en la cadena de consentimiento TCF de IAB que el usuario ha proporcionado su consentimiento para los tres fines (almacenamiento, personalización, medición) o no.

| Cuando el usuario *da su consentimiento*, Audience Manager: | Cuando el usuario *rechaza* el consentimiento, Audience Manager: |
|---|---|
| <ul><li>Realiza todos los casos de uso de Audience Manager que ha solicitado.</li><li>Transmite el consentimiento a terceros en sincronizaciones de ID (pasando gdpr = 1 y la cadena de consentimiento como gdpr_permission en llamadas de sincronización de ID).</li><li>Evalúa y respeta el consentimiento pasado desde los píxeles del servidor de publicidad.</li><li>Honra las sincronizaciones de ID iniciadas por el socio.</li></ul> | <ul><li>No almacena ningún dato de usuario nuevo en su instancia. Esto incluye ID de socio, señales, características o datos de píxeles.</li><li>No inicia sincronizaciones de ID de terceros.</li><li>No respeta las sincronizaciones de ID iniciadas por el socio.</li></ul> |

## Caso de uso del editor {#publisher-use-case}

Al implementar el TCF de IAB, no es necesario mantener el código personalizado para la administración de consentimiento en las propiedades web a través de un mecanismo diferente con Adobe u otros proveedores de terceros. El caso de uso se describe en la imagen y en los pasos a continuación. Empiece desde la izquierda de la imagen:

1. Un usuario visita una de sus propiedades web. Siempre que utilice las versiones más recientes de las bibliotecas ECID y DIL (consulte [Requisitos previos](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), se activa el flujo de inclusión.
2. Audience Manager comprueba si se aplica el flujo IAB (`isIabContext=true`). Consulte [Recomendaciones y cómo implementarlas](aam-iab-plugin.md#recommendations).
3. Audience Manager comprueba si el RGPD se aplica (`gdpr = 1`) y si hay un CMP, registrado con IAB, en la propiedad web. Por ejemplo, esto se aplicaría a los usuarios que visiten el área de la Unión Europea. Tenga en cuenta que es su responsabilidad como editor establecer el indicador del RGPD.
4. Si se aplica GDPR, Audience Manager comprueba la cadena de consentimiento TCF de IAB, pasada en el parámetro `gdpr_consent`, para obtener los permisos necesarios. Audience Manager necesita permisos de almacenamiento, personalización, medición, además del consentimiento del proveedor de Audience Manager para almacenar, procesar o activar datos.
5. Si la cadena de consentimiento TCF de IAB está presente y contiene los permisos necesarios, Audience Manager pasa la cadena de consentimiento TCF de IAB a nuestros servidores [de recopilación de](../../reference/system-components/components-data-collection.md) datos (DCS).
6. Audience Manager responde configurando una [cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) demdex en el explorador. Audience Manager también inicia y respeta las sincronizaciones de ID de terceros.
7. Como alternativa, si la cadena de consentimiento TCF de IAB pasada en el paso 5 no contiene todos los permisos necesarios, Audience Manager no recopila, procesa ni activa datos y no respeta ni inicia sincronizaciones de ID.

![Caso de uso del editor](assets/publisher-use-case.png)

## Caso de uso del anunciante {#advertiser-use-case}

Audience Manager evalúa y honra el consentimiento pasado en llamadas [en](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)píxeles, de acuerdo con el TCF de IAB.

Generalmente, los clientes de Audience Manager colocan los píxeles en las páginas de socios o en los servidores de publicidad para incluirlos en la respuesta de publicidad. En el primer caso, el socio debe recuperar mediante programación el parámetro de consentimiento y agregarlo al píxel antes de activarlo. En el segundo caso, que es más común y se describe en detalle a continuación, los servidores de publicidad anexan los parámetros de consentimiento que reciben de la plataforma de suministro (SSP) o de los servidores de publicidad de editor a todos los píxeles.

Audience Manager utiliza dos parámetros para transmitir el consentimiento del usuario en llamadas en píxeles:

* `gdpr` puede ser 0 (no se aplica el RGPD) o 1 (se aplica el RGPD);
* `gdpr_consent` es la cadena de consentimiento GDPR con codificación URL base64 (consulte [la especificación](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)). Una llamada de muestra para un píxel de impresión, con los dos parámetros, podría verse a continuación:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

El caso de uso se describe en la imagen y en los pasos a continuación. Empiece desde la izquierda de la imagen:

1. El usuario recibe una impresión a través de un servidor de publicidad. Esto se traduce en una llamada en píxeles a nuestros servidores de recopilación de datos (DCS).
2. Audience Manager comprueba si se aplica el indicador GDPR. Si no lo hace, Audience Manager almacena los datos pasados en variables de macro en llamadas en píxeles.
3. Si la cadena de consentimiento está presente y contiene los permisos necesarios, Audience Manager almacena los datos pasados en variables de macro en llamadas en píxeles.
4. Si falta la cadena de consentimiento o no tiene los permisos necesarios, Audience Manager descargará los datos pasados en variables de macro en llamadas en píxeles.

![Caso de uso del anunciante](assets/advertiser-use-case.png)

## Socios de activación que admiten IAB TCF {#aam-activation-partners}

El complemento Audience Manager para IAB TCF le permite reenviar la cadena de consentimiento TCF de IAB a los socios de activación, respetando al mismo tiempo las opciones de privacidad de los usuarios. Para obtener información sobre los socios de activación que admiten IAB TCF, consulte nuestra hoja de Excel **[de socio](/help/using/overview/data-security-and-privacy/assets/AAM-Partners-October2019.xlsx)**.

## Probar la implementación de IAB {#test-iab-implementation}

Para probar que ha implementado correctamente el complemento Audience Manager para IAB TCF, lea el [Caso de uso 4 en Métodos de validación para la implementación](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html)de inclusión e IAB.

## IAB y exclusión en Audience Manager. Orden de prioridad. {#iab-and-optout}

Otra opción de privacidad a disposición de los usuarios es la posibilidad de desactivar la recopilación de datos. Adobe proporciona a los usuarios los medios para hacerlo en la página [Sus opciones](https://www.adobe.com/privacy/opt-out.html#customeruse) de privacidad.

Audience Manager aborda las solicitudes de exclusión en un artículo [independiente de nuestra documentación](data-privacy-requests.md).

>[!NOTE]
>
>**Orden de prioridad** : si el usuario no desea recopilar datos mediante una herramienta de exclusión global, como se describe en el vínculo anterior, esto tiene prioridad sobre las verificaciones de inclusión e IAB.

## Recursos adicionales {#additional-resources}

* [Inclusión en el servicio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [Marco de Transparencia y Consentimiento de la IAB Europa GDPR](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Especificaciones técnicas del marco de transparencia y consentimiento de IAB Europe GDPR](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Complemento TCF IAB: demostración de vídeo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)