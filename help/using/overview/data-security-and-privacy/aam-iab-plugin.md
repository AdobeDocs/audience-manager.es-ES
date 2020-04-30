---
description: Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la funcionalidad de inclusión y a través de la compatibilidad con Transparency y Consent Fremework de IAB (Transparency). En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.
seo-description: Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la funcionalidad de inclusión y a través de la compatibilidad con Transparency y Consent Fremework de IAB (Transparency). En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.
seo-title: Complemento de Audience Manager para IAB TCF
solution: Audience Manager
title: Complemento de Audience Manager para IAB TCF
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Complemento de Audience Manager para IAB TCF {#aam-iab-plugin}

## Información general

Un aspecto importante de las obligaciones de privacidad que tiene con respecto a los usuarios es la adquisición y la transmisión de las elecciones del usuario sobre cómo se pueden utilizar sus datos personales (por ejemplo: “motivos”) y quién (por ejemplo: “empresas”).

Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de [la funcionalidad de inclusión](hhttps://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) y a través [de la compatibilidad con Transparency y Consent Fremework de IAB (Transparency)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager. El Administrador de Audiencias está registrado en el TCF de IAB con el ID de proveedor 565.

El complemento Administrador de Audiencias para IAB TCF utiliza la funcionalidad [de](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html)inclusión, que a su vez forma parte de la biblioteca del servicio de identidad de la plataforma de experiencia de Adobe [Adobe (ECID)](https://docs.adobe.com/content/help/en/id-service/using/home.html) .

## Alcance y limitaciones {#scope-and-limitations}

Como editor o anunciante que trabaja con el Administrador de Audiencias, puede transmitir las opciones de usuario al Administrador de Audiencias según IAB TCF. Esto le proporciona una manera fácil y consistente de comunicar las opciones de usuario a todos los socios con los que trabaje y el Administrador de Audiencias puede ayudarle a respetar las opciones de privacidad de sus usuarios.

El soporte TCF de la IAB que se describe en este artículo representa la primera fase del soporte planificado por el administrador de Audiencias para el marco de la IAB. Actualmente, el Administrador de Audiencias no admite:

* flujos de trabajo de dispositivos móviles;
* Gestión del consentimiento entre dispositivos;
* Adición de consentimiento a direcciones URL enviadas a destinos [](../../features/destinations/create-url-destination.md)URL;
* Adición del consentimiento a los segmentos.

## Requisitos previos {#prerequisites}

Debe cumplir los siguientes requisitos previos para utilizar el TCF de IAB con el Administrador de Audiencias:

1. Debe utilizar Adobe Experience Platform Identity Service (ECID) versión 4.1 o posterior. [Descargue](https://github.com/Adobe-Marketing-Cloud/id-service/releases) nuestra última versión de ECID.
1. Debe utilizar la versión 9.0 o posterior de la biblioteca de integración de datos (DIL) del Administrador de Audiencias, descargable desde [aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases). Obtenga información sobre [DIL en la documentación](../..//dil/dil-overview.md)del Administrador de Audiencias.
1. Como alternativa, si utiliza el reenvío del lado del servidor (SSF) para importar datos en el Administrador de Audiencias, debe actualizar a la versión más reciente de AppMeasurement. Descargue AppMeasurement con el Administrador [de códigos de](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)Analytics.
1. Debe estar utilizando una Plataforma de Gestión de Consentimiento (CMP), ya sea comercial o propia, que admita el TCF de IAB y esté registrada en el TCF de IAB. Véase la lista de [las CP/RP registradas en el marco](https://advertisingconsent.eu/cmp-list/)de la Junta de Auditores Internos.

## Recomendaciones y cómo implementar {#recommendations}

Para habilitar la asistencia TCF de IAB en el Administrador de Audiencias, lea nuestra documentación sobre [cómo configurar IAB con inclusión](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html).

Para ello, es más fácil utilizar [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) para instrumentar la inclusión de ECID en sus propiedades. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Flujo de trabajo de opciones de usuario al utilizar el marco de trabajo IAB {#user-choice-workflow}

Al visitar una propiedad web, los usuarios pueden proporcionar sus opciones con respecto a cómo el editor y los proveedores externos con los que trabaja el editor utilizarán sus datos. Los usuarios proporcionan sus opciones en forma de propósitos ** estándar y permisos a proveedores *de* terceros registrados en la lista global de proveedores. La siguiente imagen representa un ejemplo de un cuadro de diálogo CMP, mostrado en un visitante por primera vez de un sitio web. Tenga en cuenta que este cuadro de diálogo puede tener un aspecto muy diferente, según la implementación del cliente.

![Cuadro de diálogo CMP](assets/cmp.png)

Los objetivos estándar del marco de la IAB son:

* almacenamiento y acceso a la información
* Personalización
* Selección de publicidad, envío y sistema de informes
* Selección de contenido, envío y sistema de informes
* vídeo 

Consulte la página [de especificaciones del marco](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) IAB para obtener una descripción de los cinco objetivos estándar.

Los usuarios pueden conceder su consentimiento para una combinación de propósitos estándar y proveedores. Por ejemplo, los usuarios podrían conceder su consentimiento para el almacenamiento, la personalización y la medición y dar su consentimiento a todos los proveedores externos que muestre la CP/RP. O, en otro ejemplo, podrían conceder su consentimiento para los cinco fines estándar, pero sólo dar su consentimiento a unos pocos de los proveedores mostrados por la CP/RP.

Una vez que el usuario selecciona sus opciones de privacidad, las opciones del usuario se registran en la cadena de consentimiento TCF de IAB. La cadena de consentimiento TCF de la IAB almacena la combinación de propósitos y proveedores aprobados, junto con otra información de metadatos (consulte la página [de la](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) IAB para obtener más información). Cada proveedor registrado en la TCF de la IAB evalúa la cadena de consentimiento TCF de la IAB y toma decisiones en función de las opciones de privacidad de los usuarios. Tenga en cuenta que las opciones de privacidad de los usuarios son válidas en todos los proveedores aprobados.

## Finalidades estándar que necesita el Administrador de Audiencias {#aam-standard-purposes}

El Administrador de Audiencias evalúa las opciones de los usuarios almacenadas en la cadena de consentimiento TFC de IAB para:

* Acceso y almacenamiento de información (ID de propósito 1 en la lista [de proveedor](https://vendorlist.consensu.org/vendorlist.json)global)
* Personalización (ID de propósito 2)
* Medición (ID de propósito 5)
* El consentimiento del proveedor del Administrador de Audiencias para almacenar, procesar o activar datos de un editor.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## El comportamiento del Administrador de Audiencias depende de si el usuario concede el consentimiento {#aam-behavior-consent}

El Administrador de Audiencias funciona de manera diferente dependiendo de si el Administrador de Audiencias detecta en la cadena de consentimiento TCF de IAB que el usuario ha dado su consentimiento para los tres fines (almacenamiento, personalización, medición) o no.

| Cuando el usuario *da su consentimiento*, Administrador de Audiencias: | Cuando el usuario *rechaza* el consentimiento, Administrador de Audiencias: |
|---|---|
| <ul><li>Lleva a cabo todos los casos de uso del Administrador de Audiencias que ha solicitado.</li><li>Transmite el consentimiento a terceros en sincronizaciones de ID (pasando gdpr = 1 y la cadena de consentimiento como gdpr_permission en llamadas de sincronización de ID).</li><li>Evalúa y respeta el consentimiento pasado desde los píxeles del servidor de publicidad.</li><li>Honra las sincronizaciones de ID iniciadas por el socio.</li></ul> | <ul><li>No almacena ningún dato de usuario nuevo en su instancia. Esto incluye ID de socio, señales, características o datos de píxeles.</li><li>No inicia sincronizaciones de ID de terceros.</li><li>No respeta las sincronizaciones de ID iniciadas por el socio.</li></ul> |

## Caso de uso del editor {#publisher-use-case}

Al implementar el TCF de IAB, no es necesario mantener el código personalizado para la administración de consentimiento en las propiedades web a través de un mecanismo diferente con Adobe u otros proveedores de terceros. El caso de uso se describe en la imagen y en los pasos a continuación. Inicio desde la izquierda de la imagen:

1. Un usuario visita una de sus propiedades web. Siempre que utilice las versiones más recientes de las bibliotecas ECID y DIL (consulte [Requisitos previos](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), se activa el flujo de inclusión.
2. El Administrador de Audiencias comprueba si se aplica el flujo IAB (`isIabContext=true`). Consulte [Recomendaciones y cómo implementarlas](aam-iab-plugin.md#recommendations).
3. El Administrador de Audiencias comprueba si el RGPD se aplica (`gdpr = 1`) y si hay un CMP, registrado con IAB, en la propiedad web. Por ejemplo, esto se aplicaría a los usuarios que visiten el área de la Unión Europea. Tenga en cuenta que es su responsabilidad como editor establecer el indicador del RGPD.
4. Si se aplica el RGPD, el Administrador de Audiencias comprueba la cadena de consentimiento TCF de IAB, pasada en el parámetro `gdpr_consent`, para obtener los permisos necesarios. El Administrador de Audiencias necesita permisos de almacenamiento, personalización, medición y consentimiento del proveedor del Administrador de Audiencias para almacenar, procesar o activar datos.
5. Si la cadena de consentimiento TCF de IAB está presente y contiene los permisos necesarios, el Administrador de Audiencias pasa la cadena de consentimiento TCF de IAB a nuestros servidores [de recopilación de](../../reference/system-components/components-data-collection.md) datos (DCS).
6. El Administrador de Audiencias responde configurando una [cookie](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) demdex en el explorador. El Administrador de Audiencias también inicia y respeta las sincronizaciones de ID de terceros.
7. Como alternativa, si la cadena de consentimiento TCF de IAB pasada en el paso 5 no contiene todos los permisos necesarios, el Administrador de Audiencias no recopila, procesa ni activa datos y no respeta ni inicia sincronizaciones de ID.

![Caso de uso del editor](assets/publisher-use-case.png)

## Caso de uso del anunciante {#advertiser-use-case}

El Administrador de Audiencias evalúa y honra el consentimiento que se pasa en llamadas [en](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)píxeles, de acuerdo con el TCF de IAB.

Los píxeles son generalmente colocados por los clientes del Administrador de Audiencias en las páginas de socios o se colocan en servidores de publicidad para incluirlos en la respuesta de publicidad. En el primer caso, el socio debe recuperar mediante programación el parámetro de consentimiento y agregarlo al píxel antes de activarlo. En el segundo caso, que es más común y se describe en detalle a continuación, los servidores de publicidad anexan los parámetros de consentimiento que reciben de la plataforma de suministro (SSP) o de los servidores de publicidad de editor a todos los píxeles.

El Administrador de Audiencias utiliza dos parámetros para transmitir el consentimiento del usuario en llamadas en píxeles:

* `gdpr` puede ser 0 (no se aplica el RGPD) o 1 (se aplica el RGPD);
* `gdpr_consent` es la cadena de consentimiento GDPR con codificación URL base64 (consulte la [especificación](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)). Una llamada de muestra para un píxel de impresión, con los dos parámetros, podría verse a continuación:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

El caso de uso se describe en la imagen y en los pasos a continuación. Inicio desde la izquierda de la imagen:

1. El usuario recibe una impresión a través de un servidor de publicidad. Esto se traduce en una llamada en píxeles a nuestros servidores de recopilación de datos (DCS).
2. El Administrador de Audiencias comprueba si se aplica el indicador del RGPD. Si no lo hace, el Administrador de Audiencias almacena los datos pasados en variables de macro en llamadas en píxeles.
3. Si la cadena de consentimiento está presente y contiene los permisos necesarios, el Administrador de Audiencias almacena los datos pasados en variables de macro en llamadas en píxeles.
4. Si falta la cadena de consentimiento o no tiene los permisos necesarios, el Administrador de Audiencias descarta los datos pasados en variables de macro en llamadas de píxeles.

![Caso de uso del anunciante](assets/advertiser-use-case.png)

## Socios de Activación que apoyan a IAB TCF {#aam-activation-partners}

El complemento Administrador de Audiencias para IAB TCF le permite reenviar la cadena de consentimiento TCF de IAB a los socios de activación, respetando al mismo tiempo las opciones de privacidad de los usuarios. Para obtener información sobre qué socios de activación admiten IAB TCF, consulte nuestra [lista de destinos](/help/using/features/destinations/device-based-destinations-list.md)basados en dispositivos.

## Probar la implementación de IAB {#test-iab-implementation}

Para probar que ha implementado correctamente el complemento Administrador de Audiencias para IAB TCF, lea el [Caso de uso 4 en Métodos de validación para la implementación](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88)de inclusión e IAB.

## IAB y exclusión en el Administrador de Audiencias. Orden de prioridad. {#iab-and-optout}

Otra opción de privacidad a disposición de los usuarios es la posibilidad de exclusión toda la recopilación de datos. Adobe proporciona a los usuarios los medios para hacerlo en la página [Sus opciones](https://www.adobe.com/privacy/opt-out.html#customeruse) de privacidad.

El Administrador de Audiencias aborda las solicitudes de exclusión en un artículo [independiente de nuestra documentación](data-privacy-requests.md).

>[!NOTE]
>
>**Orden de prioridad** : si el usuario exclusión la recopilación de datos mediante una herramienta de exclusión global, como se describe en el vínculo anterior, esto tiene prioridad sobre las verificaciones de inclusión e IAB.

## Recursos adicionales {#additional-resources}

* [Inclusión del servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [Marco de Transparencia y Consentimiento de la IAB Europa GDPR](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Especificaciones técnicas del marco de transparencia y consentimiento de IAB Europe GDPR](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Complemento TCF IAB: demostración de vídeo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)